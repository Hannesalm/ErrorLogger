# ErrorLogger

## Install

Include gel/error-logging in your composer.json.

```
   {
    "require": {
        "gel/error-logging": "1.1"
    }
   }
```
Then do a validate/update.

```
 composer validate
 composer install --no-dev
```

Or use this command.
```
 composer require gel/error-logging
```


## Usage

Create a new instance of the class, and choose where the file will be logged via the constructor. 
```
 $myErrorLogger = new gel\logger\ErrorLogger('tmp/example/example.log.php');
```
Error messages will be removed by default. If you wanna turn them on simple call the function displayErrors.
```
$myErrorLogger->displayErrors(true)
```

You cant generate an error by using the function trigger_error.
```
trigger_error("Error is triggerd", E_USER_ERROR);
```

Error reporting is set to -1, but you can change it via changeErrorReporting function.
```
$myErrorLogger->changeErrorReporting("E_ERROR | E_WARNING");
```

Like always, try to create an instance of this class as early as possible. 
