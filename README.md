# IP-location-tracker

This is an IP location tracker made in Python 3.6, using the [urllib.request](https://docs.python.org/3/library/urllib.request.html)
 module and the [GeoJs](https://www.geojs.io/) API to get geolocation data.
 
 ## Usage
 
 `geo` is pretty simple to use and can provide with all the necessary details about an IP address such as:
 - Country (both abbreviation and full name).
 - Region (the area within a country in which the IP address is located).
 - City.
 - Timezone.
 - Latitude.
 - Longitude.
 - Organization name.
 
Below there are some examples that demonstrate `geo`'s usage:

__Getting IP address of host:__
```
import geo

ip = geo.getIP()
```
__Getting country origin of IP address:__

(The address below is one of the IP address range that Google uses.)


This will return plain text by default, as we haven't set the second argument.

```
country = geo.getCountry('121.37.54.10')
```
Result:
```
US
```
This will return the country's full name.
```
country = geo.getCountry('121.37.54.10', 'plainfull')
```
Result: 
```
Cameroon
```
This will return a json response which will contains all formats of country's name and the responding IP address.
```
country = geo.getCountry('121.37.54.10', 'json')
```
Result: 
```
{'country': 'CM', 'ip': '154.72.160.159', 'country_3': 'CMR', 'name': 'Cameroon'}
```

__Getting geolocation data of IP address:__
```
geoData = geo.getGeoData('121.37.54.10')
```
Returns:
```
{'ip': '154.72.160.159', 'organization_name': 'Camtel', 'asn': 15964, 'organization': 'AS15964 Camtel', 'area_code': '0', 'timezone': 'Africa/Douala', 'country_code': 'CM', 'country_code3': 'CMR', 'continent_code': 'AF', 'accuracy': 1000, 'longitude': '12.5', 'latitude': '6', 'country': 'Cameroon'}
```

__Getting a summary of all information about an IP address:__
```
geo.showIpDetails('154.72.160.159')
```
The output will be:
```
----------------------------------------------------------------------
                             HOST DETAILS
----------------------------------------------------------------------
Country:                                          China
Ip:                                               121.37.54.10
Organization name:                                Huawei Cloud Service data center
Asn:                                              55990
Organization:                                     AS55990 Huawei Cloud Service data center
Area code:                                        0
Timezone:                                         Asia/Shanghai
Country code:                                     CN
Country code3:                                    CHN
Continent code:                                   AS
Accuracy:                                         1000
Longitude:                                        113.722
Latitude:                                         34.7732
Country:                                          China
----------------------------------------------------------------------
```
__Getting country details for an IP address:__
```
geo.showCountryDetails(' 121.37.54.10')
```
This will return:
```
----------------------------------------------------------------------
                           COUNTRY DETAILS
----------------------------------------------------------------------
Country:                                          CN
Ip:                                               121.37.54.10
Country 3:                                        CHN
Name:                                             China
----------------------------------------------------------------------

```





