---
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 6b23728451a051f21ad3863b9a29e6290c3c837a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919013"
---
# <a name="endtoendtracing"></a>\<endToEndTracing>
Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.  
  
 \<system.ServiceModel>  
\<> de diagnóstico  
\<endToEndTracing>  
  
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
  
|Atributo|DESCRIPCIÓN|  
|---------------|-----------------|  
|`activityTracing`|Valor booleano que especifica si está habilitada la traza de actividad.|  
|`messageFlowTracing`|Valor booleano que especifica si está habilitada la traza del flujo de mensajes.|  
|`propagateActivity`|Valor booleano que especifica si el atributo de propagación está establecido en true.|  
  
### <a name="child-elements"></a>Elementos secundarios  
 Ninguno.  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<diagnostics>](diagnostics.md)|Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [Traza de un extremo a otro](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
