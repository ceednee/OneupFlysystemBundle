# Getting started

The OneupFlysystemBundle was developed and tested for Symfony2 version 2.2+.

## Installation
Perform the following steps to install and use the basic functionality of the OneupFlysystemBundle:

* Download OneupFlysystemBundle using Composer
* Enable the bundle
* Configure your filesystems

### Step 1: Download the bundle
Add OneupFlysystemBundle to your composer.json using the following construct:

```json
{
    "require": {
        "oneup/flysystem-bundle": "dev-master"
    }
}
```

Now tell composer to download the bundle by running the following command:

```
$> php composer.phar update oneup/uploader-bundle
```

Composer will now fetch and install this bundle in the vendor directory `vendor/oneup`

### Step 2: Enable the bundle
Enable the bundle in the kernel:

``` php
<?php
// app/AppKernel.php

public function registerBundles()
{
    $bundles = array(
        // ...
        new Oneup\FlysystemBundle\OneupFlysystemBundle(),
    );
}
```

### Step3: Configure your filesystems
In order to create a filesystem, you first need to create an adapter. An easy example is to define a local adapter
and afterwards create a filesystem based on it.

```yaml
# app/config/config.yml
oneup_flysystem:
    adapters:
        my_adapter:
            local:
                directory: %kernel.root_dir%/cache

    filesystems:
        my_filesystem:
            adapter: my_adapter
```

There are a bunch of adapters for you to use:

* AwsS3
* Dropbox
* Ftp
* Local filesystem
* Rackspace
* Sftp
* WebDav
* ZipArchive

### Step 4: Next steps

After installing and setting up the basic functionality of this bundle you can move on and integrate some more advanced features.

* Cache your filesystems
* Create an alias for your filesystems
* Running the tests