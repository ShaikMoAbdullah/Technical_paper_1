<br />

# Elasticsearch, Solr, and Lucene

## Table of Contents
 What is Elasticsearch?
   * What is it used for?
   * Why use Elasticsearch?
* What is Solr?
   * Features of solr
* What is Lucene?
   * Why use Lucene?
* Which one should we choose to solve our problem?
* References

<br />

# What is Elasticsearch? 
Elasticsearch is a **distributed**, **free** and **open search** and **analytics and full text search engine** Its often used for enabling search functionality for various types of *data*.
 Amazon AWS has integrated with Elasticsearch to make **Amazon Elasticsearch Service** that makes it easy to **deploy**, **operate** and **scale** Elasticsearch in the AWS Cloud.

* You can imagine this when you shop using amazon. We search for an item in a search box and that's an **Unstructured search**. 

* When you click on any item recommended by Amazon on the home page, that is a **Structured search**.
* If you **sort** the items from cheap to high on the products page as I do, that is facilitated using Elasticsearch.
* Now the items have filled the page and we need to click on **Next** to go to the next page. And, that is too facilitated using Elasticsearch.

<br />
<p align = 'center'>
<img src="https://blog.bismart.com/hs-fs/hubfs/Imported_Blog_Media/Elastic%20Search/Elasticsearch%20GIF.gif?width=900&name=Elasticsearch%20GIF.gif" alt="elasticsearch" width="400"/>
</p>
<br />

 [Elasticsearch](https://github.com/elastic) is built on **Apache Lucene** and was first released in 2010 and is known for its **simple REST APIs**, **distributed nature**, **speed**, and **scalability**.

## What is it used for?
* Application search
* Website search
* Enterprise search
* Logging and log analytics
* Infrastructure metrics and container monitoring
* Application performance monitoring
* Geospatial data analysis and visualization
* Security analytics
* Business analytics

<br />
<p align = 'center'>
<img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt50671ed5bbad50f3/608fbbdc2d1d221032193ff1/illustration-balance-cost.png" alt="Free" width="400"/>
</p>
<br />


## Why use Elasticsearch?
* Elasticsearch offers [REST APIs](https://www.elastic.co/guide/en/elasticsearch/reference/current/rest-apis.html), a simple HTTP interface, and uses schema-free JSON documents, making it easy to get started and quickly build applications for a variety of use-cases.

* **Elasticsearch is distributed**. The distributed nature of Elasticsearch enables it to process large volumes of data in **parallel**, quickly finding the best matches for your queries.


<p align = 'center'>
<img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt61799e12d10f4581/5e6158f8dc0f1706df255d1c/illustration-elasticsearch-resiliency-555.png" alt="Distributed" width="400"/>
</p>

* **Complimentary tools and plugins**. Elasticsearch comes integrated with **Kibana**, *a popular visualization and reporting tool*. It also offers integration with **Beats** and **Logstash**, while enabling you to easily transform source data and load it into your Elasticsearch cluster.

* Elasticsearch supports a variety of **programming languages** and Elasticsearch supports **34** majorly text languages. Some of them are:
   * Java
   * Python
   * Go
   * .Net
   * PHP
   * Perl
   * Ruby 

* Elasticsearch comes with a wide set of features. In addition to its **speed**, **scalability**, and **resiliency**, Elasticsearch has several powerful built-in features that make storing and searching data even more efficient, such as data rollups and index lifecycle management.


<p align = 'center'>
<img src="https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt8c328002d82e303e/5d0d573477f34fd55839b61f/illustration-elasticsearch-scalability-555.png" alt="Scalability" width="400"/>
</p>


 Let's understand some queries here. Curl is a command-line tool to transfer data to or from a server. Here, We are requesting a search in a products index for a type of product which is a thinkpadx240 laptop. This is just a simple query. More to it can be found [here](https://github.com/elastic/elasticsearch).

```
curl -X GET 'localhost:9200/products/product/_search?q=thinkpadx240'
```


 Some Technology companies using solr are Github, Uber, Shopify, Facebook, Udemy, Slack, etc.

<br />

# What is Solr?
* Solr is a JAVA-based [open source enterprise search client](https://youtu.be/0tH36OfNwNw). It's built around Lucene which is a high-performance search engine library.

* Solr is the popular, **blazing-fast**, **open source enterprise search platform**, built on Apache Lucene™. It could is integrated with **Apache Hadoop** and therefore is also capable of using with **Big data**.

* Solr is a **standalone enterprise search server** with a REST-like API. You put documents in it via JSON, XML, CSV, or binary over HTTP.

<br />

## Features of solr
* Advanced **full-text search capabilities**: Searching document in full text database by using **phrases**, **wildcards**, **joins**, **grouping** and much more across any data type.

* Optimized for **high volume traffic**: Solr is proven helpful at extremely large scales of data coming in.

* **Near real-time operations**:  Tasks such as **reading** or **writing** data usually take less than a second to complete. This lets you use Elasticsearch for near real-time use cases such as **application monitoring** and **anomaly detection**. This makes solr operations use **less** time.

* Comprehensive **administration interfaces**: Solr ships with a built-in, responsive administrative user interface to make it easy to control your Solr instances. Solr also has **database integrations** like MongoDB, HBase, Cassandra.

* **Highly scalable** and **fault-tolerant**: Solr makes it easy to scale up and down. Solr also features *replication*, *distribution*, *rebalancing* and *fault tolerance*. Solr can also accommodate **rich document handling**.

* **Flexible and adaptable** with easy configuration: Solr's is designed to adapt to your needs all while simplifying configuration.

<br />

 Some Technology companies using solr are Flipkart, Instagram, Intuit, Apple, Chegg, eBay, etc.

<br />

# What is Lucene?
 It is a powerful JAVA search library that lets you easily add search or retrieval of information to applications.
 It is not a server, but an embedded library is mostly misunderstood.
 [The structure of Apache Lucene shown in various versions](https://dzone.com/articles/structure-apache-lucene)

<br />

## Why use Lucene?

* **Scalable** and ** high-performance indexing**.

* **Powerful**, **accurate** and efficient search algorithms.

* **Open-source**, hence scalable.

* Implementations of other programming languages are also available.

 Some companies using Lucene are Nike, Walmart, Peraton, etc.

<br />


# Conclusion
 Considering switching to a different database for full text searching to improve performance, We could go for Elasticsearch because of its innumerable benefits.

* Elasticsearch is cloud-ready out of the box which makes it reliable in times of systems failure.
* Elasticsearch runs a search index on multiple servers which makes it reliable in times of systems failure.
* Performance-wise, Both Elasticsearch and Solr are the same.
* Elasticsearch is simpler to work with. Unlike solr, Elasticsearch is a single process with real-time updates making it engaging and helpful in tracking status.  

<br />

# References

* [What is ElasticSearch](https://www.elastic.co/what-is/elasticsearch)
* [Elasticsearch - Beyond Full-text Search • Alex Reelsen • GOTO 2013](https://youtu.be/yWNiRC_hUAw)
* [Amazon ElasticSearch Service]([amkette.com/my-account/orders/](https://aws.amazon.com/elasticsearch-service/the-elk-stack/what-is-elasticsearch/))
* [Why ElasticSearch](https://www.elastic.co/elasticsearch/)
* [All about ElasticSearch](https://youtu.be/yZJfsUOHJjg)
* [How can I use ElasticSearch](https://qbox.io/blog/what-is-elasticsearch)
* [Solr introduction](https://solr.apache.org/)
* [Features of Solr](https://solr.apache.org/features.html)
* [System design of Solr](https://youtu.be/0tH36OfNwNw)
* [Difference between solr and lucene](https://stackoverflow.com/questions/15704644/difference-between-solr-and-lucene#:~:text=Similarly%2C%20Lucene%20is%20a%20programmatic,use%20out%2Dof%2Dbox.&text=Solr%20is%20built%20on%20top%20of%20lucene%20to%20provide%20a%20search%20platform.&text=SOLR%20is%20a%20wrapper%20over,and%20Lucene%20is%20its%20engine.)

* [Amazon Elastic Service](https://aws.amazon.com/elasticsearch-service/)
