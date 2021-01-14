---
title: actualización dinámica
ms.date: 03/30/2017
ms.assetid: 8b6ef19b-9691-4b4b-824c-3c651a9db96e
ms.openlocfilehash: cb4b63a67aa6e9033b227198e2ecc2b1b80db927
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98190161"
---
# <a name="dynamic-update"></a><span data-ttu-id="2d007-102">actualización dinámica</span><span class="sxs-lookup"><span data-stu-id="2d007-102">Dynamic Update</span></span>

<span data-ttu-id="2d007-103">La actualización dinámica proporciona un mecanismo para que los desarrolladores de aplicaciones de flujo de trabajo actualicen la definición de flujo de trabajo de una instancia de flujo de trabajo persistente.</span><span class="sxs-lookup"><span data-stu-id="2d007-103">Dynamic update provides a mechanism for workflow application developers to update the workflow definition of a persisted workflow instance.</span></span> <span data-ttu-id="2d007-104">Puede ser para implementar una corrección de errores, nuevos requisitos o acomodar cambios inesperados.</span><span class="sxs-lookup"><span data-stu-id="2d007-104">This can be to implement a bug fix, new requirements, or to accommodate unexpected changes.</span></span> <span data-ttu-id="2d007-105">En este tema se proporciona información general sobre la funcionalidad de actualización dinámica introducida en .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="2d007-105">This topic provides an overview of the dynamic update functionality introduced in .NET Framework 4.5.</span></span>

## <a name="dynamic-update"></a><span data-ttu-id="2d007-106">actualización dinámica</span><span class="sxs-lookup"><span data-stu-id="2d007-106">Dynamic Update</span></span>

<span data-ttu-id="2d007-107">Para aplicar actualizaciones dinámicas a una instancia de flujo de trabajo persistente, se crea una <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> que contiene instrucciones para el runtime que describen cómo modificar la instancia de flujo de trabajo persistente para reflejar los cambios deseados.</span><span class="sxs-lookup"><span data-stu-id="2d007-107">To apply dynamic updates to a persisted workflow instance, a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> is created that contains instructions for the runtime that describe how to modify the persisted workflow instance to reflect the desired changes.</span></span> <span data-ttu-id="2d007-108">Una vez creada la asignación de actualización, se aplica a las instancias de flujo de trabajo persistentes deseadas.</span><span class="sxs-lookup"><span data-stu-id="2d007-108">Once the update map is created, it is applied to the desired persisted workflow instances.</span></span> <span data-ttu-id="2d007-109">Una vez que se aplica la actualización dinámica, la instancia de flujo de trabajo se puede reanudar mediante la nueva definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="2d007-109">Once the dynamic update is applied, the workflow instance may be resumed using the new updated workflow definition.</span></span> <span data-ttu-id="2d007-110">Hay cuatro pasos necesarios para crear y aplicar una asignación de actualización.</span><span class="sxs-lookup"><span data-stu-id="2d007-110">There are four steps required to create and apply an update map.</span></span>

1. [<span data-ttu-id="2d007-111">Preparar la definición de flujo de trabajo para la actualización dinámica</span><span class="sxs-lookup"><span data-stu-id="2d007-111">Prepare the workflow definition for dynamic update</span></span>](dynamic-update.md#Prepare)

2. [<span data-ttu-id="2d007-112">Actualizar la definición de flujo de trabajo para reflejar los cambios deseados</span><span class="sxs-lookup"><span data-stu-id="2d007-112">Update the workflow definition to reflect the desired changes</span></span>](dynamic-update.md#Update)

3. [<span data-ttu-id="2d007-113">Crear la asignación de la actualización</span><span class="sxs-lookup"><span data-stu-id="2d007-113">Create the update map</span></span>](dynamic-update.md#Create)

4. [<span data-ttu-id="2d007-114">Aplique la asignación de actualización a las instancias de flujo de trabajo persistentes deseadas.</span><span class="sxs-lookup"><span data-stu-id="2d007-114">Apply the update map to the desired persisted workflow instances</span></span>](dynamic-update.md#Apply)

> [!NOTE]
> <span data-ttu-id="2d007-115">Observe que los pasos del 1 al 3, que tratan sobre la creación de la asignación de actualización, se pueden realizar independientemente de la aplicación de la actualización.</span><span class="sxs-lookup"><span data-stu-id="2d007-115">Note that steps 1 through 3, which cover the creation of the update map, may be performed independently of applying the update.</span></span> <span data-ttu-id="2d007-116">Un escenario común en el que el desarrollador de flujo de trabajo creará la asignación de actualización sin conexión y, a continuación, un administrador aplicará la actualización en un momento posterior.</span><span class="sxs-lookup"><span data-stu-id="2d007-116">A common scenario that the workflow developer will create the update map offline, and then an administrator will apply the update at a later time.</span></span>

<span data-ttu-id="2d007-117">Este tema proporciona información general sobre el proceso de actualización dinámica de agregar una nueva actividad a una instancia persistente de un flujo de trabajo compilado de XAML.</span><span class="sxs-lookup"><span data-stu-id="2d007-117">This topic provides an overview of the dynamic update process of adding a new activity to a persisted instance of a compiled Xaml workflow.</span></span>

### <a name="prepare-the-workflow-definition-for-dynamic-update"></a><a name="Prepare"></a> <span data-ttu-id="2d007-118">Preparar la definición de flujo de trabajo para la actualización dinámica</span><span class="sxs-lookup"><span data-stu-id="2d007-118">Prepare the workflow definition for dynamic update</span></span>

<span data-ttu-id="2d007-119">El primer paso del proceso de actualización dinámica es preparar la definición de flujo de trabajo deseada para la actualización.</span><span class="sxs-lookup"><span data-stu-id="2d007-119">The first step in the dynamic update process is to prepare the desired workflow definition for update.</span></span> <span data-ttu-id="2d007-120">Esto se hace mediante una llamada al método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> y el envío de la definición de flujo de trabajo para modificar.</span><span class="sxs-lookup"><span data-stu-id="2d007-120">This is done by calling the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> method and passing in the workflow definition to modify.</span></span> <span data-ttu-id="2d007-121">Este método valida y después recorre el árbol de flujo de trabajo para identificar todos los objetos como actividades y variables públicas que se deben etiquetar para que se puedan comparar más adelante con la definición de flujo de trabajo modificada.</span><span class="sxs-lookup"><span data-stu-id="2d007-121">This method validates and then walks the workflow tree to identify all of the objects such as public activities and variables that need to be tagged so they can be compared later with the modified workflow definition.</span></span> <span data-ttu-id="2d007-122">Cuando esto se completa, el árbol de flujo de trabajo se clona y se adjunta a la definición de flujo de trabajo original.</span><span class="sxs-lookup"><span data-stu-id="2d007-122">When this is complete, the workflow tree is cloned and attached to the original workflow definition.</span></span> <span data-ttu-id="2d007-123">Cuando se crea la asignación de la actualización, la versión actualizada de la definición de flujo de trabajo se compara con la definición de flujo de trabajo original y se genera la asignación de actualización en función de las diferencias.</span><span class="sxs-lookup"><span data-stu-id="2d007-123">When the update map is created, the updated version of the workflow definition is compared with the original workflow definition and the update map is generated based on the differences.</span></span>

<span data-ttu-id="2d007-124">Para preparar un flujo de trabajo de XAML para la actualización dinámica se puede cargar en <xref:System.Activities.ActivityBuilder> y, a continuación, <xref:System.Activities.ActivityBuilder> se pasa a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d007-124">To prepare a Xaml workflow for dynamic update it may be loaded into an <xref:System.Activities.ActivityBuilder>, and then the <xref:System.Activities.ActivityBuilder> is passed into <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.</span></span>

> [!NOTE]
> <span data-ttu-id="2d007-125">Para obtener más información sobre cómo trabajar con flujos de trabajo serializados y <xref:System.Activities.ActivityBuilder> , vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="2d007-125">For more information about working with serialized workflows and <xref:System.Activities.ActivityBuilder>, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

<span data-ttu-id="2d007-126">En el ejemplo siguiente, se carga una definición de `MortgageWorkflow` (compuesta por una <xref:System.Activities.Statements.Sequence> con varias actividades secundarias) en <xref:System.Activities.ActivityBuilder> y, después, se prepara para la actualización dinámica.</span><span class="sxs-lookup"><span data-stu-id="2d007-126">In the following example, a `MortgageWorkflow` definition (that consists of a <xref:System.Activities.Statements.Sequence> with several child activities) is loaded into an <xref:System.Activities.ActivityBuilder>, and then prepared for dynamic update.</span></span> <span data-ttu-id="2d007-127">Después de que el método vuelva, <xref:System.Activities.ActivityBuilder> contiene la definición de flujo de trabajo original junto con una copia.</span><span class="sxs-lookup"><span data-stu-id="2d007-127">After the method returns, the <xref:System.Activities.ActivityBuilder> contains the original workflow definition as well as a copy.</span></span>

```csharp
// Load the MortgageWorkflow definition from Xaml into
// an ActivityBuilder.
XamlXmlReaderSettings readerSettings = new XamlXmlReaderSettings()
{
    LocalAssembly = Assembly.GetExecutingAssembly()
};

XamlXmlReader xamlReader = new XamlXmlReader(@"C:\WorkflowDefinitions\MortgageWorkflow.xaml",
    readerSettings);

ActivityBuilder ab = XamlServices.Load(
    ActivityXamlServices.CreateBuilderReader(xamlReader)) as ActivityBuilder;

// Prepare the workflow definition for dynamic update.
DynamicUpdateServices.PrepareForUpdate(ab);
```

### <a name="update-the-workflow-definition-to-reflect-the-desired-changes"></a><a name="Update"></a> <span data-ttu-id="2d007-128">Actualizar la definición de flujo de trabajo para reflejar los cambios deseados</span><span class="sxs-lookup"><span data-stu-id="2d007-128">Update the workflow definition to reflect the desired changes</span></span>

<span data-ttu-id="2d007-129">Una vez que la definición de flujo de trabajo se ha preparado para la actualización, pueden realizarse los cambios deseados.</span><span class="sxs-lookup"><span data-stu-id="2d007-129">Once the workflow definition has been prepared for updating, the desired changes can be made.</span></span> <span data-ttu-id="2d007-130">Puede agregar o quitar actividades, agregar, mover o eliminar variables públicas, agregar o quitar argumentos, y realizar cambios en la signatura de los delegados de actividad.</span><span class="sxs-lookup"><span data-stu-id="2d007-130">You can add or remove activities, add, move or delete public variables, add or remove arguments, and make changes to the signature of activity delegates.</span></span> <span data-ttu-id="2d007-131">No puede quitar una actividad en ejecución o cambiar la signatura de un delegado en ejecución.</span><span class="sxs-lookup"><span data-stu-id="2d007-131">You cannot remove a running activity or change the signature of a running delegate.</span></span> <span data-ttu-id="2d007-132">Estos cambios se pueden realizar mediante código o en un diseñador de flujo de trabajo rehospedado.</span><span class="sxs-lookup"><span data-stu-id="2d007-132">These changes may be made using code, or in a re-hosted workflow designer.</span></span> <span data-ttu-id="2d007-133">En el siguiente ejemplo, se agrega una actividad `VerifyAppraisal` personalizada a la secuencia que compone el cuerpo de `MortgageWorkflow` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2d007-133">In the following example, a custom `VerifyAppraisal` activity is added to the Sequence that makes up the body of the `MortgageWorkflow` from the previous example.</span></span>

```csharp
// Make desired changes to the definition. In this example, we are
// inserting a new VerifyAppraisal activity as the 3rd child of the root Sequence.
VerifyAppraisal va = new VerifyAppraisal
{
    Result = new VisualBasicReference<bool>("LoanCriteria")
};

// Get the Sequence that makes up the body of the workflow.
Sequence s = ab.Implementation as Sequence;

// Insert the new activity into the Sequence.
s.Activities.Insert(2, va);
```

### <a name="create-the-update-map"></a><a name="Create"></a> <span data-ttu-id="2d007-134">Crear la asignación de actualización</span><span class="sxs-lookup"><span data-stu-id="2d007-134">Create the update map</span></span>

<span data-ttu-id="2d007-135">Una vez que se ha modificado la definición de flujo de trabajo que se había preparado para la actualización, puede crearse la asignación de actualización.</span><span class="sxs-lookup"><span data-stu-id="2d007-135">Once the workflow definition that was prepared for update has been modified, the update map can be created.</span></span> <span data-ttu-id="2d007-136">Para crear una asignación de actualización dinámica, se invoca el método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d007-136">To create a dynamic update map, the <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> method is invoked.</span></span> <span data-ttu-id="2d007-137">Devuelve un objeto <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> que contiene la información que el runtime necesita para modificar una instancia de flujo de trabajo persistente de manera que se pueda cargar y reanudar con la nueva definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d007-137">This returns a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> that contains the information the runtime needs to modify a persisted workflow instance so that it may be loaded and resumed with the new workflow definition.</span></span> <span data-ttu-id="2d007-138">En el ejemplo siguiente, se crea una asignación dinámica para la definición modificada de `MortgageWorkflow` del ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="2d007-138">In the following example, a dynamic map is created for the modified `MortgageWorkflow` definition from the previous example.</span></span>

```csharp
// Create the update map.
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);
```

<span data-ttu-id="2d007-139">Esta asignación de actualización se puede usar inmediatamente para modificar las instancias de flujo de trabajo persistentes o se puede guardar y aplicar actualizaciones más adelante, que es lo más frecuente.</span><span class="sxs-lookup"><span data-stu-id="2d007-139">This update map can immediately be used to modify persisted workflow instances, or more typically it can be saved and the updates applied later.</span></span> <span data-ttu-id="2d007-140">Una manera de guardar la asignación de actualización es serializarla en un archivo, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2d007-140">One way to save the update map is to serialize it to a file, as shown in the following example.</span></span>

```csharp
// Serialize the update map to a file.
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Create))
{
    serializer.WriteObject(fs, map);
}
```

<span data-ttu-id="2d007-141">Cuando <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> vuelve, se quita la definición de flujo de trabajo clonada y otra información de actualización dinámica que se agregó en la llamada a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> y la definición de flujo de trabajo modificada está lista para guardarse de forma que se pueda usar más adelante cuando se reanuden instancias de flujo de trabajo actualizadas.</span><span class="sxs-lookup"><span data-stu-id="2d007-141">When <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> returns, the cloned workflow definition and other dynamic update information that was added in the call to <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> is removed, and the modified workflow definition is ready to be saved so that it can be used later when resuming updated workflow instances.</span></span> <span data-ttu-id="2d007-142">En el ejemplo siguiente, la definición de flujo de trabajo modificada se guarda en `MortgageWorkflow_v1.1.xaml`.</span><span class="sxs-lookup"><span data-stu-id="2d007-142">In the following example, the modified workflow definition is saved to `MortgageWorkflow_v1.1.xaml`.</span></span>

```csharp
// Save the modified workflow definition.
StreamWriter sw = File.CreateText(@"C:\WorkflowDefinitions\MortgageWorkflow_v1.1.xaml");
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
sw.Close();
```

### <a name="apply-the-update-map-to-the-desired-persisted-workflow-instances"></a><a name="Apply"></a> <span data-ttu-id="2d007-143">Aplicar la asignación de actualización a las instancias de flujo de trabajo persistentes deseadas</span><span class="sxs-lookup"><span data-stu-id="2d007-143">Apply the update map to the desired persisted workflow instances</span></span>

<span data-ttu-id="2d007-144">La aplicación de la asignación de actualización se puede realizar en cualquier momento después de crearla.</span><span class="sxs-lookup"><span data-stu-id="2d007-144">Applying the update map can be done at any time after creating it.</span></span> <span data-ttu-id="2d007-145">Puede realizarse inmediatamente mediante la instancia de <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> devuelta por <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> o puede realizarse más adelante mediante una copia guardada de la asignación de actualización.</span><span class="sxs-lookup"><span data-stu-id="2d007-145">It can be done right away using the <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> instance that was returned by <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>, or it can be done later using a saved copy of the update map.</span></span> <span data-ttu-id="2d007-146">Para actualizar una instancia de flujo de trabajo, cárguela en <xref:System.Activities.WorkflowApplicationInstance> mediante <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d007-146">To update a workflow instance, load it into a <xref:System.Activities.WorkflowApplicationInstance> using <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d007-147">A continuación, cree una <xref:System.Activities.WorkflowApplication> mediante la definición de flujo de trabajo actualizada y la <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2d007-147">Next, create a <xref:System.Activities.WorkflowApplication> using the updated workflow definition, and the desired <xref:System.Activities.WorkflowIdentity>.</span></span> <span data-ttu-id="2d007-148">Esta <xref:System.Activities.WorkflowIdentity> puede ser diferente de la que se usó para hacer persistente el flujo de trabajo original y normalmente es para reflejar que se ha modificado la instancia persistente.</span><span class="sxs-lookup"><span data-stu-id="2d007-148">This <xref:System.Activities.WorkflowIdentity> may be different than the one that was used to persist the original workflow, and typically is in order to reflect that the persisted instance has been modified.</span></span> <span data-ttu-id="2d007-149">Una vez que se crea <xref:System.Activities.WorkflowApplication>, se carga mediante la sobrecarga de <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> que toma <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> y después se descarga con una llamada a <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d007-149">Once the <xref:System.Activities.WorkflowApplication> is created, it is loaded using the overload of <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> that takes a <xref:System.Activities.DynamicUpdate.DynamicUpdateMap>, and then unloaded with a call to <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="2d007-150">Aplica la actualización dinámica y hace persistente la instancia de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="2d007-150">This applies the dynamic update and persists the updated workflow instance.</span></span>

```csharp
// Load the serialized update map.
DynamicUpdateMap map;
using (FileStream fs = File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Open))
{
    DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
    object updateMap = serializer.ReadObject(fs);
    if (updateMap == null)
    {
        throw new ApplicationException("DynamicUpdateMap is null.");
    }

    map = (DynamicUpdateMap)updateMap;
}

// Retrieve a list of workflow instance ids that corresponds to the
// workflow instances to update. This step is the responsibility of
// the application developer.
List<Guid> ids = GetPersistedWorkflowIds();
foreach (Guid id in ids)
{
    // Get a proxy to the persisted workflow instance.
    SqlWorkflowInstanceStore store = new SqlWorkflowInstanceStore(connectionString);
    WorkflowApplicationInstance instance = WorkflowApplication.GetInstance(id, store);

    // If desired, you can inspect the WorkflowIdentity of the instance
    // using the DefinitionIdentity property to determine whether to apply
    // the update.
    Console.WriteLine(instance.DefinitionIdentity);

    // Create a workflow application. You must specify the updated workflow definition, and
    // you may provide an updated WorkflowIdentity if desired to reflect the update.
    WorkflowIdentity identity = new WorkflowIdentity
    {
        Name = "MortgageWorkflow v1.1",
        Version = new Version(1, 1, 0, 0)
    };

    // Load the persisted workflow instance using the updated workflow definition
    // and with an updated WorkflowIdentity. In this example the MortgageWorkflow class
    // contains the updated definition.
    WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

    // Apply the dynamic update on the loaded instance.
    wfApp.Load(instance, map);

    // Unload the updated instance.
    wfApp.Unload();
}
```

### <a name="resuming-an-updated-workflow-instance"></a><span data-ttu-id="2d007-151">Reanudar una instancia de flujo de trabajo actualizada</span><span class="sxs-lookup"><span data-stu-id="2d007-151">Resuming an Updated Workflow Instance</span></span>

<span data-ttu-id="2d007-152">Una vez aplicada la actualización dinámica, la instancia de flujo de trabajo puede reanudarse.</span><span class="sxs-lookup"><span data-stu-id="2d007-152">Once dynamic update has been applied, the workflow instance may be resumed.</span></span> <span data-ttu-id="2d007-153">Observe que deben usarse la nueva definición actualizada y <xref:System.Activities.WorkflowIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2d007-153">Note that the new updated definition and <xref:System.Activities.WorkflowIdentity> must be used.</span></span>

> [!NOTE]
> <span data-ttu-id="2d007-154">Para obtener más información sobre cómo trabajar con <xref:System.Activities.WorkflowApplication> y <xref:System.Activities.WorkflowIdentity> , vea [usar WorkflowIdentity y control de versiones](using-workflowidentity-and-versioning.md).</span><span class="sxs-lookup"><span data-stu-id="2d007-154">For more information about working with <xref:System.Activities.WorkflowApplication> and <xref:System.Activities.WorkflowIdentity>, see [Using WorkflowIdentity and Versioning](using-workflowidentity-and-versioning.md).</span></span>

<span data-ttu-id="2d007-155">En el ejemplo siguiente, el flujo de trabajo de `MortgageWorkflow_v1.1.xaml` del ejemplo anterior se ha compilado, y se carga y se reanuda mediante la definición de flujo de trabajo actualizada.</span><span class="sxs-lookup"><span data-stu-id="2d007-155">In the following example, the `MortgageWorkflow_v1.1.xaml` workflow from the previous example has been compiled, and is loaded and resumed using the updated workflow definition.</span></span>

```csharp
// Load the persisted workflow instance using the updated workflow definition
// and updated WorkflowIdentity.
WorkflowIdentity identity = new WorkflowIdentity
{
    Name = "MortgageWorkflow v1.1",
    Version = new Version(1, 1, 0, 0)
};

WorkflowApplication wfApp = new WorkflowApplication(new MortgageWorkflow(), identity);

// Configure persistence and desired workflow event handlers.
// (Omitted for brevity.)
ConfigureWorkflowApplication(wfApp);

// Load the persisted workflow instance.
wfApp.Load(InstanceId);

// Resume the workflow.
// wfApp.ResumeBookmark(...);
```
