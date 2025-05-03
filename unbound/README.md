# Unbound DNS Server Add-on für Home Assistant OS

## Beschreibung
Dieses Add-on stellt einen **Unbound DNS Server** für Home Assistant OS bereit. Unbound ist ein leistungsstarker rekursiver und cachingfähiger DNS-Resolver, der als lokaler DNS-Server verwendet werden kann.

## Funktionen
- **Rekursiver DNS-Resolver** mit hoher Performance
- **Caching** zur Beschleunigung von DNS-Anfragen
- **Root-Hints**-basierte Namensauflösung
- **IPv4-Unterstützung** (IPv6 kann optional aktiviert werden)
- **Volle Kontrolle über DNS-Anfragen** für mehr Datenschutz

## Installation
1. Kopiere dieses Repository in dein Home Assistant Add-on Verzeichnis.
2. Navigiere zu **Einstellungen > Add-ons** und wähle **Unbound DNS Server** aus.
3. Installiere das Add-on und starte es.

## Konfiguration
Dieses Add-on benötigt keine spezielle Konfiguration. Es läuft mit den Standardwerten, kann aber durch Bearbeiten der `unbound.conf` angepasst werden.

## Ports
| Port | Beschreibung         |
|------|----------------------|
| 5335 | DNS Server (TCP/UDP) |

## Hinweise
- Die Datei `root.hints` wird bei jedem Start automatisch aktualisiert.
- Standardmäßig werden alle Anfragen von allen IP-Adressen akzeptiert (`access-control: 0.0.0.0/0 allow`). Falls notwendig, sollte dies angepasst werden.

## Lizenz
Dieses Add-on steht unter der **MIT-Lizenz**.

