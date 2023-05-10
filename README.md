# Rules for php code sniffer
#### Install a linter for PHP via Composer:
```sh
composer global require "squizlabs/php_codesniffer=*"
```
#### Required vscode extensions:
1. PHP IntelliSense
2. phpcs

#### Set up a linter:
1. Open the VSCode user settings by pressing `Ctrl + ,` (Windows/Linux) or `Command + ,` (Mac), and then click on the "Open Settings (JSON)" button in the top right corner.
2. Add the following lines to your VSCode user settings:
```json
"php.validate.enable": false,
"php.suggest.basic": false,
"php.suggest.experimentalFeatures": false,
"phpcs.enable": true,
"phpcs.standard": "PSR12",
"phpcs.executablePath": "/path/to/composer/vendor/bin/phpcs"
```
3. Make sure to replace `/path/to/composer` with the path to your Composer installation directory. You can find this path by running the following command in your terminal:
```sh
composer global config bin-dir --absolute
```
This will display the absolute path to your Composer bin directory. Append /phpcs to the end of the path to specify the path to the PHPCS executable.
4. Save your VSCode user settings, and then open a PHP file in VSCode. You should now see linting errors and warnings in the editor based on the PSR-12 coding standard.

### Set up custom rules by slevomat\coding-standard
1. Install the coding standard globally through Composer:
```sh
composer global require 'slevomat/coding-standard=*'
```
2. Change the {path} value to your Composer installation path:
```xml
<ruleset name="cscart rulset">
    <config name="installed_paths" value="{path}/slevomat/coding-standard" />
```
You can find this path by running the following command in your terminal:
```sh
composer global config bin-dir --absolute
```

#### Install Ruleset:
1. Create a file `ruleset.xml` in the root of your php project
2. Copy the code from  `ruleset.xml` which is in the repository to your `ruleset.xml`
