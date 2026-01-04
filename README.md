📩 SMS Module Installation & Usage

This module provides a simple and clean way to send SMS messages using Laravel’s Service Provider and Facade architecture.

1️⃣ Configuration

First, create a configuration file for the SMS module.

📁 Path:

config/sms.php


📄 Content:

<?php

return [
    'username' => env('SMS_USERNAME'),
    'password' => env('SMS_PASSWORD'),
];


Then, add the required credentials to your .env file:

SMS_USERNAME=your_sms_username
SMS_PASSWORD=your_sms_password

2️⃣ Register the Service Provider

Next, you need to register the SMS module service provider.

📁 Path:

bootstrap/services/providers.php


📄 Add the provider to the array:

<?php

return [
    App\Providers\AppServiceProvider::class,
    App\Modules\Sms\SmsServiceProvider::class,
];


This step ensures that Laravel properly loads and boots the SMS module.

3️⃣ Using the SMS Facade

After registering the service provider, you can access the SMS module methods via its Facade.

📌 Import the Facade:

use App\Modules\Sms\Facades\Sms;


📌 Example Usage:

Sms::send('09123456789', 'Your verification code is 1234');


The Facade provides a clean and expressive interface to interact with the SMS service without dealing directly with the underlying implementation.

✅ Summary

Configuration is handled via config/sms.php

Sensitive credentials are stored securely in .env

The module is loaded through a custom Service Provider

All SMS functionalities are accessible via a Laravel Facade

This structure keeps the module modular, testable, and easy to maintain.