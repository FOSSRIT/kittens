kittens
=======

A means of sending friendly images of kittens to a target.

Setup
=====

First, you'll need to make an account with [Mogreet](https://developer.mogreet.com).
Once you've done that, you'll need to create a configuration file to tell `kittens`
where to find the credentials for your Mogreet accounts as well as where to find
the kittens. Configuration file should either be called `.kittens.conf` in your
home directory, or `/etc/kittens.conf` in the system root.

The config file should be formatted as an INI file, like so:

    [mogreet]
    client_id = 123
    token = 123
    campaign_id = 123
    [kittens]
    image_list = ["url1", "url2", "url3"]

To be clear, `image_list` should be a JSON list of
url strings that link to images of kittens.

Usage
=====

Use the `kittens` tool from the command line like this:

    python -m kittens phone_number message [repetitions]

Where `message` is a message to send with the MMS, and
the optional `repetitions` parameter is how kittens to
send them. Each sending will randomly select a kitten from
the list to send, so your target will never lack for novelty.