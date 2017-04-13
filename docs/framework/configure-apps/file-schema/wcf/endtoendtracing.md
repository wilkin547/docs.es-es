---
title: "&lt;endToEndTracing&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;endToEndTracing&gt;
Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.  
  
## Sintaxis  
  
```  
  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|`activityTracing`|Valor booleano que especifica si está habilitada la traza de actividad.|  
|`messageFlowTracing`|Valor booleano que especifica si está habilitada la traza del flujo de mensajes.|  
|`propagateActivity`|Valor booleano que especifica si el atributo de propagación está establecido en true.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<diagnóstico\>](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.|  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>   
 <xref:System.ServiceModel.Diagnostics>   
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>   
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>   
 [Seguimiento de traza de un extremo a otro](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)