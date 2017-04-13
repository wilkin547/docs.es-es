---
title: "&lt;activityScheduledQuery&gt; de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 25f6eee1-3d98-4c39-b517-c0813f03f106
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;activityScheduledQuery&gt; de WCF
Representa una colección de consultas que se utilizan para realizar el seguimiento de una actividad programada para su ejecución por parte de una actividad primaria.  La consulta es necesaria para que un participante de seguimiento se suscriba a los registros programados de la actividad.  
  
 Para obtener más información sobre las consultas de los perfiles de seguimiento, consulte [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Sintaxis  
  
```vb  
  
<tracking>  
     <trackingProfile name="Name">  
       <workflow>  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
       </workflow>  
     </trackingProfile>  
</tracking>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|activityName|Una cadena que especifica el nombre de la actividad que está solicitando la cancelación.|  
|childActivityName|Una cadena que especifica el nombre de la actividad secundaria para la que se solicitó la cancelación.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<activityScheduledQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activityscheduledquery.md)|Una consulta que se usa para realizar el seguimiento de una actividad programada para ser ejecutada por una actividad primaria.|  
  
## Vea también  
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityScheduledQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityScheduledQuery](assetId:///System.Activities.Tracking.ActivityScheduledQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)