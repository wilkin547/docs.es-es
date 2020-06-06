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
<span data-ttu-id="b9948-101">En esta sección se registra un nuevo extremo estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="b9948-101">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="b9948-102">Puede agregar un punto de conexión estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de punto de conexión, así como el atributo `name` en el nombre del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="b9948-102">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="b9948-103">El ejemplo siguiente usa el elemento `add`, así como el atributo `name` para agregar un extremo estándar a la sección `<endpointExtensions>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="b9948-103">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="b9948-104">Una vez registrado el punto de conexión estándar, puede usarlo como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b9948-104">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="b9948-105">En el [\<endpoint>](endpoint-element.md) elemento, el `kind` atributo especifica el tipo de punto de conexión estándar que se ha registrado en la `<endpointExtensions>` sección.</span><span class="sxs-lookup"><span data-stu-id="b9948-105">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="b9948-106">El `endpointConfiguration` atributo será idéntico al `name` atributo del elemento de configuración del extremo estándar en la `<standardEndpoints>` sección.</span><span class="sxs-lookup"><span data-stu-id="b9948-106">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
