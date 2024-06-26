# Remote Control of PSA car
### This is a Python program to control and get information from a PSA car.
I test it with a Peugeot e-208, but it works with other PSA vehicles (Citroen, Opel, Vauxhall, DS).

With this app you will be able to:
 - get the status of the car (battery level for electric vehicle, position ... )
 - start and stop the charge
 - set a charge threshold to limit the battery level to a certain percentage
 - set a stop hour to charge your vehicle only on off-peak hours
 - control air conditioning
 - control lights and horn if your vehicle is compatible
 - lock and unlock doors
 - get consumption statistics
 - visualize your trips on a map or in a table
 - get the list of car charging  
 - visualize battery charging curve
 - visualize altitude trip curve
 - get car charging CO2 emission
 - get car charging price
 - send live data to ABetterRoutePlanner

The official API is documented [here](https://developer.groupe-psa.io/webapi/b2c/quickstart/connect/#article) but it is not totally up to date, and contains some errors. 


 ## I. Installation
- [Installation as Home Assistant addon](https://github.com/JbbDE/psacc-ha/blob/main/psacc-ha/README.md)  
- [Installation in Docker](docs/Docker.md)
 ## II. Use the API

Look at [API documentation](./docs/psacc_api.md)

## III. Use the dashboard

You can add the -r argument to record the position of the vehicle and retrieve this information in a dashboard.

``python3 psa-car-controller -f config.json -c charge_config.json -r``
    
You will be able to visualize your trips, your consumption and some statistics:
    
     
![Screenshot_20210128_104519](https://user-images.githubusercontent.com/48728684/106119895-01c98d80-6156-11eb-8969-9e8bc24f3677.png)
- You have to add an API key from https://home.openweathermap.org/ in your config file, to be able to see your consumption vs exterior temperature.
- You have to add an API key from https://co2signal.com/ to have your CO2 emission by KM (in France the key isn't needed). 
### IV. Charge price calculation
The dashboard can give you the price by kilometer and price by kw that you pay.
You just have to set the price in the config file.

After a successful launch of the app, a config.ini file will be created.
In this file you can set the price you pay for electricity in the following format "0.15".

If you have a special price during the night you can set "night price", "night hour start" and "night hour end". 
Hours need to be in the following format "23h12".

You can modify a price manually in the dashboard. It can be useful if you use public charge point.
## V. Connection to other services:
- [HomeAssistant](https://github.com/Flodu31/HomeAssistant-PeugeotIntegration)


## FAQ
If you have a problem or a question, please check if the answer isn't already in the [FAQ](FAQ.md). 

## Contribute
If you need information to contribute or edit this program go [here](docs/Develop.md).


