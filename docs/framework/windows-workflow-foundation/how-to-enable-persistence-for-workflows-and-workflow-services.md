---
title: Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo
description: Aprenda a configurar el almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo mediante programación y mediante un archivo de configuración.
ms.date: 03/30/2017
ms.assetid: 2b1c8bf3-9866-45a4-b06d-ee562393e503
ms.openlocfilehash: 31fe6e3f06989e9a42254747565342cf97e4b9f1
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421519"
---
# <a name="how-to-enable-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="7473e-103">Procedimiento para habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="7473e-103">How to: Enable Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="7473e-104">En este tema se describe cómo habilitar la persistencia para los flujos de trabajo y los servicios de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7473e-104">This topic describes how to enable persistence for workflows and workflow services.</span></span>

## <a name="enable-persistence-for-workflows"></a><span data-ttu-id="7473e-105">Habilitar persistencia para los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="7473e-105">Enable Persistence for Workflows</span></span>

<span data-ttu-id="7473e-106">Puede asociar un almacén de instancias con **WorkflowApplication** mediante la <xref:System.Activities.WorkflowApplication.InstanceStore%2A> propiedad de la <xref:System.Activities.WorkflowApplication> clase.</span><span class="sxs-lookup"><span data-stu-id="7473e-106">You can associate an instance store with a **WorkflowApplication** by using the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property of the <xref:System.Activities.WorkflowApplication> class.</span></span> <span data-ttu-id="7473e-107">El método <xref:System.Activities.WorkflowApplication.Persist%2A> guarda o conserva un flujo de trabajo en el almacén de instancias asociado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7473e-107">The <xref:System.Activities.WorkflowApplication.Persist%2A> method saves or persists a workflow into the instance store associated with the application.</span></span> <span data-ttu-id="7473e-108">El método <xref:System.Activities.WorkflowApplication.Unload%2A> conserva un flujo de trabajo en el almacén de instancias y, a continuación, descarga la instancia de la memoria.</span><span class="sxs-lookup"><span data-stu-id="7473e-108">The <xref:System.Activities.WorkflowApplication.Unload%2A> method persists a workflow into the instance store and then unloads the instance from the memory.</span></span> <span data-ttu-id="7473e-109">El método **Load** carga un flujo de trabajo en la memoria utilizando los datos de flujo de trabajo almacenados en el almacén de persistencia de la instancia.</span><span class="sxs-lookup"><span data-stu-id="7473e-109">The **Load** method loads a workflow into memory using the workflow data stored in the instance persistence store.</span></span>

<span data-ttu-id="7473e-110">El método **Persist** realiza los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="7473e-110">The **Persist** method performs the following steps:</span></span>

1. <span data-ttu-id="7473e-111">Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="7473e-111">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="7473e-112">Conserva o guarda el flujo de trabajo en el almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="7473e-112">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="7473e-113">Reanuda el programador del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7473e-113">Resumes the workflow scheduler.</span></span>

 <span data-ttu-id="7473e-114">El método **Unload** realiza los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="7473e-114">The **Unload** method performs the following steps:</span></span>

1. <span data-ttu-id="7473e-115">Pausa el programador del flujo de trabajo y espera hasta que el flujo de trabajo entre en el estado inactivo.</span><span class="sxs-lookup"><span data-stu-id="7473e-115">Pauses the workflow scheduler and waits until the workflow enters the idle state.</span></span>

2. <span data-ttu-id="7473e-116">Conserva o guarda el flujo de trabajo en el almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="7473e-116">Persists or saves the workflow into the persistence store.</span></span>

3. <span data-ttu-id="7473e-117">Elimina la instancia de flujo de trabajo en la memoria.</span><span class="sxs-lookup"><span data-stu-id="7473e-117">Disposes the workflow instance in the memory.</span></span>

<span data-ttu-id="7473e-118">Los métodos de **persistencia** y **descarga** se bloquearán mientras un flujo de trabajo se encuentra en una zona sin persistencia hasta que el flujo de trabajo salga de la zona sin persistencia.</span><span class="sxs-lookup"><span data-stu-id="7473e-118">Both the **Persist** and **Unload** methods will block while a workflow is in a no-persist zone until the workflow exits the no-persist zone.</span></span> <span data-ttu-id="7473e-119">El método continúa con la operación de persistencia o descarga después de que se complete la zona sin persistencia.</span><span class="sxs-lookup"><span data-stu-id="7473e-119">The method continues with the persist or unload operation after the no-persist zone completes.</span></span> <span data-ttu-id="7473e-120">Si la zona sin persistencia no se completa antes de que transcurra el tiempo de espera o, si el proceso de persistencia tarda demasiado, se iniciará una TimeoutException.</span><span class="sxs-lookup"><span data-stu-id="7473e-120">If the no-persist zone does not complete before the time-out elapses, or if the persistence process takes too long, a TimeoutException will be thrown.</span></span>

## <a name="enable-persistence-for-workflow-services-in-code"></a><span data-ttu-id="7473e-121">Habilitar persistencia para los servicios de flujo de trabajo en código</span><span class="sxs-lookup"><span data-stu-id="7473e-121">Enable Persistence for Workflow Services in Code</span></span>

<span data-ttu-id="7473e-122">El miembro **DurableInstancingOptions** de la <xref:System.ServiceModel.WorkflowServiceHost> clase tiene una propiedad denominada **InstanceStore** que puede usar para asociar un almacén de instancias a **WorkflowServiceHost**.</span><span class="sxs-lookup"><span data-stu-id="7473e-122">The **DurableInstancingOptions** member of the <xref:System.ServiceModel.WorkflowServiceHost> class has a property named **InstanceStore** that you can use to associate an instance store with the **WorkflowServiceHost**.</span></span>

```csharp
// wsh is an instance of WorkflowServiceHost class
wsh.DurableInstancingOptions.InstanceStore = new SqlWorkflowInstanceStore();
```

<span data-ttu-id="7473e-123">Cuando se abre **WorkflowServiceHost** , la persistencia se habilita automáticamente si **DurableInstancingOptions. InstanceStore** no es NULL.</span><span class="sxs-lookup"><span data-stu-id="7473e-123">When the **WorkflowServiceHost** is opened, persistence is automatically enabled if the **DurableInstancingOptions.InstanceStore** is not null.</span></span>

<span data-ttu-id="7473e-124">Normalmente, un comportamiento de servicio proporciona el almacén de instancias concreto que se va a usar con un host de servicio de flujo de trabajo mediante la propiedad **InstanceStore** .</span><span class="sxs-lookup"><span data-stu-id="7473e-124">Typically, a service behavior provides the concrete instance store to be used with a workflow service host by using the **InstanceStore** property.</span></span> <span data-ttu-id="7473e-125">Por ejemplo, el SqlWorkflowInstanceStoreBehavior crea una instancia de **SqlWorkflowInstanceStore**, la configura y la asigna a **DurableInstancingOptions. InstanceStore**(puede estar en inglés).</span><span class="sxs-lookup"><span data-stu-id="7473e-125">For example, the SqlWorkflowInstanceStoreBehavior creates an instance of the **SqlWorkflowInstanceStore**, configures it, and assigns it to the **DurableInstancingOptions.InstanceStore**.</span></span>

## <a name="enable-persistence-for-workflow-services-using-an-application-configuration-file"></a><span data-ttu-id="7473e-126">Habilita la persistencia para los servicios de flujo de trabajo usando un archivo de configuración de la aplicación</span><span class="sxs-lookup"><span data-stu-id="7473e-126">Enable Persistence for Workflow Services Using an Application Configuration File</span></span>

<span data-ttu-id="7473e-127">La persistencia puede habilitarse mediante un archivo de configuración de la aplicación agregando el código siguiente al archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="7473e-127">Persistence can be enabled using an application configuration file by adding the following code to your app.config or web.config file:</span></span>

```xml
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="myBehavior">
          <sqlWorkflowInstanceStore connectionString="Data Source=myDatabaseServer;Initial Catalog=myPersistenceDatabase" />
        </behavior>
      </serviceBehaviors>
    </behaviors>
  </system.serviceModel>
</configuration>
```
