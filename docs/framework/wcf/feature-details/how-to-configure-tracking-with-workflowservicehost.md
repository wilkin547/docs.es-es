---
title: "C&#243;mo: Configurar el seguimiento con WorkflowServiceHost | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# C&#243;mo: Configurar el seguimiento con WorkflowServiceHost
En este tema, se explica cómo configurar el seguimiento para un flujo de trabajo [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.  Se configura a través de un archivo Web.config especificando un comportamiento de servicio.  
  
### Configurar el seguimiento en la configuración  
  
1.  Agregue <xref:System.Activities.Tracking.EtwTrackingParticipant> mediante el elemento \<`behavior`\> en un archivo de configuración, como se muestra en el siguiente ejemplo.  
  
    ```  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>              
       </serviceBehaviors>  
    <behaviors>  
  
    ```  
  
    > [!NOTE]
    >  En el ejemplo de configuración anterior, se usa la configuración simplificada.  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     El ejemplo de configuración anterior agrega <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento.  Se crean perfiles de seguimiento en un elemento \<`trackingProfile`\> dentro de un elemento\<`tracking`\>.  El perfil de seguimiento contiene consultas de seguimiento que permiten a un participante de seguimiento suscribirse a eventos de flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.  En el siguiente ejemplo, se muestra cómo crear un perfil de seguimiento.  
  
    ```xml  
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
       </tracking>  
    </system.serviceModel>  
  
    ```  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los perfiles de seguimiento, vea [Perfiles de seguimiento](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] seguimiento en general, vea [Seguimiento y traza del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  
  
### Configurar el seguimiento en el código  
  
1.  Agregue el objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> con el comportamiento <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> en el código, según se muestra en el código siguiente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     El ejemplo de código anterior agrega un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento.  Los perfiles de seguimiento se crean en un elemento \<`trackingProfile`\> dentro de un elemento \<`tracking`\> según se muestra en la sección anterior.  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] los perfiles de seguimiento, vea [Perfiles de seguimiento](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md).  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)] seguimiento en general, vea [Seguimiento y traza del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md).  Para obtener un ejemplo de cómo configurar el seguimiento mediante programación, vea [Configurar seguimiento para un flujo de trabajo](../../../../docs/framework/windows-workflow-foundation//configuring-tracking-for-a-workflow.md).  
  
## Vea también  
 [Configuración simplificada de los servicios de WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)   
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)   
 [Perfiles de seguimiento](../../../../docs/framework/windows-workflow-foundation//tracking-profiles.md)