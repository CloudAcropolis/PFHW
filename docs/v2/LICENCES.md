# Licence inventory of the PFHW 2.5.0 images

This list was made from the images of this release, by reading the licence information of every installed package and downloaded file. **It is not legal advice:** the column *marks* only flags GPL, LGPL, AGPL and limits on use (attribution, commercial use). Each part keeps its own licence; the `LICENSE` of PFHW (free to use, not open source) covers PFHW's own software only and takes no right away from you under these licences. Debian packages: the `License:` fields of their copyright file, or the first licence named in it, marked *(text)*. *How used*: every Debian package is a separate program or library installed unmodified from Ubuntu's archive (the packages of the build date, listed in `docs/v2/packages/`) or the named vendor repository; nothing is modified or linked into our code except the Python libraries of Core.

Packages: 605 Debian, 28 Python, 57 downloaded files (distinct name and version over 8 images).

## The main components

| component | version | licence | marks | how used | how verified |
|---|---|---|---|---|---|
| sftpgo | 2.7.6 | AGPL-3.0 | AGPL | separate program, unmodified; customers use it over the network (AGPL section 13 applies to modified versions) | verified: /usr/share/licenses/sftpgo/LICENSE in the web image |
| pm2 | 7.1.2 | AGPL-3.0 | AGPL | separate program (the process manager of Node.js and Next.js apps), unmodified, installed from the npm registry tarball whose integrity is checked; customers use it only through the portal's Apps (AGPL section 13 applies to modified versions) | verified: package.json of pm2 7.1.2 ("license": "AGPL-3.0"); its npm dependencies (MIT, ISC, Apache-2.0, Python-2.0) are listed with their licences in docs/v2/packages/pfhw-web-<version>.txt |
| postgresql-18 | 18.6-1.pgdg24.04+2 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysau-ishii |  | separate program, unmodified (Debian package) | dpkg copyright file (pg) |
| adminer | 6.1.2 | Apache-2.0 OR GPL-2.0 (either) | GPL | separate web application, unmodified; a plugin and a sign-on script of ours beside it (pfhw-plugin.php, pfhw-signon.php) | verified: @license lines of /usr/share/pfhw-adminer/6.1.2/adminer.php in the pg image |
| pdns-server | 5.1.5-1pdns.ubuntu24.04 | BSD-3;Expat;GPL-2;GPL-2 with OpenSSL Exception;GPL-2+;GPL-3-Autoconf;ISC;LGPL-2.1+;Unlicense;curl;free-fsf;free-generic | GPL LGPL | separate program, unmodified (Debian package) | dpkg copyright file (dns) |
| mariadb-server | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | separate program, unmodified (Debian package) | dpkg copyright file (db) |
| clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0-Expat-LLVM-exception;BSD-2-clause;BSD-3-clause;Expat;GPL-2;GPL-2 with OpenSSL exception;GPL-2+;GPL-3+ with Bison exception;ISC;LGPL-2.1;LGPL-2.1 and BSD-3-clause;LZW;MPL-2.0;Zlib;nsis-bzip2;public-domain~1;public-domain~3 | GPL LGPL | separate program, unmodified (Debian package) | dpkg copyright file (web) |
| phpmyadmin | 5.2.3 | GPL-2.0 | GPL | separate web application, unmodified; one sign-on script of ours added beside it (pfhw-signon.php) | verified: /usr/share/pfhw-phpmyadmin/5.2.3/LICENSE |
| owasp-crs | 4.30.0 | Apache-2.0 |  | rule files read by ModSecurity, unmodified (rules switched off by id in our configuration) | verified: /etc/nginx/pfhw/waf/crs-4.30.0/LICENSE |
| goaccess | 1:1.8.1-1build3 | Expat;GPL-3 | GPL | separate program, unmodified (Debian package) | dpkg copyright file (web) |
| ttyd | 1.7.4-1build2 | BSD-3;MIT |  | separate program, unmodified (Debian package) | dpkg copyright file (web) |
| checkmk-agent | v2.5.0p17 | GPL-2.0 | GPL | separate program (shell script), unmodified | verified: header of /usr/bin/check_mk_agent ("License: GNU General Public License v2") |
| db-ip-country-lite | 2026-10 | CC-BY-4.0 (attribution required) | limits | data file read by the agent (country blocks), unmodified | not verified from the file (its metadata names DB-IP.com only); upstream: db-ip.com/db/lite |

## Downloaded files (outside apt)

| name | version | licence | marks | how used | how verified | images |
|---|---|---|---|---|---|---|
| adminer | 6.1.2 | Apache-2.0 OR GPL-2.0 (either) | GPL | separate web application, unmodified; a plugin and a sign-on script of ours beside it (pfhw-plugin.php, pfhw-signon.php) | verified: @license lines of /usr/share/pfhw-adminer/6.1.2/adminer.php in the pg image | pg |
| checkmk-agent | v2.5.0p17 | GPL-2.0 | GPL | separate program (shell script), unmodified | verified: header of /usr/bin/check_mk_agent ("License: GNU General Public License v2") | core, db, dns, pg, web |
| db-ip-country-lite | 2026-10 | CC-BY-4.0 (attribution required) | limits | data file read by the agent (country blocks), unmodified | not verified from the file (its metadata names DB-IP.com only); upstream: db-ip.com/db/lite | web |
| inter | 5.0.18 | SIL-OFL-1.1 |  | font file (latin, variable) the portal's pages load from their own address, unmodified | verified: the licence text shipped with the font (static/fonts/LICENSE-Inter-OFL.txt in the core image): SIL Open Font License, Version 1.1 | core |
| libnginx-mod-http-brotli-filter | 1.0.0~rc-5build1 | MISSING |  |  |  | web |
| libnginx-mod-http-brotli-static | 1.0.0~rc-5build1 | MISSING |  |  |  | web |
| lucide-icons | 1.0.0 | ISC |  | 17 icons (SVG) drawn by the portal's style sheet as masks, unmodified; their licence text is in the same folder | verified: the licence text shipped with the icons (static/icons/LICENSE-Lucide-ISC.txt in the core image); sha256 here is that file's | core |
| mariadb-keyring | 177F4010FE56CA3336300305F1656F24C74CD1D8 | n/a (public signing key) |  | apt repository key | - | db |
| mariadb-server | 1:11.8.9+maria~ubu2404 | GPL-2.0 | GPL | separate program, unmodified | verified: dpkg copyright file of mariadb-server in the db image | db |
| modsecurity-unicode.mapping | v3.0.14 | Apache-2.0 |  | data file, unmodified | not verified from the file (no header); upstream: ModSecurity repository LICENSE | web |
| nodejs | 22.23.4 | MIT (plus bundled components listed in LICENSE) |  | separate program for customer applications, unmodified | verified: /opt/node/<major>/LICENSE ("Node.js is licensed for use as follows", MIT terms) | web |
| nodejs | 24.22.1 | MIT (plus bundled components listed in LICENSE) |  | separate program for customer applications, unmodified | verified: /opt/node/<major>/LICENSE ("Node.js is licensed for use as follows", MIT terms) | web |
| nodejs | 26.12.1 | MIT (plus bundled components listed in LICENSE) |  | separate program for customer applications, unmodified | verified: /opt/node/<major>/LICENSE ("Node.js is licensed for use as follows", MIT terms) | web |
| owasp-crs | 4.30.0 | Apache-2.0 |  | rule files read by ModSecurity, unmodified (rules switched off by id in our configuration) | verified: /etc/nginx/pfhw/waf/crs-4.30.0/LICENSE | web |
| pdns-server | 5.1.5-1pdns.ubuntu24.04 | GPL-2.0 | GPL | separate program, unmodified | verified: dpkg copyright file of pdns-server in the dns image | dns |
| pgdg-key | B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8 | n/a (public signing key) |  | apt repository key | - | pg |
| phpmyadmin | 5.2.3 | GPL-2.0 | GPL | separate web application, unmodified; one sign-on script of ours added beside it (pfhw-signon.php) | verified: /usr/share/pfhw-phpmyadmin/5.2.3/LICENSE | db |
| pm2 | 7.1.2 | AGPL-3.0 | AGPL | separate program (the process manager of Node.js and Next.js apps), unmodified, installed from the npm registry tarball whose integrity is checked; customers use it only through the portal's Apps (AGPL section 13 applies to modified versions) | verified: package.json of pm2 7.1.2 ("license": "AGPL-3.0"); its npm dependencies (MIT, ISC, Apache-2.0, Python-2.0) are listed with their licences in docs/v2/packages/pfhw-web-<version>.txt | web |
| postgresql-18 | 18.6-1.pgdg24.04+2 | PostgreSQL |  | separate program, unmodified | verified: dpkg copyright file of postgresql-18 in the pg image ("License: PostgreSQL") | pg |
| powerdns-key | 9FAAA5577E8FCF62093D036C1B0C6205FD380FBB | n/a (public signing key) |  | apt repository key | - | dns |
| pypi:annotated-doc | 0.0.5 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:annotated-types | 0.8.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:anyio | 4.15.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:certifi | 2026.10.23 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:cffi | 2.1.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:click | 8.5.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:cryptography | 50.0.2 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:dnspython | 2.9.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:email-validator | 2.3.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:fastapi | 0.162.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:h11 | 0.16.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:httpcore | 1.0.9 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:httpx | 0.28.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:idna | 3.20 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:jinja2 | 3.1.6 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:markupsafe | 3.0.4 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:opentelemetry-api | 1.45.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:pycparser | 3.12 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:pydantic | 2.14.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:pydantic-core | 2.50.1 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:python-multipart | 0.0.32 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:pyyaml | 6.0.3 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:segno | 1.6.6 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:starlette | 1.10.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:typing-extensions | 4.16.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:typing-inspection | 0.4.4 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| pypi:uvicorn | 0.54.0 | see the pip rows |  | Python libraries linked into Core (imported), unmodified | verified: package metadata in the core image | core |
| python-build-standalone | 3.11.18+20261026 | MPL-2.0 (the build scripts); the builds contain CPython (PSF-2.0) and its bundled libraries (OpenSSL Apache-2.0, SQLite public domain, libedit BSD, others in the archive's licence files) |  | the Python builds used as /opt/python/<x.y>, unmodified | not verified from the file: upstream github.com/astral-sh/python-build-standalone LICENSE; release 20261026, sha256 from its SHA256SUMS | web |
| python-build-standalone | 3.12.16+20261026 | MPL-2.0 (the build scripts); the builds contain CPython (PSF-2.0) and its bundled libraries (OpenSSL Apache-2.0, SQLite public domain, libedit BSD, others in the archive's licence files) |  | the Python builds used as /opt/python/<x.y>, unmodified | not verified from the file: upstream github.com/astral-sh/python-build-standalone LICENSE; release 20261026, sha256 from its SHA256SUMS | web |
| python-build-standalone | 3.13.18+20261026 | MPL-2.0 (the build scripts); the builds contain CPython (PSF-2.0) and its bundled libraries (OpenSSL Apache-2.0, SQLite public domain, libedit BSD, others in the archive's licence files) |  | the Python builds used as /opt/python/<x.y>, unmodified | not verified from the file: upstream github.com/astral-sh/python-build-standalone LICENSE; release 20261026, sha256 from its SHA256SUMS | web |
| python-build-standalone | 3.14.10+20261026 | MPL-2.0 (the build scripts); the builds contain CPython (PSF-2.0) and its bundled libraries (OpenSSL Apache-2.0, SQLite public domain, libedit BSD, others in the archive's licence files) |  | the Python builds used as /opt/python/<x.y>, unmodified | not verified from the file: upstream github.com/astral-sh/python-build-standalone LICENSE; release 20261026, sha256 from its SHA256SUMS | web |
| python-build-standalone | 3.15.2+20261026 | MPL-2.0 (the build scripts); the builds contain CPython (PSF-2.0) and its bundled libraries (OpenSSL Apache-2.0, SQLite public domain, libedit BSD, others in the archive's licence files) |  | the Python builds used as /opt/python/<x.y>, unmodified | not verified from the file: upstream github.com/astral-sh/python-build-standalone LICENSE; release 20261026, sha256 from its SHA256SUMS | web |
| ruby | 3.3.13 | Ruby OR BSD-2-Clause |  | separate program for customer applications, built from the unmodified source into /opt/ruby/<x.y> | not verified from the file: upstream ruby-lang.org/en/about/license.txt; tarballs from cache.ruby-lang.org, sha256 from its index.txt | web |
| ruby | 3.4.12 | Ruby OR BSD-2-Clause |  | separate program for customer applications, built from the unmodified source into /opt/ruby/<x.y> | not verified from the file: upstream ruby-lang.org/en/about/license.txt; tarballs from cache.ruby-lang.org, sha256 from its index.txt | web |
| ruby | 4.0.9 | Ruby OR BSD-2-Clause |  | separate program for customer applications, built from the unmodified source into /opt/ruby/<x.y> | not verified from the file: upstream ruby-lang.org/en/about/license.txt; tarballs from cache.ruby-lang.org, sha256 from its index.txt | web |
| sftpgo | 2.7.6 | AGPL-3.0 | AGPL | separate program, unmodified; customers use it over the network (AGPL section 13 applies to modified versions) | verified: /usr/share/licenses/sftpgo/LICENSE in the web image | web |
| wp-cli | 2.12.0 | MIT |  | separate program (PHP), unmodified | not verified from the file (the phar's licence could not be read); upstream: github.com/wp-cli/wp-cli LICENSE | web |

## Python packages (Core's virtual environment)

| name | version | licence | marks |
|---|---|---|---|
| annotated-doc | 0.0.5 | MIT |  |
| annotated-types | 0.8.0 | MIT |  |
| anyio | 4.15.1 | MIT |  |
| certifi | 2026.10.23 | MPL-2.0 |  |
| cffi | 2.1.1 | MIT-0 |  |
| click | 8.5.0 | BSD-3-Clause |  |
| cryptography | 50.0.2 | Apache-2.0 OR BSD-3-Clause |  |
| dnspython | 2.9.0 | ISC |  |
| email-validator | 2.3.0 | Unlicense |  |
| fastapi | 0.162.0 | MIT |  |
| h11 | 0.16.0 | MIT |  |
| httpcore | 1.0.9 | BSD-3-Clause |  |
| httpx | 0.28.1 | BSD-3-Clause |  |
| idna | 3.20 | BSD-3-Clause |  |
| Jinja2 | 3.1.6 | BSD License |  |
| MarkupSafe | 3.0.4 | BSD-3-Clause |  |
| opentelemetry-api | 1.45.1 | Apache-2.0 |  |
| pip | 24.0 | MIT |  |
| pycparser | 3.12 | BSD-3-Clause |  |
| pydantic | 2.14.1 | MIT |  |
| pydantic_core | 2.50.1 | MIT |  |
| python-multipart | 0.0.32 | Apache-2.0 |  |
| PyYAML | 6.0.3 | MIT |  |
| segno | 1.6.6 | BSD License |  |
| starlette | 1.10.0 | BSD-3-Clause |  |
| typing-inspection | 0.4.4 | MIT |  |
| typing_extensions | 4.16.0 | PSF-2.0 |  |
| uvicorn | 0.54.0 | BSD-3-Clause |  |

## Debian packages

| package | version | licence | marks | images |
|---|---|---|---|---|
| acl | 2.3.2-1build1.1 | GPL-2+;LGPL-2+ | GPL LGPL | web |
| adduser | 3.137ubuntu1 | GPL-2+ | GPL | base, core, db, dns, pg, users, web |
| apache2 | 2.4.58-1ubuntu8.19 | Apache-2.0;Apache-2.0 and BSD-3-clause-Cambridge;Apache-2.0 and Cisco;Apache-2.0 and Haines;Apache-2.0 and MD5;Apache-2.0 and Zeus;Apache-2.0 or GPL-2+;BSD-2... | GPL | web |
| apache2-bin | 2.4.58-1ubuntu8.19 | Apache-2.0;Apache-2.0 and BSD-3-clause-Cambridge;Apache-2.0 and Cisco;Apache-2.0 and Haines;Apache-2.0 and MD5;Apache-2.0 and Zeus;Apache-2.0 or GPL-2+;BSD-2... | GPL | web |
| apache2-data | 2.4.58-1ubuntu8.19 | Apache-2.0;Apache-2.0 and BSD-3-clause-Cambridge;Apache-2.0 and Cisco;Apache-2.0 and Haines;Apache-2.0 and MD5;Apache-2.0 and Zeus;Apache-2.0 or GPL-2+;BSD-2... | GPL | web |
| apache2-suexec-custom | 2.4.58-1ubuntu8.19 | Apache-2.0;Apache-2.0 and BSD-3-clause-Cambridge;Apache-2.0 and Cisco;Apache-2.0 and Haines;Apache-2.0 and MD5;Apache-2.0 and Zeus;Apache-2.0 or GPL-2+;BSD-2... | GPL | web |
| apache2-utils | 2.4.58-1ubuntu8.19 | Apache-2.0;Apache-2.0 and BSD-3-clause-Cambridge;Apache-2.0 and Cisco;Apache-2.0 and Haines;Apache-2.0 and MD5;Apache-2.0 and Zeus;Apache-2.0 or GPL-2+;BSD-2... | GPL | web |
| appstream | 1.0.2-1build6 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+;SIL-1.1 | GPL LGPL | web |
| apt | 2.8.3 | BSD-3-clause;Expat;GPL-2;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| base-files | 13ubuntu10.5 | isc (text) |  | base, builder, core, db, dns, pg, users, web |
| base-passwd | 3.6.3build1 | GPL-2;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| bash | 5.2.21-2ubuntu4 | BSD-4-clause-UC;BSD-4-clause-UC and MIT-like;GFDL-NIV-1.3;GPL-2+;GPL-3+;GPL-3+ with Bison exception;Latex2e;MIT-like;permissive | GPL | base, builder, core, db, dns, pg, users, web |
| bind9-dnsutils | 1:9.18.39-0ubuntu0.24.04.9 | BSD-2-clause;BSD-3-clause;CC0-1.0;FSFAP;ISC;ISC or MPL-2.0;MPL-2.0;MPL-2.0 and CC0-1.0;MPL-2.0 and ISC;MPL-2.0 and ISC and BSD-2-clause and BSD-3-clause;MPL-... |  | core, dns |
| bind9-host | 1:9.18.39-0ubuntu0.24.04.9 | BSD-2-clause;BSD-3-clause;CC0-1.0;FSFAP;ISC;ISC or MPL-2.0;MPL-2.0;MPL-2.0 and CC0-1.0;MPL-2.0 and ISC;MPL-2.0 and ISC and BSD-2-clause and BSD-3-clause;MPL-... |  | core, dns |
| bind9-libs | 1:9.18.39-0ubuntu0.24.04.9 | BSD-2-clause;BSD-3-clause;CC0-1.0;FSFAP;ISC;ISC or MPL-2.0;MPL-2.0;MPL-2.0 and CC0-1.0;MPL-2.0 and ISC;MPL-2.0 and ISC and BSD-2-clause and BSD-3-clause;MPL-... |  | core, dns |
| binutils | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| binutils-common | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| binutils-x86-64-linux-gnu | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| bsd-mailx | 8.1.2-0.20220412cvs-1build1 | BSD-3-Clause |  | base, core, db, dns, pg, web |
| bsdutils | 1:2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| build-essential | 12.10ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| bzip2 | 1.0.8-5.1ubuntu0.1 | BSD-variant;GPL-2 | GPL | builder, web |
| ca-certificates | 20260816ubuntu0.24.04.2 | GPL-2+;MPL-2.0 | GPL | base, builder, core, db, dns, pg, users, web |
| ca-certificates-java | 20240118ubuntu0.24.04.2 | GPL (text) | GPL | web |
| clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| clamav-base | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| clamav-daemon | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| clamav-freshclam | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| clamdscan | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| coreutils | 9.4-3ubuntu6.3 | BSD-4-clause-UC;FSFULLR;GFDL-NIV-1.3;GPL-3+;GPL-3+ and BSD-4-clause-UC;GPL-3+ and ISC;ISC | GPL | base, builder, core, db, dns, pg, users, web |
| cpanminus | 1.7047-1 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| cpio | 2.15+dfsg-1ubuntu2.1 | GPL-3+;LGPL-3+ | GPL LGPL | base, core, db, dns, pg, web |
| cpp | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| cpp-13 | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| cpp-13-x86-64-linux-gnu | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| cpp-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| cron | 3.0pl1-184ubuntu2 | Artistic;GPL-2+;ISC;Paul-Vixie's-license;Paul-Vixie's-license and GPL-2+ and ISC | GPL | base, core, db, dns, pg, web |
| cron-daemon-common | 3.0pl1-184ubuntu2 | Artistic;GPL-2+;ISC;Paul-Vixie's-license;Paul-Vixie's-license and GPL-2+ and ISC | GPL | base, core, db, dns, pg, web |
| curl | 8.5.0-2ubuntu10.16 | BSD-3-Clause;BSD-3-clause;BSD-4-Clause-UC;FSFULLR;GPL-2+ with Autoconf-data exception;GPL-2+ with Libtool exception;GPL-3+ with Autoconf-data exception;ISC;O... | GPL | base, builder, core, db, dns, pg, web |
| dash | 0.5.12-6ubuntu5 | BSD-3-Clause;BSD-3-clause;GPL-2+;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| dbus | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| dbus-bin | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| dbus-daemon | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| dbus-session-bus-common | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| dbus-system-bus-common | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| debconf | 1.5.86ubuntu1 | BSD-2-clause |  | base, builder, core, db, dns, pg, users, web |
| debianutils | 5.17build1 | GPL-2+;SMAIL-GPL;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| diffutils | 1:3.10-1ubuntu0.1 | FSFAP;FSFULLR;GFDL-NIV-1.3;GPL-2+;GPL-3+;GPL-3+ and FSFULLR;GPL-3+ with autoconf exception;GPL-3+ with texinfo exception;LGPL-2.0+;LGPL-2.1+;LGPL-3.0+;LGPL-3... | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| dirmngr | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| distro-info-data | 2026.10.12-0ubuntu0.24.04.1 | ISC |  | web |
| dpkg | 1.22.6ubuntu6.6 | GPL-2+;public-domain-s-s-d | GPL | base, builder, core, db, dns, pg, users, web |
| dpkg-dev | 1.22.6ubuntu6.6 | GPL-2+;public-domain-s-s-d | GPL | builder, web |
| e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | Apache-2;BSD-3-Clause;GPL or MIT-US-export;GPL-2;GPL-2+ with Texinfo exception;ISC;Kazlib;LGPL-2;Latex2e | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| fail2ban | 1.0.2-3ubuntu0.1 | GNU General Public License (text) | GPL | web |
| fakeroot | 1.33-1 | GNU General Public License (text) | GPL | web |
| findutils | 4.9.0-5build1 | BSD-3-clause;BSD-3-clause and/or GPL-3+;FSFAP;FSFULLR;GFDL-NIV-1.3+;GPL with automake exception;GPL-2+;GPL-2+ with Autoconf-data exception;GPL-3+;GPL-3+ with... | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| fontconfig-config | 2.15.0-1.1ubuntu2 | mpl (text) |  | db, web |
| fonts-dejavu-core | 2.37-8 | GPL-2+;bitstream-vera | GPL | db, web |
| fonts-dejavu-mono | 2.37-8 | GPL-2+;bitstream-vera | GPL | db, web |
| g++ | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| g++-13 | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| g++-13-x86-64-linux-gnu | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| g++-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| galera-4 | 26.4.27-ubu2404 | CC-BY-SA-3.0;GFDL-1.1+;GFDL-1.1+ or CC-BY-SA-3.0;GPL-2;other | GPL limits | db |
| gawk | 1:5.2.1-2ubuntu0.1 | GPL-3+ | GPL | db |
| gcc | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| gcc-13 | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| gcc-13-base | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| gcc-13-x86-64-linux-gnu | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| gcc-14-base | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | base, builder, core, db, dns, pg, users, web |
| gcc-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GNU General Public License (text) | GPL | builder, web |
| geoip-database | 20240403-1ubuntu1 | OpenDataLicense |  | web |
| gir1.2-girepository-2.0 | 1.80.1-1 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;BSD-2-clause;CC-BY-SA-3.0;CC0-1.0;Expat;Expat and GPL-2+;FSFAP;FSFAP and FSFULLR;FSFULLR;GPL with... | GPL LGPL limits | web |
| gir1.2-glib-2.0 | 2.80.0-6ubuntu3.10 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;CC-BY-SA-3.0;CC0-1.0;CC0-1.0 or Mingw-PD;Expat;FSFULLR;GPL-2+;Iconv-PD;Janik-permissive;Janik-per... | GPL LGPL limits | web |
| gir1.2-packagekitglib-1.0 | 1.2.8-2ubuntu1.5 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+ | GPL LGPL | web |
| git | 1:2.43.0-1ubuntu7.4 | Apache-2.0;BSD-3-clause;Boost;EDL-1.0;Expat;GPL-1+ or Artistic-1;GPL-2;GPL-2+;ISC;LGPL-2+;LGPL-2.1+;Zlib;dlmalloc;mingw-runtime | GPL LGPL | builder, web |
| git-man | 1:2.43.0-1ubuntu7.4 | Apache-2.0;BSD-3-clause;Boost;EDL-1.0;Expat;GPL-1+ or Artistic-1;GPL-2;GPL-2+;ISC;LGPL-2+;LGPL-2.1+;Zlib;dlmalloc;mingw-runtime | GPL LGPL | builder, web |
| gnupg | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| gnupg-utils | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| goaccess | 1:1.8.1-1build3 | Expat;GPL-3 | GPL | web |
| gpg | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| gpg-agent | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| gpgconf | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| gpgsm | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| gpgv | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| grep | 3.11-4build1 | GPL-3+ | GPL | base, builder, core, db, dns, pg, users, web |
| gzip | 1.12-1ubuntu3.2 | FSF-manpages;GFDL-1.3+-no-invariant;GPL-3+ | GPL | base, builder, core, db, dns, pg, users, web |
| hostname | 3.23+nmu2ubuntu2 | GPL-2 | GPL | base, builder, core, db, dns, pg, users, web |
| icu-devtools | 74.2-1ubuntu3.1 | GPL-3;MIT | GPL | builder |
| imagemagick-6-common | 8:6.9.12.98+dfsg1-5.2build2 | BSD-with-FSF-change-public-domain;GNU-All-Permissive-License;GPL-2+;GPL2+-with-Autoconf-Macros-exception;GPL3+-with-Autoconf-Macros-exception;GPL3+-with-Auto... | GPL LGPL | web |
| init-system-helpers | 1.66ubuntu1 | BSD-3-clause;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| iproute2 | 6.1.0-1ubuntu6.4 | GPL-2 | GPL | base, core, db, dns, pg, web |
| iputils-ping | 3:20240117-1ubuntu0.1 | BSD-3-clause;GPL-2+;public-domain | GPL | base, core, db, dns, pg, web |
| iputils-tracepath | 3:20240117-1ubuntu0.1 | BSD-3-clause;GPL-2+;public-domain | GPL | web |
| iso-codes | 4.16.0-1 | LGPL-2.1+ | LGPL | web |
| java-common | 0.75+exp1 | GPL-2+ | GPL | web |
| keyboxd | 2.4.4-2ubuntu17.6 | BSD-3-clause;CC0-1.0;Expat;GPL-2+;GPL-3+;GPL-3+ or BSD-3-clause;LGPL-2.1+;LGPL-3+;LGPL-3+ or GPL-2+;RFC-Reference;TinySCHEME;permissive | GPL LGPL | base, core, db, dns, pg, web |
| ldap-utils | 2.6.10+dfsg-0ubuntu0.24.04.1 | BSD-3-clause;BSD-3-clause-California;BSD-3-clause-variant;BSD-4-clause-California;Beerware;Expat;Expat-ISC;Expat-UNM;F5;FSF-unlimited;FSF-unlimited and GPL-2... | GPL | users, web |
| less | 590-2ubuntu2.1 | GPL-3+;GPL-3+ or Less;GPL-3+ or Less, and X11;Less;Spencer-86;X11;public-domain | GPL | base, core, db, dns, pg, web |
| libacl1 | 2.3.2-1build1.1 | GPL-2+;LGPL-2+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libaio1t64 | 0.3.113-6build1.1 | LGPL-2.1+ | LGPL | db |
| libalgorithm-diff-perl | 1.201-1 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| libalgorithm-diff-xs-perl | 0.04-8build3 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| libalgorithm-merge-perl | 0.08-5 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| libaom3 | 3.8.2-2ubuntu0.2 | BSD-2-Clause;BSD-2-clause;BSD-3-clause;Expat;ISC;public-domain-md5 |  | db, web |
| libapache-pom-java | 29-2 | Apache-2.0 |  | web |
| libapparmor1 | 4.0.1really4.0.1-0ubuntu0.24.04.9 | BSD-3-clause;BSD-3-clause or GPL-2+;GPL-2;GPL-2+;LGPL-2.1+ | GPL LGPL | base, core, db, dns, pg, web |
| libappstream5 | 1.0.2-1build6 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+;SIL-1.1 | GPL LGPL | web |
| libapr1t64 | 1.7.2-3.1ubuntu0.1 | Apache License (text) |  | web |
| libaprutil1-dbd-sqlite3 | 1.6.3-1.1ubuntu7.1 | Apache License (text) |  | web |
| libaprutil1-ldap | 1.6.3-1.1ubuntu7.1 | Apache License (text) |  | web |
| libaprutil1t64 | 1.6.3-1.1ubuntu7.1 | Apache License (text) |  | web |
| libapt-pkg6.0t64 | 2.8.3 | BSD-3-clause;Expat;GPL-2;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| libargon2-1 | 0~20190702+dfsg-4build1 | Apache-2.0;CC0;CC0 or Apache-2.0 |  | base, core, db, dns, pg, users, web |
| libasan8 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libassuan0 | 2.5.6-1build1 | GAP;GAP~FSF;GPL-2+;GPL-2+ with libtool exception;GPL-3+;LGPL-2.1+;LGPL-3+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libatomic1 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libattr1 | 1:2.5.2-1ubuntu0.1 | GPL-2+;LGPL-2+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libaudit-common | 1:3.1.2-2.1ubuntu0.1 | GPL-2;LGPL-2.1 | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libaudit1 | 1:3.1.2-2.1ubuntu0.1 | GPL-2;LGPL-2.1 | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libbcel-java | 6.5.0-2 | Apache-2.0 |  | web |
| libbinutils | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| libblkid1 | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libboost-program-options1.83.0 | 1.83.0-2.1ubuntu3.2 | Apache-2.0;Apache-2.0 and BSL-1.0;BSD2;BSD2 and BSL-1.0;BSD3_DEShaw;BSD3_DEShaw and BSL-1.0;BSD3_Google;BSL-1.0;BSL-1.0 and CrystalClear;BSL-1.0 and HP and S... |  | dns |
| libbpf1 | 1:1.3.0-2build2 | BSD-2-Clause;BSD-3-Clause;GPL-2 with Linux-syscall-note exception;GPL-2 with Linux-syscall-note exception OR BSD-3-Clause;GPL-2+;GPL-2.0;LGPL-2.1;LGPL-2.1 or... | GPL LGPL | base, core, db, dns, pg, web |
| libbrotli1 | 1.1.0-2ubuntu0.1 | MIT |  | base, builder, core, db, dns, pg, web |
| libbsd0 | 0.12.1-1build1.1 | BSD-2-clause;BSD-2-clause-NetBSD;BSD-2-clause-author;BSD-2-clause-verbatim;BSD-3-clause;BSD-3-clause-John-Birrell;BSD-3-clause-Regents;BSD-3-clause-Regents a... |  | base, core, db, dns, pg, web |
| libbz2-1.0 | 1.0.8-5.1ubuntu0.1 | BSD-variant;GPL-2 | GPL | base, builder, core, db, dns, pg, users, web |
| libc-bin | 2.39-0ubuntu8.12 | mpl (text) |  | builder, pg, web |
| libc-bin | 2.39-0ubuntu8.9 | mpl (text) |  | base, core, db, dns, users |
| libc-dev-bin | 2.39-0ubuntu8.12 | mpl (text) |  | builder, web |
| libc-devtools | 2.39-0ubuntu8.12 | mpl (text) |  | web |
| libc6 | 2.39-0ubuntu8.12 | mpl (text) |  | builder, pg, web |
| libc6 | 2.39-0ubuntu8.9 | mpl (text) |  | base, core, db, dns, users |
| libc6-dev | 2.39-0ubuntu8.12 | mpl (text) |  | builder, web |
| libcap-ng0 | 0.8.4-2build2 | GPL-2+;GPL-3;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libcap2 | 1:2.66-5ubuntu2.4 | BSD-3-clause;BSD-3-clause or GPL-2;BSD-3-clause or GPL-2+;GPL-2;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| libcap2-bin | 1:2.66-5ubuntu2.4 | BSD-3-clause;BSD-3-clause or GPL-2;BSD-3-clause or GPL-2+;GPL-2;GPL-2+ | GPL | base, core, db, dns, pg, web |
| libcbor0.10 | 0.10.2-1.2ubuntu2 | Expat |  | core, web |
| libcc1-0 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libclamav12 | 1.5.4+dfsg-0ubuntu0.24.04.1 | 0BSD-MIT-Apache-2.0;0BSD-MIT-Apache-2.0-Zlib;Apache-2.0;Apache-2.0 with GPL exception;Apache-2.0-BSL-1.0;Apache-2.0-Expat;Apache-2.0-Expat or Zlib;Apache-2.0... | GPL LGPL | web |
| libcom-err2 | 1.47.0-2.4~exp1ubuntu4.1 | Apache-2;BSD-3-Clause;GPL or MIT-US-export;GPL-2;GPL-2+ with Texinfo exception;ISC;Kazlib;LGPL-2;Latex2e | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libcommons-compress-java | 1.25.0-1 | Apache-2.0 |  | web |
| libcommons-io-java | 2.11.0-2 | Apache-2.0 |  | web |
| libcommons-parent-java | 56-1 | Apache-2.0 |  | web |
| libconfig-inifiles-perl | 3.000003-2ubuntu0.1 | Artistic;Artistic or GPL-1+;Expat;GPL-1+;GPL-3+ | GPL | db, web |
| libcpan-distnameinfo-perl | 0.12-3 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| libcpan-meta-check-perl | 0.017-1 | Artistic;Artistic or GPL-1+;GPL-1+;GPL-3+ | GPL | builder, web |
| libcrypt-dev | 1:4.4.36-4build1 | mpl (text) |  | builder, web |
| libcrypt1 | 1:4.4.36-4build1 | mpl (text) |  | base, builder, core, db, dns, pg, users, web |
| libcryptsetup12 | 2:2.7.0-1ubuntu4.2 | Apache-2.0;CC0;CC0 or Apache-2.0;GPL-2+;GPL-2+ with OpenSSL exception;GPL-3+;LGPL-2.1+;LGPL-2.1+ with OpenSSL exception;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libctf-nobfd0 | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| libctf0 | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| libcurl3t64-gnutls | 8.5.0-2ubuntu10.16 | BSD-3-Clause;BSD-3-clause;BSD-4-Clause-UC;FSFULLR;GPL-2+ with Autoconf-data exception;GPL-2+ with Libtool exception;GPL-3+ with Autoconf-data exception;ISC;O... | GPL | builder, web |
| libcurl4t64 | 8.5.0-2ubuntu10.16 | BSD-3-Clause;BSD-3-clause;BSD-4-Clause-UC;FSFULLR;GPL-2+ with Autoconf-data exception;GPL-2+ with Libtool exception;GPL-3+ with Autoconf-data exception;ISC;O... | GPL | base, builder, core, db, dns, pg, web |
| libdb5.3t64 | 5.3.28+dfsg2-7 | Artistic or BSD-3-clause;BSD-3-clause;BSD-3-clause-fjord;GPL;GPL or Artistic;GPL-3;MIT-old;Ms-PL;Sleepycat;Sleepycat and BSD-3-clause;TCL-like;X11;zlib | GPL | base, builder, core, db, dns, pg, users, web |
| libdbd-mysql-perl | 4.052-1ubuntu3 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| libdbi-perl | 1.643-4ubuntu0.4 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | db, web |
| libdbus-1-3 | 1.14.10-4ubuntu4.1 | AFL-2.1;BSD-3-clause;BSD-3-clause and BSD-3-clause-generic;BSD-3-clause-generic;Expat;FSF-unlimited-permission;GPL-2+;GPL-2+ or AFL-2.1, and Expat and Tcl-BS... | GPL LGPL | base, core, db, dns, pg, web |
| libdebconfclient0 | 0.271ubuntu3 | BSD-2-Clause;BSD-2-clause;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| libdeflate0 | 1.19-1build1.1 | Expat |  | db, web |
| libdevmapper1.02.1 | 2:1.02.185-3ubuntu3.2 | BSD-2-Clause;GPL-2.0;GPL-2.0+;LGPL-2.1 | GPL LGPL | base, core, db, dns, pg, web |
| libdpkg-perl | 1.22.6ubuntu6.6 | GPL-2+;public-domain-s-s-d | GPL | builder, web |
| libduktape207 | 2.7.0+tests-0ubuntu3 | CC0;expat;unicode |  | web |
| libdw1t64 | 0.190-1.1ubuntu0.1 | BSD-2-clause;GFDL-NIV-1.3;GPL-3+;GPL-3+ with Bison exception;LGPL-2.1+;LGPL-3+ or GPL-2+ | GPL LGPL | web |
| libeclipse-jdt-core-java | 3.32.0+eclipse4.26-2 | Apache-1.1;Apache-2.0;BSD-3-clause;EPL-2.0 |  | web |
| libedit2 | 3.1-20230828-1build1 | BSD-3-clause |  | base, core, db, dns, pg, web |
| libelf1t64 | 0.190-1.1ubuntu0.1 | BSD-2-clause;GFDL-NIV-1.3;GPL-3+;GPL-3+ with Bison exception;LGPL-2.1+;LGPL-3+ or GPL-2+ | GPL LGPL | base, core, db, dns, pg, web |
| liberror-perl | 0.17029-2 | Artistic;Artistic or GPL-1+;GPL-1+;MIT/X11 | GPL | builder, web |
| libexpat1 | 2.6.1-2ubuntu0.6 | MIT |  | base, builder, core, db, dns, pg, web |
| libexpat1-dev | 2.6.1-2ubuntu0.6 | MIT |  | builder |
| libext2fs2t64 | 1.47.0-2.4~exp1ubuntu4.1 | Apache-2;BSD-3-Clause;GPL or MIT-US-export;GPL-2;GPL-2+ with Texinfo exception;ISC;Kazlib;LGPL-2;Latex2e | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libfakeroot | 1.33-1 | GNU General Public License (text) | GPL | web |
| libfdisk1 | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libffi-dev | 3.4.6-1build1 | Expat;GPL;GPL-2+;GPL-3+;MPL-1.1 or GPL-2+ or LGPL-2.1+;X11;public-domain | GPL LGPL | builder |
| libffi8 | 3.4.6-1build1 | Expat;GPL;GPL-2+;GPL-3+;MPL-1.1 or GPL-2+ or LGPL-2.1+;X11;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libfftw3-double3 | 3.3.10-1ubuntu3 | GPL-2+ | GPL | web |
| libfido2-1 | 1.14.0-1build3 | BSD-2-clause;ISC;ISC and BSD-2-clause;public-domain |  | core, web |
| libfile-fcntllock-perl | 0.22-4ubuntu5 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| libfile-pushd-perl | 1.016-2 | Apache-2.0;other |  | builder, web |
| libfontconfig1 | 2.15.0-1.1ubuntu2 | mpl (text) |  | db, web |
| libfreetype6 | 2.13.2+dfsg-1ubuntu0.2 | BSD-3-Clause;BSL-1.0;Expat;FSFAP;FTL;FTL and Expat;GPL-2+;GPL-3+;MIT-Modern-Variant;MIT-SMC;OpenGroup-MIT;Public-Domain;Zlib | GPL | db, web |
| libfuzzy2 | 2.14.1+git20180629.57fcfff-3 | GPL-2;GPL-2+;GPL-3;boost-software-license;boost-software-license or GPL-2 or GPL-3;public-domain | GPL | web |
| libgcc-13-dev | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libgcc-s1 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | base, builder, core, db, dns, pg, users, web |
| libgcrypt20 | 1.10.3-2ubuntu0.2 | LGPL (text) | LGPL | base, builder, core, db, dns, pg, users, web |
| libgd3 | 2.3.3-9ubuntu5 | BSD-3-clause;GAP~Makefile.in;GAP~configure;GD;GPL-2+;GPL-2+ with Autoconf exception;HPND;MIT;WEBP;XFIG | GPL | db, web |
| libgdbm-compat4t64 | 1.23-5.1build1 | GFDL-NIV-1.3+;GPL-2+;GPL-3+ | GPL | builder, db, pg, users, web |
| libgdbm6t64 | 1.23-5.1build1 | GFDL-NIV-1.3+;GPL-2+;GPL-3+ | GPL | builder, db, pg, users, web |
| libgeoip1t64 | 1.6.12-11.1build1 | ISC;LGPL-2.1+ | LGPL | web |
| libgirepository-1.0-1 | 1.80.1-1 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;BSD-2-clause;CC-BY-SA-3.0;CC0-1.0;Expat;Expat and GPL-2+;FSFAP;FSFAP and FSFULLR;FSFULLR;GPL with... | GPL LGPL limits | web |
| libglib2.0-0t64 | 2.80.0-6ubuntu3.10 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;CC-BY-SA-3.0;CC0-1.0;CC0-1.0 or Mingw-PD;Expat;FSFULLR;GPL-2+;Iconv-PD;Janik-permissive;Janik-per... | GPL LGPL limits | web |
| libglib2.0-bin | 2.80.0-6ubuntu3.10 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;CC-BY-SA-3.0;CC0-1.0;CC0-1.0 or Mingw-PD;Expat;FSFULLR;GPL-2+;Iconv-PD;Janik-permissive;Janik-per... | GPL LGPL limits | web |
| libglib2.0-data | 2.80.0-6ubuntu3.10 | AFL-2.0;AFL-2.0 or LGPL-2.1+;Apache-2.0 with LLVM exception;CC-BY-SA-3.0;CC0-1.0;CC0-1.0 or Mingw-PD;Expat;FSFULLR;GPL-2+;Iconv-PD;Janik-permissive;Janik-per... | GPL LGPL limits | web |
| libgmp-dev | 2:6.3.0+dfsg-2ubuntu6.1 | GPL-2+;GPL-2+ or LGPL-3+;GPL-3+;GPL-3+ with Bison exception;LGPL-3+ | GPL LGPL | builder |
| libgmp10 | 2:6.3.0+dfsg-2ubuntu6.1 | GPL-2+;GPL-2+ or LGPL-3+;GPL-3+;GPL-3+ with Bison exception;LGPL-3+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libgmpxx4ldbl | 2:6.3.0+dfsg-2ubuntu6.1 | GPL-2+;GPL-2+ or LGPL-3+;GPL-3+;GPL-3+ with Bison exception;LGPL-3+ | GPL LGPL | builder |
| libgnutls30t64 | 3.8.3-1.1ubuntu3.6 | Apache-2.0;BSD-3-Clause;CC0 license;Expat;GPLv3+;LGPLv2.1+;LGPLv3+_or_GPLv2+;The main library is licensed under GNU Lesser | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libgomp1 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libgpg-error0 | 1.47-3build2.1 | BSD-3-clause;GPL-3+;LGPL-2.1+;LGPL-2.1+ or BSD-3-clause;g10-permissive | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libgpm2 | 1.20.7-11 | GPL-2.0+;GPL-3.0+ | GPL | web |
| libgprofng0 | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| libgssapi-krb5-2 | 1.20.1-6ubuntu2.10 | isc (text) |  | base, builder, core, db, dns, pg, web |
| libgstreamer1.0-0 | 1.24.2-1ubuntu0.1 | GPL-2+;GPL-3+;LGPL-2+;LGPL-2.1+ | GPL LGPL | web |
| libheif-plugin-aomdec | 1.17.6-1ubuntu4.9 | BOOST-1.0;BSD-3-clause;BSD-4-clause;GPL-3+;LGPL-3+;MIT | GPL LGPL | db, web |
| libheif-plugin-aomenc | 1.17.6-1ubuntu4.9 | BOOST-1.0;BSD-3-clause;BSD-4-clause;GPL-3+;LGPL-3+;MIT | GPL LGPL | db, web |
| libheif1 | 1.17.6-1ubuntu4.9 | BOOST-1.0;BSD-3-clause;BSD-4-clause;GPL-3+;LGPL-3+;MIT | GPL LGPL | db, web |
| libhogweed6t64 | 3.9.1-2.2build1.1 | Expat;GAP;GPL-2;GPL-2+;GPL-3+ with Autoconf exception;LGPL-2+;LGPL-3+;LGPL-3+ or GPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libhwasan0 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libicu-dev | 74.2-1ubuntu3.1 | GPL-3;MIT | GPL | builder |
| libicu74 | 74.2-1ubuntu3.1 | GPL-3;MIT | GPL | base, builder, core, db, dns, pg, web |
| libidn2-0 | 2.3.7-2build1.1 | GPL-2+;GPL-3+;LGPL-3+;LGPL-3+ or GPL-2+;Unicode | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libisl23 | 0.26-3build1.1 | BSD-2-clause;LGPL-2.1+;MIT | LGPL | builder, web |
| libitm1 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libjansson4 | 2.14-2build2 | Expat |  | base, builder, core, db, dns, pg, web |
| libjbig0 | 2.1-6.1ubuntu2 | GPL-2+ | GPL | db, web |
| libjemalloc2 | 5.3.0-2build1 | BSD-2-Clause;BSD-2-Clause-Chemeris;BSD-3-Clause;BSD-3-Clause-Google;BSD-3-Clause-Hiroshima-University;Expat |  | web |
| libjpeg-turbo8 | 2.1.5-2ubuntu2 | BSD-3-clause;BSD-BY-LC-NE;Expat;NTP;Zlib;zlib |  | db, web |
| libjpeg8 | 8c-2ubuntu11 | LGPL-2.1 | LGPL | db, web |
| libjson-c5 | 0.17-1build1 | Expat |  | base, core, db, dns, pg, web |
| libjson-perl | 4.10000-1 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | pg |
| libk5crypto3 | 1.20.1-6ubuntu2.10 | isc (text) |  | base, builder, core, db, dns, pg, web |
| libkeyutils1 | 1.6.3-3build1 | GPL-2+;LGPL-2+ | GPL LGPL | base, builder, core, db, dns, pg, web |
| libkmod2 | 31+20240202-2ubuntu7.2 | GPL-2+;LGPL-2.1+ | GPL LGPL | base, core, db, dns, pg, web |
| libkrb5-3 | 1.20.1-6ubuntu2.10 | isc (text) |  | base, builder, core, db, dns, pg, web |
| libkrb5support0 | 1.20.1-6ubuntu2.10 | isc (text) |  | base, builder, core, db, dns, pg, web |
| libksba8 | 1.6.6-1build1 | FSFUL;LGPL-2.1-or-later | LGPL | base, core, db, dns, pg, web |
| liblcms2-2 | 2.14-2ubuntu0.1 | GPL-2+;GPL-3;IJG;MIT | GPL | web |
| libldap2 | 2.6.10+dfsg-0ubuntu0.24.04.1 | BSD-3-clause;BSD-3-clause-California;BSD-3-clause-variant;BSD-4-clause-California;Beerware;Expat;Expat-ISC;Expat-UNM;F5;FSF-unlimited;FSF-unlimited and GPL-2... | GPL | base, builder, core, db, dns, pg, users, web |
| liblerc4 | 4.0.0+ds-4ubuntu2 | Apache-2.0 |  | db, web |
| liblmdb0 | 0.9.31-1build1 | OpenLDAP-2.8 |  | core, dns |
| liblocal-lib-perl | 2.000029-1 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| liblocale-gettext-perl | 1.07-6ubuntu5 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | web |
| liblockfile-bin | 1.17-1build3 | GPL-2+;LGPL-2+ | GPL LGPL | base, core, db, dns, pg, web |
| liblockfile1 | 1.17-1build3 | GPL-2+;LGPL-2+ | GPL LGPL | base, core, db, dns, pg, web |
| liblqr-1-0 | 0.4.2-2.1build2 | GPLv3 | GPL | web |
| liblsan0 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libltdl7 | 2.4.7-7build1 | GFDL-NIV-1.3+;GPL-2+ | GPL | users, web |
| liblua5.3-0 | 5.3.6-2build2 | Expat |  | web |
| liblua5.4-0 | 5.4.6-3build2 | Expat |  | web |
| libluajit-5.1-2 | 2.1.0+git20231223.c525bcb+dfsg-1ubuntu0.1 | MIT/X;PD |  | dns |
| libluajit-5.1-common | 2.1.0+git20231223.c525bcb+dfsg-1ubuntu0.1 | MIT/X;PD |  | dns |
| liblz4-1 | 1.9.4-1build1.1 | BSD-2-clause;GPL-2+;GPL-2+ or BSD-2-clause | GPL | base, builder, core, db, dns, pg, users, web |
| liblzf1 | 3.6-4 | BSD-2-clause;BSD-3-clause;BSD-3-clause or GPL-2;FSFUL;GPL-2;MIT/X11 | GPL | web |
| liblzma5 | 5.6.1+really5.4.5-1ubuntu0.3 | Autoconf;GPL-2;GPL-2+;LGPL-2.1+;PD;PD-debian;config-h;noderivs;none;permissive-fsf;permissive-nowarranty;probably-PD | GPL LGPL | base, core, db, dns, pg, users |
| liblzma5 | 5.6.1+really5.4.5-1ubuntu0.4 | Autoconf;GPL-2;GPL-2+;LGPL-2.1+;PD;PD-debian;config-h;noderivs;none;permissive-fsf;permissive-nowarranty;probably-PD | GPL LGPL | builder, web |
| libmagickcore-6.q16-7t64 | 8:6.9.12.98+dfsg1-5.2build2 | BSD-with-FSF-change-public-domain;GNU-All-Permissive-License;GPL-2+;GPL2+-with-Autoconf-Macros-exception;GPL3+-with-Autoconf-Macros-exception;GPL3+-with-Auto... | GPL LGPL | web |
| libmagickwand-6.q16-7t64 | 8:6.9.12.98+dfsg1-5.2build2 | BSD-with-FSF-change-public-domain;GNU-All-Permissive-License;GPL-2+;GPL2+-with-Autoconf-Macros-exception;GPL3+-with-Autoconf-Macros-exception;GPL3+-with-Auto... | GPL LGPL | web |
| libmariadb-dev | 1:10.11.14-0ubuntu0.24.04.1 | Artistic;BSD-2-Clause;BSD-2-clause;BSD-3-clause;GPL-2;GPL-2 or Artistic;GPL-2+;GPL-2+-with-bison-exception;GPL-3+-with-bison-exception;LGPL;LGPL-2;LGPL-2+;LG... | GPL LGPL | builder |
| libmariadb3 | 1:10.11.14-0ubuntu0.24.04.1 | Artistic;BSD-2-Clause;BSD-2-clause;BSD-3-clause;GPL-2;GPL-2 or Artistic;GPL-2+;GPL-2+-with-bison-exception;GPL-3+-with-bison-exception;LGPL;LGPL-2;LGPL-2+;LG... | GPL LGPL | builder, web |
| libmariadb3 | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| libmaxminddb0 | 1.9.1-1build1 | Apache-2.0;BSD-2-clause and BSD-3-clause and BSD-4-clause;CC-BY-SA-3.0;GPL-2+ | GPL limits | core, dns, web |
| libmd0 | 1.1.0-2build1.1 | BSD-2-clause;BSD-2-clause-NetBSD;BSD-3-clause;BSD-3-clause-Aaron-D-Gifford;Beerware;ISC;public-domain-md4;public-domain-md5;public-domain-sha1 |  | base, builder, core, db, dns, pg, users, web |
| libmnl0 | 1.0.5-2build1 | GPL-2+;LGPL-2.1 | GPL LGPL | base, core, db, dns, pg, web |
| libmodsecurity-dev | 3.0.12-1.1build2 | Apache-2.0;BSD-3-Clause;Expat;FSFAP;FSFUL;FSFULLR;FSFULLR or GPL-2+ with AutoConf exception;GPL-2+ with AutoConf exception;GPL-2+ with LibTool exception;GPL-... | GPL | web |
| libmodsecurity3t64 | 3.0.12-1.1build2 | Apache-2.0;BSD-3-Clause;Expat;FSFAP;FSFUL;FSFULLR;FSFULLR or GPL-2+ with AutoConf exception;GPL-2+ with AutoConf exception;GPL-2+ with LibTool exception;GPL-... | GPL | web |
| libmodule-build-perl | 0.423400-2 | Artistic;Artistic or GPL-1+;CC0-1.0;GPL-1+ | GPL | builder, web |
| libmodule-cpanfile-perl | 1.1004-2 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| libmount1 | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libmpc3 | 1.3.1-1build1.1 | LGPL (text) | LGPL | builder, web |
| libmpfr6 | 4.2.1-1build1.1 | LGPL (text) | LGPL | builder, db, web |
| libmspack0t64 | 0.11-1.1ubuntu0.24.04.1 | LGPL-2.1 | LGPL | web |
| libmysqlclient21 | 8.0.46-0ubuntu0.24.04.5 | Artistic;Artistic or GPL-2;BSD-2-clause;BSD-3-clause;BSD-3-clause and GPL-2;BSD-like;Boost-1.0;GPL-2;GPL-2+;ISC;LGPL;public-domain;zlib/libpng | GPL LGPL | web |
| libncurses6 | 6.4+20240113-1ubuntu2.2 | BSD-3-clause;MIT/X11;X11 |  | db, web |
| libncursesw6 | 6.4+20240113-1ubuntu2.2 | BSD-3-clause;MIT/X11;X11 |  | base, builder, core, db, dns, pg, users, web |
| libnettle8t64 | 3.9.1-2.2build1.1 | Expat;GAP;GPL-2;GPL-2+;GPL-3+ with Autoconf exception;LGPL-2+;LGPL-3+;LGPL-3+ or GPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libnftables1 | 1.0.9-1ubuntu0.1 | CC-BY-SA-4.0;GPL-2;GPL-2+ | GPL limits | base, core, db, dns, pg, web |
| libnftnl11 | 1.2.6-2build1 | GPL-2;GPL-2+ | GPL | base, core, db, dns, pg, web |
| libnghttp2-14 | 1.59.0-1ubuntu0.4 | BSD-2-clause;Expat;GPL-3+ with autoconf exception;MIT;all-permissive | GPL | base, builder, core, db, dns, pg, web |
| libnginx-mod-http-brotli-filter | 1.0.0~rc-5build1 | BSD-2-clause |  | web |
| libnginx-mod-http-brotli-static | 1.0.0~rc-5build1 | BSD-2-clause |  | web |
| libnginx-mod-http-modsecurity | 1.0.3-1build3 | Apache |  | web |
| libnginx-mod-http-ndk | 1:0.3.3-1build1 | BSD-3-clause;SSLeay |  | web |
| libnl-3-200 | 3.7.0-0.3build1.1 | mpl (text) |  | base, core, db, dns, pg, web |
| libnl-genl-3-200 | 3.7.0-0.3build1.1 | mpl (text) |  | base, core, db, dns, pg, web |
| libnpth0t64 | 1.6-3.1build1 | LGPL-2.1+ | LGPL | base, builder, core, db, dns, pg, users, web |
| libnsl2 | 1.3.0-3build3 | BSD-3-clause;GPL-2+-autoconf-exception;GPL-2+-libtool-exception;GPL-3+-autoconf-exception;LGPL-2.1;LGPL-2.1+;MIT;permissive-autoconf-m4;permissive-autoconf-m... | GPL LGPL | base, core, db, dns, pg, web |
| libnspr4 | 2:4.35-1.1build1 | MPL-2.0 |  | web |
| libnss-ldapd | 0.9.12-4build1 | mpl (text) |  | web |
| libnss3 | 2:3.98-1ubuntu0.3 | BSD-3;MPL-2.0;Zlib;public-domain |  | web |
| libnuma1 | 2.0.18-1ubuntu0.24.04.1 | GNU General Public License (text) | GPL | pg |
| libodbc2 | 2.3.12-1ubuntu0.24.04.1 | GPL-2+;LGPL-2+;LGPL-2.1+;ppowell | GPL LGPL | users |
| libonig5 | 6.9.9-1build1 | BSD-2-clause;GPL-2+ | GPL | db, pg, web |
| libopenjp2-7 | 2.5.0-2ubuntu0.5 | BSD-2;BSD-3;LIBPNG;LIBTIFF;LIBTIFF-GLARSON;LIBTIFF-PIXAR;MIT;ZLIB;public-domain |  | web |
| libp11-kit0 | 0.25.3-4ubuntu2.2 | Apache-2.0;BSD-3-clause;FSFAP;FSFULLR;GPL-2+ with Autoconf-data exception;GPL-3+ with Autoconf-data exception;ISC;LGPL-2.1+;X11;customFSFUL;customFSFULLRWD | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libpackagekit-glib2-18 | 1.2.8-2ubuntu1.5 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+ | GPL LGPL | web |
| libpam-ldapd | 0.9.12-4build1 | mpl (text) |  | web |
| libpam-modules | 1.5.3-5ubuntu5.7 | BSD-3-clause or GPL;BSD-tcp_wrappers;Beerware;GPL-2;GPL-2+;GPL-3;GPL-3+ with Bison exception;LGPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libpam-modules-bin | 1.5.3-5ubuntu5.7 | BSD-3-clause or GPL;BSD-tcp_wrappers;Beerware;GPL-2;GPL-2+;GPL-3;GPL-3+ with Bison exception;LGPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libpam-runtime | 1.5.3-5ubuntu5.7 | BSD-3-clause or GPL;BSD-tcp_wrappers;Beerware;GPL-2;GPL-2+;GPL-3;GPL-3+ with Bison exception;LGPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libpam-systemd | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libpam0g | 1.5.3-5ubuntu5.7 | BSD-3-clause or GPL;BSD-tcp_wrappers;Beerware;GPL-2;GPL-2+;GPL-3;GPL-3+ with Bison exception;LGPL-2+;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libparse-pmfile-perl | 0.45-1 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| libpcre2-8-0 | 10.42-4ubuntu2.1 | BSD-2-clause;BSD-3-clause;BSD-3-clause-Cambridge with BINARY LIBRARY-LIKE PACKAGES exception;X11;public-domain |  | base, builder, core, dns, pg, users, web |
| libpcre2-8-0 | 10.42-4ubuntu2.2 | BSD-2-clause;BSD-3-clause;BSD-3-clause-Cambridge with BINARY LIBRARY-LIKE PACKAGES exception;X11;public-domain |  | db |
| libpcre2-posix3 | 10.42-4ubuntu2.2 | BSD-2-clause;BSD-3-clause;BSD-3-clause-Cambridge with BINARY LIBRARY-LIKE PACKAGES exception;X11;public-domain |  | db |
| libpcsclite1 | 2.0.3-1build1 | BSD-3-clause;GPL-3+;ISC | GPL | web |
| libperl-dev | 5.38.2-3.2ubuntu0.7 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | builder |
| libperl5.38t64 | 5.38.2-3.2ubuntu0.7 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | builder, db, pg, users, web |
| libpkgconf3 | 1.8.1-2build1 | BSD-2;BSD-4;GPL-2+;ISC;X11 | GPL | builder |
| libpng16-16t64 | 1.6.43-5ubuntu0.7 | Apache-2.0;BSD-3-clause;BSD-like-with-advertising-clause;GPL-2+;GPL-2+ or BSD-like-with-advertising-clause;expat;libpng;libpng OR Apache-2.0 OR BSD-3-clause | GPL | db, web |
| libpolkit-agent-1-0 | 124-2ubuntu1.24.04.4 | Apache-2.0;Expat;LGPL-2.0+;LGPL-2.0+ and Expat | LGPL | web |
| libpolkit-gobject-1-0 | 124-2ubuntu1.24.04.4 | Apache-2.0;Expat;LGPL-2.0+;LGPL-2.0+ and Expat | LGPL | web |
| libpopt0 | 1.19+dfsg-1build1 | GPL-2+;expat | GPL | base, core, db, dns, pg, web |
| libpq-dev | 16.15-0ubuntu0.24.04.1 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysa... |  | builder |
| libpq5 | 16.15-0ubuntu0.24.04.1 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysa... |  | builder |
| libpq5 | 18.6-1.pgdg24.04+2 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysa... |  | pg |
| libproc2-0 | 2:4.0.4-4ubuntu3.3 | GPL-2.0+;LGPL-2.0+;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libpsl5t64 | 0.21.2-1.1build1 | Chromium;MIT;gnulib |  | base, builder, core, db, dns, pg, web |
| libpython3-stdlib | 3.12.3-0ubuntu2.1 | isc (text) |  | base, builder, core, db, dns, pg, web |
| libpython3.12-minimal | 3.12.3-1ubuntu0.17 | * Permission to use this software in any way is granted without;By obtaining, using, and/or copying this software and/or its;Permission  is  hereby granted, ... |  | base, builder, core, db, dns, pg, web |
| libpython3.12-stdlib | 3.12.3-1ubuntu0.17 | * Permission to use this software in any way is granted without;By obtaining, using, and/or copying this software and/or its;Permission  is  hereby granted, ... |  | base, builder, core, db, dns, pg, web |
| libquadmath0 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libraw23t64 | 0.21.2-2.1ubuntu0.24.04.2 | CC-BY-SA-3.0;CDDL-1.0;GPL-2+;LGPL-2.1;LGPL-2.1 or CDDL-1.0 | GPL LGPL limits | web |
| libreadline8t64 | 8.2-4build1 | GFDL-NIV-1.3+;GPL-2+;GPL-3;GPL-3+;ISC-no-attribution | GPL limits | base, builder, core, db, dns, pg, web |
| librtmp1 | 2.4+20151223.gitfa8646d.1-2build7 | mpl (text) |  | base, builder, core, db, dns, pg, web |
| libsasl2-2 | 2.1.28+dfsg1-5ubuntu3.1 | BSD-2-clause;BSD-2-clause and MIT-CMU;BSD-2.2-clause;BSD-3-Clause-Attribution;BSD-3-Clause-Attribution and IBM-as-is;BSD-3-Clause-Attribution and MIT-Export;... | GPL limits | base, builder, core, db, dns, pg, users, web |
| libsasl2-modules | 2.1.28+dfsg1-5ubuntu3.1 | BSD-2-clause;BSD-2-clause and MIT-CMU;BSD-2.2-clause;BSD-3-Clause-Attribution;BSD-3-Clause-Attribution and IBM-as-is;BSD-3-Clause-Attribution and MIT-Export;... | GPL limits | base, core, db, dns, pg, web |
| libsasl2-modules-db | 2.1.28+dfsg1-5ubuntu3.1 | BSD-2-clause;BSD-2-clause and MIT-CMU;BSD-2.2-clause;BSD-3-Clause-Attribution;BSD-3-Clause-Attribution and IBM-as-is;BSD-3-Clause-Attribution and MIT-Export;... | GPL limits | base, builder, core, db, dns, pg, users, web |
| libseccomp2 | 2.5.5-1ubuntu3.1 | LGPL-2.1 | LGPL | base, builder, core, db, dns, pg, users, web |
| libselinux1 | 3.5-2ubuntu2.1 | GPL-2;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| libsemanage-common | 3.5-1build5 | GPL-2;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libsemanage2 | 3.5-1build5 | GPL-2;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libsepol2 | 3.5-2build1 | GPL-2;GPL-2+;LGPL-2.1+;Zlib | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libsframe1 | 2.42-4ubuntu2.10 | GNU General Public License (text) | GPL | builder, web |
| libsharpyuv0 | 1.3.2-0.4build3 | Apache-2.0;BSD-3-Clause |  | db, web |
| libsigsegv2 | 2.14-1ubuntu2 | Expat;FSFULL;GPL-2+;GPL-2+ with Autoconf exception;GPL-3+ with Autoconf exception;permissive | GPL | db |
| libsmartcols1 | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libsodium23 | 1.0.18-1ubuntu0.24.04.1 | BSD-2-clause;CC0;GPL-2+;ISC;MIT;public-domain | GPL | db, dns, pg, web |
| libsqlite3-0 | 3.45.1-1ubuntu2.9 | GPL-2+;public-domain | GPL | base, builder, core, db, dns, pg, web |
| libsqlite3-dev | 3.45.1-1ubuntu2.9 | GPL-2+;public-domain | GPL | builder |
| libss2 | 1.47.0-2.4~exp1ubuntu4.1 | Apache-2;BSD-3-Clause;GPL or MIT-US-export;GPL-2;GPL-2+ with Texinfo exception;ISC;Kazlib;LGPL-2;Latex2e | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libssh-4 | 0.10.6-2ubuntu0.5 | BSD-2-clause;BSD-3-clause;LGPL-2.1;LGPL-2.1+~OpenSSL;LGPL-2.1+~OpenSSL or BSD-2-clause or BSD-3-clause;public-domain | LGPL | base, builder, core, db, dns, pg, web |
| libssl-dev | 3.0.13-0ubuntu3.16 | Apache-2.0;Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder |
| libssl3t64 | 3.0.13-0ubuntu3.16 | Apache-2.0;Artistic;Artistic or GPL-1+;GPL-1+ | GPL | base, builder, core, db, dns, pg, users, web |
| libstdc++-13-dev | 13.3.0-6ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libstdc++6 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | base, builder, core, db, dns, pg, users, web |
| libstemmer0d | 2.2.0-4build1 | BSD-3-snowball |  | web |
| libstring-shellquote-perl | 1.04-3 | Artistic;Artistic or GPL-1+;GPL-1+ | GPL | builder, web |
| libsystemd-shared | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libsystemd0 | 255.4-1ubuntu8.17 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | builder, users |
| libsystemd0 | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libtasn1-6 | 4.19.0-3ubuntu0.24.04.2 | LGPL (text) | LGPL | base, builder, core, db, dns, pg, users, web |
| libterm-readkey-perl | 2.38-2build4 | Artistic;Artistic or GPL-1+;GPL-1+;termreadkey;termreadkey or Artistic or GPL-1+ | GPL | web |
| libtiff6 | 4.5.1+git230720-4ubuntu2.5 | Hylafax |  | db, web |
| libtinfo6 | 6.4+20240113-1ubuntu2.2 | BSD-3-clause;MIT/X11;X11 |  | base, builder, core, db, dns, pg, users, web |
| libtirpc-common | 1.3.4+ds-1.1build1 | BSD-2-Clause;BSD-3-Clause;BSD-4-Clause;GPL-2;LGPL-2.1+;PERMISSIVE;__AUTO_PERMISSIVE__ | GPL LGPL | base, core, db, dns, pg, web |
| libtirpc3t64 | 1.3.4+ds-1.1build1 | BSD-2-Clause;BSD-3-Clause;BSD-4-Clause;GPL-2;LGPL-2.1+;PERMISSIVE;__AUTO_PERMISSIVE__ | GPL LGPL | base, core, db, dns, pg, web |
| libtomcat10-java | 10.1.55-1ubuntu2~24.04.1 | Apache-2.0;CDDL |  | web |
| libtsan2 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libubsan1 | 14.2.0-4ubuntu2~24.04.1 | mpl (text) |  | builder, web |
| libudev1 | 255.4-1ubuntu8.17 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | builder, users |
| libudev1 | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| libunistring5 | 1.1-2build1.1 | FreeSoftware;GFDL-NIV-1.2+;GPL-2+;GPL-2+ with distribution exception;GPL-2+ with distribution exception, Expat and GPL-2+;GPL-3+;GPL-3+ or GFDL-NIV-1.2+;LGPL... | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libunwind8 | 1.6.2-3build1.1 | Expat;GPL-2+ | GPL | web |
| liburing2 | 2.5-1build1 | GPL-2 with Linux-syscall-note exception;GPL-2 with Linux-syscall-note exception or MIT;LGPL-2.1+;LGPL-2.1+ or MIT;MIT | GPL LGPL | db, pg |
| libuuid1 | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| libuv1t64 | 1.48.0-1.1build1 | Apache-2.0;BSD-2-clause;CC-BY-4.0;Expat;GPL3+ with autoconf exception;ISC | GPL limits | core, dns, web |
| libwebp7 | 1.3.2-0.4build3 | Apache-2.0;BSD-3-Clause |  | db, web |
| libwebpdemux2 | 1.3.2-0.4build3 | Apache-2.0;BSD-3-Clause |  | web |
| libwebpmux3 | 1.3.2-0.4build3 | Apache-2.0;BSD-3-Clause |  | web |
| libwebsockets-evlib-uv | 4.3.3-1.1build3 | Apache-2.0;BSD-1;BSD-3-AIST;BSD-3-Institute;BSD-3-WIDE;BSD-3-zlib;BSD-4-UC;CC0-1.0;Expat;LGPL-2.1;MIT;MIT or LGPL-2.1 | LGPL | web |
| libwebsockets19t64 | 4.3.3-1.1build3 | Apache-2.0;BSD-1;BSD-3-AIST;BSD-3-Institute;BSD-3-WIDE;BSD-3-zlib;BSD-4-UC;CC0-1.0;Expat;LGPL-2.1;MIT;MIT or LGPL-2.1 | LGPL | web |
| libwrap0 | 7.6.q-33 | BSD-3-clause;SSH;TCP-wrappers |  | base, core, db, dns, pg, users, web |
| libx11-6 | 2:1.8.7-1ubuntu0.1 | MIT license (text) |  | db, web |
| libx11-data | 2:1.8.7-1ubuntu0.1 | MIT license (text) |  | db, web |
| libxau6 | 1:1.0.9-1build6 | MPL (text) |  | db, web |
| libxcb1 | 1.15-1ubuntu2 | MPL (text) |  | db, web |
| libxdmcp6 | 1:1.1.3-0ubuntu6 | MPL (text) |  | db, web |
| libxext6 | 2:1.3.4-1build2 | MPL (text) |  | web |
| libxml2 | 2.9.14+dfsg-1.3ubuntu3.10 | ISC;MIT-1 |  | builder, core, db, dns, pg, web |
| libxml2-dev | 2.9.14+dfsg-1.3ubuntu3.10 | ISC;MIT-1 |  | builder |
| libxmlb2 | 0.3.24-1~ubuntu0.24.04.1 | CC0-1.0;LGPL-2.1+ | LGPL | web |
| libxpm4 | 1:3.5.17-1ubuntu0.24.04.2 | MPL (text) |  | db, web |
| libxslt1.1 | 1.1.39-0exp1ubuntu0.24.04.3 | MPL (text) |  | db, pg, web |
| libxtables12 | 1.8.10-3ubuntu2 | Artistic;GPL-2;GPL-2+;custom | GPL | base, core, db, dns, pg, web |
| libxxhash0 | 0.8.2-2build1 | BSD-2-clause;BSD-2-clause or GPL-2+;GPL-2+ | GPL | base, builder, core, db, dns, pg, users, web |
| libyajl2 | 2.1.0-5build1 | ISC |  | web |
| libyaml-0-2 | 0.2.5-1build1 | Expat;permissive |  | base, builder, core, db, dns, pg, web |
| libyaml-dev | 0.2.5-1build1 | Expat;permissive |  | builder |
| libzip4t64 | 1.7.3-1.1ubuntu2 | isc (text) |  | db, web |
| libzstd1 | 1.5.5+dfsg2-2build1.1 | BSD-3-clause;BSD-3-clause or GPL-2;Expat;GPL-2;zlib | GPL | base, builder, core, db, dns, pg, users, web |
| linux-libc-dev | 6.8.0-149.149 | GNU General Public License (text) | GPL | builder, web |
| locales | 2.39-0ubuntu8.12 | mpl (text) |  | pg |
| login | 1:4.13+dfsg1-4ubuntu3.2 | BSD-3-clause;GPL-1;GPL-2+;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| logrotate | 3.21.0-2build1 | BSD-3-Clause;GPL-2;GPL-3+ | GPL | base, core, db, dns, pg, web |
| logsave | 1.47.0-2.4~exp1ubuntu4.1 | Apache-2;BSD-3-Clause;GPL or MIT-US-export;GPL-2;GPL-2+ with Texinfo exception;ISC;Kazlib;LGPL-2;Latex2e | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| lsb-release | 12.0-2 | ISC |  | web |
| lsof | 4.95.0-1build3 | BSD-4-clause;GPL-2+;LGPL-2+;Purdue;sendmail | GPL LGPL | base, core, db, dns, pg, web |
| lto-disabled-list | 47 | GPL-2+ | GPL | builder, web |
| make | 4.3-4.1build2 | GPL-3+ | GPL | builder, web |
| manpages | 6.7-2 | BSD-2-clause;BSD-3-clause;BSD-4-clause;BSD-4-clause and Linux-man-pages-copyleft;Expat;GPL-1+;GPL-2;GPL-2+;GPL-2+ and Linux-man-pages-copyleft;GPL-3;LGPL-3.0... | GPL LGPL | web |
| manpages-dev | 6.7-2 | BSD-2-clause;BSD-3-clause;BSD-4-clause;BSD-4-clause and Linux-man-pages-copyleft;Expat;GPL-1+;GPL-2;GPL-2+;GPL-2+ and Linux-man-pages-copyleft;GPL-3;LGPL-3.0... | GPL LGPL | web |
| mariadb-backup | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mariadb-client | 1:10.11.14-0ubuntu0.24.04.1 | Artistic;BSD-2-Clause;BSD-2-clause;BSD-3-clause;GPL-2;GPL-2 or Artistic;GPL-2+;GPL-2+-with-bison-exception;GPL-3+-with-bison-exception;LGPL;LGPL-2;LGPL-2+;LG... | GPL LGPL | web |
| mariadb-client | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mariadb-client-core | 1:10.11.14-0ubuntu0.24.04.1 | Artistic;BSD-2-Clause;BSD-2-clause;BSD-3-clause;GPL-2;GPL-2 or Artistic;GPL-2+;GPL-2+-with-bison-exception;GPL-3+-with-bison-exception;LGPL;LGPL-2;LGPL-2+;LG... | GPL LGPL | web |
| mariadb-client-core | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mariadb-common | 1:10.11.14-0ubuntu0.24.04.1 | Artistic;BSD-2-Clause;BSD-2-clause;BSD-3-clause;GPL-2;GPL-2 or Artistic;GPL-2+;GPL-2+-with-bison-exception;GPL-3+-with-bison-exception;LGPL;LGPL-2;LGPL-2+;LG... | GPL LGPL | builder, web |
| mariadb-common | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mariadb-server | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mariadb-server-core | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mawk | 1.3.4.20240123-1build1 | CC-BY-3.0;GPL-2.0-only;X11 | GPL limits | base, builder, core, db, dns, pg, users, web |
| media-types | 10.1.0 | ad-hoc |  | base, builder, core, db, dns, pg, web |
| modsecurity-crs | 3.3.5-2 | ASLv2;GPL-2 | GPL | web |
| mount | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| mysql-common | 1:11.8.9+maria~ubu2404 | GPL (text) | GPL | db |
| mysql-common | 5.8+1.1.0build1 | GPL-2+ | GPL | builder, web |
| nano | 7.2-2ubuntu0.2 | GFDL-NIV+;GFDL-NIV+ or GPL-3+;GPL-3+ | GPL | base, core, db, dns, pg, web |
| ncurses-base | 6.4+20240113-1ubuntu2.2 | BSD-3-clause;MIT/X11;X11 |  | base, builder, core, db, dns, pg, users, web |
| ncurses-bin | 6.4+20240113-1ubuntu2.2 | BSD-3-clause;MIT/X11;X11 |  | base, builder, core, db, dns, pg, users, web |
| netbase | 6.4 | GPL-2 | GPL | base, builder, core, db, dns, pg, web |
| nftables | 1.0.9-1ubuntu0.1 | CC-BY-SA-4.0;GPL-2;GPL-2+ | GPL limits | base, core, db, dns, pg, web |
| nginx | 1.24.0-2ubuntu7.19 | BSD-2-clause;Expat;GPL-2+;public-domain | GPL | core, db, pg, web |
| nginx-common | 1.24.0-2ubuntu7.19 | BSD-2-clause;Expat;GPL-2+;public-domain | GPL | core, db, pg, web |
| nslcd | 0.9.12-4build1 | mpl (text) |  | web |
| openjdk-17-jre-headless | 17.0.21.0.3+1-1~24.04.1 | BSD-3-Clause;GPL2 with Classpath exception;LGPL-2.1;MIT | GPL LGPL | web |
| openjdk-21-jre-headless | 21.0.13.0.3+1-1~24.04.1 | BSD-3-Clause;GPL2 with Classpath exception;LGPL-2.1;MIT | GPL LGPL | web |
| openjdk-25-jre-headless | 25.0.5.0.3+1-1~24.04.1 | BSD-3-Clause;GPL2 with Classpath exception;LGPL-2.1;MIT | GPL LGPL | web |
| openssh-client | 1:9.6p1-3ubuntu13.20 | BSD-2-clause;BSD-3-clause;Expat-with-advertising-restriction;Mazieres-BSD-style;OpenSSH;Powell-BSD-style;public-domain |  | core, web |
| openssh-server | 1:9.6p1-3ubuntu13.20 | BSD-2-clause;BSD-3-clause;Expat-with-advertising-restriction;Mazieres-BSD-style;OpenSSH;Powell-BSD-style;public-domain |  | web |
| openssh-sftp-server | 1:9.6p1-3ubuntu13.20 | BSD-2-clause;BSD-3-clause;Expat-with-advertising-restriction;Mazieres-BSD-style;OpenSSH;Powell-BSD-style;public-domain |  | web |
| openssl | 3.0.13-0ubuntu3.16 | Apache-2.0;Artistic;Artistic or GPL-1+;GPL-1+ | GPL | base, builder, core, db, dns, pg, users, web |
| packagekit | 1.2.8-2ubuntu1.5 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+ | GPL LGPL | web |
| packagekit-tools | 1.2.8-2ubuntu1.5 | FSFAP;GPL-2+;GPL-2+ and LGPL-2.1+;LGPL-2.1+ | GPL LGPL | web |
| passwd | 1:4.13+dfsg1-4ubuntu3.2 | BSD-3-clause;GPL-1;GPL-2+;public-domain | GPL | base, builder, core, db, dns, pg, users, web |
| patch | 2.7.6-7build3 | GNU General Public License (text) | GPL | builder, web |
| pdns-backend-sqlite3 | 5.1.5-1pdns.ubuntu24.04 | BSD-3;Expat;GPL-2;GPL-2 with OpenSSL Exception;GPL-2+;GPL-3-Autoconf;ISC;LGPL-2.1+;Unlicense;curl;free-fsf;free-generic | GPL LGPL | dns |
| pdns-server | 5.1.5-1pdns.ubuntu24.04 | BSD-3;Expat;GPL-2;GPL-2 with OpenSSL Exception;GPL-2+;GPL-3-Autoconf;ISC;LGPL-2.1+;Unlicense;curl;free-fsf;free-generic | GPL LGPL | dns |
| perl | 5.38.2-3.2ubuntu0.7 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | builder, db, pg, users, web |
| perl-base | 5.38.2-3.2ubuntu0.6 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | base, core, dns |
| perl-base | 5.38.2-3.2ubuntu0.7 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | builder, db, pg, users, web |
| perl-modules-5.38 | 5.38.2-3.2ubuntu0.7 | Artistic;Artistic or GPL-1+ or Artistic-dist;Artistic-2;Artistic-dist;BSD-3-clause;BSD-3-clause-GENERIC;BSD-3-clause-with-weird-numbering;BSD-4-clause-POWERD... | GPL LGPL | builder, db, pg, users, web |
| php-common | 2:101~+ubuntu24.04.1+deb.sury.org+1 | Expat |  | web |
| php-common | 2:93ubuntu2 | Expat |  | db, pg |
| php-pear | 1:1.10.16+submodules+notgz-2+ubuntu24.04.1+deb.sury.org+1 | BSD-2-clause;LGPL-3.0+ | LGPL | web |
| php8.2-bcmath | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-cli | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-common | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-curl | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-fpm | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-gd | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-igbinary | 3.2.16-6+ubuntu24.04.1+deb.sury.org+1 | BSD-3-clause;PHP-3.01 |  | web |
| php8.2-imagick | 3.8.1-1+ubuntu24.04.1+deb.sury.org+1 | Expat;OFL-1.1;PHP-3.01 |  | web |
| php8.2-intl | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-mbstring | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-mysql | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-opcache | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-readline | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-redis | 6.3.0-2+ubuntu24.04.1+deb.sury.org+1 | Expat;PHP-3.01 |  | web |
| php8.2-soap | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-xml | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.2-zip | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-bcmath | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-bz2 | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-cli | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-cli | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-common | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-common | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-curl | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-curl | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-fpm | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-fpm | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-gd | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-gd | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-igbinary | 3.2.16-6+ubuntu24.04.1+deb.sury.org+1 | BSD-3-clause;PHP-3.01 |  | web |
| php8.3-imagick | 3.8.1-1+ubuntu24.04.1+deb.sury.org+1 | Expat;OFL-1.1;PHP-3.01 |  | web |
| php8.3-intl | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-intl | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-mbstring | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-mbstring | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-mysql | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-mysql | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-opcache | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-opcache | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-pgsql | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | pg |
| php8.3-readline | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-readline | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db, pg |
| php8.3-redis | 6.3.0-2+ubuntu24.04.1+deb.sury.org+1 | Expat;PHP-3.01 |  | web |
| php8.3-soap | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-xml | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-xml | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.3-zip | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.3-zip | 8.3.6-0ubuntu0.24.04.13 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | db |
| php8.4-bcmath | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-cli | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-common | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-curl | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-fpm | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-gd | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-igbinary | 3.2.16-6+ubuntu24.04.1+deb.sury.org+1 | BSD-3-clause;PHP-3.01 |  | web |
| php8.4-imagick | 3.8.1-1+ubuntu24.04.1+deb.sury.org+1 | Expat;OFL-1.1;PHP-3.01 |  | web |
| php8.4-intl | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-mbstring | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-mysql | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-opcache | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-readline | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-redis | 6.3.0-2+ubuntu24.04.1+deb.sury.org+1 | Expat;PHP-3.01 |  | web |
| php8.4-soap | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-xml | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.4-zip | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-bcmath | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-cli | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-common | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-curl | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-fpm | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-gd | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-igbinary | 3.2.16-6+ubuntu24.04.1+deb.sury.org+1 | BSD-3-clause;PHP-3.01 |  | web |
| php8.5-imagick | 3.8.1-1+ubuntu24.04.1+deb.sury.org+1 | Expat;OFL-1.1;PHP-3.01 |  | web |
| php8.5-intl | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-mbstring | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-mysql | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-readline | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-redis | 6.3.0-2+ubuntu24.04.1+deb.sury.org+1 | Expat;PHP-3.01 |  | web |
| php8.5-soap | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-xml | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| php8.5-zip | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | Apache-2.0;BSD-2-clause;BSD-2-clause and LGPL-3+;BSD-2-clause-libmagic;BSD-3-clause;BSD-3-clause and PHP-3.01;BSD-4-clause;BSD-TSRM;CC0;Expat;GD;LGPL-2+;LGPL... | LGPL | web |
| pinentry-curses | 1.2.1-3ubuntu5 | GPL-2;GPL-2+;LGPL-3+;LGPL-3+ or GPL-2+;X11 | GPL LGPL | base, core, db, dns, pg, web |
| pkg-config | 1.8.1-2build1 | BSD-2;BSD-4;GPL-2+;ISC;X11 | GPL | builder |
| pkgconf | 1.8.1-2build1 | BSD-2;BSD-4;GPL-2+;ISC;X11 | GPL | builder |
| pkgconf-bin | 1.8.1-2build1 | BSD-2;BSD-4;GPL-2+;ISC;X11 | GPL | builder |
| polkitd | 124-2ubuntu1.24.04.4 | Apache-2.0;Expat;LGPL-2.0+;LGPL-2.0+ and Expat | LGPL | web |
| postfix | 3.8.6-1ubuntu0.1 | GNU General Public License (text) | GPL | base, core, db, dns, pg, web |
| postgresql-18 | 18.6-1.pgdg24.04+2 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysa... |  | pg |
| postgresql-client-18 | 18.6-1.pgdg24.04+2 | BSD-2-clause;BSD-3-Clause;BSD-3-clause;Custom-Unicode;Custom-pg_dump;Custom-regex;PostgreSQL;PostgreSQL and Custom-regex and Tcl;Tcl;double-metaphone;nagaysa... |  | pg |
| postgresql-client-common | 293.pgdg24.04+1 | GPL-2+ | GPL | pg |
| postgresql-common | 293.pgdg24.04+1 | GPL-2+ | GPL | pg |
| procps | 2:4.0.4-4ubuntu3.3 | GPL-2.0+;LGPL-2.0+;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| psmisc | 23.7-1build1 | GPL-2+ | GPL | base, core, db, dns, pg, users, web |
| python-apt-common | 2.7.7ubuntu5.3 | GPL-2+;Permissive | GPL | web |
| python3 | 3.12.3-0ubuntu2.1 | isc (text) |  | base, builder, core, db, dns, pg, web |
| python3-apt | 2.7.7ubuntu5.3 | GPL-2+;Permissive | GPL | web |
| python3-blinker | 1.7.0-1 | BSD-3-clause;Expat |  | web |
| python3-cffi-backend | 1.16.0-2build1 | Expat |  | base, core, db, dns, pg, web |
| python3-cryptography | 41.0.7-4ubuntu0.4 | Apache;Expat |  | base, core, db, dns, pg, web |
| python3-dbus | 1.3.2-5build3 | AFL-2.1;Expat;GPL-2+;GPL-2+ or AFL-2.1, and Expat | GPL | web |
| python3-distro | 1.9.0-1 | Apache-2.0 |  | web |
| python3-distro-info | 1.7ubuntu0.1 | ISC |  | web |
| python3-gi | 3.48.2-1 | Expat;LGPL-2.1+ | LGPL | web |
| python3-httplib2 | 0.20.4-3ubuntu0.1 | BSD-3;Expat;GPL-2+;GPL-3+;LGPL-2.1+;MPL-1.1;MPL-1.1 or GPL-2+ or LGPL-2.1+ | GPL LGPL | web |
| python3-jinja2 | 3.1.2-1ubuntu1.3 | isc (text) |  | base, core, db, dns, pg, web |
| python3-jwt | 2.7.0-1ubuntu0.4 | Expat |  | web |
| python3-launchpadlib | 1.11.0-6 | LGPL-3.0;LGPL-3.0+ | LGPL | web |
| python3-lazr.restfulclient | 0.14.6-1 | LGPL-3.0;LGPL-3.0+ | LGPL | web |
| python3-lazr.uri | 1.0.6-3 | LGPL-3.0 | LGPL | web |
| python3-markupsafe | 2.1.5-1build2 | isc (text) |  | base, core, db, dns, pg, web |
| python3-minimal | 3.12.3-0ubuntu2.1 | isc (text) |  | base, builder, core, db, dns, pg, web |
| python3-oauthlib | 3.2.2-1 | BSD-3-clause |  | web |
| python3-pip-whl | 24.0+dfsg-1ubuntu1.3 | Apache-2.0;Apache-2.0 OR BSD-2;BSD-2;BSD-3;Expat;ISC;LGPL-2.1+;MPL-2;Python | LGPL | core |
| python3-pkg-resources | 68.1.2-2ubuntu1.2 | Apache-2.0;BSD-3-clause |  | web |
| python3-pyasyncore | 1.0.2-2 | PSFL-2 |  | web |
| python3-pyinotify | 0.9.6-2ubuntu1 | Expat;GPL-2 | GPL | web |
| python3-pyparsing | 3.1.1-1 | BSD-2-clause;BSD-3-clause;Expat;MIT/X11;ellis-and-grant;salvolainen |  | web |
| python3-setuptools | 68.1.2-2ubuntu1.2 | Apache-2.0;BSD-3-clause |  | web |
| python3-setuptools-whl | 68.1.2-2ubuntu1.2 | Apache-2.0;BSD-3-clause |  | core |
| python3-six | 1.16.0-4 | Expat |  | web |
| python3-software-properties | 0.99.49.4 | GPL-2+;GPL-3;LGPL-3 | GPL LGPL | web |
| python3-systemd | 235-1build4 | LGPL-2.1+ | LGPL | base, core, db, dns, pg, web |
| python3-venv | 3.12.3-0ubuntu2.1 | isc (text) |  | core |
| python3-wadllib | 1.3.6-5 | LGPL-3.0 | LGPL | web |
| python3-yaml | 6.0.1-2build2 | MPL (text) |  | base, core, db, dns, pg, web |
| python3.12 | 3.12.3-1ubuntu0.17 | * Permission to use this software in any way is granted without;By obtaining, using, and/or copying this software and/or its;Permission  is  hereby granted, ... |  | base, builder, core, db, dns, pg, web |
| python3.12-minimal | 3.12.3-1ubuntu0.17 | * Permission to use this software in any way is granted without;By obtaining, using, and/or copying this software and/or its;Permission  is  hereby granted, ... |  | base, builder, core, db, dns, pg, web |
| python3.12-venv | 3.12.3-1ubuntu0.17 | * Permission to use this software in any way is granted without;By obtaining, using, and/or copying this software and/or its;Permission  is  hereby granted, ... |  | core |
| quota | 4.06-1build6 | GNU General Public License (text) | GPL | base, core, db, dns, pg, web |
| readline-common | 8.2-4build1 | GFDL-NIV-1.3+;GPL-2+;GPL-3;GPL-3+;ISC-no-attribution | GPL limits | base, builder, core, db, dns, pg, web |
| redis-server | 5:7.0.15-1ubuntu0.24.04.5 | BSD-2-clause;BSD-3-clause;MIT |  | web |
| redis-tools | 5:7.0.15-1ubuntu0.24.04.5 | BSD-2-clause;BSD-3-clause;MIT |  | web |
| rpcsvc-proto | 1.4.2-0ubuntu7 | BSD-3-clause;GPL-2+-autoconf-exception;GPL-3+-autoconf-exception;MIT;permissive-autoconf-m4;permissive-autoconf-m4-no-warranty;permissive-configure;permissiv... | GPL | builder, web |
| rsync | 3.2.7-1ubuntu1.5 | GNU General Public License (text) | GPL | db, web |
| sed | 4.9-2ubuntu0.24.04.1 | BSD-4-clause-UC;BSL-1;GFDL-NIV-1.3+;GPL-3+;GPL-3+ and ISC;ISC;X11;pcre | GPL | base, builder, core, db, dns, pg, users, web |
| sensible-utils | 0.0.22 | All-permissive;BSD-2-clause;GPL-2+;configure;installsh | GPL | base, builder, core, db, dns, pg, users, web |
| sftpgo | 2.7.6-1 | unknown |  | web |
| sgml-base | 1.31 | GPL-2+ | GPL | web |
| shared-mime-info | 2.4-4 | GNU General Public License (text) | GPL | web |
| slapd | 2.6.10+dfsg-0ubuntu0.24.04.1 | BSD-3-clause;BSD-3-clause-California;BSD-3-clause-variant;BSD-4-clause-California;Beerware;Expat;Expat-ISC;Expat-UNM;F5;FSF-unlimited;FSF-unlimited and GPL-2... | GPL | users |
| socat | 1.8.0.0-4ubuntu0.1 | GPL (text) | GPL | db |
| software-properties-common | 0.99.49.4 | GPL-2+;GPL-3;LGPL-3 | GPL LGPL | web |
| sqlite3 | 3.45.1-1ubuntu2.9 | GPL-2+;public-domain | GPL | core, dns |
| ssl-cert | 1.1.2ubuntu1 | BSD-3-clause |  | base, core, db, dns, pg, web |
| sudo | 1.9.15p5-3ubuntu5.24.04.4 | BSD-2-Clause;BSD-3-Clause;GPL-2+;ISC;Zlib;other;public-domain | GPL | base, core, db, dns, pg, web |
| systemd | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| systemd-dev | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| systemd-sysv | 255.4-1ubuntu8.18 | CC0-1.0;Expat;GPL-2 with Linux-syscall-note exception;GPL-2+;LGPL-2.1+;public-domain | GPL LGPL | base, core, db, dns, pg, web |
| sysvinit-utils | 3.08-6ubuntu3 | GPL-2.0;GPL-2.0+;GPL-3.0;LGPL-2.1+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| tar | 1.35+dfsg-3ubuntu0.4 | GPL-2+;GPL-3+;GPL-3+ with Bison exception;LGPL-2.1+;LGPL-3+ | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| tomcat-jakartaee-migration | 1.0.7-2 | Apache-2.0 |  | web |
| tomcat10 | 10.1.55-1ubuntu2~24.04.1 | Apache-2.0;CDDL |  | web |
| tomcat10-common | 10.1.55-1ubuntu2~24.04.1 | Apache-2.0;CDDL |  | web |
| traceroute | 1:2.1.5-1 | GPL-2+;LGPL-2.1+ | GPL LGPL | web |
| ttyd | 1.7.4-1build2 | BSD-3;MIT |  | web |
| tzdata | 2026e-0ubuntu0.24.04.1 | ICU;public-domain |  | base, builder, core, db, dns, pg, web |
| ubuntu-keyring | 2023.11.28.1 | GPL (text) | GPL | base, builder, core, db, dns, pg, users, web |
| ucf | 3.0043+nmu1 | GPL-2 | GPL | db, pg, web |
| unattended-upgrades | 2.9.1+nmu4ubuntu1 | GPL-2+ | GPL | web |
| unminimize | 0.2.1 | GPL-2.0+ | GPL | base, builder, core, db, dns, pg, users, web |
| unzip | 6.0-28ubuntu4.1 | isc (text) |  | web |
| util-linux | 2.39.3-9ubuntu6.6 | BSD-3-clause;BSD-4-clause;BSLA;GPL-2;GPL-2+;GPL-3+;LGPL;LGPL-2+;LGPL-2.1+;LGPL-3+;MIT;public-domain | GPL LGPL | base, builder, core, db, dns, pg, users, web |
| whois | 5.5.22 | GPL (please see /usr/share/common-licenses/GPL-2). | GPL | web |
| xdg-user-dirs | 0.18-1build1 | GNU General Public License (text) | GPL | web |
| xml-core | 0.19 | GPL-2+ | GPL | web |
| xz-utils | 5.6.1+really5.4.5-1ubuntu0.4 | Autoconf;GPL-2;GPL-2+;LGPL-2.1+;PD;PD-debian;config-h;noderivs;none;permissive-fsf;permissive-nowarranty;probably-PD | GPL LGPL | builder, web |
| zlib1g | 1:1.3.dfsg-3.1ubuntu2.2 | Zlib |  | base, core, db, dns, pg, users, web |
| zlib1g | 1:1.3.dfsg-3.1ubuntu2.3 | Zlib |  | builder |
| zlib1g-dev | 1:1.3.dfsg-3.1ubuntu2.3 | Zlib |  | builder |
## Source code of third-party programs

PFHW's own software is not open source (see `LICENSE`). The programs listed below are under GPL, LGPL or AGPL
licences, which give you the right to their source code. They are installed unmodified, as separate programs.

**Written offer.** CloudAcropolis UAB will give you, on request, the complete source code of any program listed here,
in the exact version contained in this release, for at least three years after you received the release. Write to
info@cloudacropolis.com and name the program and its version. We may charge only what it costs us to provide the copy.
The sources are also public at the upstream addresses given below.

### Programs from their own vendors

| program | version | licence | source code |
|---|---|---|---|
| SFTPGo | 2.7.6 | AGPL-3.0 | https://github.com/drakkan/sftpgo/archive/refs/tags/v2.7.6.tar.gz |
| PM2 | 7.1.2 | AGPL-3.0 | https://github.com/Unitech/pm2/archive/refs/tags/v7.1.2.tar.gz |
| phpMyAdmin | 5.2.3 | GPL-2.0 | https://files.phpmyadmin.net/phpMyAdmin/5.2.3/phpMyAdmin-5.2.3-all-languages.tar.gz |
| Adminer | 6.1.2 | Apache-2.0 or GPL-2.0 | https://github.com/vrana/adminer/archive/refs/tags/v6.1.2.tar.gz |
| MariaDB Server | 11.8.9 | GPL-2.0 | https://archive.mariadb.org/mariadb-11.8.9/source/mariadb-11.8.9.tar.gz |
| PowerDNS Authoritative Server | 5.1.5 | GPL-2.0 | https://downloads.powerdns.com/releases/pdns-5.1.5.tar.bz2 |
| Checkmk agent | v2.5.0p17 | GPL-2.0 | https://github.com/Checkmk/checkmk/archive/refs/tags/v2.5.0p17.tar.gz |

### Debian and Ubuntu packages

Each package is built from the source package named here. The address is the source package's page, which lists the source files (Ubuntu), or the vendor's source archive.

| package | version | licence marks | source package | source version | where to get the source |
|---|---|---|---|---|---|
| acl | 2.3.2-1build1.1 | GPL LGPL | acl | 2.3.2-1build1.1 | https://launchpad.net/ubuntu/+source/acl/2.3.2-1build1.1 |
| adduser | 3.137ubuntu1 | GPL | adduser | 3.137ubuntu1 | https://launchpad.net/ubuntu/+source/adduser/3.137ubuntu1 |
| apache2 | 2.4.58-1ubuntu8.19 | GPL | apache2 | 2.4.58-1ubuntu8.19 | https://launchpad.net/ubuntu/+source/apache2/2.4.58-1ubuntu8.19 |
| apache2-bin | 2.4.58-1ubuntu8.19 | GPL | apache2 | 2.4.58-1ubuntu8.19 | https://launchpad.net/ubuntu/+source/apache2/2.4.58-1ubuntu8.19 |
| apache2-data | 2.4.58-1ubuntu8.19 | GPL | apache2 | 2.4.58-1ubuntu8.19 | https://launchpad.net/ubuntu/+source/apache2/2.4.58-1ubuntu8.19 |
| apache2-suexec-custom | 2.4.58-1ubuntu8.19 | GPL | apache2 | 2.4.58-1ubuntu8.19 | https://launchpad.net/ubuntu/+source/apache2/2.4.58-1ubuntu8.19 |
| apache2-utils | 2.4.58-1ubuntu8.19 | GPL | apache2 | 2.4.58-1ubuntu8.19 | https://launchpad.net/ubuntu/+source/apache2/2.4.58-1ubuntu8.19 |
| appstream | 1.0.2-1build6 | GPL LGPL | appstream | 1.0.2-1build6 | https://launchpad.net/ubuntu/+source/appstream/1.0.2-1build6 |
| apt | 2.8.3 | GPL | apt | 2.8.3 | https://launchpad.net/ubuntu/+source/apt/2.8.3 |
| base-passwd | 3.6.3build1 | GPL | base-passwd | 3.6.3build1 | https://launchpad.net/ubuntu/+source/base-passwd/3.6.3build1 |
| bash | 5.2.21-2ubuntu4 | GPL | bash | 5.2.21-2ubuntu4 | https://launchpad.net/ubuntu/+source/bash/5.2.21-2ubuntu4 |
| binutils | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| binutils-common | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| binutils-x86-64-linux-gnu | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| bsdutils | 1:2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| build-essential | 12.10ubuntu1 | GPL | build-essential | 12.10ubuntu1 | https://launchpad.net/ubuntu/+source/build-essential/12.10ubuntu1 |
| bzip2 | 1.0.8-5.1ubuntu0.1 | GPL | bzip2 | 1.0.8-5.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/bzip2/1.0.8-5.1ubuntu0.1 |
| ca-certificates | 20260816ubuntu0.24.04.2 | GPL | ca-certificates | 20260816ubuntu0.24.04.2 | https://launchpad.net/ubuntu/+source/ca-certificates/20260816ubuntu0.24.04.2 |
| ca-certificates-java | 20240118ubuntu0.24.04.2 | GPL | ca-certificates-java | 20240118ubuntu0.24.04.2 | https://launchpad.net/ubuntu/+source/ca-certificates-java/20240118ubuntu0.24.04.2 |
| clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| clamav-base | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| clamav-daemon | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| clamav-freshclam | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| clamdscan | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| coreutils | 9.4-3ubuntu6.3 | GPL | coreutils | 9.4-3ubuntu6.3 | https://launchpad.net/ubuntu/+source/coreutils/9.4-3ubuntu6.3 |
| cpanminus | 1.7047-1 | GPL | cpanminus | 1.7047-1 | https://launchpad.net/ubuntu/+source/cpanminus/1.7047-1 |
| cpio | 2.15+dfsg-1ubuntu2.1 | GPL LGPL | cpio | 2.15+dfsg-1ubuntu2.1 | https://launchpad.net/ubuntu/+source/cpio/2.15+dfsg-1ubuntu2.1 |
| cpp | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| cpp-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| cron | 3.0pl1-184ubuntu2 | GPL | cron | 3.0pl1-184ubuntu2 | https://launchpad.net/ubuntu/+source/cron/3.0pl1-184ubuntu2 |
| cron-daemon-common | 3.0pl1-184ubuntu2 | GPL | cron | 3.0pl1-184ubuntu2 | https://launchpad.net/ubuntu/+source/cron/3.0pl1-184ubuntu2 |
| curl | 8.5.0-2ubuntu10.16 | GPL | curl | 8.5.0-2ubuntu10.16 | https://launchpad.net/ubuntu/+source/curl/8.5.0-2ubuntu10.16 |
| dash | 0.5.12-6ubuntu5 | GPL | dash | 0.5.12-6ubuntu5 | https://launchpad.net/ubuntu/+source/dash/0.5.12-6ubuntu5 |
| dbus | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| dbus-bin | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| dbus-daemon | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| dbus-session-bus-common | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| dbus-system-bus-common | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| debianutils | 5.17build1 | GPL | debianutils | 5.17build1 | https://launchpad.net/ubuntu/+source/debianutils/5.17build1 |
| diffutils | 1:3.10-1ubuntu0.1 | GPL LGPL | diffutils | 1:3.10-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/diffutils/1:3.10-1ubuntu0.1 |
| dirmngr | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| dpkg | 1.22.6ubuntu6.6 | GPL | dpkg | 1.22.6ubuntu6.6 | https://launchpad.net/ubuntu/+source/dpkg/1.22.6ubuntu6.6 |
| dpkg-dev | 1.22.6ubuntu6.6 | GPL | dpkg | 1.22.6ubuntu6.6 | https://launchpad.net/ubuntu/+source/dpkg/1.22.6ubuntu6.6 |
| e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | GPL LGPL | e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | https://launchpad.net/ubuntu/+source/e2fsprogs/1.47.0-2.4~exp1ubuntu4.1 |
| fail2ban | 1.0.2-3ubuntu0.1 | GPL | fail2ban | 1.0.2-3ubuntu0.1 | https://launchpad.net/ubuntu/+source/fail2ban/1.0.2-3ubuntu0.1 |
| fakeroot | 1.33-1 | GPL | fakeroot | 1.33-1 | https://launchpad.net/ubuntu/+source/fakeroot/1.33-1 |
| findutils | 4.9.0-5build1 | GPL LGPL | findutils | 4.9.0-5build1 | https://launchpad.net/ubuntu/+source/findutils/4.9.0-5build1 |
| fonts-dejavu-core | 2.37-8 | GPL | fonts-dejavu | 2.37-8 | https://launchpad.net/ubuntu/+source/fonts-dejavu/2.37-8 |
| fonts-dejavu-mono | 2.37-8 | GPL | fonts-dejavu | 2.37-8 | https://launchpad.net/ubuntu/+source/fonts-dejavu/2.37-8 |
| g++ | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| g++-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| galera-4 | 26.4.27-ubu2404 | GPL limits | galera-4 | 26.4.27-ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| gawk | 1:5.2.1-2ubuntu0.1 | GPL | gawk | 1:5.2.1-2ubuntu0.1 | https://launchpad.net/ubuntu/+source/gawk/1:5.2.1-2ubuntu0.1 |
| gcc | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| gcc-x86-64-linux-gnu | 4:13.2.0-7ubuntu1 | GPL | gcc-defaults | 1.214ubuntu1 | https://launchpad.net/ubuntu/+source/gcc-defaults/1.214ubuntu1 |
| gir1.2-girepository-2.0 | 1.80.1-1 | GPL LGPL limits | gobject-introspection | 1.80.1-1 | https://launchpad.net/ubuntu/+source/gobject-introspection/1.80.1-1 |
| gir1.2-glib-2.0 | 2.80.0-6ubuntu3.10 | GPL LGPL limits | glib2.0 | 2.80.0-6ubuntu3.10 | https://launchpad.net/ubuntu/+source/glib2.0/2.80.0-6ubuntu3.10 |
| gir1.2-packagekitglib-1.0 | 1.2.8-2ubuntu1.5 | GPL LGPL | packagekit | 1.2.8-2ubuntu1.5 | https://launchpad.net/ubuntu/+source/packagekit/1.2.8-2ubuntu1.5 |
| git | 1:2.43.0-1ubuntu7.4 | GPL LGPL | git | 1:2.43.0-1ubuntu7.4 | https://launchpad.net/ubuntu/+source/git/1:2.43.0-1ubuntu7.4 |
| git-man | 1:2.43.0-1ubuntu7.4 | GPL LGPL | git | 1:2.43.0-1ubuntu7.4 | https://launchpad.net/ubuntu/+source/git/1:2.43.0-1ubuntu7.4 |
| gnupg | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| gnupg-utils | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| goaccess | 1:1.8.1-1build3 | GPL | goaccess | 1:1.8.1-1build3 | https://launchpad.net/ubuntu/+source/goaccess/1:1.8.1-1build3 |
| gpg | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| gpg-agent | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| gpgconf | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| gpgsm | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| gpgv | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| grep | 3.11-4build1 | GPL | grep | 3.11-4build1 | https://launchpad.net/ubuntu/+source/grep/3.11-4build1 |
| gzip | 1.12-1ubuntu3.2 | GPL | gzip | 1.12-1ubuntu3.2 | https://launchpad.net/ubuntu/+source/gzip/1.12-1ubuntu3.2 |
| hostname | 3.23+nmu2ubuntu2 | GPL | hostname | 3.23+nmu2ubuntu2 | https://launchpad.net/ubuntu/+source/hostname/3.23+nmu2ubuntu2 |
| icu-devtools | 74.2-1ubuntu3.1 | GPL | icu | 74.2-1ubuntu3.1 | https://launchpad.net/ubuntu/+source/icu/74.2-1ubuntu3.1 |
| imagemagick-6-common | 8:6.9.12.98+dfsg1-5.2build2 | GPL LGPL | imagemagick | 8:6.9.12.98+dfsg1-5.2build2 | https://launchpad.net/ubuntu/+source/imagemagick/8:6.9.12.98+dfsg1-5.2build2 |
| init-system-helpers | 1.66ubuntu1 | GPL | init-system-helpers | 1.66ubuntu1 | https://launchpad.net/ubuntu/+source/init-system-helpers/1.66ubuntu1 |
| iproute2 | 6.1.0-1ubuntu6.4 | GPL | iproute2 | 6.1.0-1ubuntu6.4 | https://launchpad.net/ubuntu/+source/iproute2/6.1.0-1ubuntu6.4 |
| iputils-ping | 3:20240117-1ubuntu0.1 | GPL | iputils | 3:20240117-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/iputils/3:20240117-1ubuntu0.1 |
| iputils-tracepath | 3:20240117-1ubuntu0.1 | GPL | iputils | 3:20240117-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/iputils/3:20240117-1ubuntu0.1 |
| iso-codes | 4.16.0-1 | LGPL | iso-codes | 4.16.0-1 | https://launchpad.net/ubuntu/+source/iso-codes/4.16.0-1 |
| java-common | 0.75+exp1 | GPL | java-common | 0.75+exp1 | https://launchpad.net/ubuntu/+source/java-common/0.75+exp1 |
| keyboxd | 2.4.4-2ubuntu17.6 | GPL LGPL | gnupg2 | 2.4.4-2ubuntu17.6 | https://launchpad.net/ubuntu/+source/gnupg2/2.4.4-2ubuntu17.6 |
| ldap-utils | 2.6.10+dfsg-0ubuntu0.24.04.1 | GPL | openldap | 2.6.10+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/openldap/2.6.10+dfsg-0ubuntu0.24.04.1 |
| less | 590-2ubuntu2.1 | GPL | less | 590-2ubuntu2.1 | https://launchpad.net/ubuntu/+source/less/590-2ubuntu2.1 |
| libacl1 | 2.3.2-1build1.1 | GPL LGPL | acl | 2.3.2-1build1.1 | https://launchpad.net/ubuntu/+source/acl/2.3.2-1build1.1 |
| libaio1t64 | 0.3.113-6build1.1 | LGPL | libaio | 0.3.113-6build1.1 | https://launchpad.net/ubuntu/+source/libaio/0.3.113-6build1.1 |
| libalgorithm-diff-perl | 1.201-1 | GPL | libalgorithm-diff-perl | 1.201-1 | https://launchpad.net/ubuntu/+source/libalgorithm-diff-perl/1.201-1 |
| libalgorithm-diff-xs-perl | 0.04-8build3 | GPL | libalgorithm-diff-xs-perl | 0.04-8build3 | https://launchpad.net/ubuntu/+source/libalgorithm-diff-xs-perl/0.04-8build3 |
| libalgorithm-merge-perl | 0.08-5 | GPL | libalgorithm-merge-perl | 0.08-5 | https://launchpad.net/ubuntu/+source/libalgorithm-merge-perl/0.08-5 |
| libapparmor1 | 4.0.1really4.0.1-0ubuntu0.24.04.9 | GPL LGPL | apparmor | 4.0.1really4.0.1-0ubuntu0.24.04.9 | https://launchpad.net/ubuntu/+source/apparmor/4.0.1really4.0.1-0ubuntu0.24.04.9 |
| libappstream5 | 1.0.2-1build6 | GPL LGPL | appstream | 1.0.2-1build6 | https://launchpad.net/ubuntu/+source/appstream/1.0.2-1build6 |
| libapt-pkg6.0t64 | 2.8.3 | GPL | apt | 2.8.3 | https://launchpad.net/ubuntu/+source/apt/2.8.3 |
| libassuan0 | 2.5.6-1build1 | GPL LGPL | libassuan | 2.5.6-1build1 | https://launchpad.net/ubuntu/+source/libassuan/2.5.6-1build1 |
| libattr1 | 1:2.5.2-1ubuntu0.1 | GPL LGPL | attr | 1:2.5.2-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/attr/1:2.5.2-1ubuntu0.1 |
| libaudit-common | 1:3.1.2-2.1ubuntu0.1 | GPL LGPL | audit | 1:3.1.2-2.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/audit/1:3.1.2-2.1ubuntu0.1 |
| libaudit1 | 1:3.1.2-2.1ubuntu0.1 | GPL LGPL | audit | 1:3.1.2-2.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/audit/1:3.1.2-2.1ubuntu0.1 |
| libbinutils | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| libblkid1 | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| libbpf1 | 1:1.3.0-2build2 | GPL LGPL | libbpf | 1.3.0-2build2 | https://launchpad.net/ubuntu/+source/libbpf/1.3.0-2build2 |
| libbz2-1.0 | 1.0.8-5.1ubuntu0.1 | GPL | bzip2 | 1.0.8-5.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/bzip2/1.0.8-5.1ubuntu0.1 |
| libcap-ng0 | 0.8.4-2build2 | GPL LGPL | libcap-ng | 0.8.4-2build2 | https://launchpad.net/ubuntu/+source/libcap-ng/0.8.4-2build2 |
| libcap2 | 1:2.66-5ubuntu2.4 | GPL | libcap2 | 1:2.66-5ubuntu2.4 | https://launchpad.net/ubuntu/+source/libcap2/1:2.66-5ubuntu2.4 |
| libcap2-bin | 1:2.66-5ubuntu2.4 | GPL | libcap2 | 1:2.66-5ubuntu2.4 | https://launchpad.net/ubuntu/+source/libcap2/1:2.66-5ubuntu2.4 |
| libclamav12 | 1.5.4+dfsg-0ubuntu0.24.04.1 | GPL LGPL | clamav | 1.5.4+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/clamav/1.5.4+dfsg-0ubuntu0.24.04.1 |
| libcom-err2 | 1.47.0-2.4~exp1ubuntu4.1 | GPL LGPL | e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | https://launchpad.net/ubuntu/+source/e2fsprogs/1.47.0-2.4~exp1ubuntu4.1 |
| libconfig-inifiles-perl | 3.000003-2ubuntu0.1 | GPL | libconfig-inifiles-perl | 3.000003-2ubuntu0.1 | https://launchpad.net/ubuntu/+source/libconfig-inifiles-perl/3.000003-2ubuntu0.1 |
| libcpan-distnameinfo-perl | 0.12-3 | GPL | libcpan-distnameinfo-perl | 0.12-3 | https://launchpad.net/ubuntu/+source/libcpan-distnameinfo-perl/0.12-3 |
| libcpan-meta-check-perl | 0.017-1 | GPL | libcpan-meta-check-perl | 0.017-1 | https://launchpad.net/ubuntu/+source/libcpan-meta-check-perl/0.017-1 |
| libcryptsetup12 | 2:2.7.0-1ubuntu4.2 | GPL LGPL | cryptsetup | 2:2.7.0-1ubuntu4.2 | https://launchpad.net/ubuntu/+source/cryptsetup/2:2.7.0-1ubuntu4.2 |
| libctf-nobfd0 | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| libctf0 | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| libcurl3t64-gnutls | 8.5.0-2ubuntu10.16 | GPL | curl | 8.5.0-2ubuntu10.16 | https://launchpad.net/ubuntu/+source/curl/8.5.0-2ubuntu10.16 |
| libcurl4t64 | 8.5.0-2ubuntu10.16 | GPL | curl | 8.5.0-2ubuntu10.16 | https://launchpad.net/ubuntu/+source/curl/8.5.0-2ubuntu10.16 |
| libdb5.3t64 | 5.3.28+dfsg2-7 | GPL | db5.3 | 5.3.28+dfsg2-7 | https://launchpad.net/ubuntu/+source/db5.3/5.3.28+dfsg2-7 |
| libdbd-mysql-perl | 4.052-1ubuntu3 | GPL | libdbd-mysql-perl | 4.052-1ubuntu3 | https://launchpad.net/ubuntu/+source/libdbd-mysql-perl/4.052-1ubuntu3 |
| libdbi-perl | 1.643-4ubuntu0.4 | GPL | libdbi-perl | 1.643-4ubuntu0.4 | https://launchpad.net/ubuntu/+source/libdbi-perl/1.643-4ubuntu0.4 |
| libdbus-1-3 | 1.14.10-4ubuntu4.1 | GPL LGPL | dbus | 1.14.10-4ubuntu4.1 | https://launchpad.net/ubuntu/+source/dbus/1.14.10-4ubuntu4.1 |
| libdebconfclient0 | 0.271ubuntu3 | GPL | cdebconf | 0.271ubuntu3 | https://launchpad.net/ubuntu/+source/cdebconf/0.271ubuntu3 |
| libdevmapper1.02.1 | 2:1.02.185-3ubuntu3.2 | GPL LGPL | lvm2 | 2.03.16-3ubuntu3.2 | https://launchpad.net/ubuntu/+source/lvm2/2.03.16-3ubuntu3.2 |
| libdpkg-perl | 1.22.6ubuntu6.6 | GPL | dpkg | 1.22.6ubuntu6.6 | https://launchpad.net/ubuntu/+source/dpkg/1.22.6ubuntu6.6 |
| libdw1t64 | 0.190-1.1ubuntu0.1 | GPL LGPL | elfutils | 0.190-1.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/elfutils/0.190-1.1ubuntu0.1 |
| libelf1t64 | 0.190-1.1ubuntu0.1 | GPL LGPL | elfutils | 0.190-1.1ubuntu0.1 | https://launchpad.net/ubuntu/+source/elfutils/0.190-1.1ubuntu0.1 |
| liberror-perl | 0.17029-2 | GPL | liberror-perl | 0.17029-2 | https://launchpad.net/ubuntu/+source/liberror-perl/0.17029-2 |
| libext2fs2t64 | 1.47.0-2.4~exp1ubuntu4.1 | GPL LGPL | e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | https://launchpad.net/ubuntu/+source/e2fsprogs/1.47.0-2.4~exp1ubuntu4.1 |
| libfakeroot | 1.33-1 | GPL | fakeroot | 1.33-1 | https://launchpad.net/ubuntu/+source/fakeroot/1.33-1 |
| libfdisk1 | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| libffi-dev | 3.4.6-1build1 | GPL LGPL | libffi | 3.4.6-1build1 | https://launchpad.net/ubuntu/+source/libffi/3.4.6-1build1 |
| libffi8 | 3.4.6-1build1 | GPL LGPL | libffi | 3.4.6-1build1 | https://launchpad.net/ubuntu/+source/libffi/3.4.6-1build1 |
| libfftw3-double3 | 3.3.10-1ubuntu3 | GPL | fftw3 | 3.3.10-1ubuntu3 | https://launchpad.net/ubuntu/+source/fftw3/3.3.10-1ubuntu3 |
| libfile-fcntllock-perl | 0.22-4ubuntu5 | GPL | libfile-fcntllock-perl | 0.22-4ubuntu5 | https://launchpad.net/ubuntu/+source/libfile-fcntllock-perl/0.22-4ubuntu5 |
| libfreetype6 | 2.13.2+dfsg-1ubuntu0.2 | GPL | freetype | 2.13.2+dfsg-1ubuntu0.2 | https://launchpad.net/ubuntu/+source/freetype/2.13.2+dfsg-1ubuntu0.2 |
| libfuzzy2 | 2.14.1+git20180629.57fcfff-3 | GPL | ssdeep | 2.14.1+git20180629.57fcfff-3 | https://launchpad.net/ubuntu/+source/ssdeep/2.14.1+git20180629.57fcfff-3 |
| libgcrypt20 | 1.10.3-2ubuntu0.2 | LGPL | libgcrypt20 | 1.10.3-2ubuntu0.2 | https://launchpad.net/ubuntu/+source/libgcrypt20/1.10.3-2ubuntu0.2 |
| libgd3 | 2.3.3-9ubuntu5 | GPL | libgd2 | 2.3.3-9ubuntu5 | https://launchpad.net/ubuntu/+source/libgd2/2.3.3-9ubuntu5 |
| libgdbm-compat4t64 | 1.23-5.1build1 | GPL | gdbm | 1.23-5.1build1 | https://launchpad.net/ubuntu/+source/gdbm/1.23-5.1build1 |
| libgdbm6t64 | 1.23-5.1build1 | GPL | gdbm | 1.23-5.1build1 | https://launchpad.net/ubuntu/+source/gdbm/1.23-5.1build1 |
| libgeoip1t64 | 1.6.12-11.1build1 | LGPL | geoip | 1.6.12-11.1build1 | https://launchpad.net/ubuntu/+source/geoip/1.6.12-11.1build1 |
| libgirepository-1.0-1 | 1.80.1-1 | GPL LGPL limits | gobject-introspection | 1.80.1-1 | https://launchpad.net/ubuntu/+source/gobject-introspection/1.80.1-1 |
| libglib2.0-0t64 | 2.80.0-6ubuntu3.10 | GPL LGPL limits | glib2.0 | 2.80.0-6ubuntu3.10 | https://launchpad.net/ubuntu/+source/glib2.0/2.80.0-6ubuntu3.10 |
| libglib2.0-bin | 2.80.0-6ubuntu3.10 | GPL LGPL limits | glib2.0 | 2.80.0-6ubuntu3.10 | https://launchpad.net/ubuntu/+source/glib2.0/2.80.0-6ubuntu3.10 |
| libglib2.0-data | 2.80.0-6ubuntu3.10 | GPL LGPL limits | glib2.0 | 2.80.0-6ubuntu3.10 | https://launchpad.net/ubuntu/+source/glib2.0/2.80.0-6ubuntu3.10 |
| libgmp-dev | 2:6.3.0+dfsg-2ubuntu6.1 | GPL LGPL | gmp | 2:6.3.0+dfsg-2ubuntu6.1 | https://launchpad.net/ubuntu/+source/gmp/2:6.3.0+dfsg-2ubuntu6.1 |
| libgmp10 | 2:6.3.0+dfsg-2ubuntu6.1 | GPL LGPL | gmp | 2:6.3.0+dfsg-2ubuntu6.1 | https://launchpad.net/ubuntu/+source/gmp/2:6.3.0+dfsg-2ubuntu6.1 |
| libgmpxx4ldbl | 2:6.3.0+dfsg-2ubuntu6.1 | GPL LGPL | gmp | 2:6.3.0+dfsg-2ubuntu6.1 | https://launchpad.net/ubuntu/+source/gmp/2:6.3.0+dfsg-2ubuntu6.1 |
| libgnutls30t64 | 3.8.3-1.1ubuntu3.6 | GPL LGPL | gnutls28 | 3.8.3-1.1ubuntu3.6 | https://launchpad.net/ubuntu/+source/gnutls28/3.8.3-1.1ubuntu3.6 |
| libgpg-error0 | 1.47-3build2.1 | GPL LGPL | libgpg-error | 1.47-3build2.1 | https://launchpad.net/ubuntu/+source/libgpg-error/1.47-3build2.1 |
| libgpm2 | 1.20.7-11 | GPL | gpm | 1.20.7-11 | https://launchpad.net/ubuntu/+source/gpm/1.20.7-11 |
| libgprofng0 | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| libgstreamer1.0-0 | 1.24.2-1ubuntu0.1 | GPL LGPL | gstreamer1.0 | 1.24.2-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/gstreamer1.0/1.24.2-1ubuntu0.1 |
| libheif-plugin-aomdec | 1.17.6-1ubuntu4.9 | GPL LGPL | libheif | 1.17.6-1ubuntu4.9 | https://launchpad.net/ubuntu/+source/libheif/1.17.6-1ubuntu4.9 |
| libheif-plugin-aomenc | 1.17.6-1ubuntu4.9 | GPL LGPL | libheif | 1.17.6-1ubuntu4.9 | https://launchpad.net/ubuntu/+source/libheif/1.17.6-1ubuntu4.9 |
| libheif1 | 1.17.6-1ubuntu4.9 | GPL LGPL | libheif | 1.17.6-1ubuntu4.9 | https://launchpad.net/ubuntu/+source/libheif/1.17.6-1ubuntu4.9 |
| libhogweed6t64 | 3.9.1-2.2build1.1 | GPL LGPL | nettle | 3.9.1-2.2build1.1 | https://launchpad.net/ubuntu/+source/nettle/3.9.1-2.2build1.1 |
| libicu-dev | 74.2-1ubuntu3.1 | GPL | icu | 74.2-1ubuntu3.1 | https://launchpad.net/ubuntu/+source/icu/74.2-1ubuntu3.1 |
| libicu74 | 74.2-1ubuntu3.1 | GPL | icu | 74.2-1ubuntu3.1 | https://launchpad.net/ubuntu/+source/icu/74.2-1ubuntu3.1 |
| libidn2-0 | 2.3.7-2build1.1 | GPL LGPL | libidn2 | 2.3.7-2build1.1 | https://launchpad.net/ubuntu/+source/libidn2/2.3.7-2build1.1 |
| libisl23 | 0.26-3build1.1 | LGPL | isl | 0.26-3build1.1 | https://launchpad.net/ubuntu/+source/isl/0.26-3build1.1 |
| libjbig0 | 2.1-6.1ubuntu2 | GPL | jbigkit | 2.1-6.1ubuntu2 | https://launchpad.net/ubuntu/+source/jbigkit/2.1-6.1ubuntu2 |
| libjpeg8 | 8c-2ubuntu11 | LGPL | libjpeg8-empty | 8c-2ubuntu11 | https://launchpad.net/ubuntu/+source/libjpeg8-empty/8c-2ubuntu11 |
| libjson-perl | 4.10000-1 | GPL | libjson-perl | 4.10000-1 | https://launchpad.net/ubuntu/+source/libjson-perl/4.10000-1 |
| libkeyutils1 | 1.6.3-3build1 | GPL LGPL | keyutils | 1.6.3-3build1 | https://launchpad.net/ubuntu/+source/keyutils/1.6.3-3build1 |
| libkmod2 | 31+20240202-2ubuntu7.2 | GPL LGPL | kmod | 31+20240202-2ubuntu7.2 | https://launchpad.net/ubuntu/+source/kmod/31+20240202-2ubuntu7.2 |
| libksba8 | 1.6.6-1build1 | LGPL | libksba | 1.6.6-1build1 | https://launchpad.net/ubuntu/+source/libksba/1.6.6-1build1 |
| liblcms2-2 | 2.14-2ubuntu0.1 | GPL | lcms2 | 2.14-2ubuntu0.1 | https://launchpad.net/ubuntu/+source/lcms2/2.14-2ubuntu0.1 |
| libldap2 | 2.6.10+dfsg-0ubuntu0.24.04.1 | GPL | openldap | 2.6.10+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/openldap/2.6.10+dfsg-0ubuntu0.24.04.1 |
| liblocal-lib-perl | 2.000029-1 | GPL | liblocal-lib-perl | 2.000029-1 | https://launchpad.net/ubuntu/+source/liblocal-lib-perl/2.000029-1 |
| liblocale-gettext-perl | 1.07-6ubuntu5 | GPL | liblocale-gettext-perl | 1.07-6ubuntu5 | https://launchpad.net/ubuntu/+source/liblocale-gettext-perl/1.07-6ubuntu5 |
| liblockfile-bin | 1.17-1build3 | GPL LGPL | liblockfile | 1.17-1build3 | https://launchpad.net/ubuntu/+source/liblockfile/1.17-1build3 |
| liblockfile1 | 1.17-1build3 | GPL LGPL | liblockfile | 1.17-1build3 | https://launchpad.net/ubuntu/+source/liblockfile/1.17-1build3 |
| liblqr-1-0 | 0.4.2-2.1build2 | GPL | liblqr | 0.4.2-2.1build2 | https://launchpad.net/ubuntu/+source/liblqr/0.4.2-2.1build2 |
| libltdl7 | 2.4.7-7build1 | GPL | libtool | 2.4.7-7build1 | https://launchpad.net/ubuntu/+source/libtool/2.4.7-7build1 |
| liblz4-1 | 1.9.4-1build1.1 | GPL | lz4 | 1.9.4-1build1.1 | https://launchpad.net/ubuntu/+source/lz4/1.9.4-1build1.1 |
| liblzf1 | 3.6-4 | GPL | liblzf | 3.6-4 | https://launchpad.net/ubuntu/+source/liblzf/3.6-4 |
| liblzma5 | 5.6.1+really5.4.5-1ubuntu0.3 | GPL LGPL | xz-utils | 5.6.1+really5.4.5-1ubuntu0.3 | https://launchpad.net/ubuntu/+source/xz-utils/5.6.1+really5.4.5-1ubuntu0.3 |
| liblzma5 | 5.6.1+really5.4.5-1ubuntu0.4 | GPL LGPL | xz-utils | 5.6.1+really5.4.5-1ubuntu0.4 | https://launchpad.net/ubuntu/+source/xz-utils/5.6.1+really5.4.5-1ubuntu0.4 |
| libmagickcore-6.q16-7t64 | 8:6.9.12.98+dfsg1-5.2build2 | GPL LGPL | imagemagick | 8:6.9.12.98+dfsg1-5.2build2 | https://launchpad.net/ubuntu/+source/imagemagick/8:6.9.12.98+dfsg1-5.2build2 |
| libmagickwand-6.q16-7t64 | 8:6.9.12.98+dfsg1-5.2build2 | GPL LGPL | imagemagick | 8:6.9.12.98+dfsg1-5.2build2 | https://launchpad.net/ubuntu/+source/imagemagick/8:6.9.12.98+dfsg1-5.2build2 |
| libmariadb-dev | 1:10.11.14-0ubuntu0.24.04.1 | GPL LGPL | mariadb | 1:10.11.14-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/mariadb/1:10.11.14-0ubuntu0.24.04.1 |
| libmariadb3 | 1:10.11.14-0ubuntu0.24.04.1 | GPL LGPL | mariadb | 1:10.11.14-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/mariadb/1:10.11.14-0ubuntu0.24.04.1 |
| libmariadb3 | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| libmaxminddb0 | 1.9.1-1build1 | GPL limits | libmaxminddb | 1.9.1-1build1 | https://launchpad.net/ubuntu/+source/libmaxminddb/1.9.1-1build1 |
| libmnl0 | 1.0.5-2build1 | GPL LGPL | libmnl | 1.0.5-2build1 | https://launchpad.net/ubuntu/+source/libmnl/1.0.5-2build1 |
| libmodsecurity-dev | 3.0.12-1.1build2 | GPL | modsecurity | 3.0.12-1.1build2 | https://launchpad.net/ubuntu/+source/modsecurity/3.0.12-1.1build2 |
| libmodsecurity3t64 | 3.0.12-1.1build2 | GPL | modsecurity | 3.0.12-1.1build2 | https://launchpad.net/ubuntu/+source/modsecurity/3.0.12-1.1build2 |
| libmodule-build-perl | 0.423400-2 | GPL | libmodule-build-perl | 0.423400-2 | https://launchpad.net/ubuntu/+source/libmodule-build-perl/0.423400-2 |
| libmodule-cpanfile-perl | 1.1004-2 | GPL | libmodule-cpanfile-perl | 1.1004-2 | https://launchpad.net/ubuntu/+source/libmodule-cpanfile-perl/1.1004-2 |
| libmount1 | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| libmpc3 | 1.3.1-1build1.1 | LGPL | mpclib3 | 1.3.1-1build1.1 | https://launchpad.net/ubuntu/+source/mpclib3/1.3.1-1build1.1 |
| libmpfr6 | 4.2.1-1build1.1 | LGPL | mpfr4 | 4.2.1-1build1.1 | https://launchpad.net/ubuntu/+source/mpfr4/4.2.1-1build1.1 |
| libmspack0t64 | 0.11-1.1ubuntu0.24.04.1 | LGPL | libmspack | 0.11-1.1ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/libmspack/0.11-1.1ubuntu0.24.04.1 |
| libmysqlclient21 | 8.0.46-0ubuntu0.24.04.5 | GPL LGPL | mysql-8.0 | 8.0.46-0ubuntu0.24.04.5 | https://launchpad.net/ubuntu/+source/mysql-8.0/8.0.46-0ubuntu0.24.04.5 |
| libnettle8t64 | 3.9.1-2.2build1.1 | GPL LGPL | nettle | 3.9.1-2.2build1.1 | https://launchpad.net/ubuntu/+source/nettle/3.9.1-2.2build1.1 |
| libnftables1 | 1.0.9-1ubuntu0.1 | GPL limits | nftables | 1.0.9-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/nftables/1.0.9-1ubuntu0.1 |
| libnftnl11 | 1.2.6-2build1 | GPL | libnftnl | 1.2.6-2build1 | https://launchpad.net/ubuntu/+source/libnftnl/1.2.6-2build1 |
| libnghttp2-14 | 1.59.0-1ubuntu0.4 | GPL | nghttp2 | 1.59.0-1ubuntu0.4 | https://launchpad.net/ubuntu/+source/nghttp2/1.59.0-1ubuntu0.4 |
| libnpth0t64 | 1.6-3.1build1 | LGPL | npth | 1.6-3.1build1 | https://launchpad.net/ubuntu/+source/npth/1.6-3.1build1 |
| libnsl2 | 1.3.0-3build3 | GPL LGPL | libnsl | 1.3.0-3build3 | https://launchpad.net/ubuntu/+source/libnsl/1.3.0-3build3 |
| libnuma1 | 2.0.18-1ubuntu0.24.04.1 | GPL | numactl | 2.0.18-1ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/numactl/2.0.18-1ubuntu0.24.04.1 |
| libodbc2 | 2.3.12-1ubuntu0.24.04.1 | GPL LGPL | unixodbc | 2.3.12-1ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/unixodbc/2.3.12-1ubuntu0.24.04.1 |
| libonig5 | 6.9.9-1build1 | GPL | libonig | 6.9.9-1build1 | https://launchpad.net/ubuntu/+source/libonig/6.9.9-1build1 |
| libp11-kit0 | 0.25.3-4ubuntu2.2 | GPL LGPL | p11-kit | 0.25.3-4ubuntu2.2 | https://launchpad.net/ubuntu/+source/p11-kit/0.25.3-4ubuntu2.2 |
| libpackagekit-glib2-18 | 1.2.8-2ubuntu1.5 | GPL LGPL | packagekit | 1.2.8-2ubuntu1.5 | https://launchpad.net/ubuntu/+source/packagekit/1.2.8-2ubuntu1.5 |
| libpam-modules | 1.5.3-5ubuntu5.7 | GPL LGPL | pam | 1.5.3-5ubuntu5.7 | https://launchpad.net/ubuntu/+source/pam/1.5.3-5ubuntu5.7 |
| libpam-modules-bin | 1.5.3-5ubuntu5.7 | GPL LGPL | pam | 1.5.3-5ubuntu5.7 | https://launchpad.net/ubuntu/+source/pam/1.5.3-5ubuntu5.7 |
| libpam-runtime | 1.5.3-5ubuntu5.7 | GPL LGPL | pam | 1.5.3-5ubuntu5.7 | https://launchpad.net/ubuntu/+source/pam/1.5.3-5ubuntu5.7 |
| libpam-systemd | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| libpam0g | 1.5.3-5ubuntu5.7 | GPL LGPL | pam | 1.5.3-5ubuntu5.7 | https://launchpad.net/ubuntu/+source/pam/1.5.3-5ubuntu5.7 |
| libparse-pmfile-perl | 0.45-1 | GPL | libparse-pmfile-perl | 0.45-1 | https://launchpad.net/ubuntu/+source/libparse-pmfile-perl/0.45-1 |
| libpcsclite1 | 2.0.3-1build1 | GPL | pcsc-lite | 2.0.3-1build1 | https://launchpad.net/ubuntu/+source/pcsc-lite/2.0.3-1build1 |
| libperl-dev | 5.38.2-3.2ubuntu0.7 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.7 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.7 |
| libperl5.38t64 | 5.38.2-3.2ubuntu0.7 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.7 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.7 |
| libpkgconf3 | 1.8.1-2build1 | GPL | pkgconf | 1.8.1-2build1 | https://launchpad.net/ubuntu/+source/pkgconf/1.8.1-2build1 |
| libpng16-16t64 | 1.6.43-5ubuntu0.7 | GPL | libpng1.6 | 1.6.43-5ubuntu0.7 | https://launchpad.net/ubuntu/+source/libpng1.6/1.6.43-5ubuntu0.7 |
| libpolkit-agent-1-0 | 124-2ubuntu1.24.04.4 | LGPL | policykit-1 | 124-2ubuntu1.24.04.4 | https://launchpad.net/ubuntu/+source/policykit-1/124-2ubuntu1.24.04.4 |
| libpolkit-gobject-1-0 | 124-2ubuntu1.24.04.4 | LGPL | policykit-1 | 124-2ubuntu1.24.04.4 | https://launchpad.net/ubuntu/+source/policykit-1/124-2ubuntu1.24.04.4 |
| libpopt0 | 1.19+dfsg-1build1 | GPL | popt | 1.19+dfsg-1build1 | https://launchpad.net/ubuntu/+source/popt/1.19+dfsg-1build1 |
| libproc2-0 | 2:4.0.4-4ubuntu3.3 | GPL LGPL | procps | 2:4.0.4-4ubuntu3.3 | https://launchpad.net/ubuntu/+source/procps/2:4.0.4-4ubuntu3.3 |
| libraw23t64 | 0.21.2-2.1ubuntu0.24.04.2 | GPL LGPL limits | libraw | 0.21.2-2.1ubuntu0.24.04.2 | https://launchpad.net/ubuntu/+source/libraw/0.21.2-2.1ubuntu0.24.04.2 |
| libreadline8t64 | 8.2-4build1 | GPL limits | readline | 8.2-4build1 | https://launchpad.net/ubuntu/+source/readline/8.2-4build1 |
| libsasl2-2 | 2.1.28+dfsg1-5ubuntu3.1 | GPL limits | cyrus-sasl2 | 2.1.28+dfsg1-5ubuntu3.1 | https://launchpad.net/ubuntu/+source/cyrus-sasl2/2.1.28+dfsg1-5ubuntu3.1 |
| libsasl2-modules | 2.1.28+dfsg1-5ubuntu3.1 | GPL limits | cyrus-sasl2 | 2.1.28+dfsg1-5ubuntu3.1 | https://launchpad.net/ubuntu/+source/cyrus-sasl2/2.1.28+dfsg1-5ubuntu3.1 |
| libsasl2-modules-db | 2.1.28+dfsg1-5ubuntu3.1 | GPL limits | cyrus-sasl2 | 2.1.28+dfsg1-5ubuntu3.1 | https://launchpad.net/ubuntu/+source/cyrus-sasl2/2.1.28+dfsg1-5ubuntu3.1 |
| libseccomp2 | 2.5.5-1ubuntu3.1 | LGPL | libseccomp | 2.5.5-1ubuntu3.1 | https://launchpad.net/ubuntu/+source/libseccomp/2.5.5-1ubuntu3.1 |
| libselinux1 | 3.5-2ubuntu2.1 | GPL | libselinux | 3.5-2ubuntu2.1 | https://launchpad.net/ubuntu/+source/libselinux/3.5-2ubuntu2.1 |
| libsemanage-common | 3.5-1build5 | GPL LGPL | libsemanage | 3.5-1build5 | https://launchpad.net/ubuntu/+source/libsemanage/3.5-1build5 |
| libsemanage2 | 3.5-1build5 | GPL LGPL | libsemanage | 3.5-1build5 | https://launchpad.net/ubuntu/+source/libsemanage/3.5-1build5 |
| libsepol2 | 3.5-2build1 | GPL LGPL | libsepol | 3.5-2build1 | https://launchpad.net/ubuntu/+source/libsepol/3.5-2build1 |
| libsframe1 | 2.42-4ubuntu2.10 | GPL | binutils | 2.42-4ubuntu2.10 | https://launchpad.net/ubuntu/+source/binutils/2.42-4ubuntu2.10 |
| libsigsegv2 | 2.14-1ubuntu2 | GPL | libsigsegv | 2.14-1ubuntu2 | https://launchpad.net/ubuntu/+source/libsigsegv/2.14-1ubuntu2 |
| libsmartcols1 | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| libsodium23 | 1.0.18-1ubuntu0.24.04.1 | GPL | libsodium | 1.0.18-1ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/libsodium/1.0.18-1ubuntu0.24.04.1 |
| libsqlite3-0 | 3.45.1-1ubuntu2.9 | GPL | sqlite3 | 3.45.1-1ubuntu2.9 | https://launchpad.net/ubuntu/+source/sqlite3/3.45.1-1ubuntu2.9 |
| libsqlite3-dev | 3.45.1-1ubuntu2.9 | GPL | sqlite3 | 3.45.1-1ubuntu2.9 | https://launchpad.net/ubuntu/+source/sqlite3/3.45.1-1ubuntu2.9 |
| libss2 | 1.47.0-2.4~exp1ubuntu4.1 | GPL LGPL | e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | https://launchpad.net/ubuntu/+source/e2fsprogs/1.47.0-2.4~exp1ubuntu4.1 |
| libssh-4 | 0.10.6-2ubuntu0.5 | LGPL | libssh | 0.10.6-2ubuntu0.5 | https://launchpad.net/ubuntu/+source/libssh/0.10.6-2ubuntu0.5 |
| libssl-dev | 3.0.13-0ubuntu3.16 | GPL | openssl | 3.0.13-0ubuntu3.16 | https://launchpad.net/ubuntu/+source/openssl/3.0.13-0ubuntu3.16 |
| libssl3t64 | 3.0.13-0ubuntu3.16 | GPL | openssl | 3.0.13-0ubuntu3.16 | https://launchpad.net/ubuntu/+source/openssl/3.0.13-0ubuntu3.16 |
| libstring-shellquote-perl | 1.04-3 | GPL | libstring-shellquote-perl | 1.04-3 | https://launchpad.net/ubuntu/+source/libstring-shellquote-perl/1.04-3 |
| libsystemd-shared | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| libsystemd0 | 255.4-1ubuntu8.17 | GPL LGPL | systemd | 255.4-1ubuntu8.17 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.17 |
| libsystemd0 | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| libtasn1-6 | 4.19.0-3ubuntu0.24.04.2 | LGPL | libtasn1-6 | 4.19.0-3ubuntu0.24.04.2 | https://launchpad.net/ubuntu/+source/libtasn1-6/4.19.0-3ubuntu0.24.04.2 |
| libterm-readkey-perl | 2.38-2build4 | GPL | libterm-readkey-perl | 2.38-2build4 | https://launchpad.net/ubuntu/+source/libterm-readkey-perl/2.38-2build4 |
| libtirpc-common | 1.3.4+ds-1.1build1 | GPL LGPL | libtirpc | 1.3.4+ds-1.1build1 | https://launchpad.net/ubuntu/+source/libtirpc/1.3.4+ds-1.1build1 |
| libtirpc3t64 | 1.3.4+ds-1.1build1 | GPL LGPL | libtirpc | 1.3.4+ds-1.1build1 | https://launchpad.net/ubuntu/+source/libtirpc/1.3.4+ds-1.1build1 |
| libudev1 | 255.4-1ubuntu8.17 | GPL LGPL | systemd | 255.4-1ubuntu8.17 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.17 |
| libudev1 | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| libunistring5 | 1.1-2build1.1 | GPL LGPL | libunistring | 1.1-2build1.1 | https://launchpad.net/ubuntu/+source/libunistring/1.1-2build1.1 |
| libunwind8 | 1.6.2-3build1.1 | GPL | libunwind | 1.6.2-3build1.1 | https://launchpad.net/ubuntu/+source/libunwind/1.6.2-3build1.1 |
| liburing2 | 2.5-1build1 | GPL LGPL | liburing | 2.5-1build1 | https://launchpad.net/ubuntu/+source/liburing/2.5-1build1 |
| libuuid1 | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| libuv1t64 | 1.48.0-1.1build1 | GPL limits | libuv1 | 1.48.0-1.1build1 | https://launchpad.net/ubuntu/+source/libuv1/1.48.0-1.1build1 |
| libwebsockets-evlib-uv | 4.3.3-1.1build3 | LGPL | libwebsockets | 4.3.3-1.1build3 | https://launchpad.net/ubuntu/+source/libwebsockets/4.3.3-1.1build3 |
| libwebsockets19t64 | 4.3.3-1.1build3 | LGPL | libwebsockets | 4.3.3-1.1build3 | https://launchpad.net/ubuntu/+source/libwebsockets/4.3.3-1.1build3 |
| libxmlb2 | 0.3.24-1~ubuntu0.24.04.1 | LGPL | libxmlb | 0.3.24-1~ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/libxmlb/0.3.24-1~ubuntu0.24.04.1 |
| libxtables12 | 1.8.10-3ubuntu2 | GPL | iptables | 1.8.10-3ubuntu2 | https://launchpad.net/ubuntu/+source/iptables/1.8.10-3ubuntu2 |
| libxxhash0 | 0.8.2-2build1 | GPL | xxhash | 0.8.2-2build1 | https://launchpad.net/ubuntu/+source/xxhash/0.8.2-2build1 |
| libzstd1 | 1.5.5+dfsg2-2build1.1 | GPL | libzstd | 1.5.5+dfsg2-2build1.1 | https://launchpad.net/ubuntu/+source/libzstd/1.5.5+dfsg2-2build1.1 |
| linux-libc-dev | 6.8.0-149.149 | GPL | linux | 6.8.0-149.149 | https://launchpad.net/ubuntu/+source/linux/6.8.0-149.149 |
| login | 1:4.13+dfsg1-4ubuntu3.2 | GPL | shadow | 1:4.13+dfsg1-4ubuntu3.2 | https://launchpad.net/ubuntu/+source/shadow/1:4.13+dfsg1-4ubuntu3.2 |
| logrotate | 3.21.0-2build1 | GPL | logrotate | 3.21.0-2build1 | https://launchpad.net/ubuntu/+source/logrotate/3.21.0-2build1 |
| logsave | 1.47.0-2.4~exp1ubuntu4.1 | GPL LGPL | e2fsprogs | 1.47.0-2.4~exp1ubuntu4.1 | https://launchpad.net/ubuntu/+source/e2fsprogs/1.47.0-2.4~exp1ubuntu4.1 |
| lsof | 4.95.0-1build3 | GPL LGPL | lsof | 4.95.0-1build3 | https://launchpad.net/ubuntu/+source/lsof/4.95.0-1build3 |
| lto-disabled-list | 47 | GPL | lto-disabled-list | 47 | https://launchpad.net/ubuntu/+source/lto-disabled-list/47 |
| make | 4.3-4.1build2 | GPL | make-dfsg | 4.3-4.1build2 | https://launchpad.net/ubuntu/+source/make-dfsg/4.3-4.1build2 |
| manpages | 6.7-2 | GPL LGPL | manpages | 6.7-2 | https://launchpad.net/ubuntu/+source/manpages/6.7-2 |
| manpages-dev | 6.7-2 | GPL LGPL | manpages | 6.7-2 | https://launchpad.net/ubuntu/+source/manpages/6.7-2 |
| mariadb-backup | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mariadb-client | 1:10.11.14-0ubuntu0.24.04.1 | GPL LGPL | mariadb | 1:10.11.14-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/mariadb/1:10.11.14-0ubuntu0.24.04.1 |
| mariadb-client | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mariadb-client-core | 1:10.11.14-0ubuntu0.24.04.1 | GPL LGPL | mariadb | 1:10.11.14-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/mariadb/1:10.11.14-0ubuntu0.24.04.1 |
| mariadb-client-core | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mariadb-common | 1:10.11.14-0ubuntu0.24.04.1 | GPL LGPL | mariadb | 1:10.11.14-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/mariadb/1:10.11.14-0ubuntu0.24.04.1 |
| mariadb-common | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mariadb-server | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mariadb-server-core | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mawk | 1.3.4.20240123-1build1 | GPL limits | mawk | 1.3.4.20240123-1build1 | https://launchpad.net/ubuntu/+source/mawk/1.3.4.20240123-1build1 |
| modsecurity-crs | 3.3.5-2 | GPL | modsecurity-crs | 3.3.5-2 | https://launchpad.net/ubuntu/+source/modsecurity-crs/3.3.5-2 |
| mount | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| mysql-common | 1:11.8.9+maria~ubu2404 | GPL | mariadb | 1:11.8.9+maria~ubu2404 | https://archive.mariadb.org/mariadb-11.8.9/source/ |
| mysql-common | 5.8+1.1.0build1 | GPL | mysql-defaults | 1.1.0build1 | https://launchpad.net/ubuntu/+source/mysql-defaults/1.1.0build1 |
| nano | 7.2-2ubuntu0.2 | GPL | nano | 7.2-2ubuntu0.2 | https://launchpad.net/ubuntu/+source/nano/7.2-2ubuntu0.2 |
| netbase | 6.4 | GPL | netbase | 6.4 | https://launchpad.net/ubuntu/+source/netbase/6.4 |
| nftables | 1.0.9-1ubuntu0.1 | GPL limits | nftables | 1.0.9-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/nftables/1.0.9-1ubuntu0.1 |
| nginx | 1.24.0-2ubuntu7.19 | GPL | nginx | 1.24.0-2ubuntu7.19 | https://launchpad.net/ubuntu/+source/nginx/1.24.0-2ubuntu7.19 |
| nginx-common | 1.24.0-2ubuntu7.19 | GPL | nginx | 1.24.0-2ubuntu7.19 | https://launchpad.net/ubuntu/+source/nginx/1.24.0-2ubuntu7.19 |
| openjdk-17-jre-headless | 17.0.21.0.3+1-1~24.04.1 | GPL LGPL | openjdk-17 | 17.0.21.0.3+1-1~24.04.1 | https://launchpad.net/ubuntu/+source/openjdk-17/17.0.21.0.3+1-1~24.04.1 |
| openjdk-21-jre-headless | 21.0.13.0.3+1-1~24.04.1 | GPL LGPL | openjdk-21 | 21.0.13.0.3+1-1~24.04.1 | https://launchpad.net/ubuntu/+source/openjdk-21/21.0.13.0.3+1-1~24.04.1 |
| openjdk-25-jre-headless | 25.0.5.0.3+1-1~24.04.1 | GPL LGPL | openjdk-25 | 25.0.5.0.3+1-1~24.04.1 | https://launchpad.net/ubuntu/+source/openjdk-25/25.0.5.0.3+1-1~24.04.1 |
| openssl | 3.0.13-0ubuntu3.16 | GPL | openssl | 3.0.13-0ubuntu3.16 | https://launchpad.net/ubuntu/+source/openssl/3.0.13-0ubuntu3.16 |
| packagekit | 1.2.8-2ubuntu1.5 | GPL LGPL | packagekit | 1.2.8-2ubuntu1.5 | https://launchpad.net/ubuntu/+source/packagekit/1.2.8-2ubuntu1.5 |
| packagekit-tools | 1.2.8-2ubuntu1.5 | GPL LGPL | packagekit | 1.2.8-2ubuntu1.5 | https://launchpad.net/ubuntu/+source/packagekit/1.2.8-2ubuntu1.5 |
| passwd | 1:4.13+dfsg1-4ubuntu3.2 | GPL | shadow | 1:4.13+dfsg1-4ubuntu3.2 | https://launchpad.net/ubuntu/+source/shadow/1:4.13+dfsg1-4ubuntu3.2 |
| patch | 2.7.6-7build3 | GPL | patch | 2.7.6-7build3 | https://launchpad.net/ubuntu/+source/patch/2.7.6-7build3 |
| pdns-backend-sqlite3 | 5.1.5-1pdns.ubuntu24.04 | GPL LGPL | pdns | 5.1.5-1pdns.ubuntu24.04 | https://downloads.powerdns.com/releases/ |
| pdns-server | 5.1.5-1pdns.ubuntu24.04 | GPL LGPL | pdns | 5.1.5-1pdns.ubuntu24.04 | https://downloads.powerdns.com/releases/ |
| perl | 5.38.2-3.2ubuntu0.7 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.7 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.7 |
| perl-base | 5.38.2-3.2ubuntu0.6 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.6 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.6 |
| perl-base | 5.38.2-3.2ubuntu0.7 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.7 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.7 |
| perl-modules-5.38 | 5.38.2-3.2ubuntu0.7 | GPL LGPL | perl | 5.38.2-3.2ubuntu0.7 | https://launchpad.net/ubuntu/+source/perl/5.38.2-3.2ubuntu0.7 |
| php-pear | 1:1.10.16+submodules+notgz-2+ubuntu24.04.1+deb.sury.org+1 | LGPL | php-pear | 1:1.10.16+submodules+notgz-2+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php-pear/1:1.10.16+submodules+notgz-2+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-bcmath | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-cli | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-common | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-curl | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-fpm | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-gd | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-intl | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-mbstring | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-mysql | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-opcache | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-readline | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-soap | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-xml | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.2-zip | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.2 | 8.2.35-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.2/8.2.35-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-bcmath | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-bz2 | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-cli | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-cli | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-common | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-common | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-curl | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-curl | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-fpm | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-fpm | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-gd | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-gd | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-intl | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-intl | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-mbstring | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-mbstring | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-mysql | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-mysql | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-opcache | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-opcache | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-pgsql | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-readline | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-readline | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-soap | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-xml | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-xml | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.3-zip | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.3 | 8.3.36-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.3/8.3.36-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.3-zip | 8.3.6-0ubuntu0.24.04.13 | LGPL | php8.3 | 8.3.6-0ubuntu0.24.04.13 | https://launchpad.net/ubuntu/+source/php8.3/8.3.6-0ubuntu0.24.04.13 |
| php8.4-bcmath | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-cli | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-common | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-curl | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-fpm | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-gd | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-intl | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-mbstring | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-mysql | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-opcache | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-readline | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-soap | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-xml | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.4-zip | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.4 | 8.4.27-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.4/8.4.27-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-bcmath | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-cli | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-common | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-curl | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-fpm | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-gd | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-intl | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-mbstring | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-mysql | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-readline | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-soap | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-xml | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| php8.5-zip | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | LGPL | php8.5 | 8.5.12-1+ubuntu24.04.1+deb.sury.org+1 | https://launchpad.net/ubuntu/+source/php8.5/8.5.12-1+ubuntu24.04.1+deb.sury.org+1 |
| pinentry-curses | 1.2.1-3ubuntu5 | GPL LGPL | pinentry | 1.2.1-3ubuntu5 | https://launchpad.net/ubuntu/+source/pinentry/1.2.1-3ubuntu5 |
| pkg-config | 1.8.1-2build1 | GPL | pkgconf | 1.8.1-2build1 | https://launchpad.net/ubuntu/+source/pkgconf/1.8.1-2build1 |
| pkgconf | 1.8.1-2build1 | GPL | pkgconf | 1.8.1-2build1 | https://launchpad.net/ubuntu/+source/pkgconf/1.8.1-2build1 |
| pkgconf-bin | 1.8.1-2build1 | GPL | pkgconf | 1.8.1-2build1 | https://launchpad.net/ubuntu/+source/pkgconf/1.8.1-2build1 |
| polkitd | 124-2ubuntu1.24.04.4 | LGPL | policykit-1 | 124-2ubuntu1.24.04.4 | https://launchpad.net/ubuntu/+source/policykit-1/124-2ubuntu1.24.04.4 |
| postfix | 3.8.6-1ubuntu0.1 | GPL | postfix | 3.8.6-1ubuntu0.1 | https://launchpad.net/ubuntu/+source/postfix/3.8.6-1ubuntu0.1 |
| postgresql-client-common | 293.pgdg24.04+1 | GPL | postgresql-common | 293.pgdg24.04+1 | https://apt-archive.postgresql.org/pub/repos/apt/pool/main/p/postgresql-common/ |
| postgresql-common | 293.pgdg24.04+1 | GPL | postgresql-common | 293.pgdg24.04+1 | https://apt-archive.postgresql.org/pub/repos/apt/pool/main/p/postgresql-common/ |
| procps | 2:4.0.4-4ubuntu3.3 | GPL LGPL | procps | 2:4.0.4-4ubuntu3.3 | https://launchpad.net/ubuntu/+source/procps/2:4.0.4-4ubuntu3.3 |
| psmisc | 23.7-1build1 | GPL | psmisc | 23.7-1build1 | https://launchpad.net/ubuntu/+source/psmisc/23.7-1build1 |
| python-apt-common | 2.7.7ubuntu5.3 | GPL | python-apt | 2.7.7ubuntu5.3 | https://launchpad.net/ubuntu/+source/python-apt/2.7.7ubuntu5.3 |
| python3-apt | 2.7.7ubuntu5.3 | GPL | python-apt | 2.7.7ubuntu5.3 | https://launchpad.net/ubuntu/+source/python-apt/2.7.7ubuntu5.3 |
| python3-dbus | 1.3.2-5build3 | GPL | dbus-python | 1.3.2-5build3 | https://launchpad.net/ubuntu/+source/dbus-python/1.3.2-5build3 |
| python3-gi | 3.48.2-1 | LGPL | pygobject | 3.48.2-1 | https://launchpad.net/ubuntu/+source/pygobject/3.48.2-1 |
| python3-httplib2 | 0.20.4-3ubuntu0.1 | GPL LGPL | python-httplib2 | 0.20.4-3ubuntu0.1 | https://launchpad.net/ubuntu/+source/python-httplib2/0.20.4-3ubuntu0.1 |
| python3-launchpadlib | 1.11.0-6 | LGPL | python-launchpadlib | 1.11.0-6 | https://launchpad.net/ubuntu/+source/python-launchpadlib/1.11.0-6 |
| python3-lazr.restfulclient | 0.14.6-1 | LGPL | lazr.restfulclient | 0.14.6-1 | https://launchpad.net/ubuntu/+source/lazr.restfulclient/0.14.6-1 |
| python3-lazr.uri | 1.0.6-3 | LGPL | lazr.uri | 1.0.6-3 | https://launchpad.net/ubuntu/+source/lazr.uri/1.0.6-3 |
| python3-pip-whl | 24.0+dfsg-1ubuntu1.3 | LGPL | python-pip | 24.0+dfsg-1ubuntu1.3 | https://launchpad.net/ubuntu/+source/python-pip/24.0+dfsg-1ubuntu1.3 |
| python3-pyinotify | 0.9.6-2ubuntu1 | GPL | pyinotify | 0.9.6-2ubuntu1 | https://launchpad.net/ubuntu/+source/pyinotify/0.9.6-2ubuntu1 |
| python3-software-properties | 0.99.49.4 | GPL LGPL | software-properties | 0.99.49.4 | https://launchpad.net/ubuntu/+source/software-properties/0.99.49.4 |
| python3-systemd | 235-1build4 | LGPL | python-systemd | 235-1build4 | https://launchpad.net/ubuntu/+source/python-systemd/235-1build4 |
| python3-wadllib | 1.3.6-5 | LGPL | python-wadllib | 1.3.6-5 | https://launchpad.net/ubuntu/+source/python-wadllib/1.3.6-5 |
| quota | 4.06-1build6 | GPL | quota | 4.06-1build6 | https://launchpad.net/ubuntu/+source/quota/4.06-1build6 |
| readline-common | 8.2-4build1 | GPL limits | readline | 8.2-4build1 | https://launchpad.net/ubuntu/+source/readline/8.2-4build1 |
| rpcsvc-proto | 1.4.2-0ubuntu7 | GPL | rpcsvc-proto | 1.4.2-0ubuntu7 | https://launchpad.net/ubuntu/+source/rpcsvc-proto/1.4.2-0ubuntu7 |
| rsync | 3.2.7-1ubuntu1.5 | GPL | rsync | 3.2.7-1ubuntu1.5 | https://launchpad.net/ubuntu/+source/rsync/3.2.7-1ubuntu1.5 |
| sed | 4.9-2ubuntu0.24.04.1 | GPL | sed | 4.9-2ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/sed/4.9-2ubuntu0.24.04.1 |
| sensible-utils | 0.0.22 | GPL | sensible-utils | 0.0.22 | https://launchpad.net/ubuntu/+source/sensible-utils/0.0.22 |
| sgml-base | 1.31 | GPL | sgml-base | 1.31 | https://launchpad.net/ubuntu/+source/sgml-base/1.31 |
| shared-mime-info | 2.4-4 | GPL | shared-mime-info | 2.4-4 | https://launchpad.net/ubuntu/+source/shared-mime-info/2.4-4 |
| slapd | 2.6.10+dfsg-0ubuntu0.24.04.1 | GPL | openldap | 2.6.10+dfsg-0ubuntu0.24.04.1 | https://launchpad.net/ubuntu/+source/openldap/2.6.10+dfsg-0ubuntu0.24.04.1 |
| socat | 1.8.0.0-4ubuntu0.1 | GPL | socat | 1.8.0.0-4ubuntu0.1 | https://launchpad.net/ubuntu/+source/socat/1.8.0.0-4ubuntu0.1 |
| software-properties-common | 0.99.49.4 | GPL LGPL | software-properties | 0.99.49.4 | https://launchpad.net/ubuntu/+source/software-properties/0.99.49.4 |
| sqlite3 | 3.45.1-1ubuntu2.9 | GPL | sqlite3 | 3.45.1-1ubuntu2.9 | https://launchpad.net/ubuntu/+source/sqlite3/3.45.1-1ubuntu2.9 |
| sudo | 1.9.15p5-3ubuntu5.24.04.4 | GPL | sudo | 1.9.15p5-3ubuntu5.24.04.4 | https://launchpad.net/ubuntu/+source/sudo/1.9.15p5-3ubuntu5.24.04.4 |
| systemd | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| systemd-dev | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| systemd-sysv | 255.4-1ubuntu8.18 | GPL LGPL | systemd | 255.4-1ubuntu8.18 | https://launchpad.net/ubuntu/+source/systemd/255.4-1ubuntu8.18 |
| sysvinit-utils | 3.08-6ubuntu3 | GPL LGPL | sysvinit | 3.08-6ubuntu3 | https://launchpad.net/ubuntu/+source/sysvinit/3.08-6ubuntu3 |
| tar | 1.35+dfsg-3ubuntu0.4 | GPL LGPL | tar | 1.35+dfsg-3ubuntu0.4 | https://launchpad.net/ubuntu/+source/tar/1.35+dfsg-3ubuntu0.4 |
| traceroute | 1:2.1.5-1 | GPL LGPL | traceroute | 1:2.1.5-1 | https://launchpad.net/ubuntu/+source/traceroute/1:2.1.5-1 |
| ubuntu-keyring | 2023.11.28.1 | GPL | ubuntu-keyring | 2023.11.28.1 | https://launchpad.net/ubuntu/+source/ubuntu-keyring/2023.11.28.1 |
| ucf | 3.0043+nmu1 | GPL | ucf | 3.0043+nmu1 | https://launchpad.net/ubuntu/+source/ucf/3.0043+nmu1 |
| unattended-upgrades | 2.9.1+nmu4ubuntu1 | GPL | unattended-upgrades | 2.9.1+nmu4ubuntu1 | https://launchpad.net/ubuntu/+source/unattended-upgrades/2.9.1+nmu4ubuntu1 |
| unminimize | 0.2.1 | GPL | unminimize | 0.2.1 | https://launchpad.net/ubuntu/+source/unminimize/0.2.1 |
| util-linux | 2.39.3-9ubuntu6.6 | GPL LGPL | util-linux | 2.39.3-9ubuntu6.6 | https://launchpad.net/ubuntu/+source/util-linux/2.39.3-9ubuntu6.6 |
| whois | 5.5.22 | GPL | whois | 5.5.22 | https://launchpad.net/ubuntu/+source/whois/5.5.22 |
| xdg-user-dirs | 0.18-1build1 | GPL | xdg-user-dirs | 0.18-1build1 | https://launchpad.net/ubuntu/+source/xdg-user-dirs/0.18-1build1 |
| xml-core | 0.19 | GPL | xml-core | 0.19 | https://launchpad.net/ubuntu/+source/xml-core/0.19 |
| xz-utils | 5.6.1+really5.4.5-1ubuntu0.4 | GPL LGPL | xz-utils | 5.6.1+really5.4.5-1ubuntu0.4 | https://launchpad.net/ubuntu/+source/xz-utils/5.6.1+really5.4.5-1ubuntu0.4 |


Debian packages without a licence found in their copyright file: 1 (sftpgo 2.7.6-1; see the downloads table where they are listed)

