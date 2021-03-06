# What is FLBW, the PHP extension ?

FLBW is a dynamic and lightweight C++ encryption algorithm allowing you to encrypt a string with or without a password.

The PHP extension allows to benefit the speed of C/C++ with the latitud of PHP.

Actual version : _(cpp)_ __0.6__  
:warning: PHP **7.0** or greater is required.

-----
We use the great [PHP-CPP](https://www.php-cpp.com) to generate the PHP extension from the C++ FLBW library.

# Installation

You have only **2** things to do !

## 1. Add the extension to your `php.ini`.

Append to your `php.ini` :
```
extension=flbw_ext.so
```

:information_source: Usually, your `php.ini` file is located under : `/etc/php/<YOUR_PHP_VERSION>/cli/php.ini`.

## 2. Run the makefile install.

:warning: For developing, we used the **7.0** version of PHP. If you have a different version, **please update** the line `3` of the `./Makefile`.
```bash
sudo make install
```

# Use

The FLBW PHP extension provide 2 functions : encryption and decryption of string.

```php
$encrypted_string = flbw_encrypt("My super-secure string.", "my_perfect_password", bruteforce_difficulty);
```

```php
$decrypted_string = flbw_decrypt("SSdtIHNlY3JldA==", "my_perfect_password", bruteforce_difficulty);
```

:information_source: `difficulty` is the bruteforce protection difficulty, set it `0` to disable it. A normal value might be `250000`, corresponding to ~1 second (but this highly depends on your computer configuration).

:information_source: If you've provided a wrong password or an error occured, `false` will be returned.

# Uninstallation

```bash
sudo make uninstall
```