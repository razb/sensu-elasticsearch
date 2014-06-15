# sensu-elasticsearch

This repository contains a Sensu extension for [Elasticsearch](http://elasticsearch.org):
It accepts metrics in graphite format. 
Note: if you want to append metadata tags to your metrics in elasticsearch then add the tags to your client definition in the sensu client.json.
e.g.

<pre>
{
  "client": {
    "name": "myserver",
    "environment": "TEST",
    "address": "10.1.1.141",
    "subscriptions": [ "linux","linux_metrics","webservers" ],
    "tags" : { "os":"linux", "applications": [ "sensu","apache","haproxy" ], "role":"appserver" },
    "safe_mode": false
  }
}
</pre>

## Installation

The elasticsearch and patron gems are required

    gem install elasticsearch
    gem install patron
    
    copy elastic.rb to /etc/sensu/extensions/handlers
    and elastic.json to /etc/sensu/conf.d

## Usage

   edit elastic.json
   and modify with the appropriate host, index and type values
   
## License

This software is licensed under the Apache 2 license, quoted below.

    Copyright (c) 2013 Elasticsearch <http://www.elasticsearch.org>

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
