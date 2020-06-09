---
title: Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: 51b25c86-292c-43e4-8d13-273d2badc8ad
ms.openlocfilehash: 3881d1af21dcc0c211c6738162360e522648d949
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593599"
---
# <a name="how-to-configure-workflow-unhandled-exception-behavior-with-workflowservicehost"></a><span data-ttu-id="a9bf7-102">Procedimiento para configurar el comportamiento de excepción no controlada del flujo de trabajo con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="a9bf7-102">How to: Configure Workflow Unhandled Exception Behavior with WorkflowServiceHost</span></span>
<span data-ttu-id="a9bf7-103"><xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> es un comportamiento que le permite especificar la acción que se debe llevar a cabo si se produce una excepción no controlada en un flujo de trabajo hospedado en <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-103">The <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> is a behavior that enables you to specify the action to take if an unhandled exception occurs within a workflow hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost>.</span></span> <span data-ttu-id="a9bf7-104">En este tema, se muestra cómo configurar este comportamiento en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-104">This topic shows how to configure this behavior in a configuration file.</span></span>  
  
### <a name="to-configure-workflowunhandledexceptionbehavior"></a><span data-ttu-id="a9bf7-105">Para configurar WorkflowUnhandledExceptionBehavior</span><span class="sxs-lookup"><span data-stu-id="a9bf7-105">To configure WorkflowUnhandledExceptionBehavior</span></span>  
  
1. <span data-ttu-id="a9bf7-106">Agregue un `workflowUnhandledException` elemento <> en un elemento de> de <`behavior` dentro de un `serviceBehaviors` elemento <>, utilizando el `action` atributo para especificar la acción que se llevará a cabo cuando se produzca una excepción no controlada, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-106">Add a <`workflowUnhandledException`> element in a <`behavior`> element within a <`serviceBehaviors`> element, using the `action` attribute to specify the action to take when an unhandled exception occurs as shown in the following example.</span></span>  
  
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
    > <span data-ttu-id="a9bf7-107">En el ejemplo de configuración anterior, se usa la configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-107">The preceding configuration sample is using simplified configuration.</span></span> <span data-ttu-id="a9bf7-108">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a9bf7-108">For more information, see [Simplified Configuration](../simplified-configuration.md).</span></span>  
  
     <span data-ttu-id="a9bf7-109">Este comportamiento se puede configurar en código, tal y como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-109">This behavior can be configured in code as shown in the following example.</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new WorkflowUnhandledExceptionBehavior { Action = WorkflowUnhandledExceptionAction.AbandonAndSuspend });  
    ```  
  
     <span data-ttu-id="a9bf7-110">El `action` atributo del elemento <`workflowUnhandledException`> se puede establecer en uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a9bf7-110">The `action` attribute of the <`workflowUnhandledException`> element can be set to one of the following values:</span></span>  
  
     <span data-ttu-id="a9bf7-111">**salir**</span><span class="sxs-lookup"><span data-stu-id="a9bf7-111">**abandon**</span></span>  
     <span data-ttu-id="a9bf7-112">Anula la instancia en memoria sin modificar el estado de instancia persistente (es decir, vuelta al último punto persistente).</span><span class="sxs-lookup"><span data-stu-id="a9bf7-112">Aborts the instance in memory without touching the persisted instance state (that is, roll back to the last persist point).</span></span>  
  
     <span data-ttu-id="a9bf7-113">**abandonAndSuspend**</span><span class="sxs-lookup"><span data-stu-id="a9bf7-113">**abandonAndSuspend**</span></span>  
     <span data-ttu-id="a9bf7-114">Anula la instancia en memoria y actualiza la instancia persistente que se desea suspender.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-114">Aborts the instance in memory and updates the persisted instance to be suspended.</span></span>  
  
     <span data-ttu-id="a9bf7-115">**cancel**</span><span class="sxs-lookup"><span data-stu-id="a9bf7-115">**cancel**</span></span>  
     <span data-ttu-id="a9bf7-116">Llama a los controladores de cancelaciones de la instancia y, a continuación, completa la instancia en memoria, de manera que también puede eliminarse del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-116">Calls cancellation handlers for the instance and then completes the instance in memory, which may also remove it from the instance store</span></span>  
  
     <span data-ttu-id="a9bf7-117">**cancela**</span><span class="sxs-lookup"><span data-stu-id="a9bf7-117">**terminate**</span></span>  
     <span data-ttu-id="a9bf7-118">Completa la instancia en memoria y la elimina del almacén de instancias.</span><span class="sxs-lookup"><span data-stu-id="a9bf7-118">Completes the instance in memory and removes it from the instance store.</span></span>  
  
     <span data-ttu-id="a9bf7-119">Para obtener más información acerca de <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior> , consulte [extensibilidad de host de servicio de flujo de trabajo](workflow-service-host-extensibility.md).</span><span class="sxs-lookup"><span data-stu-id="a9bf7-119">For more information about <xref:System.ServiceModel.Activities.Description.WorkflowUnhandledExceptionBehavior>, see [Workflow Service Host Extensibility](workflow-service-host-extensibility.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9bf7-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9bf7-120">See also</span></span>

- [<span data-ttu-id="a9bf7-121">Extensibilidad de host de servicio de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a9bf7-121">Workflow Service Host Extensibility</span></span>](workflow-service-host-extensibility.md)
- [<span data-ttu-id="a9bf7-122">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a9bf7-122">Workflow Services</span></span>](workflow-services.md)
