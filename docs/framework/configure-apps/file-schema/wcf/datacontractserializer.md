---
title: "dataContractSerializer | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# dataContractSerializer
Contiene los datos de configuración para <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
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
|ignoreExtensionDataObject|Un valor booleano que especifica si se omiten los datos proporcionados por el extremo, cuando se serializa o deserializa.|  
|maxItemsInObjectGraph|Un entero que especifica el número máximo de elementos para serializar o deserializar.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un extremo.|  
  
## Comentarios  
 Para obtener más información sobre los tipos conocidos, vea la documentación <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
> [!CAUTION]
>  El elemento de comportamiento `<dataContractSerializer>` \(si está presente\) debe aparecer siempre antes del elemento de comportamiento `<enableWebScript>` del archivo de configuración.  En caso contrario, el comportamiento resultante no está definido.  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>   
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>   
 [Tipos conocidos de contratos de datos](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [Transferencia y serialización de datos](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)