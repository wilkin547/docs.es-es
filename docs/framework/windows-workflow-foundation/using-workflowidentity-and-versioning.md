---
description: Más información acerca de cómo usar WorkflowIdentity y control de versiones
title: Usar WorkflowIdentity y el control de versiones
ms.date: 03/30/2017
ms.assetid: b8451735-8046-478f-912b-40870a6c0c3a
ms.openlocfilehash: b51bce26b69d77e0be702e40a315dcd138d2fc03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754971"
---
# <a name="using-workflowidentity-and-versioning"></a><span data-ttu-id="57f72-103">Usar WorkflowIdentity y el control de versiones</span><span class="sxs-lookup"><span data-stu-id="57f72-103">Using WorkflowIdentity and Versioning</span></span>

<span data-ttu-id="57f72-104"><xref:System.Activities.WorkflowIdentity> proporciona una manera para que los desarrolladores de aplicaciones de flujo de trabajo asocien un nombre y una <xref:System.Version> con una definición de flujo de trabajo, y para que esta información se asocie a una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="57f72-104"><xref:System.Activities.WorkflowIdentity> provides a way for workflow application developers to associate a name and a <xref:System.Version> with a workflow definition, and for this information to be associated with a persisted workflow instance.</span></span> <span data-ttu-id="57f72-105">Los desarrolladores de aplicaciones de flujo de trabajo pueden usar esta información de identidad para habilitar escenarios como la ejecución en paralelo de varias versiones de una definición de flujo de trabajo; además esta información proporciona la piedra angular para otras funcionalidades como la actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="57f72-105">This identity information can be used by workflow application developers to enable scenarios such as side-by-side execution of multiple versions of a workflow definition, and provides the cornerstone for other functionality such as dynamic update.</span></span> <span data-ttu-id="57f72-106">Este tema proporciona información general sobre cómo usar <xref:System.Activities.WorkflowIdentity> con hospedaje de <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="57f72-106">This topic provides as overview of using <xref:System.Activities.WorkflowIdentity> with <xref:System.Activities.WorkflowApplication> hosting.</span></span> <span data-ttu-id="57f72-107">Para obtener información sobre la ejecución en paralelo de definiciones de flujo de trabajo en un servicio de flujo de trabajo, vea [control de versiones en paralelo en WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span><span class="sxs-lookup"><span data-stu-id="57f72-107">For information on side-by-side execution of workflow definitions in a workflow service, see [Side by Side Versioning in WorkflowServiceHost](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).</span></span> <span data-ttu-id="57f72-108">Para obtener información sobre la actualización dinámica, consulte [actualización dinámica](dynamic-update.md).</span><span class="sxs-lookup"><span data-stu-id="57f72-108">For information on dynamic update, see [Dynamic Update](dynamic-update.md).</span></span>

## <a name="in-this-topic"></a><span data-ttu-id="57f72-109">En este tema</span><span class="sxs-lookup"><span data-stu-id="57f72-109">In this topic</span></span>

- [<span data-ttu-id="57f72-110">Usar WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="57f72-110">Using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#UsingWorkflowIdentity)

  - [<span data-ttu-id="57f72-111">Ejecución en paralelo mediante WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="57f72-111">Side-by-side Execution using WorkflowIdentity</span></span>](using-workflowidentity-and-versioning.md#SxS)

- [<span data-ttu-id="57f72-112">Actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57f72-112">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)

  - [<span data-ttu-id="57f72-113">Para actualizar el esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="57f72-113">To upgrade the database schema</span></span>](using-workflowidentity-and-versioning.md#ToUpgrade)

## <a name="using-workflowidentity"></a><a name="UsingWorkflowIdentity"></a> <span data-ttu-id="57f72-114">Usar WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="57f72-114">Using WorkflowIdentity</span></span>

<span data-ttu-id="57f72-115">Para usar <xref:System.Activities.WorkflowIdentity>, cree una instancia, configúrela y asóciela con una instancia de <xref:System.Activities.WorkflowApplication>.</span><span class="sxs-lookup"><span data-stu-id="57f72-115">To use <xref:System.Activities.WorkflowIdentity>, create an instance, configure it, and associate it with a <xref:System.Activities.WorkflowApplication> instance.</span></span> <span data-ttu-id="57f72-116">Una instancia de <xref:System.Activities.WorkflowIdentity> contiene tres elementos de identificación de información.</span><span class="sxs-lookup"><span data-stu-id="57f72-116">A <xref:System.Activities.WorkflowIdentity> instance contains three identifying pieces of information.</span></span> <span data-ttu-id="57f72-117"><xref:System.Activities.WorkflowIdentity.Name%2A> y <xref:System.Activities.WorkflowIdentity.Version%2A> contienen un nombre y <xref:System.Version> y son necesarios, y <xref:System.Activities.WorkflowIdentity.Package%2A> es opcional y se puede usar para especificar una cadena adicional que contiene información como el nombre del ensamblado u otra información deseada.</span><span class="sxs-lookup"><span data-stu-id="57f72-117"><xref:System.Activities.WorkflowIdentity.Name%2A> and <xref:System.Activities.WorkflowIdentity.Version%2A> contain a name and a <xref:System.Version> and are required, and <xref:System.Activities.WorkflowIdentity.Package%2A> is optional and can be used to specify an additional string containing information such as assembly name or other desired information.</span></span> <span data-ttu-id="57f72-118"><xref:System.Activities.WorkflowIdentity> es único si cualquiera de sus tres propiedades son diferentes de otra <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="57f72-118">A <xref:System.Activities.WorkflowIdentity> is unique if any of its three properties are different from another <xref:System.Activities.WorkflowIdentity>.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="57f72-119">Un objeto <xref:System.Activities.WorkflowIdentity> no debe contener información de identificación personal (PII).</span><span class="sxs-lookup"><span data-stu-id="57f72-119">A <xref:System.Activities.WorkflowIdentity> should not contain any personally identifiable information (PII).</span></span> <span data-ttu-id="57f72-120">El runtime emite la información acerca del elemento <xref:System.Activities.WorkflowIdentity> usado para crear una instancia a cualquier servicio de seguimiento configurado en diferentes puntos del ciclo de vida de actividad.</span><span class="sxs-lookup"><span data-stu-id="57f72-120">Information about the <xref:System.Activities.WorkflowIdentity> used to create an instance is emitted to any configured tracking services at several different points of the activity life-cycle by the runtime.</span></span> <span data-ttu-id="57f72-121">El seguimiento de WF no tiene ningún mecanismo para ocultar la PII (datos de usuario confidenciales).</span><span class="sxs-lookup"><span data-stu-id="57f72-121">WF Tracking does not have any mechanism to hide PII (sensitive user data).</span></span> <span data-ttu-id="57f72-122">Por lo tanto, una instancia de <xref:System.Activities.WorkflowIdentity> no debe contener datos PII ya que el runtime los emitirá en registros de seguimiento y serán visibles para cualquiera que tenga acceso para ver los registros de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="57f72-122">Therefore, a <xref:System.Activities.WorkflowIdentity> instance should not contain any PII data as it will be emitted by the runtime in tracking records and may be visible to anyone with access to view the tracking records.</span></span>

<span data-ttu-id="57f72-123">En el ejemplo siguiente, se crea una <xref:System.Activities.WorkflowIdentity> y se asocia a una instancia de un flujo de trabajo creado mediante una definición de flujo de trabajo de `MortgageWorkflow`.</span><span class="sxs-lookup"><span data-stu-id="57f72-123">In the following example, a <xref:System.Activities.WorkflowIdentity> is created and associated with an instance of a workflow created using a `MortgageWorkflow` workflow definition.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="57f72-124">Al recargar y al reanudar un flujo de trabajo, se debe usar una <xref:System.Activities.WorkflowIdentity> configurada para coincidir con la <xref:System.Activities.WorkflowIdentity> de la instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="57f72-124">When reloading and resuming a workflow, a <xref:System.Activities.WorkflowIdentity> that is configured to match the <xref:System.Activities.WorkflowIdentity> of the persisted workflow instance must be used.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the workflow.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="57f72-125">Si la <xref:System.Activities.WorkflowIdentity> usada al recargar la instancia de flujo de trabajo no coincide con la <xref:System.Activities.WorkflowIdentity> persistente, se producirá <xref:System.Activities.VersionMismatchException>.</span><span class="sxs-lookup"><span data-stu-id="57f72-125">If the <xref:System.Activities.WorkflowIdentity> used when reloading the workflow instance does not match the persisted <xref:System.Activities.WorkflowIdentity>, a <xref:System.Activities.VersionMismatchException> is thrown.</span></span> <span data-ttu-id="57f72-126">En el ejemplo siguiente se realiza un intento de carga en la instancia de `MortgageWorkflow` que se ha hecho persistente en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="57f72-126">In the following example a load attempt is made on the `MortgageWorkflow` instance that was persisted in the previous example.</span></span> <span data-ttu-id="57f72-127">Este intento de carga se realiza mediante una <xref:System.Activities.WorkflowIdentity> configurada para una versión más reciente del flujo de trabajo de hipotecas que no coincide con la instancia persistente.</span><span class="sxs-lookup"><span data-stu-id="57f72-127">This load attempt is made using a <xref:System.Activities.WorkflowIdentity> configured for a newer version of the mortgage workflow that does not match the persisted instance.</span></span>

```csharp
WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow_v2(), identityV2);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Attempt to load the workflow instance.
wfApp.Load(instanceId);

// Resume the workflow...
```

<span data-ttu-id="57f72-128">Cuando se ejecuta el código anterior, se produce la <xref:System.Activities.VersionMismatchException> siguiente.</span><span class="sxs-lookup"><span data-stu-id="57f72-128">When the previous code is executed, the following <xref:System.Activities.VersionMismatchException> is thrown.</span></span>

```output
The WorkflowIdentity ('MortgageWorkflow v1; Version=1.0.0.0') of the loaded instance does not match the WorkflowIdentity ('MortgageWorkflow v2; Version=2.0.0.0') of the provided workflow definition. The instance can be loaded using a different definition, or updated using Dynamic Update.
```

### <a name="side-by-side-execution-using-workflowidentity"></a><a name="SxS"></a> <span data-ttu-id="57f72-129">Ejecución en paralelo mediante WorkflowIdentity</span><span class="sxs-lookup"><span data-stu-id="57f72-129">Side-by-side Execution using WorkflowIdentity</span></span>

<span data-ttu-id="57f72-130"><xref:System.Activities.WorkflowIdentity> se puede usar para facilitar la ejecución de varias versiones de un flujo de trabajo en paralelo.</span><span class="sxs-lookup"><span data-stu-id="57f72-130"><xref:System.Activities.WorkflowIdentity> can be used to facilitate the execution of multiple versions of a workflow side-by-side.</span></span> <span data-ttu-id="57f72-131">Un escenario común es cambiar los requisitos comerciales de un flujo de trabajo de ejecución prolongada.</span><span class="sxs-lookup"><span data-stu-id="57f72-131">One common scenario is changing business requirements on a long-running workflow.</span></span> <span data-ttu-id="57f72-132">Pueden ejecutarse varias instancias de un flujo de trabajo cuando se implementa una versión actualizada.</span><span class="sxs-lookup"><span data-stu-id="57f72-132">Many instances of a workflow could be running when an updated version is deployed.</span></span> <span data-ttu-id="57f72-133">La aplicación host se puede configurar para usar la definición de flujo de trabajo actualizada al iniciar nuevas instancias y es responsabilidad de la aplicación host proporcionar la definición de flujo de trabajo correcta al reanudar las instancias.</span><span class="sxs-lookup"><span data-stu-id="57f72-133">The host application can be configured to use the updated workflow definition when starting new instances, and it is the responsibility of the host application to provide the correct workflow definition when resuming instances.</span></span> <span data-ttu-id="57f72-134"><xref:System.Activities.WorkflowIdentity> puede usarse para identificar y proporcionar la definición de flujo de trabajo coincidente al reanudar instancias de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57f72-134"><xref:System.Activities.WorkflowIdentity> can be used to identify and supply the matching workflow definition when resuming workflow instances.</span></span>

<span data-ttu-id="57f72-135">Para recuperar la <xref:System.Activities.WorkflowIdentity> de una instancia de flujo de trabajo persistente, se usa el método <xref:System.Activities.WorkflowApplication.GetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="57f72-135">To retrieve the <xref:System.Activities.WorkflowIdentity> of a persisted workflow instance, the <xref:System.Activities.WorkflowApplication.GetInstance%2A> method is used.</span></span> <span data-ttu-id="57f72-136">El método <xref:System.Activities.WorkflowApplication.GetInstance%2A> toma el <xref:System.Activities.WorkflowApplication.Id%2A> de la instancia de flujo de trabajo persistente y el <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> que contiene la instancia persistente y devuelve una <xref:System.Activities.WorkflowApplicationInstance>.</span><span class="sxs-lookup"><span data-stu-id="57f72-136">The <xref:System.Activities.WorkflowApplication.GetInstance%2A> method takes the <xref:System.Activities.WorkflowApplication.Id%2A> of the persisted workflow instance and the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that contains the persisted instance and returns a <xref:System.Activities.WorkflowApplicationInstance>.</span></span> <span data-ttu-id="57f72-137"><xref:System.Activities.WorkflowApplicationInstance> contiene información sobre una instancia de flujo de trabajo persistente, incluida su <xref:System.Activities.WorkflowIdentity> asociada.</span><span class="sxs-lookup"><span data-stu-id="57f72-137">A <xref:System.Activities.WorkflowApplicationInstance> contains information about a persisted workflow instance, including its associated <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="57f72-138">El host puede usar esta <xref:System.Activities.WorkflowIdentity> asociada para proporcionar la definición de flujo de trabajo correcta al cargar y reanudar la instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57f72-138">This associated <xref:System.Activities.WorkflowIdentity> can be used by the host to supply the correct workflow definition when loading and resuming the workflow instance.</span></span>

> [!NOTE]
> <span data-ttu-id="57f72-139">Un objeto <xref:System.Activities.WorkflowIdentity> NULL es válido y el host puede usarlo para asignar las instancias persistentes sin ningún <xref:System.Activities.WorkflowIdentity> asociado a la definición de flujo de trabajo adecuada.</span><span class="sxs-lookup"><span data-stu-id="57f72-139">A null <xref:System.Activities.WorkflowIdentity> is valid, and can be used by the host to map instances that were persisted with no associated <xref:System.Activities.WorkflowIdentity> to the proper workflow definition.</span></span> <span data-ttu-id="57f72-140">Este escenario puede producirse cuando una aplicación de flujo de trabajo no se escribió inicialmente con el control de versiones de flujo de trabajo o cuando se actualiza una aplicación desde .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="57f72-140">This scenario can occur when a workflow application was not initially written with workflow versioning, or when an application is upgraded from .NET Framework 4.</span></span> <span data-ttu-id="57f72-141">Para obtener más información, consulte [actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones de flujo de trabajo](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span><span class="sxs-lookup"><span data-stu-id="57f72-141">For more information, see [Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases).</span></span>

<span data-ttu-id="57f72-142">En el ejemplo siguiente `Dictionary<WorkflowIdentity, Activity>` , se usa para asociar <xref:System.Activities.WorkflowIdentity> instancias con sus definiciones de flujo de trabajo coincidentes, y un flujo de trabajo se inicia utilizando la `MortgageWorkflow` definición de flujo de trabajo, que está asociada a `identityV1` <xref:System.Activities.WorkflowIdentity> .</span><span class="sxs-lookup"><span data-stu-id="57f72-142">In the following example a `Dictionary<WorkflowIdentity, Activity>` is used to associate <xref:System.Activities.WorkflowIdentity> instances with their matching workflow definitions, and a workflow is started using the `MortgageWorkflow` workflow definition, which is associated with the `identityV1` <xref:System.Activities.WorkflowIdentity>.</span></span>

```csharp
WorkflowIdentity identityV1 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1",
    Version = new Version(1, 0, 0, 0)
};

WorkflowIdentity identityV2 = new WorkflowIdentity
{
    Name = "MortgageWorkflow v2",
    Version = new Version(2, 0, 0, 0)
};

Dictionary<WorkflowIdentity, Activity> WorkflowVersionMap = new Dictionary<WorkflowIdentity, Activity>();
WorkflowVersionMap.Add(identityV1, new MortgageWorkflow());
WorkflowVersionMap.Add(identityV2, new MortgageWorkflow_v2());

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identityV1);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Run the workflow.
wfApp.Run();
```

<span data-ttu-id="57f72-143">En el ejemplo siguiente, la información sobre la instancia de flujo de trabajo persistente del ejemplo anterior se recupera mediante una llamada a <xref:System.Activities.WorkflowApplication.GetInstance%2A> y la información persistente de <xref:System.Activities.WorkflowIdentity> se usa para recuperar la definición de flujo de trabajo coincidente.</span><span class="sxs-lookup"><span data-stu-id="57f72-143">In the following example, information about the persisted workflow instance from the previous example is retrieved by calling <xref:System.Activities.WorkflowApplication.GetInstance%2A>, and the persisted <xref:System.Activities.WorkflowIdentity> information is used to retrieve the matching workflow definition.</span></span> <span data-ttu-id="57f72-144">Esta información se usa para configurar <xref:System.Activities.WorkflowApplication> y después se carga el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57f72-144">This information is used to configure the <xref:System.Activities.WorkflowApplication>, and then the workflow is loaded.</span></span> <span data-ttu-id="57f72-145">Tenga en cuenta que como se usa la sobrecarga de <xref:System.Activities.WorkflowApplication.Load%2A> que toma <xref:System.Activities.WorkflowApplicationInstance>, la <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usa el <xref:System.Activities.WorkflowApplicationInstance> configurado en <xref:System.Activities.WorkflowApplication> y por tanto no es necesario configurar su propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A>.</span><span class="sxs-lookup"><span data-stu-id="57f72-145">Note that because the <xref:System.Activities.WorkflowApplication.Load%2A> overload that takes the <xref:System.Activities.WorkflowApplicationInstance> is used, the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> that was configured on the <xref:System.Activities.WorkflowApplicationInstance> is used by the <xref:System.Activities.WorkflowApplication> and therefore its <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property does not need to be configured.</span></span>

> [!NOTE]
> <span data-ttu-id="57f72-146">Si se establece la propiedad <xref:System.Activities.WorkflowApplication.InstanceStore%2A>, debe estar establecida con la misma instancia de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> usada por <xref:System.Activities.WorkflowApplicationInstance> o se producirá una <xref:System.ArgumentException> con el mensaje siguiente: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span><span class="sxs-lookup"><span data-stu-id="57f72-146">If the <xref:System.Activities.WorkflowApplication.InstanceStore%2A> property is set, it must be set with the same <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> instance used by the <xref:System.Activities.WorkflowApplicationInstance> or else an <xref:System.ArgumentException> will be thrown with the following message: `The instance is configured with a different InstanceStore than this WorkflowApplication.`.</span></span>

```csharp
// Get the WorkflowApplicationInstance of the desired workflow from the specified
// SqlWorkflowInstanceStore.
WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(instanceId, store);

// Use the persisted WorkflowIdentity to retrieve the correct workflow
// definition from the dictionary.
Activity definition = WorkflowVersionMap[instance.DefinitionIdentity];

WorkflowApplication wfApp = new WorkflowApplication(definition, instance.DefinitionIdentity);

// Configure the WorkflowApplication with persistence and desired workflow event handlers.
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(instance);

// Resume the workflow...
```

## <a name="upgrading-net-framework-4-persistence-databases-to-support-workflow-versioning"></a><a name="UpdatingWF4PersistenceDatabases"></a> <span data-ttu-id="57f72-147">Actualización de bases de datos de persistencia de .NET Framework 4 para admitir el control de versiones del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57f72-147">Upgrading .NET Framework 4 Persistence Databases to Support Workflow Versioning</span></span>

<span data-ttu-id="57f72-148">Se proporciona un script de base de datos SqlWorkflowInstanceStoreSchemaUpgrade. SQL para actualizar las bases de datos de persistencia creadas con los scripts de base de datos de .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="57f72-148">A SqlWorkflowInstanceStoreSchemaUpgrade.sql database script is provided to upgrade persistence databases created using the .NET Framework 4 database scripts.</span></span> <span data-ttu-id="57f72-149">Este script actualiza las bases de datos para admitir las nuevas capacidades de control de versiones introducidas en .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="57f72-149">This script updates the databases to support the new versioning capabilities introduced in .NET Framework 4.5.</span></span> <span data-ttu-id="57f72-150">Cualquier instancia de flujo de trabajo persistente en las bases de datos recibe valores de control de versión predeterminados y puede participar en ejecuciones en paralelo y en actualizaciones dinámicas.</span><span class="sxs-lookup"><span data-stu-id="57f72-150">Any persisted workflow instances in the databases are given default versioning values, and can then participate in side-by-side execution and dynamic update.</span></span>

<span data-ttu-id="57f72-151">Si una aplicación de flujo de trabajo .NET Framework 4,5 intenta cualquier operación de persistencia que use las nuevas características de control de versiones en una base de datos de persistencia que no se haya actualizado mediante el script proporcionado, <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> se produce una excepción con un mensaje similar al siguiente mensaje.</span><span class="sxs-lookup"><span data-stu-id="57f72-151">If a .NET Framework 4.5 workflow application attempts any persistence operations that use the new versioning features on a persistence database which has not been upgraded using the provided script, an <xref:System.Runtime.DurableInstancing.InstancePersistenceCommandException> is thrown with a message similar to the following message.</span></span>

```output
The SqlWorkflowInstanceStore has a database version of '4.0.0.0'. InstancePersistenceCommand 'System.Activities.DurableInstancing.CreateWorkflowOwnerWithIdentityCommand' cannot be run against this database version.  Please upgrade the database to '4.5.0.0'.
```

### <a name="to-upgrade-the-database-schema"></a><a name="ToUpgrade"></a> <span data-ttu-id="57f72-152">Para actualizar el esquema de la base de datos</span><span class="sxs-lookup"><span data-stu-id="57f72-152">To upgrade the database schema</span></span>

1. <span data-ttu-id="57f72-153">Abra SQL Server Management Studio y conéctese al servidor de base de datos de persistencia, por ejemplo **.\SQLEXPRESS**.</span><span class="sxs-lookup"><span data-stu-id="57f72-153">Open SQL Server Management Studio and connect to the persistence database server, for example **.\SQLEXPRESS**.</span></span>

2. <span data-ttu-id="57f72-154">Elija **abrir**, **archivo** en el menú **archivo** .</span><span class="sxs-lookup"><span data-stu-id="57f72-154">Choose **Open**, **File** from the **File** menu.</span></span> <span data-ttu-id="57f72-155">Busque la siguiente carpeta: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span><span class="sxs-lookup"><span data-stu-id="57f72-155">Browse to the following folder: `C:\Windows\Microsoft.NET\Framework\v4.0.30319\sql\en`</span></span>

3. <span data-ttu-id="57f72-156">Seleccione **SqlWorkflowInstanceStoreSchemaUpgrade. SQL** y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="57f72-156">Select **SqlWorkflowInstanceStoreSchemaUpgrade.sql** and click **Open**.</span></span>

4. <span data-ttu-id="57f72-157">Seleccione el nombre de la base de datos de persistencia en el menú desplegable bases de datos **disponibles** .</span><span class="sxs-lookup"><span data-stu-id="57f72-157">Select the name of the persistence database in the **Available Databases** drop-down.</span></span>

5. <span data-ttu-id="57f72-158">Elija **Ejecutar** en el menú **consulta** .</span><span class="sxs-lookup"><span data-stu-id="57f72-158">Choose **Execute** from the **Query** menu.</span></span>

<span data-ttu-id="57f72-159">Cuando la consulta se completa, el esquema de la base de datos se actualiza y, si lo desea, puede ver la identidad de flujo de trabajo predeterminada que se asignó a las instancias de flujo de trabajo persistentes.</span><span class="sxs-lookup"><span data-stu-id="57f72-159">When the query completes, the database schema is upgraded, and if desired, you can view the default workflow identity that was assigned to the persisted workflow instances.</span></span> <span data-ttu-id="57f72-160">Expanda la base de datos de persistencia en el nodo **bases** de datos del **Explorador de objetos** y, a continuación, expanda el nodo **vistas** .</span><span class="sxs-lookup"><span data-stu-id="57f72-160">Expand your persistence database in the **Databases** node of the **Object Explorer**, and then expand the **Views** node.</span></span> <span data-ttu-id="57f72-161">Haga clic con el botón secundario en **System. Activities. DurableInstancing. instances** y elija **seleccionar las primeras 1000 filas**.</span><span class="sxs-lookup"><span data-stu-id="57f72-161">Right-click **System.Activities.DurableInstancing.Instances** and choose **Select Top 1000 Rows**.</span></span> <span data-ttu-id="57f72-162">Desplácese hasta el final de las columnas y observe que se han agregado seis columnas adicionales a la vista: **IdentityName**, **IdentityPackage**, **Build**, **major**, **Minor** y **revision**.</span><span class="sxs-lookup"><span data-stu-id="57f72-162">Scroll to end of the columns and note that there are six additional columns added to the view: **IdentityName**, **IdentityPackage**, **Build**, **Major**, **Minor**, and **Revision**.</span></span> <span data-ttu-id="57f72-163">Cualquier flujo de trabajo persistente tendrá un valor **null** para estos campos, que representa una identidad de flujo de trabajo nula.</span><span class="sxs-lookup"><span data-stu-id="57f72-163">Any persisted workflows will have a value of **NULL** for these fields, representing a null workflow identity.</span></span>
