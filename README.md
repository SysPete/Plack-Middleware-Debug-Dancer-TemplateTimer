# NAME

Plack::Middleware::Debug::Dancer::TemplateTimer - Template and layout rendering timer for Dancer

# VERSION

0.001

# SYNOPSIS

To activate this panel:

    plack_middlewares:
      Debug:
        - panels
        -
          - Dancer::TemplateTimer

Or by manually creating an app.psgi, that might contain:

    builder {
        enable 'Debug', panels => ['Dancer::TemplateTimer'];
        $app;
    };

# DESCRIPTION

This middleware adds timers around calls to ["render" in Dancer::Template::Abstract](https://metacpan.org/pod/Dancer::Template::Abstract#render)
and ["layout" in Dancer::Template::Abstract](https://metacpan.org/pod/Dancer::Template::Abstract#layout) to track the time spent rendering
the template and the layout for the page.

This module uses ["install\_modifier" in Class::Method::Modifiers](https://metacpan.org/pod/Class::Method::Modifiers#install_modifier) rather than
adding hooks since we want to be sure we are only timing the template engine
and not other code inside hooks.

# AUTHOR

Peter Mottram (SysPete), `<peter at sysnix.com>`

# LICENSE AND COPYRIGHT

Copyright 2016 Peter Mottram (SysPete).

This program is free software; you can redistribute it and/or modify it
under the terms of either: the GNU General Public License as published
by the Free Software Foundation; or the Artistic License.

See [http://dev.perl.org/licenses/](http://dev.perl.org/licenses/) for more information.
