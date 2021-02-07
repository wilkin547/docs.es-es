---
description: Más información acerca de cómo configurar el seguimiento con WorkflowServiceHost
title: Procedimiento para configurar el seguimiento con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: 11c48c3989ab9b788c1e6834d8cbfe53e2b8a53e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99734833"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a>Procedimiento para configurar el seguimiento con WorkflowServiceHost

En este tema, se explica cómo configurar el seguimiento para un flujo de trabajo [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>. Se configura a través de un archivo Web.config especificando un comportamiento de servicio.  
  
### <a name="configure-tracking-in-configuration"></a>Configurar el seguimiento en la configuración  
  
1. Agregue <xref:System.Activities.Tracking.EtwTrackingParticipant> mediante el elemento <`behavior`> en un archivo de configuración, tal y como se muestra en el ejemplo siguiente.  
  
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
    > En el ejemplo de configuración anterior, se usa la configuración simplificada. Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).  
  
     El ejemplo de configuración anterior agrega <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento. Los perfiles de seguimiento se crean en un `trackingProfile` elemento <> dentro de un `tracking` elemento de> <. El perfil de seguimiento contiene consultas de seguimiento que permiten a un participante de seguimiento suscribirse a eventos de flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución. En el siguiente ejemplo, se muestra cómo crear un perfil de seguimiento.  
  
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
  
     Para obtener más información acerca de los perfiles de seguimiento, consulte [perfiles de seguimiento](../../windows-workflow-foundation/tracking-profiles.md).  
  
     Para obtener más información sobre el seguimiento en general, vea [seguimiento y](../../windows-workflow-foundation/workflow-tracking-and-tracing.md)seguimiento de flujos de trabajo.  
  
### <a name="configure-tracking-in-code"></a>Configurar el seguimiento en el código  
  
1. Agregue el objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> con el comportamiento <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> en el código, según se muestra en el código siguiente.  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     El ejemplo de código anterior agrega un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento. Los perfiles de seguimiento se crean en un `trackingProfile` elemento <> dentro de un `tracking` elemento de> <como se muestra en la sección anterior.  
  
     Para obtener más información acerca de los perfiles de seguimiento, consulte [perfiles de seguimiento](../../windows-workflow-foundation/tracking-profiles.md).  
  
     Para obtener más información sobre el seguimiento en general, vea [seguimiento y](../../windows-workflow-foundation/workflow-tracking-and-tracing.md)seguimiento de flujos de trabajo. Para obtener un ejemplo de cómo configurar el seguimiento mediante programación, vea [configurar el seguimiento de un flujo de trabajo](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).  
  
## <a name="see-also"></a>Vea también

- [Configuración simplificada de los servicios de WCF](../samples/simplified-configuration-for-wcf-services.md)
- [Servicios de flujo de trabajo](workflow-services.md)
- [Perfiles de seguimiento](../../windows-workflow-foundation/tracking-profiles.md)
