---
title: '&lt;faultPropagationQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: fabafbc8-3e45-4feb-8321-0725e9f4079c
ms.openlocfilehash: c3853c470a9243835e071d35008dfff5b885591d
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49123324"
---
# <a name="ltfaultpropagationquerygt-of-wcf"></a>&lt;faultPropagationQuery&gt; de WCF

Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.  Este evento se produce cada vez que un FaultHandler procesa un error. Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad. La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.  
  
Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md).  
  
\<system.serviceModel>  
\<seguimiento >  
\<perfiles de >  
\<trackingProfile >  
\<flujo de trabajo >  
\<faultPropagationQueries >  
\<faultPropagationQuery >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <faultPropagationQueries>
          <faultPropagationQuery faultSourceActivityName="String"
                                 faultHandlerActivityName="String"/>
        </faultPropagationQueries>
      </workflow>
    </trackingProfile>
  </profiles>
</tracking>
```
  
## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|`faultSourceActivityName`|Una cadena que especifica el nombre de la actividad del controlador de errores que propagó el error. El valor predeterminado es \*, lo que indica que los registros de propagación de errores se devuelven para todas las actividades.|  
|`faultHandlerActivityName`|Una cadena que especifica el nombre de la actividad que originó el error.|  
  
### <a name="child-elements"></a>Elementos secundarios

Ninguno.
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<faultPropagationQueries>](faultpropagationqueries-of-wcf.md)|Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.  Este evento se produce cada vez que un FaultHandler procesa un error.|
  
## <a name="see-also"></a>Vea también  
 
- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Seguimiento y traza de flujos de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
