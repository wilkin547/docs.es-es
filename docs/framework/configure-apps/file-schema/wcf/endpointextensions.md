---
description: 'Más información acerca de: <endpointExtensions>'
title: <endpointExtensions>
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: d9684ccfab868b1b0d5fe9e054a3a97912712324
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664761"
---
# \<endpointExtensions>

<span data-ttu-id="21bfc-102">En esta sección se registra un nuevo extremo estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="21bfc-102">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="21bfc-103">Puede agregar un punto de conexión estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de punto de conexión, así como el atributo `name` en el nombre del punto de conexión estándar.</span><span class="sxs-lookup"><span data-stu-id="21bfc-103">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="21bfc-104">El ejemplo siguiente usa el elemento `add`, así como el atributo `name` para agregar un extremo estándar a la sección `<endpointExtensions>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="21bfc-104">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="21bfc-105">Una vez registrado el punto de conexión estándar, puede usarlo como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="21bfc-105">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="21bfc-106">En el [\<endpoint>](endpoint-element.md) elemento, el `kind` atributo especifica el tipo de punto de conexión estándar que se ha registrado en la `<endpointExtensions>` sección.</span><span class="sxs-lookup"><span data-stu-id="21bfc-106">In the [\<endpoint>](endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="21bfc-107">El `endpointConfiguration` atributo será idéntico al `name` atributo del elemento de configuración del extremo estándar en la `<standardEndpoints>` sección.</span><span class="sxs-lookup"><span data-stu-id="21bfc-107">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
