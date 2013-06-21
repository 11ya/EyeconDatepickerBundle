## Current Version

This bundle allow usage any version of library that you wish. Original lib uses as a package with forced version and original files is symlinked.

Just go to https://github.com/statichippo/eyecon-datepicker and check tags.

## Installation

### Add bundle to your composer.json file

Set needed version and branch in `version` and `reference` of package.

``` js
// composer.json

{
    "repositories": {
        // ...

        "statichippo/eyecon-datepicker": {
            "type": "package",
            "package": {
                "name": "statichippo/eyecon-datepicker",
                "version": "1.0",
                "source": {
                    "url": "https://github.com/statichippo/eyecon-datepicker.git",
                    "type": "git",
                    "reference": "origin/master"
                }
            }
        }
    },

    // ...

    "require": {
		// ...
        "fanforfun/eyecon-datepicker-bundle": "dev-master"
    }
}
```

### Add bundle to your application kernel

``` php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Fanforfun\EyeconDatepickerBundle\FanforfunEyeconDatepickerBundle(),
        // ...
    );
}
```

### Download the bundle using Composer

``` bash
$ php composer.phar update fanforfun/eyecon-datepicker-bundle
```

### Install assets

Given your server's public directory is named "web", install the public vendor resources

``` bash
$ php app/console assets:install web
```

Optionally, use the --symlink attribute to create links rather than copies of the resources

``` bash
$ php app/console assets:install --symlink web
```

## Usage

Refer to the desired files in your twig/HTML template, e.g.

``` html
{% javascripts output='resources/js/*.js' '@FanforfunEyeconDatepickerBundle/Resources/public/js/datepicker.js' %}
    <script type="text/javascript" src="{{ asset_url }}"></script>
{% endjavascripts %}

{% stylesheets filter='cssrewrite' output='resources/css/*.css' 'bundles/fanforfuneyecondatepicker/css/datepicker.css' %}
    <link href="{{ asset_url }}" rel="stylesheet" type="text/css" />
{% endstylesheets %}
```

## Licenses

Refer to the source code of the included files for license information

## References

1. http://symfony.com/

2. https://github.com/statichippo/eyecon-datepicker