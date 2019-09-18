# Composer Issue 8320

Track a case where composer installers can't work

See https://github.com/composer/composer/issues/8320

## Reproducing

Run the following commands to see the issue here. These commands are also
available as `run.sh` in this project.

```
composer install
composer diagnose
composer where drupal/webform
# drupal/webform(type:drupal-module managed by Composer\Installers\Installer) is installed at ./modules/webform
composer why composer/installers
# roygoldman/composer-installers-discovery  dev-fix-installer-order  requires  composer/installers (^1.2)
# roygoldman/drupal-project-installers      8.0.1                    requires  composer/installers (^1.2)
```

The expected is for this project to install `drupal/webform` into
`./web/modules/webform`.
