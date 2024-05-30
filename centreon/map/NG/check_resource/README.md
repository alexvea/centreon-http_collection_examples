## Description ##
This json allow you to check if a resource (by his configuration id), is present or not on a specific map view 

## List of constants used ##
| Constant  | description |
| ------------- | ------------- |
|--constant='hostname=10.25.15.53' | MAP NG ip address  |
|--constant='protocol=http' | MAP NG protocol  |
|--constant='port=8081' | MAP NG port  |
|--constant='username=centreon_map'  | MAP user  |
|--constant='password=centreon_map_PASSWORD'  | MAP user pwd  |
|--constant='map_id=1046'  | map id (see screenshot)  |
|--constant='view_id=1045' | view id (see screenshot)  |
|--constant='resource_id=13' | resource id (from configuration page)  |

![image](https://github.com/alexvea/http_collection_examples/assets/35368807/a0673cb6-0cdb-498d-8864-e3323aac24d2)


## Example ##
````
sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin  apps::protocols::http::plugin --mode collection  --constant='hostname=10.25.15.53' --constant='protocol=http' --constant='port=8081'  --constant='username=centreon_map' --constant='password=centreon_map_PASSWORD' --constant='map_id=1046' --constant='view_id=1045' --constant='resource_id=13'  --config /tmp/get_view_resource_id_map_NG.json
````
same plugin command :
````
sudo -u centreon-engine /usr/lib/centreon/plugins/centreon_protocol_http.pl --plugin  apps::protocols::http::plugin --mode collection \
--constant='hostname=10.25.15.53' --constant='protocol=http' --constant='port=8081' \
--constant='username=centreon_map' --constant='password=centreon_map_PASSWORD' \
--constant='map_id=1046' --constant='view_id=1045' --constant='resource_id=13' \
--config /tmp/get_view_resource_id_map_NG.json
````
OK output : 

````
OK: Resource found in map view | 'resource.count'=1;0;;0;1
````

CRITICAL output :

````
CRITICAL: resource : 0 | 'resource.count'=0;0;;0;0
````
## Use case ##

Bug : to check for ressource that disappear suddently on MAP NG

## Improvement ##

This only works if there is no other widgets of same resource id present in the view.
