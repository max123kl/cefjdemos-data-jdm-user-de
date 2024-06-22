<!-- Filename: J4.x:Optional_Technical_Requirements / Display title: Optionale technische Voraussetzungen -->

## Optionale Voraussetzungen für Joomla! 4.x

Diese Seite listet „optionale“ technische Anforderungen auf, die nicht
erforderlich sind, um Joomla! zu installieren und zu betreiben, aber für
einige interne APIs erforderlich sind.

|                                  |                                                                                                                                                                       |
|----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Applikation**                  |                                                                                                                                                                       |
| JApplicationDaemon               | Benötigt PHP's `ext/pcntl` und `ext/posix`                                                                                                                            |
| **Archive**                      |                                                                                                                                                                       |
| BZ2                              | Benötigt PHP's `ext/bz2`                                                                                                                                              |
| GZip                             | Benötigt PHP's `ext/zlib`                                                                                                                                             |
| Zip                              | Benötigt PHP's `ext/zip` oder `ext/zlib`                                                                                                                              |
| **Cache**                        |                                                                                                                                                                       |
| APC                              | Benötigt PHP's `ext/apc` unter PHP 5.3 oder 5.4, `ext/apcu` unter PHP 5.5 oder 5.6, nicht unterstützt unter PHP 7.x (Hinweis: **Dieser Punkt muss überprüft werden**) |
| APCu                             | Benötigt PHP's ext/apcu unter PHP 5.3+                                                                                                                                |
| CacheLite                        | Benötigt das PEAR Cache_Lite-Paket (getestet mit Version 1.7.16, wird auch mit Version 1.8 funktionieren)                                                             |
| Memcache                         | Benötigt PHP's `ext/memcache` und einen Memcache Server (Hinweis: Die Memcache Erweiterung ist nicht kompatibel mit PHP 7.x)                                          |
| Memcached                        | Benötigt PHP's `ext/memcached` und einen Memcached Server                                                                                                             |
| Redis                            | Benötigt PHP's `ext/redis` und einen Redis Server                                                                                                                     |
| Wincache                         | Benötigt PHP's `ext/wincache` (nur Windows)                                                                                                                           |
| XCache                           | Benötigt PHP's `ext/xcache`                                                                                                                                           |
| **Client-Adapter**               |                                                                                                                                                                       |
| LDAP                             | Benötigt PHP's `ext/ldap`                                                                                                                                             |
| HTTP/Curl                        | Benötigt PHP's `ext/curl`                                                                                                                                             |
| HTTP/Socket                      | Benötigt PHP's `fsockopen()`, die Funktion muss aktiviert sein                                                                                                        |
| HTTP/Stream                      | Benötigt PHP's `fopen()`, die Funktion und `allow_url_fopen` muss aktiviert sein                                                                                      |
| **Kryptografie/Verschlüsselung** |                                                                                                                                                                       |
| JCrypt                           | Benötigt PHP's `ext/mcrypt` für alle Verschlüsselungen, mit Ausnahme von SodiumCipher, das `ext/sodium` benötigt.                                                     |
| JKeychain                        | Benötigt PHP's `ext/openssl`                                                                                                                                          |
| **Datenbank**                    |                                                                                                                                                                       |
| Microsoft SQL Azure              | Benötigt PHP's `ext/sqlsrv` (die PHP 5.x Erweiterung unterstützt nur Windows, eine Linux kompatible Version der Erweiterung ist für PHP 7.x verfügbar)                |
| Microsoft SQL Server             | Benötigt PHP's `ext/sqlsrv` (die PHP 5.x Erweiterung unterstützt nur Windows, eine Linux kompatible Version der Erweiterung ist für PHP 7.x verfügbar)                |
| MySQL                            | Benötigt PHP's `ext/mysql` (nicht unterstützt unter PHP 7.x)                                                                                                          |
| MySQLi                           | Benötigt PHP's `ext/mysqli`                                                                                                                                           |
| Oracle                           | Benötigt PHP's `ext/pdo` mit Oracle Unterstützung (verfügbar nur für 3PD; das CMS läuft nicht damit)                                                                  |
| PDO MySQL                        | Benötigt PHP's `ext/pdo` mit MySQL Unterstützung                                                                                                                      |
| PostgreSQL                       | Benötigt PHP's `ext/pgsql`                                                                                                                                            |
| SQLite                           | Benötigt PHP's `ext/pdo` mit SQLite Unterstützung (verfügbar nur für 3PD; das CMS läuft damit nicht)                                                                  |
| **Bilder**                       |                                                                                                                                                                       |
|                                  | Benötigt PHP's `ext/gd`                                                                                                                                               |
|                                  | Benötigt PHP's `ext/fileinfo`                                                                                                                                         |
| **Session**                      |                                                                                                                                                                       |
| APC                              | Benötigt PHP's `ext/apc` unter PHP 5.3 oder 5.4, `ext/apcu` unter PHP 5.5 oder 5.6, nicht unterstützt unter PHP 7.x (Hinweis: **Dieser Punkt muss überprüft werden**) |
| Memcache                         | Benötigt PHP's `ext/memcache` und einem Memcache Server (Hinweis: Die Memcache Erweiterung ist nicht kompatibel mit PHP 7.x)                                          |
| Memcached                        | Benötigt PHP's `ext/memcached` und einen Memcached Server                                                                                                             |
| Wincache                         | Benötigt PHP's `ext/wincache` (nur Windows)                                                                                                                           |
| XCache                           | Benötigt PHP's `ext/xcache`                                                                                                                                           |
| **OPTIONALE VERBESSERUNGEN**     |                                                                                                                                                                       |
| **String**                       |                                                                                                                                                                       |
| mbstring                         | PHP's `ext/mbstring` aktivieren, für die phputf8-Bibliothek, um native Funktionen zu nutzen                                                                           |
