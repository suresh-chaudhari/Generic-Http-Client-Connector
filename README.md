Generic Http Client Connector
=============================

The Connector is designed as generic way using apache library. 
Using this HTTP Client Connector, You can communicate withing any URL or Restful API.
You can easily send the data as input stream and in the form of query param. 


Usage
=============================

``` Java

//Base URL
private static String baseUrl = "http://localhost:8080/Servlet/test";

// Create Http Connector Object to make request
HttpConnector httpConnector = new HttpConnector();

//Set content Type and charset in HttpContent constructor
HttpContent content = new HttpContent("application/json", HttpConstant.UTF_8); 


//send Reqquest body data as input stream, you can send json,xml string.
//uncomment the below code of setRequestEntityData entity if you want to send data in Request body

content.setRequestEntityData("Send Request Body data as stream");

OR

// You can send data either as also query param using below commented method
// Note: set any one data either queryparmadata or request entity data

Map<String, String> queryParamData = new HashMap<String, String>();
queryParamData.put("req", testReq);
content.setRequestDataMap(queryParamData);


//If url needs credential to authenticate, provide credential as below format
//If it does not needs you don't need to be set
//you don't need to set the username and password content Object....

content.setUsername("admins");
content.setUsername("password@123");

//execute httpconnector method here E.X: post,get,put,delete 
HttpConnectorResponse response = httpConnector.post(testUrl, content);


```
