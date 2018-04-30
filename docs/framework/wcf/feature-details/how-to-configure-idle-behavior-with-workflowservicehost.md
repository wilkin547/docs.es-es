---
title: 'Cómo: Configurar el comportamiento inactivo con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 1bb93652-d687-46ff-bff6-69ecdcf97437
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22c71c0840b4fa44c585dfac4d99bdcbb3227fdb
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-configure-idle-behavior-with-workflowservicehost"></a><span data-ttu-id="18c33-102">Cómo: Configurar el comportamiento inactivo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="18c33-102">How to: Configure Idle Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="18c33-103">Los flujos de trabajo pasan a estar inactivos cuando encuentran un marcador que se debe reanudar mediante algún estímulo externo, por ejemplo cuando la instancia de flujo de trabajo está esperando la entrega de un mensaje usando una actividad <xref:System.ServiceModel.Activities.Receive> .</span><span class="sxs-lookup"><span data-stu-id="18c33-103">Workflows go idle when they encounter a bookmark that must be resumed by some external stimulus, for example when the workflow instance is waiting for a message to be delivered using a <xref:System.ServiceModel.Activities.Receive> activity.</span></span> <span data-ttu-id="18c33-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> es un comportamiento que le permite especificar el tiempo transcurrido desde que una instancia de servicio pasa a estado inactivo hasta que la instancia se guarda o se descarga.</span><span class="sxs-lookup"><span data-stu-id="18c33-104"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> is a behavior that allows you to specify the time between when a service instance goes idle and when the instance is persisted or unloaded.</span></span> <span data-ttu-id="18c33-105">Contiene dos propiedades que permiten establecer estas duraciones.</span><span class="sxs-lookup"><span data-stu-id="18c33-105">It contains two properties that enable you to set these time spans.</span></span> <span data-ttu-id="18c33-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda.</span><span class="sxs-lookup"><span data-stu-id="18c33-106"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="18c33-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> especifica el intervalo de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se descarga, donde la descarga significa guardar la instancia en el almacén de instancia y eliminarla de la memoria.</span><span class="sxs-lookup"><span data-stu-id="18c33-107"><xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A> specifies the time span between when a workflow service instance goes idle and when the workflow service instance is unloaded, where unload means persisting the instance to the instance store and removing it from memory.</span></span> <span data-ttu-id="18c33-108">En este tema, se explica cómo configurar la clase <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="18c33-108">This topic explains how to configure the <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior> in a configuration file.</span></span>  
  
### <a name="to-configure-workflowidlebehavior"></a><span data-ttu-id="18c33-109">Para configurar WorkflowIdleBehavior</span><span class="sxs-lookup"><span data-stu-id="18c33-109">To configure WorkflowIdleBehavior</span></span>  
  
1.  <span data-ttu-id="18c33-110">Agregar un <`workflowIdle`> elemento a la <`behavior`> elemento dentro de la <`serviceBehaviors`> elemento tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="18c33-110">Add a <`workflowIdle`> element to the <`behavior`> element within the <`serviceBehaviors`> element as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowIdle timeToUnload="0:05:0" timeToPersist="0:04:0"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
     <span data-ttu-id="18c33-111">El atributo `timeToUnload` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicho servicio se descarga.</span><span class="sxs-lookup"><span data-stu-id="18c33-111">The `timeToUnload` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service is unloaded.</span></span> <span data-ttu-id="18c33-112">El atributo `timeToPersist` especifica el período de tiempo entre el momento en el que una instancia de servicio del flujo de trabajo se inactiva y el momento en el que dicha instancia se guarda.</span><span class="sxs-lookup"><span data-stu-id="18c33-112">The `timeToPersist` attribute specifies the time period between when a workflow service instance goes idle and when the workflow service instance is persisted.</span></span> <span data-ttu-id="18c33-113">El valor predeterminado de `timeToUnload` es 1 minuto.</span><span class="sxs-lookup"><span data-stu-id="18c33-113">The default value for `timeToUnload` is 1 minute.</span></span> <span data-ttu-id="18c33-114">El valor predeterminado de `timeToPersist` es <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="18c33-114">The default value for `timeToPersist` is <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="18c33-115">Si desea conservar las instancias inactivas en memoria pero hacer que persistan por integridad, establezca los valores de modo que `timeToPersist` < `timeToUnload`.</span><span class="sxs-lookup"><span data-stu-id="18c33-115">If you want to keep idle instances in memory but persist them for robustness, set values so that `timeToPersist` < `timeToUnload`.</span></span> <span data-ttu-id="18c33-116">Si desea impedir que las instancias inactivas se carguen, establezca `timeToUnload` en <xref:System.TimeSpan.MaxValue>.</span><span class="sxs-lookup"><span data-stu-id="18c33-116">If you want to prevent idle instances from being unloaded, set `timeToUnload` to <xref:System.TimeSpan.MaxValue>.</span></span> <span data-ttu-id="18c33-117">Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, consulte [extensibilidad de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span><span class="sxs-lookup"><span data-stu-id="18c33-117">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18c33-118">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="18c33-118">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="18c33-119">Para obtener más información, consulte [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="18c33-119">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
### <a name="to-change-idle-behavior-in-code"></a><span data-ttu-id="18c33-120">Para cambiar el comportamiento inactivo en el código</span><span class="sxs-lookup"><span data-stu-id="18c33-120">To change idle behavior in code</span></span>  
  
-   <span data-ttu-id="18c33-121">En el siguiente ejemplo se cambia el tiempo que se espera antes de persistir y descargar mediante programación.</span><span class="sxs-lookup"><span data-stu-id="18c33-121">The following example changes the time to wait before persisting and unloading programmatically.</span></span>  
  
     [!code-csharp[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/wf_svchost_idle_persist/cs/source.cs#1)]
     [!code-vb[Wf_SvcHost_Idle_persist#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/wf_svchost_idle_persist/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="18c33-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="18c33-122">See Also</span></span>  
 [<span data-ttu-id="18c33-123">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="18c33-123">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="18c33-124">Configuración simplificada</span><span class="sxs-lookup"><span data-stu-id="18c33-124">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)  
 [<span data-ttu-id="18c33-125">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="18c33-125">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
