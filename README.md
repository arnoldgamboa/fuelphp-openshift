# Installing PHP 5.3 on OpenShift

(This assumes you already have OpenShift's CLI tools. [Here's how to get started with OpenShift](https://developers.openshift.com/en/getting-started-overview.html))

Run this command on your shell.

```sh
$ rhc app create fuelphpopenshift php-5.3 --from-code=https://github.com/arnoldgamboa/fuelphp-$ openshift.git
```

where: "fuelphpopenshift" is your app name.

That's it! You should see it run and install your app.

A few notes about this repo
---------------------------
- This version of FuelPHP 1.7.2 intentionally omits the fuel/vendors directory for a reason.

- The .openshift/action_hooks/post_deploy file runs the needed composer command automatically upon deploy.

- On your local script folder, you need to run the composer:

```sh
$ curl -s https://getcomposer.org/installer | php -- --install-dir=./
$ php composer.phar install
```

- .gitignore lists all the files and directories that needs to be ignored so that the composer 
