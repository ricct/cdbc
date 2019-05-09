# CDBC Client Configuration
---------------------------------------
CDBC Service use WCF architecture. WCF information should be set in the app.config file.

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


# Creating CdbcConnection  
---------------------------------------
C#
```c#
//Same as ODP.net,  
string connString = "Data Source=(DESCRIPTION =(ADDRESS_LIST =(ADDRESS = (PROTOCOL = TCP)(HOST = ***.***.***.***)(PORT = 1521)))(CONNECT_DATA =(SERVICE_NAME = ***)));Persist Security Info=True;User ID=*;Password=*";
CdbcConnection conn = new CdbcConnection(connString);

conn.DatabaseProduct = CdbcCommon.Data.Client.Type.DatabaseProductType.Oracle;
conn.UserId = "unittest";
conn.Psk = "***************";

```


# Querying with the DataReader  
---------------------------------------

![エビフライトライアングル](/img/111.jpg "サンプル")

C#
```c#
//Same as ODP.net,  
string connString = "Data Source=(DESCRIPTION =(ADDRESS_LIST =(ADDRESS = (PROTOCOL = TCP)(HOST = ***.***.***.***)(PORT = 1521)))(CONNECT_DATA =(SERVICE_NAME = ***)));Persist Security Info=True;User ID=*;Password=*";
CdbcConnection conn = new CdbcConnection(connString);

conn.DatabaseProduct = CdbcCommon.Data.Client.Type.DatabaseProductType.Oracle;
conn.UserId = "unittest";
conn.Psk = "***************";

CdbcCommand cmd = new CdbcCommand("SELECT * FROM ALL_TABLES", conn);
DbDataReader dr = cmd.ExecuteReader();

while (dr.Read())
{
    Console.WriteLine(String.Format("{0}", dr[0]));
}
```

VB.Net
```vb.net
string connectionString = "DataSource=C:\\My.accdb";

using (AccessConnection connection = new AccessConnection(connectionString)) {
  AccessCommand cmd = new AccessCommand("SELECT * FROM Orders", connection);

  AccessDataReader rdr = cmd.ExecuteReader();

  while (rdr.Read()) {
    Console.WriteLine(String.Format("\t{0} --> \t\t{1}", rdr["ShipName"], rdr["ShipCity"]));
  }
}
```


# Querying with the DataAdapter  
---------------------------------------
CdbcAdapter's Fill method can retrieve data from the data source having save  syntax with other sql client.  

C#
```c#
string connectionString = "DataSource=C:\\My.accdb";

using (AccessConnection connection = new AccessConnection(connectionString)) {
  AccessCommand cmd = new AccessCommand("SELECT * FROM Orders", connection);

  AccessDataReader rdr = cmd.ExecuteReader();

  while (rdr.Read()) {
    Console.WriteLine(String.Format("\t{0} --> \t\t{1}", rdr["ShipName"], rdr["ShipCity"]));
  }
}
```

VB.Net
```vb.net
string connectionString = "DataSource=C:\\My.accdb";

using (AccessConnection connection = new AccessConnection(connectionString)) {
  AccessCommand cmd = new AccessCommand("SELECT * FROM Orders", connection);

  AccessDataReader rdr = cmd.ExecuteReader();

  while (rdr.Read()) {
    Console.WriteLine(String.Format("\t{0} --> \t\t{1}", rdr["ShipName"], rdr["ShipCity"]));
  }
}
```

# Update with the DataAdapter  
---------------------------------------


# ExecuteNonQuery with the CdbcCommand  
---------------------------------------


# ExecuteScalar with the CdbcCommand  
---------------------------------------



* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs help` - Print this help message.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
