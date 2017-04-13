---
title: "&lt;callbackDebug&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;callbackDebug&gt;
Especifica la depuración de servicio para un objeto de devolución de llamada [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## Sintaxis  
  
```  
  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## Tipo  
 `Type`  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`includeExceptionDetailInFaults`|Un valor que especifica si los objetos de devolución de llamada de cliente devuelven información de excepción administrada en errores SOAP al servicio.<br /><br /> Si establece este atributo en `true` de manera programática, puede habilitar el flujo de información de excepción administrada en un objeto de devolución de llamada de cliente al servicio de depuración. **Caution:**  Devolver información de excepción administrada a los clientes puede ser un riesgo para la seguridad.  Esto es porque los detalles de excepción exponen información acerca de la implementación de servicio interna que podría ser usada por clientes no autorizados.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<comportamiento\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Especifica el comportamiento de un extremo.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>   
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>