# PHP

## CLI

`php -S localhost:8080 [-c ./php.ini]` - Built-in PHP dev web-server, with option specific ini file.

## Examples

### Class Auto-Loader
```php
// PHP Class Auto-loader
spl_autoload_register(function ($class) {
	include "path" . $class . ".class.php";
});
```

### Convert errors to exceptions
```php
// PHP Convert Errors to Exceptions
set_error_handler(function($errorNumber, $errorMessage, $errorFile, $errorLine) {
    throw new \ErrorException($errorMessage, 0, $errorNumber, $errorFile, $errorLine);
});
```

### Register shutdown function
```php
// PHP Register Shut-down Function - Handle Errors
register_shutdown_function(function() {
    $errorData = error_get_last();
    if (is_array($errorData)) {
        ob_end_clean();
        echo 'Error occured! - ' . $errorData['message'];
    }
});
```