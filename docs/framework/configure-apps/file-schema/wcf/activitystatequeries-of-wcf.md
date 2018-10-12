---
title: '&lt;activityStateQueries&gt; de WCF'
ms.date: 10/08/2018
ms.assetid: 9e45db49-ed85-4fdf-bd65-0d5477e31823
ms.openlocfilehash: 081dc297912ed5735dd51111936b85b61f463d2d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123246"
---
# <a name="ltactivitystatequeriesgt-of-wcf"></a>&lt;activityStateQueries&gt; de WCF

Representa una colección de consultas que se usan para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo. Por ejemplo, desea realizar un seguimiento de cada vez que se complete la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo. Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad. Los estados de suscripción disponibles se especifican en ActivityStates.

Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).

\<system.serviceModel>  
\<seguimiento >  
\<perfiles de >  
\<trackingProfile >  
\<flujo de trabajo >  
\<activityStateQueries >  

## <a name="syntax"></a>Sintaxis  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <activityStateQueries>
          <activityStateQuery activityName="String">
            <arguments>
              <argument name="String"/>
            </arguments>
            <states>
              <state name="String"/>
            </states>
            <variables>
              <variable name="String"/>
            </variables>
          </activityStateQuery>
        </activityStateQueries>
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

|Elemento|Descripción|
|-------------|-----------------|
|[\<activityStateQuery >](activitystatequery-of-wcf.md)|Una consulta que se utiliza para realizar el seguimiento del control de errores que se producen dentro de una actividad.  Este evento se produce cada vez que un FaultHandler procesa un error.|

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<flujo de trabajo >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad `activityDefinitionId`.|

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElementCollection>    
- <xref:System.Activities.Tracking.ActivityStateQuery>    
- [Seguimiento y traza de flujos de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
- [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
