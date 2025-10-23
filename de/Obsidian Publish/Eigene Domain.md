---
description: Erfahre, wie du eine eigene Domain oder Subdomain für deine Obsidian Publish-Webseite einrichtest.
publish: true
mobile: true
aliases:
  - Obsidian Publish/Eigene Domain einrichten
permalink: publish/domains
---

Du kannst für deine [[Einführung in Obsidian Publish|Obsidian Publish]]-Webseite eine benutzerdefinierte Domain oder Subdomain einrichten.

> [!warning] Achtung
> Derzeit unterstützen wir die Einrichtung einer benutzerdefinierten Domain nur über die folgenden Methoden:
>
> - [[#Einrichtung mit CloudFlare]] im [Full Modus](https://developers.cloudflare.com/ssl/origin-configuration/ssl-modes/full/).
> - [[#Einrichtung über einen Proxy]]
> 
> Aktuell haben wir noch keine Möglichkeit, dir ein SSL-Zertifikat bereitzustellen.

## Einrichtung mit CloudFlare

Der einfachste Weg, eine benutzerdefinierte Domain oder Subdomain einzurichten, besteht darin, ein [CloudFlare](https://cloudflare.com)-Konto zu erstellen und den DNS deiner Domain von CloudFlare verwalten zu lassen.

Nachfolgend wird gezeigt, wie du deine Obsidian Publish-Webseite unter Verwendung einer eigenen Domain (`meineseite.com`) oder Subdomain (`notizen.meineseite.com`) einrichten kannst.

> [!important] Wichtig
> CloudFlare ist der einzige **offiziell unterstützte Provider** für die Einrichtung von benutzerdefinierten Domains. Diese Anleitung funktioniert wahrscheinlich nicht für andere Anbieter.

**CloudFlare:**

1. Öffne CloudFlare für die Domain, auf der du deine Publish-Webseite hosten möchtest, z.B. `meineseite.com` (auch wenn du eine Subdomain verwenden möchtest).
2. Unter **DNS** klicke **Add Record**.
3. Wähle **CNAME**.
4. Als **Name** trägst du deine Domain oder Subdomain ein, z.B. `notizen.meineseite.com`.
5. Als **Target** trägst du `publish-main.obsidian.md` ein. Deine Sub-URL lässt du hier weg, diese übernimmt Obsidian Publish aus deiner Konfiguration.
6. Stelle sicher, dass **Proxy Status** aktiviert ist, das sollte die Standardeinstellung sein.
7. Unter **SSL/TLS** setze den SSL/TLS-Verschlüsselungsmodus auf "Full", um das SSL/TLS-Zertifikat automatisch zu konfigurieren.

> [!note] Hinweis
> Um sowohl `meineseite.com` als auch `www.meineseite.com` auf Obsidian Publish weiterzuleiten, musst du eine [Seitenregel](https://support.cloudflare.com/hc/en-us/articles/200172336-Creating-Page-Rules) mit den folgenden Einstellungen einrichten:
>
> - URL match: `www.meineseite.com/*`
> - Forward URL - 301 Permanent Redirect
> - Redirect URL: `https://meineseite.com/$1`
>
> Erstelle anschließend einen weiteren CNAME-Eintrag für `www.meineseite.com` wie oben beschrieben.

**Obsidian:**

1. Starte Obsidian.
2. In der [[Werkzeugleiste]] wähle **Änderungen veröffentlichen** ( ![[lucide-send.svg#icon]] ).
3. Im **Publish**-Dialog wähle **Seiteneinstellungen ändern** ( ![[lucide-settings.svg#icon]] ).
4. Klicke neben **Eigene Domain** auf **Konfigurieren**.
5. Trage unter **Eigene URL** die URL deiner Domain oder Subdomain ein. Stelle sicher, nicht `www.` einzutragen.

> [!note] Hinweis
> Falls deine Konfiguration zu einer Weiterleitungsschleife führt, könnte es sein, dass der Verschlüsselungsmodus in CloudFlare auf "Flexible", anstatt auf "Full" eingestellt ist.

## Einrichtung über einen Proxy

Du kannst SSL/TLS für deine benutzerdefinierte Domain auch einrichten, indem du deinen eigenen Webserver verwendest.

Wenn du unter deiner Domain bereits eine Webseite hostest, kannst du auch diese Option nutzen und deine Webseite so einrichten, dass die Obsidian Publish-Webseite unter einem bestimmten URL-Pfad geladen wird, anstatt die gesamte Webseite zu hosten.

Leite alle Anfragen unter dieser URL an `https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen/...` um und konfiguriere die Seiteneinstellungen in Obsidian auf denselben URL-Pfad, indem du **Eigene URL** auf `meineseite.com/meine-notizen` setzt.

Du kannst Obsidian Publish auch als Sub-URL deiner eigenen Seite einrichten, bspw.
`https://meineseite.com/meine-notizen/`. Dazu muss du deinen eigenen Webserver hosten und alle Anfragen weiterleiten an unseren Server auf `https://publish.obsidian.md/`.

Die nachfolgenden Proxy-Konfigurations-Beispiele sind nicht vollständig, geben aber einen Einblick in gebräuchliche Implementierungen.

### NGINX

Ergänze deine NGINX-Konfiguration wie folgt:

```nginx
location /meine-notizen {
  proxy_pass https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen/;
  proxy_ssl_server_name on;
  proxy_set_header Host publish.obsidian.md;
}
```


Einige Anwender haben darauf hingewiesen, dass die Proxy-Weiterleitung möglicherweise um `$request_uri` erweitert werden muss:

```nginx
location /meine-notizen {
  proxy_pass https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen$request_uri;
  proxy_ssl_server_name on;
  proxy_set_header Host publish.obsidian.md;
}
```

### Apache

Ergänze deine `.htaccess` wie folgt:

```htaccess
RewriteEngine  on
RewriteRule    "^meine-notizen/(.*)$"  "https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen/$1"  [L,P]
```

> [!note] Hinweis
> `mod_rewrite` muss aktiviert sein und möglicherweise ist es notwendig, deine [SSLProxyEngine](https://stackoverflow.com/questions/40938148/reverse-proxy-for-external-url-apache) zu konfigurieren.

### Netlify

[Konfiguriere die Weiterleitungen](https://docs.netlify.com/routing/redirects/#syntax-for-the-netlify-configuration-file) in deiner `netlify.toml`, :

```plain
[[redirects]]
  from = "https://meineseite.com/meine-notizen/*"
  to = "https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen/:splat"
  status = 200
  force = true
```

### Vercel

[Konfiguriere die Weiterleitungen](https://vercel.com/docs/configuration#project/rewrites) in deiner `vercel.json`, :

```json
{
  ...

  "rewrites": [
    {
      "source": "/meine-notizen/",
      "destination": "https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen"
    },
    {
      "source": "/meine-notizen/:path*",
      "destination": "https://publish.obsidian.md/serve?url=meineseite.com/meine-notizen/:path*"
    }
  ]
}
```

### Caddy

```plain
meineseite.com {
  encode zstd gzip
  handle /meine-notizen* {
    reverse_proxy https://publish.obsidian.md {
      header_up Host {upstream_hostport}
    }
    rewrite * /serve?url=meineseite.com{path}
  }
}
```

### Traefik

Ergänze deine Traefik-Konfiguration wie im Beispiel angedeutet, um `meineseite.com` nach Obsidian Publish umzuleiten. Für ein vollständiges Beispiel, siehe die [Traefik Dokumentation](https://doc.traefik.io/traefik/routing/overview/).

```yaml
http:
  routers:
    mysite:
      rule: Host(`meineseite.com`)
      service: obsidian-publish
      middlewares:
        - "publish-headers"
  services:
    obsidian-publish:
      loadBalancer:
        servers:
          - url: https://publish.obsidian.md
  middlewares:
    publish-headers:
      headers:
        customRequestHeaders:
          Host: "publish.obsidian.md"
          x-obsidian-custom-domain: "meineseite.com"
```

### Unterstützte HTTP X-Header

Falls dein Proxy-Dienst keine Suchpfade erlaubt, kannst du `https://publish.obsidian.md/` mit einem benutzerdefinierten Header `x-obsidian-custom-domain` verwenden, dem deine Sub-URL `meineseite.com/meine-notizen` zugewiesen ist.

## Weiterleitung zur benutzerdefinierten Domain

Wenn du deine Besucher von der alten `publish.obsidian.md` Webseite zu deiner neuen benutzerdefinierten Domain weiterleiten möchtest, aktiviere die Option **Weiterleitung auf deine eigene Domain**.

## Fehlerbehandlung

Wenn du deine Webseite zuvor über einen `https://publish.obsidian.md/slug`-Link besucht hast, musst du nach der Einrichtung deiner eigenen Domain möglicherweise den Browser-Cache leeren, damit bestimmte Elemente (Schriftarten, Graphen oder der Passwortzugriff) erwartungsgemäß funktionieren. Das liegt an den domänenübergreifenden Sicherheitsbeschränkungen in modernen Browsern. Wenn du Besuchern nur den Zugriff über deine benutzerdefinierte Domain erlaubst, dürfte dieses Problem nicht auftauchen.
