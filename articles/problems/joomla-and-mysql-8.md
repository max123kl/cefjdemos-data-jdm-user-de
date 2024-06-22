<!-- Filename: Joomla_and_MySQL_8 / Display title: Joomla und MySQL 8 -->

## MySQL Standard-Authentifizierungs-Plugin Problem

Joomla
<img src="https://docs.joomla.org/images/4/4d/Compat_icon_3_x.png"
decoding="async" data-file-width="40" data-file-height="17" width="40"
height="17" alt="Joomla 3.x" /> kann mit einer MySQL 8-Datenbank
verbunden werden, die MySQL 8-Installation-Konfiguration benötigt
Anpassungen. Der Grund dafür ist, dass MySQL 8 viele Änderungen unter
der Haube hat. Eine Änderung betrifft Joomla – das
Standard-Authentifizierungs-Plugin, das `sha256_password` anstelle von
`mysql_native_password` nutzt. Der native PHP MySQL-Treiber unterstützt
MySQL 8 mit diesem Plugin nicht. <a
href="https://github.com/php/php-src/commit/d6e81f0bfd0cb90586dd83d4fd47a4302605261a"
class="external text" target="_blank"
rel="nofollow noreferrer noopener">PHP 7.3 (alpha)</a> unterstützt
jedoch MySQL 8.

## Änderungen der MySQL-Konfiguration, um Joomla mit MySQL 8 zu verbinden

Glücklicherweise gibt es einen Ausweg! Wir können das
`mysql_native_password` Standard-Authentifizierungs-Plugin für MySQL
verwenden. Wir müssen unsere Konfigurationsdatei `sudo nano /etc/my.cnf`
öffnen (Bitte beachte, dass sich die Datei in einem anderen Verzeichnis
befinden kann) und füge die folgende Konfiguration hinzu:

    [mysqld]
    default-authentication-plugin=mysql_native_password

Wenn kein Zugriff auf die Konfigurationsdatei möglich ist, kann man den
Benutzer wie folgt aktualisieren:

    ALTER USER 'username'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';

Ersetze den Benutzernamen durch den Namen des Benutzerkontos und das
Passwort durch das zum Konto gehörende Passwort. Starte MySQL neu und
fertig...., aber nur wenn man Joomla 3.8 oder 3.9 installiert hat.

## How MySQL default authentication plugin works

The advantage of `mysql_native_password` is that it supports the
challenge-response mechanism which is very quick and does not require
encrypted connection. However, `mysql_native_password` relies on SHA1
algorithm and NIST has recommended to stop using it.

Further, if two user accounts use the same password,
`mysql_native_password` transformation is the same in the mysql.user
table. Although the hash does not expose information about the actual
password, it still tells which two users use the same password. To avoid
that, a salt should be used. A salt is basically a random number that is
used as one of the parameters to cryptographic hash functions used to
transform user passwords. Since a salt is random and different for each
execution, even if two users use the same passwords, the end result of
transformation would look very different. Since MySQL 5.6,
sha256_password authentication plugin is supported. It uses multiple
rounds of SHA256 hash on a salted password to make sure that the hash
transformation is more secure. However, it requires either encrypted
connections or support for an RSA key pair. So, while password security
is stronger, secure connections and multiple rounds of hash
transformations require more time in the authentication process.

caching_sha2_password tries to combine the best of both worlds.
<sup>[\[1\]](#cite_note-1)</sup>

1.  <span id="cite_note-1">[↑](#cite_ref-1) <a
    href="https://mysqlserverteam.com/mysql-8-0-4-new-default-authentication-plugin-caching_sha2_password/"
    class="external free" target="_blank"
    rel="nofollow noreferrer noopener">https://mysqlserverteam.com/mysql-8-0-4-new-default-authentication-plugin-caching_sha2_password/</a></span>
