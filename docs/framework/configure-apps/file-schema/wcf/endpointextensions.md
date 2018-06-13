---
title: '&lt;endpointExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 6c80b9edb2da9368c0f53be7068d638b045ac19c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752356"
---
# <a name="ltendpointextensionsgt"></a>&lt;endpointExtensions&gt;
En esta sección se registra un nuevo punto de conexión estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación. Puede agregar un extremo estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de extremo, así como el atributo `name` en el nombre del extremo estándar.  
  
 El ejemplo siguiente usa el elemento `add`, así como el atributo `name` para agregar un extremo estándar a la sección `<endpointExtensions>` del archivo de configuración.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 Una vez registrado el punto de conexión estándar, puede usarlo como se muestra en el siguiente ejemplo. En el [ \<extremo >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento, el `kind` atributo especifica el tipo de punto de conexión estándar que se ha registrado en la `<endpointExtensions>` sección. El `endpointConfiguration` será idéntico al atributo el `name` atributo del elemento de configuración del punto de conexión estándar en la `<standardEndpoints>` sección.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
```
