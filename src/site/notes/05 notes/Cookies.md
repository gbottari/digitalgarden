---
{"dg-publish":true,"permalink":"/05-notes/cookies/","dgHomeLink":true,"dgPassFrontmatter":false}
---


# Cookies
Tags: #🌲evergreen 
Links: [[Adtech|Adtech]] | [[Sticky Session|Sticky Session]] | [[05 notes/System Security|System Security]] | [[Browser Storage|Browser Storage]]

---
A cookie is a text-file that stores information about the user on their machine. It is a way to add stateful information to the stateless [[HTTP|HTTP]] protocol [^1].

A cookie is sent with every request.

Used to serve as a [[Browser Storage|Browser Storage]] backend, but it has been replaced by more modern solutions.

A cookie has three purposes:
1. session management: logins, carts
2. personalization: preferences, language preferences, themes
3. tracking: used to identify the user to record their behavior and infer what kind of ad should be served

## Expiration
A cookie has a lifetime that can either be controlled by the browser (session cookies) or set by the server with the `Expires`/`Max-Age` attribute (called permanent cookies).

## Access Restriction
To avoid sending the cookie in plain-text connections, use the `Secure` header. It will always require HTTPS except for localhost.

You can't read a `HttpOnly` cookie using the Javascript API (`Document.cookie`) helping to mitigate [[05 notes/XSS|XSS]] attack.

## Cookie Scope
Defines where the cookie is supposed to be sent. With the `Domain` attribute we define which hosts can receive the cookie. Example: having `Domain=mozilla.org` would allow cookies to be sent to `developer.mozilla.org`. The `Path` attribute controls the URL path, e.g. `Path=/docs`.

`SameSite` controls cross-site settings.
- `SameSite=Lax` (default) - cookies are only sent when the user navigates to the original site (the one that performed `Set-Cookie`)
- `SameSite=Strict` - cookies are only sent to the original site
- `SameSite=None` - cookies are sent everywhere (cross-site) but requires `Secure`

## Difference between first-party and third-party Cookies
A first-party cookie is a cookie that is stored by the site you are currently visiting. It allows the owner to collect analytics.

Third-party cookies are placed by other websites that you haven't directly visited. They can be used to track you across sites and to do [[Retargeting|Retargeting]].

An unknown third-party can read the cookie across multiple websites and the user is unaware of this, leading to privacy issues.

[1]: [Using HTTP cookies - HTTP | MDN](https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies)