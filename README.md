# NAME

Selenium::Remote::Driver::UserAgent - Emulate mobile devices by setting user agents when using webdriver

# VERSION

version 0.001

# SYNOPSIS

    my $dua = Selenium::Remote::Driver::UserAgent->new(
        browserName => 'chrome',
        agent => 'iphone'
    );

    my $caps = $dua->caps;
    my $driver = Selenium::Remote::Driver->new_from_caps(%$caps);

# DESCRIPTION

This package will help you test your websites on mobile devices by
convincing your browsers to masquerade as a mobile device. You can
start up Firefox or Chrome with the same user agents that your mobile
browsers would send, along with the same screen resolution and layout.

Although the experience may not be 100% the same as manually testing
on an actual mobile device, the advantage of testing this way is that
you hardly need any additional infrastructure if you've already got a
webdriver testing suite set up.

# ATTRIBUTES

## browserName

Required: specify which browser type to use. Currently, we only
support `Chrome` and `Firefox`.

    my $dua = Selenium::Remote::Driver::UserAgent->new(
        browserName => 'chrome',
        agent => 'ipad'
    );

## agent

Required: specify which mobile device type to emulate. Your options
are:

    iphone
    ipad_seven
    ipad
    android_phone
    android_tablet

Usage looks like:

    my $dua = Selenium::Remote::Driver::UserAgent->new(
        browserName => 'chrome',
        agent => 'ipad_seven'
    );

## orientation

Optional: specify the orientation of the mobile device. Your options
are `portrait` or `landscape`; defaults to `portrait`.

# AUTHOR

Daniel Gempesaw <gempesaw@gmail.com>

# COPYRIGHT AND LICENSE

This software is copyright (c) 2014 by Daniel Gempesaw.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
