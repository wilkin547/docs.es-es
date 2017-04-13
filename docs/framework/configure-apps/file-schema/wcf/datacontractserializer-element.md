---
title: "&lt;dataContractSerializer&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "<dataContractSerializer> (elemento)"
  - "DataContractSerializer"
  - "dataContractSerializer (elemento)"
  - "KnownTypes"
ms.assetid: f41fb4d5-24e7-4059-8010-286a30bfea93
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# &lt;dataContractSerializer&gt;
Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.  Este elemento se produce en dos jerarquías diferentes.  Uno aparece en la lista de la siguiente sección, Jerarquía del esquema, y el otro se enumera en la sección Comentarios.  
  
## Sintaxis  
  
```  
  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
   maxItemsInObjectGraph="Integer" />  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|ignoreExtensionDataObject|Un valor booleano que especifica si se omiten los datos proporcionados por el extremo cuando se serializa o deserializa.  Este atributo se puede configurar sólo en `<dataContractSerializer>` bajo el elemento `<behavior>`.|  
|maxItemsInObjectGraph|Un entero que especifica el número máximo de elementos para serializar o deserializar.  Este atributo es 65536.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md)|Una colección de valores para el comportamiento de un servicio.|  
|[\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)|Representa el elemento raíz para la sección de espacio de nombres <xref:System.Runtime.Serialization> y contiene elementos para establecer opciones de <xref:System.Runtime.Serialization.DataContractSerializer>.|  
  
## Comentarios  
 Tal como se indica en la Introducción de este tema, esta es la segunda jerarquía en la que se produce el elemento \<X509Extension\>.  
  
 [\<system.runtime.serialization\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-runtime-serialization.md)  
  
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
  
 Para obtener más información sobre los tipos conocidos, consulte <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [Transferencia y serialización de datos](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)