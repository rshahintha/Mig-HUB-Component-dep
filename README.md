# Digital Enable Platform (DEP)



| Branch | Build Status |
| :------------ |:-------------
| master | [![Build Status](http://ci.wso2telco.com/job/component-dep/badge/icon)](http://ci.wso2telco.com/job/component-dep/)


This is the platform for both the product Digital Enable Hub &  Digital Enable Gateway .This includes all the required components for managing web components , mediator component, analytic tools etc..


If you are using api-invocation-handler-1.0.0.jar to invoke Mobile Connect APIs through HUB,

1. Copy the api-invocation-handler-1.0.0.jar file to <HUB_HOME>/repository/componenet/dropins/ 
2. Place the  mig_aouth_token.properties file in <HUB HOME>/repository/conf/ location.
3. Edit the API synapse to add below handler at the top of handlers
  ```
  <handler class="com.wso2telco.dep.apihandler.ApiInvocationHandler"/>
  ```

4. For token, userinfo API synapse add the below snippet additionaly before ```<send> ``` tag of ```<inSequence> ```
```
<property xmlns:ns="http://org.apache.synapse/xsd"  
          name="Authorization"  
          expression="$ctx:tempAuthVal"  
          scope="transport"/>
                ```

