# Composer

```
composer create-project drupal-composer/drupal-project:8.x-dev my_site_name_dir --stability dev --no-interaction
```

配置了 Composer 中国镜像，安装 Drupal 花了 7 分钟。

```
Installing drupal-composer/drupal-project (8.x-dev 4df8a592db3740a164f74a2036b42ea6b2b61e52)
  - Installing drupal-composer/drupal-project (8.x-dev 4df8a59): Cloning 4df8a592db from cache
Created project in drupal-8
> DrupalProject\composer\ScriptHandler::checkComposerVersion
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 102 installs, 0 updates, 0 removals
  - Installing cweagans/composer-patches (1.6.1): Downloading (100%)         
  - Installing drupal-composer/drupal-scaffold (2.3.0): Downloading (100%)         
  - Installing composer/installers (v1.3.0): Downloading (100%)         
  - Installing jakub-onderka/php-console-color (0.1): Downloading (100%)         
  - Installing jakub-onderka/php-console-highlighter (v0.3.2): Downloading (100%)         
  - Installing dnoegel/php-xdg-base-dir (0.1): Downloading (100%)         
  - Installing nikic/php-parser (v3.0.5): Downloading (100%)         
  - Installing symfony/polyfill-mbstring (v1.3.0): Downloading (100%)         
  - Installing symfony/var-dumper (v2.8.20): Downloading (100%)         
  - Installing psr/log (1.0.2): Downloading (100%)         
  - Installing symfony/debug (v2.8.20): Downloading (100%)         
  - Installing symfony/console (v2.8.20): Downloading (100%)         
  - Installing psy/psysh (v0.8.4): Downloading (100%)         
  - Installing symfony/expression-language (v2.8.20): Downloading (100%)         
  - Installing doctrine/lexer (v1.0.1): Downloading (100%)         
  - Installing doctrine/annotations (v1.2.7): Downloading (100%)         
  - Installing gabordemooij/redbean (v4.3.4): Downloading (100%)         
  - Installing psr/http-message (1.0.1): Downloading (100%)         
  - Installing guzzlehttp/psr7 (1.4.2): Downloading (100%)         
  - Installing guzzlehttp/promises (v1.3.1): Downloading (100%)         
  - Installing guzzlehttp/guzzle (6.2.3): Downloading (100%)         
  - Installing ircmaxell/password-compat (v1.0.4): Downloading (100%)         
  - Installing symfony/polyfill-php55 (v1.3.0): Downloading (100%)         
  - Installing symfony/polyfill-php54 (v1.3.0): Downloading (100%)         
  - Installing symfony/http-foundation (v2.8.20): Downloading (100%)         
  - Installing symfony/dom-crawler (v3.2.8): Downloading (100%)         
  - Installing symfony/css-selector (v2.8.20): Downloading (100%)         
  - Installing doctrine/collections (v1.4.0): Downloading (100%)         
  - Installing symfony/process (v2.8.20): Downloading (100%)         
  - Installing symfony/filesystem (v2.8.20): Downloading (100%)         
  - Installing alchemy/zippy (0.4.3): Downloading (100%)         
  - Installing symfony/finder (v2.8.20): Downloading (100%)         
  - Installing symfony/yaml (v2.8.20): Downloading (100%)         
  - Installing drupal/console-extend-plugin (0.6.0): Downloading (100%)         
  - Installing webflo/drupal-finder (0.3.0): Downloading (100%)         
  - Installing twig/twig (v1.33.2): Downloading (100%)         
  - Installing symfony/translation (v2.8.20): Downloading (100%)         
  - Installing symfony/event-dispatcher (v2.8.20): Downloading (100%)         
  - Installing symfony/dependency-injection (v2.8.20): Downloading (100%)         
  - Installing symfony/config (v2.8.20): Downloading (100%)         
  - Installing stecman/symfony-console-completion (0.7.0): Downloading (100%)         
  - Installing drupal/console-en (1.0.0-rc19): Downloading (100%)         
  - Installing dflydev/placeholder-resolver (v1.0.2): Downloading (100%)         
  - Installing dflydev/dot-access-data (v1.1.0): Downloading (100%)         
  - Installing dflydev/dot-access-configuration (v1.0.1): Downloading (100%)         
  - Installing drupal/console-core (1.0.0-rc19): Downloading (100%)         
  - Installing drupal/console (1.0.0-rc19): Downloading (100%)         
  - Installing zendframework/zend-stdlib (3.1.0): Downloading (100%)         
  - Installing zendframework/zend-escaper (2.5.2): Downloading (100%)         
  - Installing zendframework/zend-feed (2.8.0): Downloading (100%)         
  - Installing zendframework/zend-diactoros (1.4.0): Downloading (100%)         
  - Installing symfony/validator (v2.8.20): Downloading (100%)         
  - Installing symfony/serializer (v2.8.20): Downloading (100%)         
  - Installing symfony/routing (v2.8.20): Downloading (100%)         
  - Installing symfony/psr-http-message-bridge (v1.0.0): Downloading (100%)         
  - Installing symfony/polyfill-iconv (v1.3.0): Downloading (100%)         
  - Installing symfony/http-kernel (v2.8.20): Downloading (100%)         
  - Installing symfony/polyfill-apcu (v1.3.0): Downloading (100%)         
  - Installing symfony/class-loader (v2.8.20): Downloading (100%)         
  - Installing symfony-cmf/routing (1.4.1): Downloading (100%)         
  - Installing stack/builder (v1.0.4): Downloading (100%)         
  - Installing paragonie/random_compat (v2.0.10): Downloading (100%)         
  - Installing masterminds/html5 (2.2.2): Downloading (100%)         
  - Installing egulias/email-validator (1.2.14): Downloading (100%)         
  - Installing easyrdf/easyrdf (0.9.1): Downloading (100%)         
  - Installing doctrine/inflector (v1.1.0): Downloading (100%)         
  - Installing doctrine/cache (v1.6.1): Downloading (100%)         
  - Installing doctrine/common (v2.7.2): Downloading (100%)         
  - Installing composer/semver (1.4.2): Downloading (100%)         
  - Installing asm89/stack-cors (1.1.0): Downloading (100%)         
  - Installing drupal/core (8.3.2): Downloading (100%)         
  - Installing webmozart/assert (1.2.0): Downloading (100%)         
  - Installing webmozart/path-util (2.3.0): Downloading (100%)         
  - Installing phpdocumentor/reflection-docblock (2.0.4): Downloading (100%)         
  - Installing pear/console_table (v1.3.0): Downloading (100%)         
  - Installing consolidation/output-formatters (3.1.9): Downloading (100%)         
  - Installing consolidation/annotated-command (2.4.8): Downloading (100%)         
  - Installing drush/drush (8.1.11): Downloading (100%)         
  - Installing symfony/browser-kit (v3.2.8): Downloading (100%)         
  - Installing fabpot/goutte (v3.2.1): Downloading (100%)         
  - Installing behat/mink (v1.7.1): Downloading (100%)         
  - Installing behat/mink-browserkit-driver (v1.3.2): Downloading (100%)         
  - Installing behat/mink-goutte-driver (v1.2.1): Downloading (100%)         
  - Installing jcalderonzumba/gastonjs (v1.0.3): Downloading (100%)         
  - Installing jcalderonzumba/mink-phantomjs-driver (v0.3.3): Downloading (100%)         
  - Installing mikey179/vfsstream (v1.6.4): Downloading (100%)         
  - Installing sebastian/version (1.0.6): Downloading (100%)         
  - Installing sebastian/global-state (1.1.1): Downloading (100%)         
  - Installing sebastian/recursion-context (1.0.5): Downloading (100%)         
  - Installing sebastian/exporter (1.2.2): Downloading (100%)         
  - Installing sebastian/environment (1.3.8): Downloading (100%)         
  - Installing sebastian/diff (1.4.1): Downloading (100%)         
  - Installing sebastian/comparator (1.2.4): Downloading (100%)         
  - Installing doctrine/instantiator (1.0.5): Downloading (100%)         
  - Installing phpunit/php-text-template (1.2.1): Downloading (100%)         
  - Installing phpunit/phpunit-mock-objects (2.3.8): Downloading (100%)         
  - Installing phpunit/php-timer (1.0.9): Downloading (100%)         
  - Installing phpunit/php-file-iterator (1.4.2): Downloading (100%)         
  - Installing phpunit/php-token-stream (1.4.11): Downloading (100%)         
  - Installing phpunit/php-code-coverage (2.2.4): Downloading (100%)         
  - Installing phpspec/prophecy (v1.7.0): Downloading (100%)         
  - Installing phpunit/phpunit (4.8.35): Downloading (100%)         
symfony/var-dumper suggests installing ext-symfony_debug ()
psy/psysh suggests installing ext-pdo-sqlite (The doc command requires SQLite to work.)
psy/psysh suggests installing hoa/console (A pure PHP readline implementation. You'll want this if your PHP install doesn't already support readline or libedit.)
alchemy/zippy suggests installing guzzle/guzzle (To use the GuzzleTeleporter with Guzzle 3)
symfony/dependency-injection suggests installing symfony/proxy-manager-bridge (Generate service proxies to lazy load them)
zendframework/zend-feed suggests installing zendframework/zend-cache (Zend\Cache component, for optionally caching feeds between requests)
zendframework/zend-feed suggests installing zendframework/zend-db (Zend\Db component, for use with PubSubHubbub)
zendframework/zend-feed suggests installing zendframework/zend-http (Zend\Http for PubSubHubbub, and optionally for use with Zend\Feed\Reader)
zendframework/zend-feed suggests installing zendframework/zend-servicemanager (Zend\ServiceManager component, for easily extending ExtensionManager implementations)
zendframework/zend-feed suggests installing zendframework/zend-validator (Zend\Validator component, for validating email addresses used in Atom feeds and entries ehen using the Writer subcomponent)
symfony/validator suggests installing symfony/intl ()
symfony/validator suggests installing symfony/property-access (For using the 2.4 Validator API)
symfony/serializer suggests installing symfony/property-access (For using the ObjectNormalizer.)
paragonie/random_compat suggests installing ext-libsodium (Provides a modern crypto API that can be used to generate random bytes.)
easyrdf/easyrdf suggests installing ml/json-ld (~1.0)
phpdocumentor/reflection-docblock suggests installing dflydev/markdown (~1.0)
phpdocumentor/reflection-docblock suggests installing erusev/parsedown (~1.0)
pear/console_table suggests installing pear/Console_Color2 (>=0.1.2)
drush/drush suggests installing drush/config-extra (Provides configuration workflow commands, such as config-merge.)
behat/mink suggests installing behat/mink-selenium2-driver (slow, but JS-enabled driver for any app (requires Selenium2))
behat/mink suggests installing behat/mink-zombie-driver (fast and JS-enabled headless driver for any app (requires node.js))
sebastian/global-state suggests installing ext-uopz (*)
phpunit/phpunit-mock-objects suggests installing ext-soap (*)
phpunit/php-code-coverage suggests installing ext-xdebug (>=2.2.1)
phpunit/phpunit suggests installing phpunit/php-invoker (~1.1)
Writing lock file
Generating autoload files
Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)Downloading (100%)> DrupalProject\composer\ScriptHandler::createRequiredFiles
Create a sites/default/settings.php file with chmod 0666
Create a sites/default/files directory with chmod 0777
```



