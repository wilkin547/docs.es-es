---
title: "&lt;customTrackingQuery&gt; de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 164446ae-8440-4b67-b217-6786cfae1e01
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;customTrackingQuery&gt; de WCF
Representa una colección de consultas que se utilizan para realizar el seguimiento de los eventos que defina en sus actividades de código.  La consulta es necesaria para que un participante de seguimiento se suscriba a los registros del seguimiento personalizados.  
  
 Para obtener más información sobre las consultas de los perfiles de seguimiento, consulte [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Sintaxis  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|activityName|Una cadena que especifica el nombre de la actividad que generó el registro del seguimiento.|  
|name|Una cadena que especifica el nombre del registro de seguimiento personalizado que se emite.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<customTrackingQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/customtrackingquery.md)|Una consulta que se utiliza para realizar el seguimiento de los eventos que defina en sus actividades de código.|  
  
## Vea también  
 [System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection](assetId:///System.ServiceModel.Activities.Tracking.Configuration.CustomTrackingQueryElementCollection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.CustomTrackingQuery](assetId:///System.Activities.Tracking.CustomTrackingQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)