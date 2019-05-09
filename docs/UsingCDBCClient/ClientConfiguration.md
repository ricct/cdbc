# CDBC Client Configuration
---------------------------------------
CDBC Service use WCF architecture. WCF information should be set in the app.config file.


# Sample XML
---------------------------------------

```XML
<system.serviceModel>
    <bindings>
      <webHttpBinding>
        <binding name="BasicHttpBinding_ICdbcService" maxReceivedMessageSize="10485760" useDefaultWebProxy="false"/>
      </webHttpBinding>
      <basicHttpBinding>
        <binding name="BasicHttpBinding_ICdbcService" maxReceivedMessageSize="10485760" useDefaultWebProxy="false"
                 sendTimeout="00:10:00"
                     />
      </basicHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://cdbc.cloud/cdbcservice/CdbcService.svc/service" binding="basicHttpBinding" bindingConfiguration="BasicHttpBinding_ICdbcService"
          contract="CdbcService.ICdbcService" name="CdbcService.ICdbcService"  />
    </client>
    <behaviors>
      <endpointBehaviors>
        <behavior name="webhttp">
          <webHttp/>
          <soapProcessing />
        </behavior>
      </endpointBehaviors>
    </behaviors>
  </system.serviceModel>
```

client-endpoint  
* `address` - URL of CDBC service.

# Details
---------------------------------------

