---
title: "&lt;activityStateQuery&gt; de WCF | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d6cdc04b-6f3a-4097-a623-ee4a1be3b5c4
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;activityStateQuery&gt; de WCF
Representa una consulta que se usa para realizar el seguimiento de los cambios del ciclo de vida de las actividades que constituyen una instancia de flujo de trabajo.  Por ejemplo, puede que desee realizar el seguimiento de todas las veces que se completa la actividad "Enviar correo electrónico" dentro de una instancia de flujo de trabajo.  Esta consulta es necesaria para que un participante de seguimiento se suscriba a los objetos de registro de estado de actividad.  Los estados de suscripción disponibles se especifican en ActivityStates.  
  
 Para obtener más información sobre las consultas de los perfiles de seguimiento, vea [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Sintaxis  
  
```vb  
  
<tracking>  
   <trackingProfile name="Name">  
       <workflow>  
          <activityStateQueries>  
             <activityStateQuery activityName="String" />  
                <arguments>  
                   <argument name="String"/>  
                </arguments>  
                <states>  
                   <state name="String"/>  
                </states>  
                <variables>  
                   <variable name="String"/>  
                </variables>  
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
|activityName|Una cadena que especifica el nombre de la actividad en la que filtrar las instancias <xref:System.Activities.Tracking.ActivityStateRecord>.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md)|Una colección de argumentos asociada a esta consulta de actividad.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Una colección de elementos de configuración que contienen los estados de la actividad suscrita para la que se debería emitir un registro del seguimiento.|  
|[\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Una colección de variables asociada a esta consulta de actividad.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<faultPropagationQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|Representa una lista de los elementos de configuración que se usan para realizar el seguimiento de las solicitudes de cancelación de una actividad secundaria por parte de la actividad primaria.  La consulta es necesaria para que un participante del seguimiento se suscriba con el fin de cancelar los objetos de registro de solicitud.|  
  
## Comentarios  
 Una característica única de ActivityStateQuery es la capacidad de extraer los datos al realizar el seguimiento de la ejecución de un flujo de trabajo.  Esto proporciona contexto adicional al tener acceso a los registros de seguimiento tras la ejecución.  Puede usar los [\<arguments\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/arguments.md), [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) y [\<states\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md) para extraer cualquier variable o argumento de cualquier actividad de un flujo de trabajo. El siguiente ejemplo muestra una consulta de estado de actividad que extrae variables y argumentos cuando se emite el registro de seguimiento de la actividad `Closed`.  Los argumentos y las variables solo se pueden extraer con ActivityStateRecord y, de esa forma, se suscriben dentro de un perfil de seguimiento mediante [\<activityStateQuery\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/activitystatequery.md).  
  
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
 [System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement](assetId:///System.ServiceModel.Activities.Tracking.Configuration.ActivityStateQueryElement?qualifyHint=False&amp;autoUpgrade=True)   
 [System.Activities.Tracking.ActivityStateQuery](assetId:///System.Activities.Tracking.ActivityStateQuery?qualifyHint=False&amp;autoUpgrade=True)   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)