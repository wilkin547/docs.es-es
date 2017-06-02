---
title: "&lt;bindingElementExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;bindingElementExtensions&gt;
En esta sección se habilita el uso de un elemento de enlace personalizado de un equipo o archivo de configuración de la aplicación.  Puede agregar un elemento de enlace personalizado a esta colección utilizando la palabra clave `add` y estableciendo el atributo de `type` del elemento en una extensión de elemento de enlace, así como el atributo de `name` al elemento de enlace personalizado.  
  
 Las extensiones de enlace le permiten al usuario crear elementos de enlace definidos por el usuario para el uso como parte de enlaces personalizados.  Desde el punto de vista de la programación, una extensión de enlace es un tipo que implementa la clase abstracta <xref:System.ServiceModel.Channels.BindingElement>.  En el archivo de configuración, la sección `bindingElementExtensions` se utiliza para definir un elemento de extensión.  
  
 El ejemplo siguiente utiliza el elemento `add`, así como el atributo de `name` para agregar una extensión obligatoria a la sección `bindingElementExtensions` del archivo de configuración.  
  
```  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Para agregar las capacidad de configuración al elemento, las necesidades de usuario de escribir y registrar un elemento `bindingElementExtensionSection`.  Para obtener más información, consulte la documentación existente sobre <xref:System.Configuration>.  
  
 Después de la definición del elemento y de su tipo de configuración, se puede utilizar la extensión como parte del enlace personalizado como se muestra en el ejemplo siguiente.  
  
```  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)