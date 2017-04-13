---
title: "&lt;bindingExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;bindingExtensions&gt;
En esta sección se habilita el uso de un enlace definido por el usuario desde un equipo o archivo de configuración de la aplicación.  Puede agregar un enlace definido por el usuario a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en un enlace definido por el usuario, así como el atributo de `name` al nombre del enlace definido por el usuario.  
  
 Las extensiones de enlace permiten al usuario crear enlaces definidos por el usuario para el uso como parte de una configuración de extremo.  Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.Binding>.  
  
 El ejemplo siguiente utiliza el elemento `add`, así como el atributo de `name` para agregar una extensión obligatoria a la sección `bindingElementExtensions` del archivo de configuración.  
  
```  
<system.serviceModel>  
    <extensions>  
        <bindingExtensions>  
           <add name="MyBinding" type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingSection`.  Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.  
  
 Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como parte del extremo como se muestra en el ejemplo siguiente.  
  
```  
<services>  
    <service name="MyService">  
        <endpoint address="myAddress" binding="MyBinding" />  
    </service>  
</services>  
  
```  
  
## Vea también  
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)