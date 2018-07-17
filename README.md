# lx-utils

Recursively clean up all files in a PHP project by assigning clean up tasks.
Clean up tasks available:
- clean up undefined constants in array square brakets (beginning with PHP 7.2 unquoted 
array keys produce the Warning "Use of undefined constant ..." and in future versions this will 
trigger a hard error). This task will automatically quote all strings which are undefined constants 
used inside square brackets for the array syntax. Observation: this fix only targets array usage 
like $a[key1] which will be automatically transformed into $a['key1']. The clean up process <b>DOES NOT</b> 
parse and compute a list of defined constants in your project, in order to white-list them for usage 
without quotes in all possible contexts.

## Notice

- It's recommended to run it for your project on DEV first, check functionality and then push to LIVE.
- When running on a real project, it's a good idea to backup the project files first, 
just to be sure that what you are doing matches what you're expecting.

## Usage

```
git clone https://github.com/eyroot/lx-utils lx-utils
cd lx-utils
composer install --no-dev
php run/cleanUpSquareBrackets.php /path/you/want/to/clean/up
```

## Development set-up

* Clone project locally:
```
git clone https://github.com/eyroot/lx-utils lx-utils
cd lx-utils
```

* Set-up project and install composer deps:
```
composer install
```

* Run unit testing:
```
mkdir testing/tmp
cd testing/
../vendor/bin/phpunit
```

* Check the code coverage of tests by opening in browser:
```
file:///tmp/coverage-lx-utils/index.html
```
