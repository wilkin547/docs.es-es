---
description: 'Más información sobre: Cómo: configurar el comportamiento inactivo con WorkflowServiceHost'
title: Procedimiento para configurar el comportamiento inactivo con WorkflowServiceHost
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
ms.openlocfilehash: 530ab1833f3f8bb91d39b19161070bc75c45f11a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780055"
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="7c9fa-103">Procedimiento para configurar el comportamiento inactivo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="7c9fa-103">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>

<span data-ttu-id="7c9fa-104">Los flujos de trabajo pasan a estar inactivos cuando encuentran un marcador que se debe reanudar mediante algún estímulo externo, por ejemplo cuando la instancia de flujo de trabajo está esperando la entrega de un mensaje usando una actividad <xref:System.ServiceModel.Activities.Receive> .</span><span class="sxs-lookup"><span data-stu-id="7c9fa-104">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="7c9fa-105"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> es un comportamiento que le permite especificar el tiempo transcurrido desde que una instancia de servicio pasa a estado inactivo hasta que la instancia se guarda o se descarga.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-105"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="7c9fa-106">Contiene dos propiedades que permiten establecer estas duraciones.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-106">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="7c9fa-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="7c9fa-108"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> especifica el intervalo de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se descarga, donde la descarga significa guardar la instancia en el almacén de instancia y eliminarla de la memoria.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-108"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="7c9fa-109">En este tema, se explica cómo configurar la clase <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-109">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="7c9fa-110">Para configurar WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="7c9fa-110">To configure WorkflowIdleBehavior</span></span>  
  
1. <span data-ttu-id="7c9fa-111">Agregue un elemento de> de <`workflowIdle` al `behavior` elemento de> <en el elemento <> `serviceBehaviors` como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-111">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="7c9fa-112">El atributo `timeToUnload` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicho servicio se descarga.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-112">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="7c9fa-113">El atributo `timeToPersist` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-113">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="7c9fa-114">El valor predeterminado de `timeToUnload` es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-114">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="7c9fa-115">El valor predeterminado de `timeToPersist` es <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-115">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="7c9fa-116">Si desea conservar las instancias inactivas en memoria pero hacer que persistan por integridad, establezca los valores de modo que `timeToPersist` < `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-116">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="7c9fa-117">Si desea impedir que las instancias inactivas se carguen, establezca `timeToUnload` en <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-117">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="7c9fa-118">Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> , consulte [extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="7c9fa-118">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7c9fa-119">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-119">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="7c9fa-120">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7c9fa-120">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="7c9fa-121">Para cambiar el comportamiento inactivo en el código</span><span class="sxs-lookup"><span data-stu-id="7c9fa-121">To change idle behavior in code</span></span>  
  
- <span data-ttu-id="7c9fa-122">En el siguiente ejemplo se cambia el tiempo que se espera antes de persistir y descargar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="7c9fa-122">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7c9fa-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="7c9fa-123">See also</span></span>

- [<span data-ttu-id="7c9fa-124">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7c9fa-124">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)
- [<span data-ttu-id="7c9fa-125">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="7c9fa-125">Simplified Configuration</span></span>](../simplified-configuration.md)
- [<span data-ttu-id="7c9fa-126">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7c9fa-126">Workflow Services</span></span>](workflow-services.md)
