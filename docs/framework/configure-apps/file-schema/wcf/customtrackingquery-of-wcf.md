---
title: '&lt;customTrackingQuery&gt; de WCF'
ms.date: 03/30/2017
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
ms.openlocfilehash: e13064afbd9f5dbc8d7216eb384001e1e005785c
ms.sourcegitcommit: d88024e6d6d8b242feae5f4007a709379355aa24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2018
ms.locfileid: "49316238"
---
# <a name="ltcustomtrackingquerygt-of-wcf"></a>&lt;customTrackingQuery&gt; de WCF

Representa una consulta que se usa para realizar un seguimiento de eventos que defina en sus actividades de código. La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.

Para obtener más información sobre las consultas de perfil de seguimiento, vea [perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<seguimiento >  
\<perfiles de >  
\<trackingProfile >  
\<flujo de trabajo >  
\<customTrackingQueries >  
\<customTrackingQuery >  
  
## <a name="syntax"></a>Sintaxis  
  
```xml
<tracking>
  <profiles>
    <trackingProfile name="Name">
      <workflow>
        <customTrackingQueries>
          <customTrackingQuery activityName="String"
                               name="String"/>
        </customTrackingQueries>
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
|`activityName`|Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.|  
|`name`|Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.|  
  
### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|  
|-------------|-----------------|  
|[\<customTrackingQueries >](customtrackingqueries-of-wcf.md)|Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.|
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.CustomTrackingQuery?displayProperty=nameWithType>
- [Seguimiento y traza de flujos de trabajo](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
