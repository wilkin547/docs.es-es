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

En esta sección se habilita el uso de un enlace definido por el usuario desde un equipo o archivo de configuración de la aplicación. Puede agregar un enlace definido por el usuario a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en un enlace definido por el usuario, así como el atributo de `name` al nombre del enlace definido por el usuario.

Las extensiones de enlace permiten al usuario crear enlaces definidos por el usuario para el uso como parte de una configuración de extremo. Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.Binding>.

En el ejemplo siguiente se usa el `add` elemento, así como el `name` atributo para agregar una extensión de enlace a la `bindingExtensions` sección del archivo de configuración:

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

Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingSection`. Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.

Una vez definidos el elemento y su tipo de configuración, la extensión se puede usar como parte de un extremo, tal como se muestra en el ejemplo siguiente:

```xml
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```

## <a name="see-also"></a>Consulte también

- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
