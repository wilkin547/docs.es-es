---
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: fe57cb84cfa70b1f6b92abf1dbac89ddad9d4dc8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "69925709"
---
# \<endpointExtensions>
En esta sección se registra un nuevo extremo estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación. Puede agregar un punto de conexión estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de punto de conexión, así como el atributo `name` en el nombre del punto de conexión estándar.  
  
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
  
 Una vez registrado el punto de conexión estándar, puede usarlo como se muestra en el siguiente ejemplo. En el [\<endpoint>](endpoint-element.md) elemento, el `kind` atributo especifica el tipo de punto de conexión estándar que se ha registrado en la `<endpointExtensions>` sección. El `endpointConfiguration` atributo será idéntico al `name` atributo del elemento de configuración del extremo estándar en la `<standardEndpoints>` sección.  
  
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
      <standardEndpoint name="udpConfig"
                        multicastAddress="soap.udp://239.255.255.250:3703"
                        ... />
    </udpDiscoveryEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
