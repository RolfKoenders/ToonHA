# Toon Home Assistant component

The toon component platform can be used to control your Toon thermostat. It uses the toonapilib library by Costas Tyfoxylos (https://github.com/costastf/toonapilib). This component adds a climate device for your Toon thermostat and sensors for power and gas consumption.

Installation
===

On your Home Assistant instance, go to \<config directory\>/custom_components. Create folders named binary_sensor, sensor, climate and switch, if they don't already exist. Now copy the files:
```
toon.py ---> <config directory>/custom_components
binary_sensor/toon.py ---> <config directory>/custom_components/binary_sensor
climate/toon.py ---> <config directory>/custom_components/climate
sensor/toon.py ---> <config directory>/custom_components/sensor
switch/toon.py ---> <config directory>/custom_components/switch
```

Configuration
===

To use this custom component you will need to setup your own app using a Toon developer account. Don't worry, this will take a few minutes at most and is completely free of charge.

1. Go to [developer.toon.eu/user/register](https://developer.toon.eu/user/register), fill in your details and accept the ToS.
2. You should get an email with an activation link, click it, complete your account signup and make sure you log in.
3. Open the [My Apps](https://developer.toon.eu/user/me/apps) page and click on "Add a new App".
4. Enter an app name ("hass" for example), set the Callback URL to `localhost` and be sure to check the box next to "Toon" under "Product". You can now create your new app.
5. Go back to the [My Apps](https://developer.toon.eu/user/me/apps) page and click on the newly created app. This should give you the required `consumer_key` and `consumer_secret`.

To add Toon to Home Assistant, add the following to your configuration.yaml file:

```
# Example configuration.yaml entry
toon:
    username: YOUR_USERNAME
    password: YOUR_PASSWORD
    consumer_key: API_CONSUMER_KEY
    consumer_secret: API_CONSUMER_SECRET
```
- **username** (*Required*): Username for Mijn Eneco.
- **password** (*Required*): Password for Mijn Eneco.
- **consumer_key** (*Required*): The consumer key of your Toon App.
- **consumer_secret** (*Required*): The consumer secret of your Toon App.

Note that the `username` and `password` fields should contain your Mijn Eneco (Toon app) credentials and should not be confused with your Toon developer account details.
