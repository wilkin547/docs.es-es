---
title: '&lt;endToEndTracing&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a43801f4c45d7ac518c3b24cadc58ffbec40adb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltendtoendtracinggt"></a>&lt;endToEndTracing&gt;
Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un punto de conexión a otro durante el funcionamiento de una aplicación de servicio.  
  
 \<sistema. ServiceModel >  
\<diagnóstico >  
\<endToEndTracing >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<system.serviceModel>  
   <diagnostics>  
       <endToEndTracing activityTracing="Boolean"  
          messageFlowTracing="Boolean"  
          propagateActivity="Boolean" />  
   </diagnostics>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`activityTracing`|Valor booleano que especifica si está habilitada la traza de actividad.|  
|`messageFlowTracing`|Valor booleano que especifica si está habilitada la traza del flujo de mensajes.|  
|`propagateActivity`|Valor booleano que especifica si el atributo de propagación está establecido en true.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<diagnóstico >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.|  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Configuration.DiagnosticSection>  
 <xref:System.ServiceModel.Diagnostics>  
 <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>  
 <xref:System.ServiceModel.Configuration.EndToEndTracingElement>  
 [Traza de un extremo a otro](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)
