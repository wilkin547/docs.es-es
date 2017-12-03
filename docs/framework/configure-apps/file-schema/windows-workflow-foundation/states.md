---
title: '&lt;Estados&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e5e9050a01cf58c3c103fdbe4e8b22e173efaf5c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="ltstatesgt"></a>&lt;Estados&gt;
Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.  
  
 Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel >  
\<seguimiento >  
\<trackingProfile >  
\<flujo de trabajo >  
\<workflowInstanceQueries >  
\<workflowInstanceQuery >  
\<Estados >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
 Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<estado >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<workflowInstanceQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.|  
  
## <a name="remarks"></a>Comentarios  
 Los registros devueltos se filtran por los estados de esta colección.  
  
 En la siguiente tabla se describen los valores de estado posibles.  
  
|Estado|Descripción|  
|-----------|-----------------|  
|Anulado|Se ha anulado la instancia de flujo de trabajo.|  
|Completado|Se ha completado la instancia de flujo de trabajo.|  
|Deleted|Se ha eliminado la instancia de flujo de trabajo.|  
|Inactivo|La instancia de flujo de trabajo está inactiva.|  
|Conservado|Se ha guardado la instancia de flujo de trabajo.|  
|Reanudado|Se ha reanudado la instancia de flujo de trabajo.|  
|Comenzado|Se ha iniciado la instancia de flujo de trabajo.|  
|UnhandledException|La instancia de flujo de trabajo ha detectado una excepción no controlada.|  
|Unloaded|Se ha descargado la instancia de flujo de trabajo.|  
|Cancelado|Se ha cancelado la instancia de flujo de trabajo.|  
|Suspendido|Se suspende la instancia de flujo de trabajo.|  
|Terminado|Se ha terminado la instancia de flujo de trabajo.|  
|No suspendido|No se suspende la instancia de flujo de trabajo.|  
  
## <a name="example"></a>Ejemplo  
 La siguiente configuración se suscribe a los registros de seguimiento de nivel de instancia de flujo de trabajo del estado de instancia `Started` mediante esta consulta.  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>       
 [Seguimiento y traza de flujos de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
