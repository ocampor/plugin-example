# Custom Plugin Example

This is an example of a custom rescore plugin that is based on the original 
[rescore plugin example](https://github.com/elastic/elasticsearch/tree/master/plugins/examples/rescore). 
Besides the plugin, the project includes the configuration files to install the plugin and start Elasticsearch and
debug the source files.

## Test

```
gradle test yamlRestTest
```

## Start Elasticsearch

```
gradle run
```
