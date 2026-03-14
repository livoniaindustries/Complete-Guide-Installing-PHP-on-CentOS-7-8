# Complete Guide: Installing PHP on CentOS 7 & 8

**📌 About PHP:** Today, virtually no web applications will work without PHP. PHP differs from other programming languages in that it is executed on the server side and generates HTML code dynamically. This guide covers PHP installation on CentOS 7 and 8 using Remi repositories for the latest PHP versions.

CentOS 7

CentOS 8

## Installing PHP on CentOS 7

**🐘 PHP Versions Available:** Using Remi repository, you can install PHP 5.6, 7.0, 7.1, 7.2, 7.3, 7.4, 8.0, 8.1, 8.2, 8.3. This guide uses PHP 7.3 as an example.

### Step 1: Install Prerequisites

\# Install wget for downloading files sudo yum install wget -y # Install yum-utils for repository management sudo yum install yum-utils -y # Install EPEL (Extra Packages for Enterprise Linux) sudo yum install epel-release -y

### Step 2: Add Remi Repository

\# Download and install Remi repository for CentOS 7 rpm -ivh http://rpms.famillecollet.com/enterprise/remi-release-7.rpm

**Note:** Remi repository provides the latest PHP versions that are not available in the default CentOS repositories.

### Step 3: Enable Desired PHP Version

\# Enable PHP 7.3 from Remi repository sudo yum-config-manager --enable remi-php73 # For PHP 7.4, use: remi-php74 # For PHP 8.0, use: remi-php80 # For PHP 8.1, use: remi-php81 # For PHP 8.2, use: remi-php82 # For PHP 8.3, use: remi-php83

| PHP Version | Repository Enable Command |
| --- | --- |
| PHP 5.6 | `yum-config-manager --enable remi-php56` |
| PHP 7.0 | `yum-config-manager --enable remi-php70` |
| PHP 7.1 | `yum-config-manager --enable remi-php71` |
| PHP 7.2 | `yum-config-manager --enable remi-php72` |
| PHP 7.3 | `yum-config-manager --enable remi-php73` |
| PHP 7.4 | `yum-config-manager --enable remi-php74` |
| PHP 8.0 | `yum-config-manager --enable remi-php80` |
| PHP 8.1 | `yum-config-manager --enable remi-php81` |
| PHP 8.2 | `yum-config-manager --enable remi-php82` |
| PHP 8.3 | `yum-config-manager --enable remi-php83` |

### Step 4: Install PHP and Required Modules

\# Install PHP core with common modules sudo yum install php php-common php-opcache php-mcrypt php-cli php-gd php-curl php-mysqlnd -y # Install additional useful modules (optional) sudo yum install php-xml php-mbstring php-zip php-json php-intl php-bcmath -y

#### PHP Module Descriptions:

| Module | Purpose |
| --- | --- |
| php | Core PHP package |
| php-common | Common files for PHP |
| php-opcache | OPcache for performance improvement |
| php-mcrypt | Encryption functions |
| php-cli | Command-line interface for PHP |
| php-gd | Image processing library |
| php-curl | cURL library for HTTP requests |
| php-mysqlnd | MySQL native driver (for MySQL/MariaDB) |
| php-xml | XML parsing functions |
| php-mbstring | Multibyte string support |
| php-zip | ZIP file handling |
| php-json | JSON support |
| php-intl | Internationalization functions |
| php-bcmath | Arbitrary precision mathematics |

### Step 5: Verify PHP Installation

\# Check PHP version php -v # Check installed PHP modules php -m # Check PHP configuration php -i | grep "Loaded Configuration File"

Example output:

```
PHP 7.3.33 (cli) (built: Oct 19 2021 14:48:14) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.3.33, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.3.33, Copyright (c) 1999-2018, by Zend Technologies
```

## Installing PHP on CentOS 8

**🐘 PHP Versions Available:** CentOS 8 with Remi repository supports PHP 7.2, 7.3, 7.4, 8.0, 8.1, 8.2, 8.3. This guide covers PHP 8.0+ installation.

**Note:** CentOS 8 uses DNF (Dandified YUM) as the package manager instead of YUM. DNF is the next-generation version of YUM.

### Step 1: Install EPEL Repository

\# Install EPEL for CentOS 8 sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm -y

### Step 2: Install Remi Repository

\# Install Remi repository for CentOS 8 sudo dnf install https://rpms.remirepo.net/enterprise/remi-release-8.rpm -y

### Step 3: Verify Repository Installation (Optional)

\# Check if EPEL is installed rpm -qa | grep epel # Check if Remi is installed rpm -qa | grep remi

### Step 4: List Available PHP Versions

\# View available PHP modules and versions dnf module list php

Example output:

```
CentOS-8 - AppStream
Name    Stream    Profiles                         Summary
php     7.2       common [d], devel, minimal       PHP scripting language
php     7.3       common [d], devel, minimal       PHP scripting language
php     7.4       common [d], devel, minimal       PHP scripting language

Remi's Modular repository
php     remi-7.4  common [d], devel, minimal       PHP scripting language
php     remi-8.0  common [d], devel, minimal       PHP scripting language
php     remi-8.1  common [d], devel, minimal       PHP scripting language
php     remi-8.2  common [d], devel, minimal       PHP scripting language
php     remi-8.3  common [d], devel, minimal       PHP scripting language
```

### Step 5: Enable Desired PHP Version

\# Reset PHP module (if previously enabled) sudo dnf module reset php -y # Enable PHP 8.0 from Remi repository sudo dnf module enable php:remi-8.0 -y # For PHP 8.1: php:remi-8.1 # For PHP 8.2: php:remi-8.2 # For PHP 8.3: php:remi-8.3

| PHP Version | Enable Command |
| --- | --- |
| PHP 7.4 | `sudo dnf module enable php:remi-7.4 -y` |
| PHP 8.0 | `sudo dnf module enable php:remi-8.0 -y` |
| PHP 8.1 | `sudo dnf module enable php:remi-8.1 -y` |
| PHP 8.2 | `sudo dnf module enable php:remi-8.2 -y` |
| PHP 8.3 | `sudo dnf module enable php:remi-8.3 -y` |

### Step 6: Install PHP and Required Modules

\# Install PHP core with common modules sudo dnf install php php-opcache php-gd php-curl php-mysqlnd -y # Install additional useful modules sudo dnf install php-cli php-xml php-mbstring php-zip php-json php-intl php-bcmath -y

#### PHP Modules for CentOS 8:

| Module | Purpose |
| --- | --- |
| php | Core PHP package |
| php-cli | Command-line interface for PHP |
| php-common | Common files for PHP |
| php-opcache | OPcache for performance improvement |
| php-gd | Image processing library |
| php-curl | cURL library for HTTP requests |
| php-mysqlnd | MySQL native driver (for MySQL/MariaDB) |
| php-xml | XML parsing functions |
| php-mbstring | Multibyte string support |
| php-zip | ZIP file handling |
| php-json | JSON support |
| php-intl | Internationalization functions |
| php-bcmath | Arbitrary precision mathematics |
| php-pdo | PHP Data Objects database abstraction layer |

### Step 7: Verify PHP Installation

\# Check PHP version php -v # Check installed PHP modules php -m # Check PHP configuration php -i | grep "Loaded Configuration File"

Example output for PHP 8.0:

```
PHP 8.0.27 (cli) (built: Dec 13 2022 14:23:16) ( NTS )
Copyright (c) The PHP Group
Zend Engine v4.0.27, Copyright (c) Zend Technologies
    with Zend OPcache v8.0.27, Copyright (c), by Zend Technologies
```

## Post-Installation Configuration

### PHP Configuration File Location

| File | Purpose | Location |
| --- | --- | --- |
| php.ini | Main PHP configuration | `/etc/php.ini` |
| php.d/ | Module-specific configurations | `/etc/php.d/` |
| php-fpm.conf | PHP-FPM configuration (if installed) | `/etc/php-fpm.conf` |

### Common PHP Configuration Changes

Edit php.ini to adjust common settings:

sudo vi /etc/php.ini

| Directive | Recommended Value | Description |
| --- | --- | --- |
| memory\_limit | `256M` | Maximum memory a script can consume |
| upload\_max\_filesize | `64M` | Maximum file upload size |
| post\_max\_size | `64M` | Maximum POST data size |
| max\_execution\_time | `300` | Maximum script execution time in seconds |
| max\_input\_time | `300` | Maximum time for parsing input data |
| date.timezone | `America/New_York` | Set your timezone (e.g., America/New\_York, Europe/London) |
| display\_errors | `Off` (production) / `On` (development) | Display PHP errors |

### Testing PHP with Apache

Create a test PHP file in your web directory:

echo "" | sudo tee /var/www/html/info.php

Access it via browser:

http://your-server-ip/info.php

**⚠️ Security Warning:** Remove or rename info.php after testing, as it exposes sensitive PHP configuration information to visitors.

## PHP-FPM Installation (Optional)

### Install PHP-FPM for Better Performance with Nginx

#### CentOS 7:

sudo yum install php-fpm -y sudo systemctl start php-fpm sudo systemctl enable php-fpm

#### CentOS 8:

sudo dnf install php-fpm -y sudo systemctl start php-fpm sudo systemctl enable php-fpm

#### PHP-FPM Configuration:

sudo vi /etc/php-fpm.d/www.conf

Common settings to adjust:

```
user = apache
group = apache
listen = /run/php-fpm/www.sock
listen.owner = apache
listen.group = apache
listen.mode = 0660
```

## Installing Additional PHP Extensions

### Common Extensions and Their Installation

| Extension | Purpose | Install Command (CentOS 7) | Install Command (CentOS 8) |
| --- | --- | --- | --- |
| php-redis | Redis support | `yum install php-redis` | `dnf install php-redis` |
| php-memcached | Memcached support | `yum install php-memcached` | `dnf install php-memcached` |
| php-pgsql | PostgreSQL support | `yum install php-pgsql` | `dnf install php-pgsql` |
| php-sqlite3 | SQLite3 support | `yum install php-sqlite3` | `dnf install php-sqlite3` |
| php-pear | PEAR package manager | `yum install php-pear` | `dnf install php-pear` |
| php-devel | PHP development files | `yum install php-devel` | `dnf install php-devel` |

**Note:** After installing new extensions, restart Apache or PHP-FPM: `sudo systemctl restart httpd` or `sudo systemctl restart php-fpm`

## Troubleshooting Common Issues

| Issue | Solution |
| --- | --- |
| PHP version not updating after enabling Remi | Clear cache: `sudo yum clean all` (CentOS 7) or `sudo dnf clean all` (CentOS 8) |
| php-mcrypt not available in PHP 7.2+ | Use `php-pecl-mcrypt` instead: `sudo yum install php-pecl-mcrypt` |
| PHP files downloading instead of executing | Ensure Apache PHP module is installed and enabled: `sudo yum install php mod_php` |
| 404 error when accessing PHP files | Check if Apache PHP handler is configured: `sudo httpd -M \| grep php` |
| Memory limit too low for applications | Increase memory\_limit in php.ini: `memory_limit = 256M` |
| PHP-FPM not starting | Check configuration: `sudo php-fpm -t`, check logs: `sudo tail -f /var/log/php-fpm/error.log` |

## Quick Reference Commands

| Action | CentOS 7 Command | CentOS 8 Command |
| --- | --- | --- |
| Install PHP | `yum install php php-common` | `dnf install php php-common` |
| Check PHP version | `php -v` |     |
| List PHP modules | `php -m` |     |
| Restart Apache | `sudo systemctl restart httpd` |     |
| Restart PHP-FPM | `sudo systemctl restart php-fpm` |     |
| Find php.ini location | `php -i \| grep "Loaded Configuration File"` |     |
| Clear package cache | `sudo yum clean all` | `sudo dnf clean all` |
