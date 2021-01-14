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
# <a name="dynamic-update"></a>actualización dinámica

La actualización dinámica proporciona un mecanismo para que los desarrolladores de aplicaciones de flujo de trabajo actualicen la definición de flujo de trabajo de una instancia de flujo de trabajo persistente. Puede ser para implementar una corrección de errores, nuevos requisitos o acomodar cambios inesperados. En este tema se proporciona información general sobre la funcionalidad de actualización dinámica introducida en .NET Framework 4,5.

## <a name="dynamic-update"></a>actualización dinámica

Para aplicar actualizaciones dinámicas a una instancia de flujo de trabajo persistente, se crea una <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> que contiene instrucciones para el runtime que describen cómo modificar la instancia de flujo de trabajo persistente para reflejar los cambios deseados. Una vez creada la asignación de actualización, se aplica a las instancias de flujo de trabajo persistentes deseadas. Una vez que se aplica la actualización dinámica, la instancia de flujo de trabajo se puede reanudar mediante la nueva definición de flujo de trabajo actualizada. Hay cuatro pasos necesarios para crear y aplicar una asignación de actualización.

1. [Preparar la definición de flujo de trabajo para la actualización dinámica](dynamic-update.md#Prepare)

2. [Actualizar la definición de flujo de trabajo para reflejar los cambios deseados](dynamic-update.md#Update)

3. [Crear la asignación de la actualización](dynamic-update.md#Create)

4. [Aplique la asignación de actualización a las instancias de flujo de trabajo persistentes deseadas.](dynamic-update.md#Apply)

> [!NOTE]
> Observe que los pasos del 1 al 3, que tratan sobre la creación de la asignación de actualización, se pueden realizar independientemente de la aplicación de la actualización. Un escenario común en el que el desarrollador de flujo de trabajo creará la asignación de actualización sin conexión y, a continuación, un administrador aplicará la actualización en un momento posterior.

Este tema proporciona información general sobre el proceso de actualización dinámica de agregar una nueva actividad a una instancia persistente de un flujo de trabajo compilado de XAML.

### <a name="prepare-the-workflow-definition-for-dynamic-update"></a><a name="Prepare"></a> Preparar la definición de flujo de trabajo para la actualización dinámica

El primer paso del proceso de actualización dinámica es preparar la definición de flujo de trabajo deseada para la actualización. Esto se hace mediante una llamada al método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> y el envío de la definición de flujo de trabajo para modificar. Este método valida y después recorre el árbol de flujo de trabajo para identificar todos los objetos como actividades y variables públicas que se deben etiquetar para que se puedan comparar más adelante con la definición de flujo de trabajo modificada. Cuando esto se completa, el árbol de flujo de trabajo se clona y se adjunta a la definición de flujo de trabajo original. Cuando se crea la asignación de la actualización, la versión actualizada de la definición de flujo de trabajo se compara con la definición de flujo de trabajo original y se genera la asignación de actualización en función de las diferencias.

Para preparar un flujo de trabajo de XAML para la actualización dinámica se puede cargar en <xref:System.Activities.ActivityBuilder> y, a continuación, <xref:System.Activities.ActivityBuilder> se pasa a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType>.

> [!NOTE]
> Para obtener más información sobre cómo trabajar con flujos de trabajo serializados y <xref:System.Activities.ActivityBuilder> , vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

En el ejemplo siguiente, se carga una definición de `MortgageWorkflow` (compuesta por una <xref:System.Activities.Statements.Sequence> con varias actividades secundarias) en <xref:System.Activities.ActivityBuilder> y, después, se prepara para la actualización dinámica. Después de que el método vuelva, <xref:System.Activities.ActivityBuilder> contiene la definición de flujo de trabajo original junto con una copia.

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

### <a name="update-the-workflow-definition-to-reflect-the-desired-changes"></a><a name="Update"></a> Actualizar la definición de flujo de trabajo para reflejar los cambios deseados

Una vez que la definición de flujo de trabajo se ha preparado para la actualización, pueden realizarse los cambios deseados. Puede agregar o quitar actividades, agregar, mover o eliminar variables públicas, agregar o quitar argumentos, y realizar cambios en la signatura de los delegados de actividad. No puede quitar una actividad en ejecución o cambiar la signatura de un delegado en ejecución. Estos cambios se pueden realizar mediante código o en un diseñador de flujo de trabajo rehospedado. En el siguiente ejemplo, se agrega una actividad `VerifyAppraisal` personalizada a la secuencia que compone el cuerpo de `MortgageWorkflow` del ejemplo anterior.

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

### <a name="create-the-update-map"></a><a name="Create"></a> Crear la asignación de actualización

Una vez que se ha modificado la definición de flujo de trabajo que se había preparado para la actualización, puede crearse la asignación de actualización. Para crear una asignación de actualización dinámica, se invoca el método <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType>. Devuelve un objeto <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> que contiene la información que el runtime necesita para modificar una instancia de flujo de trabajo persistente de manera que se pueda cargar y reanudar con la nueva definición de flujo de trabajo. En el ejemplo siguiente, se crea una asignación dinámica para la definición modificada de `MortgageWorkflow` del ejemplo anterior.

```csharp
// Create the update map.
DynamicUpdateMap map = DynamicUpdateServices.CreateUpdateMap(ab);
```

Esta asignación de actualización se puede usar inmediatamente para modificar las instancias de flujo de trabajo persistentes o se puede guardar y aplicar actualizaciones más adelante, que es lo más frecuente. Una manera de guardar la asignación de actualización es serializarla en un archivo, como se muestra en el ejemplo siguiente.

```csharp
// Serialize the update map to a file.
DataContractSerializer serializer = new DataContractSerializer(typeof(DynamicUpdateMap));
using (FileStream fs = System.IO.File.Open(@"C:\WorkflowDefinitions\MortgageWorkflow.map", FileMode.Create))
{
    serializer.WriteObject(fs, map);
}
```

Cuando <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> vuelve, se quita la definición de flujo de trabajo clonada y otra información de actualización dinámica que se agregó en la llamada a <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.PrepareForUpdate%2A?displayProperty=nameWithType> y la definición de flujo de trabajo modificada está lista para guardarse de forma que se pueda usar más adelante cuando se reanuden instancias de flujo de trabajo actualizadas. En el ejemplo siguiente, la definición de flujo de trabajo modificada se guarda en `MortgageWorkflow_v1.1.xaml`.

```csharp
// Save the modified workflow definition.
StreamWriter sw = File.CreateText(@"C:\WorkflowDefinitions\MortgageWorkflow_v1.1.xaml");
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
sw.Close();
```

### <a name="apply-the-update-map-to-the-desired-persisted-workflow-instances"></a><a name="Apply"></a> Aplicar la asignación de actualización a las instancias de flujo de trabajo persistentes deseadas

La aplicación de la asignación de actualización se puede realizar en cualquier momento después de crearla. Puede realizarse inmediatamente mediante la instancia de <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> devuelta por <xref:System.Activities.DynamicUpdate.DynamicUpdateServices.CreateUpdateMap%2A?displayProperty=nameWithType> o puede realizarse más adelante mediante una copia guardada de la asignación de actualización. Para actualizar una instancia de flujo de trabajo, cárguela en <xref:System.Activities.WorkflowApplicationInstance> mediante <xref:System.Activities.WorkflowApplication.GetInstance%2A?displayProperty=nameWithType>. A continuación, cree una <xref:System.Activities.WorkflowApplication> mediante la definición de flujo de trabajo actualizada y la <xref:System.Activities.WorkflowIdentity>. Esta <xref:System.Activities.WorkflowIdentity> puede ser diferente de la que se usó para hacer persistente el flujo de trabajo original y normalmente es para reflejar que se ha modificado la instancia persistente. Una vez que se crea <xref:System.Activities.WorkflowApplication>, se carga mediante la sobrecarga de <xref:System.Activities.WorkflowApplication.Load%2A?displayProperty=nameWithType> que toma <xref:System.Activities.DynamicUpdate.DynamicUpdateMap> y después se descarga con una llamada a <xref:System.Activities.WorkflowApplication.Unload%2A?displayProperty=nameWithType>. Aplica la actualización dinámica y hace persistente la instancia de flujo de trabajo actualizada.

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

### <a name="resuming-an-updated-workflow-instance"></a>Reanudar una instancia de flujo de trabajo actualizada

Una vez aplicada la actualización dinámica, la instancia de flujo de trabajo puede reanudarse. Observe que deben usarse la nueva definición actualizada y <xref:System.Activities.WorkflowIdentity>.

> [!NOTE]
> Para obtener más información sobre cómo trabajar con <xref:System.Activities.WorkflowApplication> y <xref:System.Activities.WorkflowIdentity> , vea [usar WorkflowIdentity y control de versiones](using-workflowidentity-and-versioning.md).

En el ejemplo siguiente, el flujo de trabajo de `MortgageWorkflow_v1.1.xaml` del ejemplo anterior se ha compilado, y se carga y se reanuda mediante la definición de flujo de trabajo actualizada.

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
