---
title: 'Cómo: Configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5cf06b90169e3915af48396aa2f6c426f1329a95
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="dc96a-102">Cómo: Configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="dc96a-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="dc96a-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="dc96a-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="dc96a-104">En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="dc96a-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="dc96a-105">Para configurar WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="dc96a-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1.  <span data-ttu-id="dc96a-106">Agregar un <`workflowUnhandledException`> elemento en un <`behavior`> elemento dentro de un <`serviceBehaviors`> elemento, con el `action` atributo para especificar la acción que se realizará cuando se produce una excepción no controlada tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dc96a-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <workflowUnhandledException action="abandonAndSuspend"/>   
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="dc96a-107">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="dc96a-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="dc96a-108">Para obtener más información, consulte [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="dc96a-108">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="dc96a-109">Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dc96a-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="dc96a-110">El `action` atributo de la <`workflowUnhandledException`> elemento puede establecerse en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="dc96a-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="dc96a-111">**Abandono**</span><span class="sxs-lookup"><span data-stu-id="dc96a-111">**abandon**</span></span>  
     <span data-ttu-id="dc96a-112">Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).</span><span class="sxs-lookup"><span data-stu-id="dc96a-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="dc96a-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="dc96a-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="dc96a-114">Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.</span><span class="sxs-lookup"><span data-stu-id="dc96a-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="dc96a-115">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="dc96a-115">**cancel**</span></span>  
     <span data-ttu-id="dc96a-116">Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="dc96a-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="dc96a-117">**terminate**</span><span class="sxs-lookup"><span data-stu-id="dc96a-117">**terminate**</span></span>  
     <span data-ttu-id="dc96a-118">Completa la instancia en memoria y la elimina del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="dc96a-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="dc96a-119"> <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, consulte [extensibilidad de Host de servicio de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="dc96a-119"> <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc96a-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc96a-120">See Also</span></span>  
 [<span data-ttu-id="dc96a-121">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc96a-121">Workflow Service Host Extensibility</span></span>](../../../../docs/framework/wcf/feature-details/workflow-service-host-extensibility.md)  
 [<span data-ttu-id="dc96a-122">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="dc96a-122">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)
