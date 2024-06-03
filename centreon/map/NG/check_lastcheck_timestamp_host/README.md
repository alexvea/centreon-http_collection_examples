## Description ##
This json allows you to check the last check timestamp of a host (by his configuration id) of MAP NG.

## List of constants used ##
| Constant  | description |
| ------------- | ------------- |
|--constant='hostname=10.25.15.53' | MAP NG ip address  |
|--constant='protocol=http' | MAP NG protocol  |
|--constant='port=8081' | MAP NG port  |
|--constant='username=centreon_map'  | MAP user  |
|--constant='password=centreon_map_PASSWORD'  | MAP user pwd  |
|--constant='host_id=13  | host id (from configuration page)   |


## Example ##
````
 sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin  apps::protocols::http::plugin --mode collection --constant='hostname=10.25.15.53' --constant='protocol=http' --constant='port=8081'  --constant='username=centreon_map' --constant='password=centreon_map_PASSWORD' --constant='host_id=13' --config /tmp/http_get_lastcheck_timestamp_host_map_NG.json --verbose
````
same plugin command :
````
sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin apps::protocols::http::plugin --mode collection \
--constant='hostname=10.25.15.53' --constant='protocol=http' --constant='port=8081'
--constant='username=centreon_map' --constant='password=centreon_map_PASSWORD'
--constant='host_id=13'
--config /tmp/http_get_lastcheck_timestamp_host_map_NG.json --verbose
````
Working output : 

````
OK: Timestamp retrieved | 'resource.last_check.timestamp'=1717432270;0;;0;
Resource type 'host' - name 'Central' : Last check timestamp='1717432270'
````

Not working output (when host id is not existing):

````
UNKNOWN: Cannot decode response (add --debug option to display returned content) 
````
## Use case ##

Bug : to check for ressource last check timestamp.

## Improvement ##

You might add --verbose to get the long output.
