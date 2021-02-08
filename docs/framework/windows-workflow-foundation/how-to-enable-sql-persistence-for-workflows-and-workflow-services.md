---
description: 'Más información acerca de cómo: habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo'
title: Procedimiento para habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo
ms.date: 03/30/2017
ms.assetid: ca7bf77f-3e5d-4b23-b17a-d0b60f46411d
ms.openlocfilehash: 5c124c4ec1d75d4b3b24468c04a4fb82236aa29a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777728"
---
# <a name="how-to-enable-sql-persistence-for-workflows-and-workflow-services"></a><span data-ttu-id="5698b-103">Procedimiento para habilitar la persistencia de SQL para flujos de trabajo y servicios de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5698b-103">How to: Enable SQL Persistence for Workflows and Workflow Services</span></span>

<span data-ttu-id="5698b-104">En este tema se describe cómo configurar la característica Almacén de instancias de flujo de trabajo de SQL para habilitar la persistencia para los flujos de trabajo y servicios de flujo de trabajo, según la programación, o mediante un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5698b-104">This topic describes how to configure the SQL Workflow Instance Store feature to enable persistence for your workflows and workflow services both programmatically and by using a configuration file.</span></span>

<span data-ttu-id="5698b-105">Windows Server APp Fabric simplifica el proceso de configuración de persistencia.</span><span class="sxs-lookup"><span data-stu-id="5698b-105">Windows Server App Fabric simplifies the process of configuring persistence.</span></span> <span data-ttu-id="5698b-106">Para obtener más información, consulte [configuración de persistencia de App fabric](/previous-versions/appfabric/ee790848(v=azure.10)).</span><span class="sxs-lookup"><span data-stu-id="5698b-106">For more information, see [App Fabric Persistence Configuration](/previous-versions/appfabric/ee790848(v=azure.10)).</span></span>

<span data-ttu-id="5698b-107">Antes de usar la característica Almacén de instancias de flujo de trabajo de SQL, cree una base de datos que la característica usará para conservar las instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-107">Before using the SQL Workflow Instance Store feature, create a database that the feature uses to persist workflow instances.</span></span> <span data-ttu-id="5698b-108">El programa de instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] copia los archivos de script de SQL asociados con la característica Almacén de instancias de flujo de trabajo en la carpeta %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN.</span><span class="sxs-lookup"><span data-stu-id="5698b-108">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] set-up program copies SQL script files associated with the SQL Workflow Instance Store feature to the %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN folder.</span></span> <span data-ttu-id="5698b-109">Ejecute estos archivos de script en una base de datos de SQL Server 2005 o SQL Server 2008 que desea que el almacén de instancias de flujo de trabajo de SQL use para conservar las instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-109">Run these script files against a SQL Server 2005 or SQL Server 2008 database that you want the SQL Workflow Instance Store to use to persist workflow instances.</span></span> <span data-ttu-id="5698b-110">Ejecute primero el archivo SqlWorkflowInstanceStoreSchema.sql y después SqlWorkflowInstanceStoreLogic.sql.</span><span class="sxs-lookup"><span data-stu-id="5698b-110">Run the SqlWorkflowInstanceStoreSchema.sql file first and then run the SqlWorkflowInstanceStoreLogic.sql file.</span></span>

> [!NOTE]
> <span data-ttu-id="5698b-111">Para limpiar la base de datos de persistencia para tener una base de datos nueva, ejecute los scripts en %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN en el siguiente orden.</span><span class="sxs-lookup"><span data-stu-id="5698b-111">To clean up the persistence database to have a fresh database, run the scripts in %WINDIR%\Microsoft.NET\Framework\v4.xxx\SQL\EN in the following order.</span></span>
>
> 1. <span data-ttu-id="5698b-112">SqlWorkflowInstanceStoreSchema.sql</span><span class="sxs-lookup"><span data-stu-id="5698b-112">SqlWorkflowInstanceStoreSchema.sql</span></span>
> 2. <span data-ttu-id="5698b-113">SqlWorkflowInstanceStoreLogic.sql</span><span class="sxs-lookup"><span data-stu-id="5698b-113">SqlWorkflowInstanceStoreLogic.sql</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5698b-114">Si no crea una base de datos de persistencia, la característica Almacén de instancias de flujo de trabajo de SQL inicia una excepción similar a la siguiente cuando un host intenta mantener flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-114">If you do not create a persistence database, the SQL Workflow Instance Store feature throws an exception similar to the following one when a host tries to persist workflows.</span></span>
>
> <span data-ttu-id="5698b-115">System.Data.SqlClient.SqlException: No se pudo encontrar el procedimiento almacenado 'System.Activities.DurableInstancing.CreateLockOwner'</span><span class="sxs-lookup"><span data-stu-id="5698b-115">System.Data.SqlClient.SqlException: Could not find stored procedure 'System.Activities.DurableInstancing.CreateLockOwner'</span></span>

<span data-ttu-id="5698b-116">En las siguientes secciones se describe cómo habilitar la persistencia para flujos de trabajo y servicios de flujo de trabajo que usen el almacén de instancias de flujo de trabajo de SQL.</span><span class="sxs-lookup"><span data-stu-id="5698b-116">The following sections describe how to enable persistence for workflows and workflow services using the SQL Workflow Instance Store.</span></span> <span data-ttu-id="5698b-117">Para obtener más información sobre las propiedades del almacén de instancias de flujo de trabajo de SQL, vea [propiedades del almacén de instancias de flujo de trabajo de SQL](properties-of-sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="5698b-117">For more information about properties of the SQL Workflow Instance Store, see [Properties of SQL Workflow Instance Store](properties-of-sql-workflow-instance-store.md).</span></span>

## <a name="enabling-persistence-for-self-hosted-workflows-that-use-workflowapplication"></a><span data-ttu-id="5698b-118">Habilitar la persistencia para flujos de trabajo auto-hospedados que usan WorkflowApplication</span><span class="sxs-lookup"><span data-stu-id="5698b-118">Enabling Persistence for Self-Hosted Workflows that use WorkflowApplication</span></span>

<span data-ttu-id="5698b-119">Puede habilitar la persistencia para los flujos de trabajo auto-hospedados que usen <xref:System.Activities.WorkflowApplication> mediante programación al utilizar el modelo de objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.</span><span class="sxs-lookup"><span data-stu-id="5698b-119">You can enable persistence for self-hosted workflows that use <xref:System.Activities.WorkflowApplication> programmatically by using the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> object model.</span></span> <span data-ttu-id="5698b-120">El siguiente procedimiento contiene los pasos para hacerlo.</span><span class="sxs-lookup"><span data-stu-id="5698b-120">The following procedure contains steps to do this.</span></span>

#### <a name="to-enable-persistence-for-self-hosted-workflows"></a><span data-ttu-id="5698b-121">Para habilitar la persistencia para los flujos de trabajo auto-hospedados</span><span class="sxs-lookup"><span data-stu-id="5698b-121">To enable persistence for self-hosted workflows</span></span>

1. <span data-ttu-id="5698b-122">Agregue una referencia a System.Activities.DurableInstancing.dll.</span><span class="sxs-lookup"><span data-stu-id="5698b-122">Add a reference to System.Activities.DurableInstancing.dll.</span></span>

2. <span data-ttu-id="5698b-123">Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.</span><span class="sxs-lookup"><span data-stu-id="5698b-123">Add the following statement at the top of the source file after the existing "using" statements.</span></span>

    ```csharp
    using System.Activities.DurableInstancing;
    ```

3. <span data-ttu-id="5698b-124">Construya un objeto <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> y asígnelo a la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A> del objeto <xref:System.Activities.WorkflowApplication> como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="5698b-124">Construct a <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> and assign it to the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> of the <xref:System.Activities.WorkflowApplication> as shown in the following code example.</span></span>

    ```csharp
    SqlWorkflowInstanceStore store =
        new SqlWorkflowInstanceStore("Server=.\\SQLEXPRESS;Initial Catalog=Persistence;Integrated Security=SSPI");

    WorkflowApplication wfApp =
        new WorkflowApplication(new Workflow1());

    wfApp.InstanceStore = store;
    ```

   > [!NOTE]
   > <span data-ttu-id="5698b-125">Según la edición de SQL Server, el nombre de servidor de cadena de conexión puede ser diferente.</span><span class="sxs-lookup"><span data-stu-id="5698b-125">Depending on your edition of SQL Server, the connection string server name may be different.</span></span>

4. <span data-ttu-id="5698b-126">Invoque el método <xref:System.Activities.WorkflowApplication.Persist%2A> en el objeto <xref:System.Activities.WorkflowApplication> para conservar un flujo de trabajo o el método <xref:System.Activities.WorkflowApplication.Unload%2A> para conservar y descargar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-126">Invoke the <xref:System.Activities.WorkflowApplication.Persist%2A> method on the <xref:System.Activities.WorkflowApplication> object to persist a workflow, or <xref:System.Activities.WorkflowApplication.Unload%2A> method to persist and unload a workflow.</span></span> <span data-ttu-id="5698b-127">También puede controlar el evento <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> emitido por el objeto <xref:System.Activities.WorkflowApplication> y devolver el miembro adecuado (<xref:System.Activities.PersistableIdleAction.Persist> o <xref:System.Activities.PersistableIdleAction.Unload>) de <xref:System.Activities.PersistableIdleAction>.</span><span class="sxs-lookup"><span data-stu-id="5698b-127">You can also handle the <xref:System.Activities.WorkflowApplication.PersistableIdle%2A> event raised by the <xref:System.Activities.WorkflowApplication> object and return appropriate (<xref:System.Activities.PersistableIdleAction.Persist> or <xref:System.Activities.PersistableIdleAction.Unload>) member of <xref:System.Activities.PersistableIdleAction>.</span></span>

   ```csharp
   wfApp.PersistableIdle = delegate(WorkflowApplicationIdleEventArgs e)
   {
       return PersistableIdleAction.Persist;
   };
   ```

> [!NOTE]
> <span data-ttu-id="5698b-128">Consulte el paso [Cómo: crear y ejecutar un flujo de trabajo de ejecución prolongada](how-to-create-and-run-a-long-running-workflow.md) del [tutorial de introducción](getting-started-tutorial.md) para obtener instrucciones paso a paso.</span><span class="sxs-lookup"><span data-stu-id="5698b-128">See the [How to: Create and Run a Long Running Workflow](how-to-create-and-run-a-long-running-workflow.md) step of the [Getting Started Tutorial](getting-started-tutorial.md) for step by step instructions.</span></span>

## <a name="enabling-persistence-for-self-hosted-workflow-services-that-use-the-workflowservicehost"></a><span data-ttu-id="5698b-129">Habilitar la persistencia para los servicios del flujo de trabajo auto-hospedados que usan WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="5698b-129">Enabling Persistence for Self-Hosted Workflow Services that use the WorkflowServiceHost</span></span>

<span data-ttu-id="5698b-130">Puede habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados que usan <xref:System.ServiceModel.WorkflowServiceHost> mediante programación al usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> o la clase <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A>.</span><span class="sxs-lookup"><span data-stu-id="5698b-130">You can enable persistence for self-hosted workflow services that use <xref:System.ServiceModel.WorkflowServiceHost> programmatically by using the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class or the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> class.</span></span>

### <a name="using-the-sqlworkflowinstancestorebehavior-class"></a><span data-ttu-id="5698b-131">Usar la clase SqlWorkflowInstanceStoreBehavior</span><span class="sxs-lookup"><span data-stu-id="5698b-131">Using the SqlWorkflowInstanceStoreBehavior Class</span></span>

<span data-ttu-id="5698b-132">El siguiente procedimiento detalla los pasos para usar la clase <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> a fin de habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados.</span><span class="sxs-lookup"><span data-stu-id="5698b-132">The following procedure contains steps to use the <xref:System.ServiceModel.Activities.Description.SqlWorkflowInstanceStoreBehavior> class to enable persistence for self-hosted workflow services.</span></span>

#### <a name="to-enable-persistence-using-sqlworkflowinstancestorebehavior"></a><span data-ttu-id="5698b-133">Para habilitar la persistencia mediante SqlWorkflowInstanceStoreBehavior</span><span class="sxs-lookup"><span data-stu-id="5698b-133">To enable persistence using SqlWorkflowInstanceStoreBehavior</span></span>

1. <span data-ttu-id="5698b-134">Agregue una referencia a System.ServiceModel.dll.</span><span class="sxs-lookup"><span data-stu-id="5698b-134">Add a reference to the System.ServiceModel.dll.</span></span>

2. <span data-ttu-id="5698b-135">Agregue la siguiente instrucción al principio del archivo de origen después de las instrucciones de uso existentes.</span><span class="sxs-lookup"><span data-stu-id="5698b-135">Add the following statement at the top of the source file after the existing "using" statements.</span></span>

    ```csharp
    using System.ServiceModel.Activities.Description;
    ```

3. <span data-ttu-id="5698b-136">Cree una instancia de `WorkflowServiceHost` y agregue los extremos para el servicio del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-136">Create an instance of the `WorkflowServiceHost` and add endpoints for the workflow service.</span></span>

    ```csharp
    WorkflowServiceHost host = new WorkflowServiceHost(new CountingWorkflow(), new Uri(hostBaseAddress));
    host.AddServiceEndpoint("ICountingWorkflow", new BasicHttpBinding(), "");
    ```

4. <span data-ttu-id="5698b-137">Construya un objeto `SqlWorkflowInstanceStoreBehavior` y defina las propiedades del objeto de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5698b-137">Construct a `SqlWorkflowInstanceStoreBehavior` object and to set properties of the behavior object.</span></span>

    ```csharp
    SqlWorkflowInstanceStoreBehavior instanceStoreBehavior = new SqlWorkflowInstanceStoreBehavior(connectionString);
    instanceStoreBehavior.HostLockRenewalPeriod = new TimeSpan(0, 0, 5);
    instanceStoreBehavior.InstanceCompletionAction = InstanceCompletionAction.DeleteAll;
    instanceStoreBehavior.InstanceLockedExceptionAction = InstanceLockedExceptionAction.AggressiveRetry;
    instanceStoreBehavior.InstanceEncodingOption = InstanceEncodingOption.GZip;
    instanceStoreBehavior.RunnableInstancesDetectionPeriod = new TimeSpan("00:00:02");
    host.Description.Behaviors.Add(instanceStoreBehavior);
    ```

5. <span data-ttu-id="5698b-138">Abra el host de servicio de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5698b-138">Open the workflow service host.</span></span>

    ```csharp
    host.Open();
    ```

### <a name="using-the-durableinstancingoptions-property"></a><span data-ttu-id="5698b-139">Usar la propiedad DurableInstancingOptions</span><span class="sxs-lookup"><span data-stu-id="5698b-139">Using the DurableInstancingOptions Property</span></span>

<span data-ttu-id="5698b-140">Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="5698b-140">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="5698b-141">Puede hacer lo mismo mediante programación para definir la propiedad <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> de `WorkflowServiceHost` sin usar la clase `SqlWorkflowInstanceStoreBehavior`, como se muestra en el siguiente código de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5698b-141">You can do the same programmatically to set the <xref:System.ServiceModel.Activities.WorkflowServiceHost.DurableInstancingOptions%2A> property of the `WorkflowServiceHost` without using the `SqlWorkflowInstanceStoreBehavior` class as shown in the following code example.</span></span>

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

## <a name="enabling-persistence-for-was-hosted-workflow-services-that-use-the-workflowservicehost-using-a-configuration-file"></a><span data-ttu-id="5698b-142">Habilitar la persistencia para los servicios de flujo de trabajo hospedados en WAS que usan WorkflowServiceHost mediante un archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="5698b-142">Enabling Persistence for WAS-Hosted Workflow Services that use the WorkflowServiceHost using a Configuration File</span></span>

<span data-ttu-id="5698b-143">Puede habilitar la persistencia para los servicios de flujo de trabajo auto-hospedados u hospedados por Windows Process Activation Service (WAS) usando un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5698b-143">You can enable persistence for self-hosted or Windows Process Activation Service (WAS)-hosted workflow services by using a configuration file.</span></span> <span data-ttu-id="5698b-144">Un servicio de flujo de trabajo hospedado en WAS usa WorkflowServiceHost tal y como lo hacen los servicios de flujo de trabajo auto-hospedados.</span><span class="sxs-lookup"><span data-stu-id="5698b-144">A WAS-hosted workflow service uses the WorkflowServiceHost as the self-hosted workflow services do.</span></span>

<span data-ttu-id="5698b-145">`SqlWorkflowInstanceStoreBehavior`, Un comportamiento de servicio que le permite cambiar las propiedades del [almacén de instancias de flujo de trabajo de SQL](sql-workflow-instance-store.md) de forma cómoda a través de la configuración XML.</span><span class="sxs-lookup"><span data-stu-id="5698b-145">The `SqlWorkflowInstanceStoreBehavior`, a service behavior that allows you to conveniently change the [SQL Workflow Instance Store](sql-workflow-instance-store.md) properties through XML configuration.</span></span> <span data-ttu-id="5698b-146">En el caso de los servicios de flujo de trabajo hospedados por WAS, use el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="5698b-146">For WAS-hosted workflow services, use the Web.config file.</span></span> <span data-ttu-id="5698b-147">El siguiente ejemplo de configuración muestra cómo configurar el Almacén de instancias de flujo de trabajo de SQL mediante el elemento de comportamiento `sqlWorkflowInstanceStore` en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="5698b-147">The following configuration example shows how to configure the SQL Workflow Instance Store by using the `sqlWorkflowInstanceStore` behavior element in a configuration file.</span></span>

```xml
<serviceBehaviors>
    <behavior name="">
        <sqlWorkflowInstanceStore
                    connectionString="Data Source=(local);Initial Catalog=DefaultPersistenceProviderDb;Integrated Security=True;Async=true"
                    instanceEncodingOption="GZip | None"
                    instanceCompletionAction="DeleteAll | DeleteNothing"
                    instanceLockedExceptionAction="NoRetry | BasicRetry |AggressiveRetry"
                    hostLockRenewalPeriod="00:00:30"
                    runnableInstancesDetectionPeriod="00:00:05" />

    </behavior>
</serviceBehaviors>
```

<span data-ttu-id="5698b-148">Si no establece los valores para las propiedades `connectionString` o `connectionStringName`, el almacén de instancias de flujo de trabajo de SQL usa la cadena de conexión con nombre predeterminada `DefaultSqlWorkflowInstanceStoreConnectionString`.</span><span class="sxs-lookup"><span data-stu-id="5698b-148">If you do not set values for the `connectionString` or the `connectionStringName` property, the SQL Workflow Instance Store uses the default named connection string `DefaultSqlWorkflowInstanceStoreConnectionString`.</span></span>

<span data-ttu-id="5698b-149">Cuando se aplica `SqlWorkflowInstanceStoreBehavior`, `DurableInstancingOptions.InstanceStore` en `WorkflowServiceHost` está definida en el objeto `SqlWorkflowInstanceStore` creado con los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="5698b-149">When the `SqlWorkflowInstanceStoreBehavior` is applied, the `DurableInstancingOptions.InstanceStore` on the `WorkflowServiceHost` is set to the `SqlWorkflowInstanceStore` object created using the configuration values.</span></span> <span data-ttu-id="5698b-150">Puede hacer lo mismo mediante programación para usar `SqlWorkflowInstanceStore` con `WorkflowServiceHost` sin usar el elemento de comportamiento del servicio.</span><span class="sxs-lookup"><span data-stu-id="5698b-150">You can do the same programmatically to use the `SqlWorkflowInstanceStore` with `WorkflowServiceHost` without using the service behavior element.</span></span>

```csharp
workflowServiceHost.DurableInstancingOptions.InstanceStore = sqlInstanceStoreObject;
```

> [!IMPORTANT]
> <span data-ttu-id="5698b-151">Se recomienda no almacenar la información confidencial, como nombres de usuario y contraseñas, en el archivo Web.config.</span><span class="sxs-lookup"><span data-stu-id="5698b-151">It is recommended that you do not store sensitive information such as user names and passwords in the Web.config file.</span></span> <span data-ttu-id="5698b-152">Si no almacena información confidencial en el archivo Web.config, debería proteger el acceso al archivo Web.config mediante las lista de control de acceso (ACL) del sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="5698b-152">If you do store sensitive information in the Web.config file, you should secure access to the Web.config file by using file system Access Control Lists (ACLs).</span></span> <span data-ttu-id="5698b-153">Además, también puede proteger los valores de configuración de un archivo de configuración, como se mencionó en [cifrar información de configuración mediante la configuración protegida](/previous-versions/aspnet/53tyfkaw(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="5698b-153">In addition, you can also secure the configuration values within a configuration file as mentioned in [Encrypting Configuration Information Using Protected Configuration](/previous-versions/aspnet/53tyfkaw(v=vs.100)).</span></span>

### <a name="machineconfig-elements-related-to-the-sql-workflow-instance-store-feature"></a><span data-ttu-id="5698b-154">Elementos Machine.config relacionados con la característica Almacén de instancias de flujo de trabajo de SQL</span><span class="sxs-lookup"><span data-stu-id="5698b-154">Machine.config Elements Related to the SQL Workflow Instance Store Feature</span></span>

<span data-ttu-id="5698b-155">La instalación de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] agrega los siguientes elementos relacionados con la característica Almacén de instancias de flujo de trabajo de SQL al archivo Machine.config:</span><span class="sxs-lookup"><span data-stu-id="5698b-155">The [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] installation adds the following elements related to the SQL Workflow Instance Store feature to the Machine.config file:</span></span>

- <span data-ttu-id="5698b-156">Agrega el siguiente elemento de extensión de comportamiento al archivo Machine.config para que pueda usar el \<sqlWorkflowInstanceStore> elemento de comportamiento del servicio en el archivo de configuración para configurar la persistencia para los servicios.</span><span class="sxs-lookup"><span data-stu-id="5698b-156">Adds the following behavior extension element to the Machine.config file so that you can use the \<sqlWorkflowInstanceStore> service behavior element in the configuration file to configure persistence for your services.</span></span>

    ```xml
    <configuration>
        <system.serviceModel>
            <extensions>
                <behaviorExtensions>
                    <add name="sqlWorkflowInstanceStore" type="System.Activities.DurableInstancing.SqlWorkflowInstanceStoreElement, System.Activities.DurableInstancing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                </behaviorExtensions>
            </extensions>
        </system.serviceModel>
    </configuration>
    ```
