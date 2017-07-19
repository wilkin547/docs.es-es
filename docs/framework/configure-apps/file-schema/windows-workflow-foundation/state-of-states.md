---
title: "&lt;state&gt; de &lt;states&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ab483c7f-a091-4933-ba6b-708d96846d38
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;state&gt; de &lt;states&gt;
Un elemento de configuración que contiene el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.  
  
 Para obtener más información sobre las consultas de los perfiles de seguimiento, consulte [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Sintaxis  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <activityStateQueries>  
             <activityStateQuery activityName="String" />  
                <states>  
                   <state name="String"/>  
                </states>  
          </activityStateQueries>  
       </workflow>  
   </trackingProfile>  
</tracking>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena que especifica el estado de la actividad suscrita para la que se debería emitir un registro de seguimiento.|  
  
### Elementos secundarios  
 Ninguno.  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states-of-activitystatequery.md)|Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.|  
  
## Comentarios  
 Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.  Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.  Puede usar los elementos [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. En el siguiente ejemplo se muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.  Los argumentos y las variables solo se pueden extraer con ActivityStateRecord y, de esa forma, se suscriben dentro de un perfil de seguimiento mediante [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
```  
  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
  
```  
  
## Vea también  
 [System.ServiceModel.Activities.Tracking.Configuration.StateElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.StateElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)