---
description: 'Más información acerca de: <endToEndTracing>'
title: <endToEndTracing>
ms.date: 03/30/2017
ms.assetid: 5034f5de-bb60-4157-9ad4-58aaade094e0
ms.openlocfilehash: 2ac4a7563d7d7881cdb503e843d34f84fd9c95a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782122"
---
# \<endToEndTracing>

Elemento de configuración que le permite habilitar y deshabilitar aspectos diferentes de traza de un extremo a otro durante el funcionamiento de una aplicación de servicio.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<diagnostics>**](diagnostics.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<endToEndTracing>**  
  
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
|[\<diagnostics>](diagnostics.md)|Define la configuración de WCF para la inspección y el control en tiempo de ejecución para el administrador.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.DiagnosticSection>
- <xref:System.ServiceModel.Diagnostics>
- <xref:System.ServiceModel.Configuration.DiagnosticSection.EndToEndTracing%2A>
- <xref:System.ServiceModel.Configuration.EndToEndTracingElement>
- [Seguimiento de un extremo a otro](../../../wcf/diagnostics/tracing/end-to-end-tracing.md)
