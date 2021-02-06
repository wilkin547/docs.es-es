---
description: 'Más información acerca de: <bindingElementExtensions>'
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: 4c1b4b924906b1a6dc143588a057129ca5ce8f40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639424"
---
# \<bindingElementExtensions>

En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación. Puede agregar un elemento de enlace personalizado a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en una extensión de elemento de enlace, así como el atributo de `name` al elemento de enlace personalizado.  
  
 Las extensiones de enlace le permiten al usuario crear elementos de enlace definidos por el usuario para el uso como parte de enlaces personalizados. Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.BindingElement>. En el archivo de configuración, la sección `bindingElementExtensions` se utiliza para definir un elemento de extensión.  
  
 El ejemplo siguiente utiliza el elemento `add`, así como el atributo de `name` para agregar una extensión obligatoria a la sección `bindingElementExtensions` del archivo de configuración.  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingElementExtensions>
      <add name="udpTransport"
           type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingElementExtensions>
  </extensions>
</system.serviceModel>
```  
  
 Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingElementExtensionSection`. Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.  
  
 Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como parte del enlace personalizado como se muestra en el ejemplo siguiente.  
  
```xml  
<customBinding>
  <binding name="test2">
    <udpTransport />
    <binaryMessageEncoding maxReadPoolSize="211"
                           maxWritePoolSize="2132"
                           maxSessionSize="3141" />
  </binding>
</customBinding>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
