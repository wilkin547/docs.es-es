---
title: '&lt;endpointExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
ms.openlocfilehash: 6c80b9edb2da9368c0f53be7068d638b045ac19c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointextensionsgt"></a><span data-ttu-id="eb12e-102">&lt;endpointExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="eb12e-102">&lt;endpointExtensions&gt;</span></span>
<span data-ttu-id="eb12e-103">En esta sección se registra un nuevo punto de conexión estándar en la sección de extensiones en un archivo de configuración de un equipo o aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb12e-103">This section registers a new standard endpoint in the extensions section in a machine or application configuration file.</span></span> <span data-ttu-id="eb12e-104">Puede agregar un extremo estándar a esta colección usando la palabra clave `add` y estableciendo el atributo `type` del elemento en el tipo de extremo, así como el atributo `name` en el nombre del extremo estándar.</span><span class="sxs-lookup"><span data-stu-id="eb12e-104">You can add a standard endpoint to this collection by using the `add` keyword, and setting the `type` attribute of the element to the endpoint type, as well as the `name` attribute to the name of the standard endpoint.</span></span>  
  
 <span data-ttu-id="eb12e-105">El ejemplo siguiente usa el elemento `add`, así como el atributo `name` para agregar un extremo estándar a la sección `<endpointExtensions>` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="eb12e-105">The following example uses the `add` element, as well as the `name` attribute to add a standard endpoint to the `<endpointExtensions>` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="eb12e-106">Una vez registrado el punto de conexión estándar, puede usarlo como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="eb12e-106">After the standard endpoint has been registered, you can use it as shown in the following example.</span></span> <span data-ttu-id="eb12e-107">En el [ \<extremo >](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) elemento, el `kind` atributo especifica el tipo de punto de conexión estándar que se ha registrado en la `<endpointExtensions>` sección.</span><span class="sxs-lookup"><span data-stu-id="eb12e-107">In the [\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) element, the `kind` attribute specifies the standard endpoint type that has been registered in the `<endpointExtensions>` section.</span></span> <span data-ttu-id="eb12e-108">El `endpointConfiguration` será idéntico al atributo el `name` atributo del elemento de configuración del punto de conexión estándar en la `<standardEndpoints>` sección.</span><span class="sxs-lookup"><span data-stu-id="eb12e-108">The `endpointConfiguration` attribute will be identical to the `name` attribute of the configuration element of the standard endpoint in the `<standardEndpoints>` section.</span></span>  
  
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
