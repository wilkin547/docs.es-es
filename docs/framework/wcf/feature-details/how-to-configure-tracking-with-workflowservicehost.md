---
title: Procedimiento para configurar el seguimiento con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 3f78b77849d6da7dfff3bdcba90bb4d5200186a7
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464155"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Procedimiento para configurar el seguimiento con WorkflowServiceHost
En este tema, se explica cómo configurar el seguimiento para un flujo de trabajo [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Se configura a través de un archivo Web.config especificando un comportamiento de servicio.  
  
### <a name="configure-tracking-in-configuration"></a>Configurar el seguimiento en la configuración  
  
1. Agregue <xref:System.Activities.Tracking.EtwTrackingParticipant> el elemento `behavior` using the using the <> en un archivo de configuración, como se muestra en el ejemplo siguiente.  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior>  
           <etwTracking profileName="Sample Tracking Profile" />  
         </behavior>
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    > En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, consulte [Configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).  
  
     El ejemplo de configuración anterior agrega <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento. Los perfiles de `trackingProfile` seguimiento se crean `tracking` en un elemento> <dentro de un elemento> <. El perfil de seguimiento contiene consultas de seguimiento que permiten a un participante de seguimiento suscribirse a eventos de flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución. En el siguiente ejemplo, se muestra cómo crear un perfil de seguimiento.  
  
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
  
     Para obtener más información sobre el seguimiento de perfiles, consulte [Perfiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)de seguimiento .  
  
     Para obtener más información sobre el seguimiento en general, vea [Seguimiento y seguimiento](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)de flujodería de trabajo .  
  
### <a name="configure-tracking-in-code"></a>Configurar el seguimiento en el código  
  
1. Agregue el objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> con el comportamiento <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> en el código, según se muestra en el código siguiente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     El ejemplo de código anterior agrega un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento. Los perfiles de `trackingProfile` seguimiento se crean `tracking` en un elemento> <dentro de un elemento> <como se muestra en la sección anterior.  
  
     Para obtener más información sobre el seguimiento de perfiles, consulte [Perfiles](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)de seguimiento .  
  
     Para obtener más información sobre el seguimiento en general, vea [Seguimiento y seguimiento](../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)de flujodería de trabajo . Para obtener un ejemplo de configuración del seguimiento mediante programación, consulte [Configuración del seguimiento de un flujo](../../../../docs/framework/windows-workflow-foundation/configuring-tracking-for-a-workflow.md)de trabajo .  
  
## <a name="see-also"></a>Consulte también

- [Configuración simplificada de los servicios de WCF](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)
- [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)
- [Perfiles de seguimiento](../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
