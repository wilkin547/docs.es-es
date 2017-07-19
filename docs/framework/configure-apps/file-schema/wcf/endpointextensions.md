---
title: "&lt;endpointExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;endpointExtensions&gt;
En esta sección se registra un nuevo extremo estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación.  Puede agregar un extremo estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de extremo, así como el atributo `name` en el nombre del extremo estándar.  
  
 El ejemplo siguiente usa el elemento `add`, así como el atributo `name` para agregar un extremo estándar a la sección `<endpointExtensions>` del archivo de configuración.  
  
```  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 Una vez registrado el extremo estándar, puede usarlo como se muestra en el siguiente ejemplo.  En el elemento [\<extremo\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md), el atributo `kind` especifica el tipo de extremo estándar registrado en la sección `<endpointExtensions>`.  El atributo `endpointConfiguration` será idéntico al atributo `name` del elemento de configuración del extremo estándar en la sección `<standardEndpoints>`.  
  
```  
  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
  
```