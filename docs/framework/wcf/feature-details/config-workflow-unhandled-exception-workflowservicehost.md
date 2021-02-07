---
description: 'Más información acerca de cómo: configurar el comportamiento de las excepciones no controladas del flujo de trabajo con WorkflowServiceHost'
title: Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 7d32ccf1262895d948cae26f0922adf3003664ba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99743387"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="a3982-103">Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="a3982-103">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>

<span data-ttu-id="a3982-104"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a3982-104">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a3982-105">En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a3982-105">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="a3982-106">Para configurar WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="a3982-106">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="a3982-107">Agregue un `workflowUnhandledException` elemento <> en un elemento de> de <`behavior` dentro de un `serviceBehaviors` elemento <>, utilizando el `action` atributo para especificar la acción que se llevará a cabo cuando se produzca una excepción no controlada, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a3982-107">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    > <span data-ttu-id="a3982-108">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="a3982-108">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="a3982-109">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a3982-109">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="a3982-110">Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a3982-110">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="a3982-111">El `action` atributo del elemento <`workflowUnhandledException`> se puede establecer en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a3982-111">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="a3982-112">**salir**</span><span class="sxs-lookup"><span data-stu-id="a3982-112">**abandon**</span></span>  
     <span data-ttu-id="a3982-113">Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).</span><span class="sxs-lookup"><span data-stu-id="a3982-113">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="a3982-114">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="a3982-114">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="a3982-115">Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.</span><span class="sxs-lookup"><span data-stu-id="a3982-115">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="a3982-116">**cancel**</span><span class="sxs-lookup"><span data-stu-id="a3982-116">**cancel**</span></span>  
     <span data-ttu-id="a3982-117">Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="a3982-117">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="a3982-118">**cancela**</span><span class="sxs-lookup"><span data-stu-id="a3982-118">**terminate**</span></span>  
     <span data-ttu-id="a3982-119">Completa la instancia en memoria y la elimina del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="a3982-119">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="a3982-120">Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> , consulte [extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="a3982-120">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3982-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3982-121">See also</span></span>

- [<span data-ttu-id="a3982-122">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a3982-122">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)
- [<span data-ttu-id="a3982-123">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a3982-123">Workflow Services</span></span>](workflow-services.md)
