# Creating a hook

When creating a hook, the important thing to remember is that you are basicly creating a service provider.
There are a few minor things to it, but that is basicly it.

## The composer.json file

The `composer.json` file is one important part of hooks, since this is where you choose your hook's name, dependencies, autoload methods and most important its service providers.
Lets take a example:

> This example is from [`voyager-polls`](https://github.com/thedevdojo/voyager-polls)
```
{
  "name": "voyager-polls",
  "description": "This is my first hook.",
  "tags": ["voyager"],
  "require": {
    "larapack/hooks": "~1.0"
  },
  "autoload": {
    "psr-4": {
      "VoyagerPolls\\": "src/"
    }
  },
  "extra": {
    "hook": {
      "providers": [
        "VoyagerPolls\\PollsServiceProvider"
      ]
    }
  }
}
```

Lets take those properties piece by peice.

### name
First the `name` proberty, this is a required property which is also the most important property.
This is the name of your hook. And unless any other Composer package, this may **not** include any slashes `/`.
In this case the name of the hook is `voyager-polls`, this means that in order to install it you will need to run:
```
php artisan hook:install voyager-polls
```

### description
This is an optional field where you can describe your hook in a few lines.

### tags
You should tag things to make them easier to find, for example I would tag everything related to Voyager with the `voyager` tag.
You can have multiple tags like this: `"tags": ["foo", "bar", "bas"]`

### require
This is where you can define your package requirements.
We recommend that you add the lastest version of `larapack/hooks` that you intend to support.
Along with the latest version of Laravel that you support.
> You can also use `require-dev` for requiring dependencies only on development mode.

### autoload
Here you can define which part of your files should be autoloaded how.
You may read more on this on Composer's website.

### providers
As an extra thing, you can define the service providers that you wish to load once the hook have been enabled.

## Installation

Once you have created your local hook, you can install your it by running `php artisan hook:install NAME` (replace `NAME` with the name of your hook).
