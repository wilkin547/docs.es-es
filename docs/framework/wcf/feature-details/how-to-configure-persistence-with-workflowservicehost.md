---
description: Más información acerca de cómo configurar la persistencia con WorkflowServiceHost
title: Procedimiento para configurar la persistencia con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 79945fb791cc25bdf362302fa884636942fb5692
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99780042"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="04a5a-103">Procedimiento para configurar la persistencia con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="04a5a-103">How to: Configure Persistence with WorkflowServiceHost</span></span>

<span data-ttu-id="04a5a-104">En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="04a5a-104">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="04a5a-105">Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="04a5a-105">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="04a5a-106">Para obtener más información, vea [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-106">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="04a5a-107">Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración</span><span class="sxs-lookup"><span data-stu-id="04a5a-107">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="04a5a-108">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML.</span><span class="sxs-lookup"><span data-stu-id="04a5a-108">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="04a5a-109">En el ejemplo de configuración siguiente se muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el `sqlWorkflowInstanceStore` elemento de comportamiento <> en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="04a5a-109">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
    ```xml  
    <serviceBehaviors>  
        <behavior name="">  
            <sqlWorkflowInstanceStore
                 connectionString="provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"  
                 instanceEncodingOption="GZip | None"  
                 instanceCompletionAction="DeleteAll | DeleteNothing"  
                 instanceLockedExceptionAction="NoRetry | SimpleRetry | AggressiveRetry"  
                 hostLockRenewalPeriod="00:00:30"
                 runnableInstancesDetectionPeriod="00:00:05">  
            </sqlWorkflowInstanceStore>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     <span data-ttu-id="04a5a-110">Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo de SQL, consulte [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-110">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="04a5a-111">Para obtener más información sobre la configuración individual del `sqlWorkflowInstanceStore` elemento <> Behavior, vea [almacén de instancias de flujo de trabajo de SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-111">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="04a5a-112">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="04a5a-112">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="04a5a-113">Para obtener más información, consulte [persistencia de Windows Server App fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="04a5a-113">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="04a5a-114">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="04a5a-114">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="04a5a-115">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="04a5a-115">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="04a5a-116">Para configurar el Almacén de instancias de flujo de trabajo de SQL en el código</span><span class="sxs-lookup"><span data-stu-id="04a5a-116">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="04a5a-117">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de código.</span><span class="sxs-lookup"><span data-stu-id="04a5a-117">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="04a5a-118">El siguiente ejemplo muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> en un código.</span><span class="sxs-lookup"><span data-stu-id="04a5a-118">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
    ```csharp  
    host.Description.Behaviors.Add(new SqlWorkflowInstanceStoreBehavior  
    {  
       ConnectionString = "provider=System.Data.SqlClient;Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true",  
       InstanceEncodingOption = "GZip | None",  
       InstanceCompletionAction = "DeleteAll | DeleteNothing",  
       InstanceLockedExceptionAction = "NoRetry | SimpleRetry | AggressiveRetry",  
       HostLockRenewalPeriod = new TimeSpan(00, 00, 30),  
       RunnableInstancesDetectionPeriod = new TimeSpan(00, 00, 05)  
    });  
    ```  
  
     <span data-ttu-id="04a5a-119">Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo de SQL, consulte [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-119">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="04a5a-120">Para obtener más información sobre la configuración individual del <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamiento, vea [almacén de instancias de flujo de trabajo de SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-120">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="04a5a-121">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="04a5a-121">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="04a5a-122">Para obtener más información, consulte [persistencia de Windows Server App fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="04a5a-122">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="04a5a-123">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="04a5a-123">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="04a5a-124">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="04a5a-124">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="04a5a-125">Para obtener un ejemplo de cómo configurar la persistencia mediante programación [, vea cómo: habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="04a5a-125">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04a5a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="04a5a-126">See also</span></span>

- [<span data-ttu-id="04a5a-127">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="04a5a-127">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="04a5a-128">Persistencia del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="04a5a-128">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="04a5a-129">[Persistencia de Windows Server App Fabric](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="04a5a-129">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
