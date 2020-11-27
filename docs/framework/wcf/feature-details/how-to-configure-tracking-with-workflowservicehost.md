---
title: Procedimiento para configurar el seguimiento con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: ed1485fe-7529-4351-bca3-8bb915260b17
ms.openlocfilehash: cf30ace90f86e282d72c4da5f2c3707905360aeb
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257358"
---
# <a name="how-to-configure-tracking-with-workflowservicehost"></a><span data-ttu-id="eba7f-102">Procedimiento para configurar el seguimiento con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="eba7f-102">How to: Configure Tracking with WorkflowServiceHost</span></span>

<span data-ttu-id="eba7f-103">En este tema, se explica cómo configurar el seguimiento para un flujo de trabajo [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="eba7f-103">This topic explains how to configure tracking for a [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="eba7f-104">Se configura a través de un archivo Web.config especificando un comportamiento de servicio.</span><span class="sxs-lookup"><span data-stu-id="eba7f-104">It is configured through a Web.config file by specifying a service behavior.</span></span>  
  
### <a name="configure-tracking-in-configuration"></a><span data-ttu-id="eba7f-105">Configurar el seguimiento en la configuración</span><span class="sxs-lookup"><span data-stu-id="eba7f-105">Configure Tracking in Configuration</span></span>  
  
1. <span data-ttu-id="eba7f-106">Agregue <xref:System.Activities.Tracking.EtwTrackingParticipant> mediante el elemento <`behavior`> en un archivo de configuración, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="eba7f-106">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <`behavior`> element in a configuration file, as shown in the following example.</span></span>  
  
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
    > <span data-ttu-id="eba7f-107">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="eba7f-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="eba7f-108">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="eba7f-108">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="eba7f-109">El ejemplo de configuración anterior agrega <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eba7f-109">The preceding configuration sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="eba7f-110">Los perfiles de seguimiento se crean en un `trackingProfile` elemento <> dentro de un `tracking` elemento de> <.</span><span class="sxs-lookup"><span data-stu-id="eba7f-110">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element.</span></span> <span data-ttu-id="eba7f-111">El perfil de seguimiento contiene consultas de seguimiento que permiten a un participante de seguimiento suscribirse a eventos de flujo de trabajo que se emiten cuando el estado de una instancia de flujo de trabajo cambia en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="eba7f-111">The tracking profile contains tracking queries that permit a tracking participant to subscribe to workflow events that are emitted when the state of a workflow instance changes at runtime.</span></span> <span data-ttu-id="eba7f-112">En el siguiente ejemplo, se muestra cómo crear un perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eba7f-112">The following example shows how to create a tracking profile.</span></span>  
  
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
  
     <span data-ttu-id="eba7f-113">Para obtener más información acerca de los perfiles de seguimiento, consulte [perfiles de seguimiento](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="eba7f-113">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="eba7f-114">Para obtener más información sobre el seguimiento en general, vea [seguimiento y](../../windows-workflow-foundation/workflow-tracking-and-tracing.md)seguimiento de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eba7f-114">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span>  
  
### <a name="configure-tracking-in-code"></a><span data-ttu-id="eba7f-115">Configurar el seguimiento en el código</span><span class="sxs-lookup"><span data-stu-id="eba7f-115">Configure Tracking in Code</span></span>  
  
1. <span data-ttu-id="eba7f-116">Agregue el objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> con el comportamiento <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> en el código, según se muestra en el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="eba7f-116">Add the <xref:System.Activities.Tracking.EtwTrackingParticipant> using the <xref:System.ServiceModel.Activities.Description.EtwTrackingBehavior> behavior in code, as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new EtwTrackingBehavior { ProfileName = "Sample Tracking Profile" });  
    ```  
  
     <span data-ttu-id="eba7f-117">El ejemplo de código anterior agrega un objeto <xref:System.Activities.Tracking.EtwTrackingParticipant> y especifica un nombre del perfil de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eba7f-117">The preceding code sample adds a <xref:System.Activities.Tracking.EtwTrackingParticipant> and specifies a tracking profile name.</span></span> <span data-ttu-id="eba7f-118">Los perfiles de seguimiento se crean en un `trackingProfile` elemento <> dentro de un `tracking` elemento de> <como se muestra en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="eba7f-118">Tracking profiles are created in a <`trackingProfile`> element within a <`tracking`> element as shown in the previous section.</span></span>  
  
     <span data-ttu-id="eba7f-119">Para obtener más información acerca de los perfiles de seguimiento, consulte [perfiles de seguimiento](../../windows-workflow-foundation/tracking-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="eba7f-119">For more information about tracking profiles, see [Tracking Profiles](../../windows-workflow-foundation/tracking-profiles.md).</span></span>  
  
     <span data-ttu-id="eba7f-120">Para obtener más información sobre el seguimiento en general, vea [seguimiento y](../../windows-workflow-foundation/workflow-tracking-and-tracing.md)seguimiento de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="eba7f-120">For more information about tracking in general, see [Workflow Tracking and Tracing](../../windows-workflow-foundation/workflow-tracking-and-tracing.md).</span></span> <span data-ttu-id="eba7f-121">Para obtener un ejemplo de cómo configurar el seguimiento mediante programación, vea [configurar el seguimiento de un flujo de trabajo](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="eba7f-121">For an example of configuring tracking programmatically see [Configuring Tracking for a Workflow](../../windows-workflow-foundation/configuring-tracking-for-a-workflow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eba7f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="eba7f-122">See also</span></span>

- [<span data-ttu-id="eba7f-123">Configuración simplificada de los servicios de WCF</span><span class="sxs-lookup"><span data-stu-id="eba7f-123">Simplified Configuration for WCF Services</span></span>](../samples/simplified-configuration-for-wcf-services.md)
- [<span data-ttu-id="eba7f-124">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="eba7f-124">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="eba7f-125">Perfiles de seguimiento</span><span class="sxs-lookup"><span data-stu-id="eba7f-125">Tracking Profiles</span></span>](../../windows-workflow-foundation/tracking-profiles.md)
