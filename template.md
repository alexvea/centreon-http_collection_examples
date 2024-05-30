## Description ##
Here put the description of the json http collection.

## List of constants used ##
| Constant  | description |
| ------------- | ------------- |
|--constant='CONSTANT_NAME=CONSTANT_VALUE' | Constant description  |
|... | ...  |
|... | ...  |

Note that for a constant to be usable, you need to add it inside the json like %(constants.CONSTANT_NAME) and on the plugin command like --constant='CONSTANT_NAME=CONSTANT_VALUE'

## Example ##
````
sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin apps::protocols::http::plugin --mode collection --constant='CONSTANT_NAME=CONSTANT_VALUE' --constant='CONSTANT_NAME2=CONSTANT_VALUE2' --constant='CONSTANT_NAME3=CONSTANT_VALUE3' --config /tmp/name_of_collection.json
````
same plugin command :
````
sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin apps::protocols::http::plugin --mode collection \
--constant='CONSTANT_NAME=CONSTANT_VALUE' \
--constant='CONSTANT_NAME2=CONSTANT_VALUE2' \
--constant='CONSTANT_NAME3=CONSTANT_VALUE3' \
--config /tmp/name_of_collection.json
````
OK output : 

````
Example of the OK output
````
WARNING output :

````
Example of the WARNING output
````

CRITICAL output :

````
Example of the CRITICAL output
````

## Use case ##

Bug : example

Monitoring : example

## Improvement ## 

List the possible improvement of the json
