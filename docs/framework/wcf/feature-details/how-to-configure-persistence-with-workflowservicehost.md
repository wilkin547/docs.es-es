---
title: Procedimiento para configurar la persistencia con WorkflowServiceHost
ms.date: 03/30/2017
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
ms.openlocfilehash: 93397923154d780ed3b714bf0bb95c15bc71bbfb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556315"
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="80821-102">Procedimiento para configurar la persistencia con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="80821-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="80821-103">En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="80821-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="80821-104">Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="80821-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="80821-105">Para obtener más información, vea [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="80821-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="80821-106">Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración</span><span class="sxs-lookup"><span data-stu-id="80821-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1. <span data-ttu-id="80821-107">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML.</span><span class="sxs-lookup"><span data-stu-id="80821-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="80821-108">En el ejemplo de configuración siguiente se muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el `sqlWorkflowInstanceStore` elemento de comportamiento <> en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="80821-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
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
  
     <span data-ttu-id="80821-109">Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo de SQL, consulte [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="80821-109">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="80821-110">Para obtener más información sobre la configuración individual del `sqlWorkflowInstanceStore` elemento <> Behavior, vea [almacén de instancias de flujo de trabajo de SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="80821-110">For more information about the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="80821-111">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="80821-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="80821-112">Para obtener más información, consulte [persistencia de Windows Server App fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="80821-112">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="80821-113">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="80821-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="80821-114">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="80821-114">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="80821-115">Para configurar el Almacén de instancias de flujo de trabajo de SQL en el código</span><span class="sxs-lookup"><span data-stu-id="80821-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1. <span data-ttu-id="80821-116">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de código.</span><span class="sxs-lookup"><span data-stu-id="80821-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="80821-117">El siguiente ejemplo muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> en un código.</span><span class="sxs-lookup"><span data-stu-id="80821-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
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
  
     <span data-ttu-id="80821-118">Para obtener más información sobre cómo configurar el almacén de instancias de flujo de trabajo de SQL, consulte [Cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="80821-118">For more information about how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> <span data-ttu-id="80821-119">Para obtener más información sobre la configuración individual del <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamiento, vea [almacén de instancias de flujo de trabajo de SQL](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="80821-119">For more information about the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="80821-120">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="80821-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="80821-121">Para obtener más información, consulte [persistencia de Windows Server App fabric](/previous-versions/appfabric/ee677272(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="80821-121">For more information, see [Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10)).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="80821-122">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="80821-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="80821-123">Para obtener más información, vea [configuración simplificada](../simplified-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="80821-123">For more information, see [Simplified Configuration](../simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="80821-124">Para obtener un ejemplo de cómo configurar la persistencia mediante programación [, vea cómo: habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="80821-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80821-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="80821-125">See also</span></span>

- [<span data-ttu-id="80821-126">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="80821-126">Workflow Services</span></span>](workflow-services.md)
- [<span data-ttu-id="80821-127">Persistencia del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="80821-127">Workflow Persistence</span></span>](../../windows-workflow-foundation/workflow-persistence.md)
- <span data-ttu-id="80821-128">[Persistencia de Windows Server App Fabric](/previous-versions/appfabric/ee677272(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="80821-128">[Windows Server App Fabric Persistence](/previous-versions/appfabric/ee677272(v=azure.10))</span></span>
