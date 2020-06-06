---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: bd6aeb32e0994bceb9e56bcb1c6267f4cb64a5a4
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73039146"
---
# \<bindingExtensions>

<span data-ttu-id="595aa-101">En esta sección se habilita el uso de un enlace definido por el usuario desde un equipo o archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="595aa-101">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="595aa-102">Puede agregar un enlace definido por el usuario a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en un enlace definido por el usuario, así como el atributo de `name` al nombre del enlace definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="595aa-102">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>

<span data-ttu-id="595aa-103">Las extensiones de enlace permiten al usuario crear enlaces definidos por el usuario para el uso como parte de una configuración de extremo.</span><span class="sxs-lookup"><span data-stu-id="595aa-103">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="595aa-104">Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="595aa-104">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>

<span data-ttu-id="595aa-105">En el ejemplo siguiente se usa el `add` elemento, así como el `name` atributo para agregar una extensión de enlace a la `bindingExtensions` sección del archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="595aa-105">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingExtensions` section of the configuration file:</span></span>

```xml
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```

<span data-ttu-id="595aa-106">Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingSection`.</span><span class="sxs-lookup"><span data-stu-id="595aa-106">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="595aa-107">Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.</span><span class="sxs-lookup"><span data-stu-id="595aa-107">For more information on this, see the <xref:System.Configuration> documentation.</span></span>

<span data-ttu-id="595aa-108">Una vez definidos el elemento y su tipo de configuración, la extensión se puede usar como parte de un extremo, tal como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="595aa-108">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example:</span></span>

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a><span data-ttu-id="595aa-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="595aa-109">See also</span></span>

- [<span data-ttu-id="595aa-110">Extensión de enlaces</span><span class="sxs-lookup"><span data-stu-id="595aa-110">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
