#Introduction to NEO


This is where your introduction to NEO's world start, here you will learn how the messages are composed what to expect on the responses and what parts of them are important for your application.

 Here we will introduce you to the two call architecture of NEO and explain why is important, we will also talk about the different parts of the NEO servers.


 For the examples bellow we will use:

 * The Orchestration Server: https://o-us-east-1a-service-vianeodev1.neo.intralinks.com

   * The Location Path: /location

   * The Entitlement Path: /entitlement

* The Content Server: https://c01-il-bos-service-vianeodev1.neo.intralinks.com

   * The Assets Path: /asset

   * The Search Path: /search

All the work from the app server can be split in two sections. one the requests to access information (the most common ones, going to the location path) and the request to update the entitlements (going to the entitlement path).

