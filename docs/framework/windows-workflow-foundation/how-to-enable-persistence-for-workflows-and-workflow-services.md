---
title: Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 6a2a8d73298e14f92f376b97b9637db91532e937
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59772711"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="d49b7-102">Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d49b7-102">How to: Enable Persistence for Workflows and Workflow Services</span></span>
<span data-ttu-id="d49b7-103">En este tema se describe cómo habilitar la persistencia para los flujos de trabajo y los servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d49b7-103">This topic describes how to enable persistence for workflows and workflow services.</span></span>  
  
## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="d49b7-104">Habilitar persistencia para los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d49b7-104">Enable Persistence for Workflows</span></span>  
 <span data-ttu-id="d49b7-105">Puede asociar un almacén de instancias con un **WorkflowApplication** utilizando el <xref:System.Activities.WorkflowApplication.InstanceStore%2A> propiedad de la <xref:System.Activities.WorkflowApplication> clase.</span><span class="sxs-lookup"><span data-stu-id="d49b7-105">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="d49b7-106">El método <xref:System.Activities.WorkflowApplication.Persist%2A> guarda o conserva un flujo de trabajo en el almacén de instancias asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d49b7-106">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="d49b7-107">El método <xref:System.Activities.WorkflowApplication.Unload%2A> conserva un flujo de trabajo en el almacén de instancias y, a continuación, descarga la instancia de la memoria.</span><span class="sxs-lookup"><span data-stu-id="d49b7-107">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="d49b7-108">El **carga** método carga un flujo de trabajo en memoria mediante los datos de flujo de trabajo almacenados en el almacén de persistencia de instancias.</span><span class="sxs-lookup"><span data-stu-id="d49b7-108">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>  
  
 <span data-ttu-id="d49b7-109">El **Persist** método lleva a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d49b7-109">The **Persist** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="d49b7-110">Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="d49b7-110">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="d49b7-111">Conserva o guarda el flujo de trabajo en el almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="d49b7-111">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="d49b7-112">Reanuda el programador del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d49b7-112">Resumes the workflow scheduler.</span></span>  
  
 <span data-ttu-id="d49b7-113">El **Unload** método lleva a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="d49b7-113">The **Unload** method performs the following steps:</span></span>  
  
1. <span data-ttu-id="d49b7-114">Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="d49b7-114">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>  
  
2. <span data-ttu-id="d49b7-115">Conserva o guarda el flujo de trabajo en el almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="d49b7-115">Persists or saves the workflow into the persistence store.</span></span>  
  
3. <span data-ttu-id="d49b7-116">Elimina la instancia de flujo de trabajo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="d49b7-116">Disposes the workflow instance in the memory.</span></span>  
  
 <span data-ttu-id="d49b7-117">Tanto el **Persist** y **Unload** métodos se bloquean mientras un flujo de trabajo está en una zona sin persistencia hasta que el flujo de trabajo salga de ella.</span><span class="sxs-lookup"><span data-stu-id="d49b7-117">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="d49b7-118">El método continúa con la operación de persistencia o descarga después de que se complete la zona sin persistencia.</span><span class="sxs-lookup"><span data-stu-id="d49b7-118">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="d49b7-119">Si la zona sin persistencia no se completa antes de que transcurra el tiempo de espera o, si el proceso de persistencia tarda demasiado, se iniciará una TimeoutException.</span><span class="sxs-lookup"><span data-stu-id="d49b7-119">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="d49b7-120">Habilitar persistencia para los servicios de flujo de trabajo en código</span><span class="sxs-lookup"><span data-stu-id="d49b7-120">Enable Persistence for Workflow Services in Code</span></span>  
 <span data-ttu-id="d49b7-121">El **DurableInstancingOptions** miembro de la <xref:System.ServiceModel.WorkflowServiceHost> clase tiene una propiedad denominada **InstanceStore** que puede usar para asociar un almacén de instancias con el **WorkflowServiceHost** .</span><span class="sxs-lookup"><span data-stu-id="d49b7-121">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>  
  
```  
// wsh is an instance of WorkflowServiceHost class  
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();  
```  
  
 <span data-ttu-id="d49b7-122">Cuando el **WorkflowServiceHost** está abierto, persistencia se habilita automáticamente si el **DurableInstancingOptions.InstanceStore** no es null.</span><span class="sxs-lookup"><span data-stu-id="d49b7-122">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>  
  
 <span data-ttu-id="d49b7-123">Normalmente, un comportamiento del servicio proporciona el almacén de instancia concreta para su uso con un host de servicio de flujo de trabajo mediante el uso de la **InstanceStore** propiedad.</span><span class="sxs-lookup"><span data-stu-id="d49b7-123">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="d49b7-124">Por ejemplo, SqlWorkflowInstanceStoreBehavior crea una instancia de la **SqlWorkflowInstanceStore**, lo configura y lo asigna a la **DurableInstancingOptions.InstanceStore**.</span><span class="sxs-lookup"><span data-stu-id="d49b7-124">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>  
  
## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="d49b7-125">Habilita la persistencia para los servicios de flujo de trabajo usando un archivo de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="d49b7-125">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>  
 <span data-ttu-id="d49b7-126">La persistencia puede habilitarse mediante un archivo de configuración de la aplicación agregando el código siguiente al archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="d49b7-126">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="myBehavior">  
          <SqlWorkflowInstanceStore connectionString="Data Source=myDatatbaseServer;Initial Catalog=myPersistenceDatabase">  
        </behavior>  
      </serviceBehaviors>  
    <behaviors>  
  </system.serviceModel>  
</configuration>  
```
