Omni
=======

# What is Omni?

Omni (in this case) is short for Omniscient - which is the capacity to know everything there is to know. Quite fitting for a Profiler for Laravel eh?

Omni allows you to see:

- Total execution time
    - Custom "checkpoints", see [this section](#custom-timers)
- Total memory usage
- SQL Query Log
- All variables passed to views

# Installation
To add Omni to your Laravel application, add the following to your *composer.json* file:

    "sorora/omni" : "dev-master"

Then run *composer update* or *composer install* if you have not already installed packages. One final step is needed, add the below to the *providers* array in *app/config/app.php* configuration file:

    'Sorora\Omni\Providers\OmniServiceProvider',

# Configuration

You will want to run the following command to publish the config to your application, otherwise it will be overwritten in updates.

    php artisan config:publish sorora/omni

## Profiler

Set this value to *false* to disable the profiler. It is *true* by default.

# Usage

## Custom Timers

To start a timer, all you need to do is:
    
    Omni::start('my timer key');

To end the timer, simply call the end function like so:

    Omni::end('my timer key');

# Logging

Omni utilizes Laravels built in logging system and captures logged events. To log events, you can do (as you would with laravel) any of these:

    Log::debug('Your message here');
    Log::info('Your message here');
    Log::notice('Your message here');
    Log::warning('Your message here');
    Log::error('Your message here');
    Log::critical('Your message here');
    Log::alert('Your message here');
    Log::emergency('Your message here');

These are colour coded in the Logs part of the Omni profiler - colours may change in future to more accurately reflect the log type.