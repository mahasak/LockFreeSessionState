Lock-free session state module for ASP.NET
==========================================

Discussion: http://stackoverflow.com/a/25231036/991267

Usage
-----

### HashTable module

Uses Hashtable-based implementation from MSDN.

* Install the package.

    ```
    Install-Package Heavysoft.LockFreeSessionState.HashTable
    ```
* These lines will be added to web.config:

    ```xml
      <system.webServer>
        <modules>
          <remove name="Session" />
          <add name="Session" type="Heavysoft.Web.SessionState.HashTableSessionStateModule,Heavysoft.LockFreeSessionState.HashTable,PublicKeyToken=ea16f0ccebd288da" />      
        </modules>
      </system.webServer>
    ```

* Lock-free session module will be loaded instead of the standard ASP.NET SessionStateModule.

https://www.nuget.org/packages/Heavysoft.LockFreeSessionState.HashTable/

### SOSS module

Uses ScaleOut StateServer software.

```
Install-Package Heavysoft.LockFreeSessionState.Soss
```

https://www.nuget.org/packages/Heavysoft.LockFreeSessionState.Soss/

Custom storage
--------------

* Install the common package.

    ```
    Install-Package Heavysoft.LockFreeSessionState.Common
    ```
* Inherit the **LockFreeSessionStateModule** class. Implement abstract methods.

https://www.nuget.org/packages/Heavysoft.LockFreeSessionState.Common/
