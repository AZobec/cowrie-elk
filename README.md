# cowrie-elk
ELK templates to have a kikoo-nice-looking view of cowrie logs in ELK

![Alt Text](/images/kibana-dashboard-cowrie.png)

## Step 1 - install elasticsearch templates
You will find in ./elasticsearch templates for adding geoip support to IP, and to handle cowrie in only one shard and 0 replica (for a single cluster node).

## Step 2 - Configure logstash to send data
You will find in ./logstash 3 files for :
	* input : will check a specific file
	* filter : will add geoip, reverse dns, ...
	* output : will send cowrie logs to a daily index

## Step 3 - Kibana
In kibana, you will need to create an index pattern for cowrie-*

Then you will be able to import ./kibana/kibana-savedobjects-cowrie.ndjson by using the import function in kibana.

(The import function is located in "Management/Saved Objects" at url : http://mykibana:5601/app/kibana#/management/kibana/objects?_g=() )
