Spree Brazilian Fields [![Build Status](https://travis-ci.org/zaeznet/spree_zaez_brazilian_fields.svg?branch=master)](https://travis-ci.org/zaeznet/spree_zaez_brazilian_fields)
====================

This gem add some brazilian fields to user class.

For the personal account is added CPF, RG, birth date and gender.
For the business account is added CNPJ, state registry and contact name.
For both accounts is added name and permission to send newsletter and SMS.

In general settings, it's possible enable/disable if the receive_sms field it should be displayed.
To set the settings through a config file, you can modify the value like so:

```ruby
Spree::Config[:sms_permission] = true
```

Installation
------------

Add spree_zaez_brazilian_fields to your Gemfile:

```ruby
gem 'spree_zaez_brazilian_fields', github: 'zaeznet/spree_zaez_brazilian_fields'
```

Bundle your dependencies and run the installation generator:

```shell
bundle
bundle exec rails g spree_zaez_brazilian_fields:install
```

Override
------------

```
spree/admin/users/_form.html.erb
```

Deface
------------

```
Backend
* add_sms_permission => spree/admin/general_settings/edit.hrml.erb

Frontend
* add_brazilian_field          -> spree/shared/_user_form.html.erb
* add_name_to_form             -> spree/shared/_user_form.html.erb
* add_user_account_constructor -> spree/user_registrations/new.html.erb
* add_id_to_form               -> spree/users/edit.html.erb
* add_user_account_constructor -> spree/users/edit.html.erb
* add_brazilian_fields         -> spree/users/show.html.erb
```

Testing
-------

First bundle your dependencies, then run `rake`. `rake` will default to building the dummy app if it does not exist, then it will run specs. The dummy app can be regenerated by using `rake test_app`.

```shell
bundle
bundle exec rake
```

When testing your applications integration with this extension you may use it's factories.
Simply add this require statement to your spec_helper:

```ruby
require 'spree_zaez_brazilian_fields/factories'
```

Copyright (c) 2015 Zaez Inovação Digital, released under the New BSD License

License
-------

The MIT License (MIT)

Copyright (c) 2015 Zaez Inovação Digital

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
