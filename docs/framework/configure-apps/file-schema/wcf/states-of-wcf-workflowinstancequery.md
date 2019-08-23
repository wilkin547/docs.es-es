---
title: <states>de WCF,<workflowInstanceQuery>
ms.date: 03/30/2017
ms.assetid: d17f7525-8035-4e9e-85a0-4cddae59f85d
ms.openlocfilehash: ef4ce4b6fa6e60ead10b196b10a7c1489e15ac25
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938982"
---
# <a name="states-of-wcf-workflowinstancequery"></a>\<indica > de WCF, \<workflowInstanceQuery >

Representa una colección de estados suscritos de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crean los registros del seguimiento.  
  
Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md) .  
  
\<system.serviceModel> \<tracking>  
\<perfiles >  
\<trackingProfile>  
\<> de flujo de trabajo  
\<workflowInstanceQueries>  
\<workflowInstanceQuery>  
\<states>  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <workflowInstanceQueries>
          <workflowInstanceQuery>
            <states>
              <state name="Name" />
            </states>
          </workflowInstanceQuery>
        </workflowInstanceQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  

Ninguno.  
  
### <a name="child-elements"></a>Elementos secundarios
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<states>](state-of-wcf-workflowinstancequery.md)|Un estado suscrito de la instancia de flujo de trabajo de la que se ha realizado el seguimiento cuando se crea el registro del seguimiento.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|DESCRIPCIÓN|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../windows-workflow-foundation/workflowinstancequery.md)|Una consulta que realiza el seguimiento de los cambios del ciclo de vida de la instancia de flujo de trabajo, como por ejemplo, un evento iniciado o completado.|  
  
## <a name="remarks"></a>Comentarios

Los registros devueltos se filtran por los estados de esta colección.  
  
En la siguiente tabla se describen los valores de estado posibles.  
  
|Estado|DESCRIPCIÓN|  
|-----------|-----------------|  
|Anulado|Se ha anulado la instancia de flujo de trabajo.|  
|Completada|Se ha completado la instancia de flujo de trabajo.|  
|Deleted|Se ha eliminado la instancia de flujo de trabajo.|  
|Inactivo|La instancia de flujo de trabajo está inactiva.|  
|Conservado|Se ha guardado la instancia de flujo de trabajo.|  
|Reanudado|Se ha reanudado la instancia de flujo de trabajo.|  
|Started|Se ha iniciado la instancia de flujo de trabajo.|  
|UnhandledException|La instancia de flujo de trabajo ha detectado una excepción no controlada.|  
|Descargado|Se ha descargado la instancia de flujo de trabajo.|  
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
      <state name="Started" />
    </states>
  </workflowInstanceQuery>
</workflowInstanceQueries>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Seguimiento y traza de flujos de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md)
