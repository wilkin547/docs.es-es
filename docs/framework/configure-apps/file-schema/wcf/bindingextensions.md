---
title: '&lt;bindingExtensions&gt;'
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: f99b38ede66dbecb44f9e8e67f921943071672ca
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltbindingextensionsgt"></a><span data-ttu-id="66133-102">&lt;bindingExtensions&gt;</span><span class="sxs-lookup"><span data-stu-id="66133-102">&lt;bindingExtensions&gt;</span></span>
<span data-ttu-id="66133-103">En esta sección se habilita el uso de un enlace definido por el usuario desde un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="66133-103">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="66133-104">Puede agregar un enlace definido por el usuario a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en un enlace definido por el usuario, así como el atributo de `name` al nombre del enlace definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="66133-104">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="66133-105">Las extensiones de enlace permiten al usuario crear enlaces definidos por el usuario para el uso como parte de una configuración de extremo.</span><span class="sxs-lookup"><span data-stu-id="66133-105">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="66133-106">Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="66133-106">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="66133-107">El ejemplo siguiente utiliza el elemento `add`, así como el atributo de `name` para agregar una extensión obligatoria a la sección `bindingElementExtensions` del archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="66133-107">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="66133-108">Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="66133-108">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="66133-109">Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="66133-109">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="66133-110">Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como parte del punto de conexión como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="66133-110">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
```  
  
## <a name="see-also"></a><span data-ttu-id="66133-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="66133-111">See Also</span></span>  
 [<span data-ttu-id="66133-112">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="66133-112">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
