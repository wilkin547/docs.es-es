---
title: "&lt;trackingProfile&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 154830ff-ddd3-4397-a3b5-5b334907777f
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;trackingProfile&gt;
Representa una sección de configuración para crear una suscripción a los registros de seguimiento del flujo de trabajo en un participante del seguimiento.  Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.  Las consultas definidas dentro de la sección de perfil de seguimiento definen los tipos de eventos que devuelve la suscripción.  
  
 Para obtener más información acerca del seguimiento del flujo de trabajo y su configuración, consulte [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md) y [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
## Sintaxis  
  
```vb  
  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="String">  
      <workflow activityDefinitionId="String">  
          <activityScheduledQueries>  
             <activityScheduledQuery activityName="String"  
                 childActivityName="String"/>  
          </activityScheduledQueries>  
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
          <bookmarkResumptionQueries>  
             <bookmarkResumptionQuery name="String" />  
          </bookmarkResumptionQueries>  
          <cancelRequestQueries>  
             <cancelRequestQuery activityName="String"  
                 childActivityName="String"/>  
          </cancelRequestQueries>  
          <customTrackingQueries>  
             <customTrackingQuery activityName="String"  
                 name="String"/>  
          </customTrackingQueries>  
          <faultPropagationQueries>  
             <faultPropagationQuery activityName="String"  
                 faultHandlerActivityName="String"/>  
          </faultPropagationQueries>  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
              <states>  
                 <state name="String"/>  
              </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|name|Una cadena que especifica el nombre de un perfil de seguimiento.|  
  
### Elementos secundarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<participants\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)|Un elemento de configuración que contiene todas las consultas para un flujo de trabajo concreto identificado por la propiedad **activityDefinitionId**.|  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<tracking\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/tracking.md)|Representa una sección de configuración para definir los valores de seguimiento de un servicio de flujo de trabajo.|  
  
## Comentarios  
 Los perfiles de seguimiento contienen consultas de seguimiento que permiten a un participante de seguimiento suscribirse a los eventos del flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.  Dependiendo de sus requisitos de supervisión, puede escribir un perfil muy general que se suscribe a un conjunto pequeño de cambios de estado de alto nivel en un flujo de trabajo.  A la inversa, puede crear un perfil específico cuyos eventos resultantes estén lo suficientemente enriquecidos para reconstruir un flujo de ejecución detallado posteriormente.  
  
 Los perfiles de seguimiento se estructuran como suscripciones declarativas para los registros de seguimiento que le permiten consultar el tiempo de ejecución de flujo de trabajo para registros de seguimiento específicos.  Hay muchos tipos de consultas que le permiten suscribirse a distintas clases de objetos de TrackingRecord.  Para obtener una lista completa de las consultas, consulte [\<participants\>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md) y [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
 El siguiente ejemplo muestra un perfil de seguimiento de un archivo de configuración que permite a un participante de seguimiento suscribirse a los eventos de flujo de trabajo `Started`y `Completed`.  
  
```  
  
<system.serviceModel>  
  <tracking>    
    <trackingProfile name="Sample Tracking Profile">  
      <workflow activityDefinitionId="*">  
         <workflowInstanceQueries>  
            <workflowInstanceQuery>  
            <states>  
              <state name="Started"/>  
              <state name="Completed"/>  
            </states>  
          </workflowInstanceQuery>  
        </workflowInstanceQueries>  
      </workflow>  
    </trackingProfile>          
   </profiles>  
  </tracking>  
</system.serviceModel>  
  
```  
  
## Vea también  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileElement>   
 <xref:System.Activities.Tracking.TrackingProfile>   
 [Seguimiento y traza del flujo de trabajo](../../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)   
 [Perfiles de seguimiento](../../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)