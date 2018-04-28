---
title: 'Cómo: Configurar la persistencia con WorkflowServiceHost'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31cd4df-13a3-4a9a-9be8-5243e0055356
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8a11ab534cbb643d17985670e202954313f5a068
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-configure-persistence-with-workflowservicehost"></a><span data-ttu-id="92ea7-102">Cómo: Configurar la persistencia con WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="92ea7-102">How to: Configure Persistence with WorkflowServiceHost</span></span>
<span data-ttu-id="92ea7-103">En este tema, se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia de los flujos de trabajo hospedados en <xref:System.ServiceModel.Activities.WorkflowServiceHost> mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="92ea7-103">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for workflows hosted in <xref:System.ServiceModel.Activities.WorkflowServiceHost> by using a configuration file.</span></span> <span data-ttu-id="92ea7-104">Antes de utilizar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos SQL que se use para guardar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="92ea7-104">Before using the SQL Workflow Instance Store feature you must create a SQL database that is used to persist workflow instances.</span></span> <span data-ttu-id="92ea7-105">Para obtener más información, consulte [Cómo: habilitar la persistencia de SQL para los flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-105">For more information, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-configuration"></a><span data-ttu-id="92ea7-106">Para configurar el Almacén de instancias de flujo de trabajo de SQL en Configuración</span><span class="sxs-lookup"><span data-stu-id="92ea7-106">To Configure the SQL Workflow Instance Store in Configuration</span></span>  
  
1.  <span data-ttu-id="92ea7-107">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de la configuración de XML.</span><span class="sxs-lookup"><span data-stu-id="92ea7-107">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through XML configuration.</span></span> <span data-ttu-id="92ea7-108">El siguiente ejemplo de configuración muestra cómo configurar el Almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <`sqlWorkflowInstanceStore`> en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="92ea7-108">The following configuration example shows how to configure the SQL workflow instance store by using the <`sqlWorkflowInstanceStore`> behavior element in a configuration file.</span></span>  
  
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
            <sqlWorkflowInstanceStore/>  
        </behavior>  
    </serviceBehaviors>  
    ```  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="92ea7-109"> Cómo configurar el almacén de instancias de flujo de trabajo SQL, consulte [Cómo: habilitar la persistencia de SQL para los flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-109"> how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="92ea7-110"> la configuración individual de la <`sqlWorkflowInstanceStore`> elemento de comportamiento, consulte [almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-110"> the individual settings for the <`sqlWorkflowInstanceStore`> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="92ea7-111">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="92ea7-111">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="92ea7-112">Para obtener más información, consulte [Windows Server App Fabric persistencia](http://go.microsoft.com/fwlink/?LinkId=193121).</span><span class="sxs-lookup"><span data-stu-id="92ea7-112">For more information, see [Windows Server App Fabric Persistence](http://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92ea7-113">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="92ea7-113">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="92ea7-114">Para obtener más información, vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="92ea7-114">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
### <a name="to-configure-the-sql-workflow-instance-store-in-code"></a><span data-ttu-id="92ea7-115">Para configurar el Almacén de instancias de flujo de trabajo de SQL en el código</span><span class="sxs-lookup"><span data-stu-id="92ea7-115">To Configure the SQL Workflow Instance Store in Code</span></span>  
  
1.  <span data-ttu-id="92ea7-116">Las propiedades del Almacén de instancias de flujo de trabajo de SQL se pueden configurar a través de <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, un comportamiento del servicio que le permite cambiar la configuración a través de código.</span><span class="sxs-lookup"><span data-stu-id="92ea7-116">The properties of the SQL workflow instance store can be configured through the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior>, a service behavior that allows you to change the settings through code.</span></span> <span data-ttu-id="92ea7-117">El siguiente ejemplo muestra cómo configurar el almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> en un código.</span><span class="sxs-lookup"><span data-stu-id="92ea7-117">The following example shows how to configure the SQL workflow instance store by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element in a code</span></span>  
  
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
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="92ea7-118"> Cómo configurar el almacén de instancias de flujo de trabajo SQL, consulte [Cómo: habilitar la persistencia de SQL para los flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-118"> how to configure the SQL workflow instance store, see [How to: Enable SQL Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-sql-persistence-for-workflows-and-workflow-services.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="92ea7-119"> la configuración individual de la <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> elemento de comportamiento, consulte [almacén de instancias de flujo de trabajo de SQL](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-119"> the individual settings for the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> behavior element, see [SQL Workflow Instance Store](../../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).</span></span> <span data-ttu-id="92ea7-120">Windows Server App Fabric proporciona su propio almacén de persistencia.</span><span class="sxs-lookup"><span data-stu-id="92ea7-120">Windows Server App Fabric provides its own persistence store.</span></span> <span data-ttu-id="92ea7-121">Para obtener más información, consulte [Windows Server App Fabric persistencia](http://go.microsoft.com/fwlink/?LinkId=193121).</span><span class="sxs-lookup"><span data-stu-id="92ea7-121">For more information, see [Windows Server App Fabric Persistence](http://go.microsoft.com/fwlink/?LinkId=193121).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="92ea7-122">El ejemplo de configuración anterior usa una configuración simplificada.</span><span class="sxs-lookup"><span data-stu-id="92ea7-122">The preceding configuration example uses simplified configuration.</span></span> <span data-ttu-id="92ea7-123">Para obtener más información, vea [configuración simplificada](../../../../docs/framework/wcf/simplified-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="92ea7-123">For more information, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)</span></span>  
  
     <span data-ttu-id="92ea7-124">Para obtener un ejemplo de cómo configurar la persistencia mediante programación, vea [Cómo: habilitar la persistencia para flujos de trabajo y los servicios de flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span><span class="sxs-lookup"><span data-stu-id="92ea7-124">For an example of how to configure persistence programmatically see [How to: Enable Persistence for Workflows and Workflow Services](../../../../docs/framework/windows-workflow-foundation/how-to-enable-persistence-for-workflows-and-workflow-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92ea7-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="92ea7-125">See Also</span></span>  
 [<span data-ttu-id="92ea7-126">Servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="92ea7-126">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="92ea7-127">Persistencia del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="92ea7-127">Workflow Persistence</span></span>](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [<span data-ttu-id="92ea7-128">Persistencia de AppFabric de Windows Server</span><span class="sxs-lookup"><span data-stu-id="92ea7-128">Windows Server App Fabric Persistence</span></span>](http://go.microsoft.com/fwlink/?LinkId=193121)
