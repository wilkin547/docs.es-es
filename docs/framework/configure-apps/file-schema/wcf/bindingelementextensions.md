---
title: <bindingElementExtensions>
ms.date: 03/30/2017
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
ms.openlocfilehash: 9a2a3af093949c1d724fdea13655bbb80fe71048
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55270477"
---
# <a name="bindingelementextensions"></a><span data-ttu-id="dbcc7-101">\<bindingElementExtensions></span><span class="sxs-lookup"><span data-stu-id="dbcc7-101">\<bindingElementExtensions></span></span>
<span data-ttu-id="dbcc7-102">En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-102">This section enables the use of a custom binding element from a machine or application configuration file.</span></span> <span data-ttu-id="dbcc7-103">Puede agregar un elemento de enlace personalizado a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en una extensión de elemento de enlace, así como el atributo de `name` al elemento de enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-103">You can add a custom binding element to this collection by using the `add` keyword, and setting the `type` attribute of the element to a binding element extension, as well as the `name` attribute to the custom binding element.</span></span>  
  
 <span data-ttu-id="dbcc7-104">Las extensiones de enlace le permiten al usuario crear elementos de enlace definidos por el usuario para el uso como parte de enlaces personalizados.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-104">Binding extensions enable the user to create user-defined binding elements for use as part of custom bindings.</span></span> <span data-ttu-id="dbcc7-105">Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.BindingElement>.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.BindingElement>.</span></span> <span data-ttu-id="dbcc7-106">En el archivo de configuración, la sección `bindingElementExtensions` se utiliza para definir un elemento de extensión.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-106">In the configuration file, the `bindingElementExtensions` section is used to define an extension element.</span></span>  
  
 <span data-ttu-id="dbcc7-107">El ejemplo siguiente utiliza el elemento `add`, así como el atributo de `name` para agregar una extensión obligatoria a la sección `bindingElementExtensions` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
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
  
 <span data-ttu-id="dbcc7-108">Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingElementExtensionSection`.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-108">To add configuration abilities to the element, the user needs to write and register a `bindingElementExtensionSection` element.</span></span> <span data-ttu-id="dbcc7-109">Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="dbcc7-110">Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como parte del enlace personalizado como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dbcc7-110">After the element and its configuration type are defined, the extension can be used as part of a custom binding as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbcc7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbcc7-111">See also</span></span>
- <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>
- [<span data-ttu-id="dbcc7-112">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="dbcc7-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
