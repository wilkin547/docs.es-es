---
title: "Elemento &lt;Directives&gt; (.NET Native) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Elemento &lt;Directives&gt; (.NET Native)
Elemento raíz de cada archivo de directivas de tiempo de ejecución para [!INCLUDE[net_native](../../../includes/net-native-md.md)].  
  
 **\<Directives xmlns\="http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"\>**  
  
## Sintaxis  
  
```xml  
  
        <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`xmlns`|El espacio de nombres XML.  Su valor es siempre **"http:\/\/schemas.microsoft.com\/netfx\/2013\/01\/metadata"**.|  
  
## Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<Application\>](../../../docs/framework/net-native/application-element-net-native.md)|Actúa como contenedor para los miembros de tipos y los tipos de toda la aplicación cuyos metadatos están disponibles para la reflexión.|  
|[\<Library\>](../../../docs/framework/net-native/library-element-net-native.md)|Define el ensamblado cuyos tipos secundarios y miembros de tipo requieren metadatos en tiempo de ejecución.|  
  
## Comentarios  
 Cada archivo de directivas de tiempo de ejecución solo puede contener un elemento `<Directives>`.  
  
 El elemento `<Directives>` puede contener cero o un elemento [\<Application\>](../../../docs/framework/net-native/application-element-net-native.md), y cero, uno o más elementos [\<Library\>](../../../docs/framework/net-native/library-element-net-native.md).  
  
## Vea también  
 [Referencia del archivo de configuración de directivas en tiempo de ejecución \(rd.xml\)](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)   
 [Elementos de directivas en tiempo de ejecución](../../../docs/framework/net-native/runtime-directive-elements.md)