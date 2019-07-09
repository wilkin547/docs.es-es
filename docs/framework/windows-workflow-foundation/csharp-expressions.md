---
title: Expresiones de C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: c8417217064fcc1f7de5b1a9b8055743fc8cd263
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67660650"
---
# <a name="c-expressions"></a>Expresiones de C#
A partir de .NET Framework 4.5, C# las expresiones se admiten en Windows Workflow Foundation (WF). Nuevo C# proyectos de flujo de trabajo creados en Visual Studio 2012 que tienen como destino .NET Framework 4.5 uso C# expresiones y los proyectos de flujo de trabajo de Visual Basic usan expresiones de Visual Basic. Los proyectos de flujo de trabajo existentes de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] que usan expresiones de Visual Basic se pueden migrar a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] independientemente del lenguaje del proyecto y son compatibles. En este tema se proporciona información general sobre las expresiones de C# en [!INCLUDE[wf1](../../../includes/wf1-md.md)].

## <a name="using-c-expressions-in-workflows"></a>Uso de expresiones de C# en los flujos de trabajo

- [Usar expresiones de C# en el Diseñador de flujo de trabajo](csharp-expressions.md#WFDesigner)

  - [Con las versiones anteriores compatibilidad](csharp-expressions.md#BackwardCompat)

- [Usar expresiones de C# en flujos de trabajo de código](csharp-expressions.md#CodeWorkflows)

- [Uso de expresiones de C# en flujos de trabajo XAML](csharp-expressions.md#XamlWorkflows)

  - [Xaml compilado](csharp-expressions.md#CompiledXaml)

  - [El lenguaje Xaml flexible](csharp-expressions.md#LooseXaml)

- [Uso de expresiones de C# en servicios de flujo de trabajo XAMLX](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a> Usar expresiones de C# en el Diseñador de flujo de trabajo

A partir de .NET Framework 4.5, C# las expresiones se admiten en Windows Workflow Foundation (WF). C#proyectos de flujo de trabajo creados en Visual Studio 2012 que tienen como destino .NET Framework 4.5 uso C# expresiones, mientras que los proyectos de flujo de trabajo de Visual Basic usan expresiones de Visual Basic. Para especificar la expresión de C# deseada, escríbala en el cuadro con la etiqueta **escriba una expresión de C#** . Esta etiqueta se muestra en la ventana de propiedades cuando se selecciona la actividad en el diseñador o en la actividad en el diseñador de flujo de trabajo. En el ejemplo siguiente, se incluyen dos actividades `WriteLine` en un `Sequence` dentro de `NoPersistScope`.

![Captura de pantalla que muestra una actividad de secuencia creadas automáticamente.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> Expresiones de C# solo se admiten en Visual Studio y no se admiten en el Diseñador de flujo de trabajo rehospedado. Para obtener más información sobre las nuevas características WF45 admitidas en el diseñador rehospedado, vea [compatibilidad con nuevas características de flujo de trabajo Foundation 4.5 en el Diseñador de flujo de trabajo Rehospedados](wf-features-in-the-rehosted-workflow-designer.md).

#### <a name="BackwardCompat"></a> Con las versiones anteriores compatibilidad

Se admiten las expresiones de Visual Basic en proyectos existentes de flujo de trabajo C# de [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] que se han migrado a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. Cuando se ven las expresiones de Visual Basic en el Diseñador de flujo de trabajo, el texto de la expresión de Visual Basic existente se reemplaza con **valor se estableció en XAML**, a menos que la expresión de Visual Basic es la sintaxis de C# válida. Si la expresión Visual Basic corresponde a una sintaxis de C# válida, se muestra la expresión. Para actualizar las expresiones de Visual Basic a C#, puede editarlas en el diseñador de flujo de trabajo y especificar la expresión equivalente en C#. No es necesario actualizar las expresiones de Visual Basic a C#, pero una vez las expresiones están actualizadas en el diseñador de flujo de trabajo, se convierten a C# y no pueden volver a Visual Basic.

### <a name="CodeWorkflows"></a> Usar expresiones de C# en flujos de trabajo de código

Las expresiones de C# se admiten en los flujos de trabajo basados en código de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], pero para poder invocar el flujo de trabajo, es necesario compilar las expresiones de C# mediante <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>. Los autores de flujo de trabajo pueden usar `CSharpValue` para representar el valor r de una expresión y `CSharpReference` para representar el valor l de una expresión. En el siguiente ejemplo, se crea un flujo de trabajo con una actividad `Assign` y una actividad `WriteLine` incluida en una actividad `Sequence`. Se especifica `CSharpReference` para el argumento `To` de `Assign` y representa el valor l de la expresión. Se especifica `CSharpValue` para el argumento de `Value` de `Assign`, y para el argumento `Text` de `WriteLine`, y representa el valor r para esas dos expresiones.

```csharp
Variable<int> n = new Variable<int>
{
    Name = "n"
};

Activity wf = new Sequence
{
    Variables = { n },
    Activities =
    {
        new Assign<int>
        {
            To = new CSharpReference<int>("n"),
            Value = new CSharpValue<int>("new Random().Next(1, 101)")
        },
        new WriteLine
        {
            Text = new CSharpValue<string>("\"The number is \" + n")
        }
    }
};

CompileExpressions(wf);

WorkflowInvoker.Invoke(wf);
```

Cuando ya se ha creado el flujo de trabajo, se compilan las expresiones de C# mediante una llamada al método del asistente `CompileExpressions` y, a continuación, se invoca el flujo de trabajo. El siguiente ejemplo es el método `CompileExpressions`.

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```

> [!NOTE]
> Si el C# expresiones no se compilan, un <xref:System.NotSupportedException> se produce cuando se invoca el flujo de trabajo con un mensaje similar al siguiente: `Expression Activity type 'CSharpValue`1' requiere compilación para ejecutarse.  Asegúrese de que se ha compilado el flujo de trabajo. "

Si el flujo de trabajo personalizado basado en código usa `DynamicActivity`, son necesarios algunos cambios en el método `CompileExpressions`, tal como se muestra en el ejemplo de código siguiente.

```csharp
static void CompileExpressions(DynamicActivity dynamicActivity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions. For Dynamic Activities this can be retrieved using the
    // name property , which must be in the form Namespace.Type.
    string activityName = dynamicActivity.Name;

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = dynamicActivity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = true
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { dynamicActivity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation(
        dynamicActivity, compiledExpressionRoot);
}
```

Hay varias diferencias en la sobrecarga de `CompileExpressions` que compila expresiones de C# en una actividad dinámica.

- El parámetro en `CompileExpressions` es un objeto `DynamicActivity`.

- El nombre de tipo y el espacio de nombres se recuperan mediante la propiedad `DynamicActivity.Name`.

- El valor de `TextExpressionCompilerSettings.ForImplementation` está establecido en `true`.

- Se llama a `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` en lugar de a `CompiledExpressionInvoker.SetCompiledExpressionRoot`.

Para obtener más información sobre cómo trabajar con expresiones en el código, consulte [creación de flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).

### <a name="XamlWorkflows"></a> Uso de expresiones de C# en flujos de trabajo XAML

Las expresiones de C# se admiten en los flujos de trabajo de XAML. Los flujos de trabajo de XAML compilados se compilan en un tipo, mientras que el runtime carga los flujos de trabajo de XAML dinámico que se compilan en un árbol de actividades cuando se ejecuta el flujo de trabajo.

- [Xaml compilado](csharp-expressions.md#CompiledXaml)

- [El lenguaje Xaml flexible](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a> Xaml compilado

Las expresiones de C# se admiten en flujos de trabajo de XAML compilado que se compilan en un tipo como parte de un proyecto de flujo de trabajo de C# que está destinado a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]. XAML compilado es el tipo predeterminado de la creación del flujo de trabajo en Visual Studio y proyectos de flujo de trabajo de C# creados en Visual Studio que tienen como destino [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] utilice expresiones de C#.

#### <a name="LooseXaml"></a> El lenguaje Xaml flexible

Las expresiones de C# se admiten en los flujos de trabajo de XAML dinámico. El programa host de flujo de trabajo que carga e invoca el flujo de trabajo de XAML dinámico debe tener como destino [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] y <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> debe estar establecido en `true` (el valor predeterminado es `false`). Para establecer <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> en `true`, cree una instancia de <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> con la propiedad <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> establecida en `true` y pásela como un parámetro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>. Si `CompileExpressions` no está establecido en `true`, un <xref:System.NotSupportedException> se iniciará con un mensaje similar al siguiente: `Expression Activity type 'CSharpValue`1' requiere compilación para ejecutarse.  Asegúrese de que se ha compilado el flujo de trabajo. "

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Para obtener más información sobre cómo trabajar con flujos de trabajo XAML, vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).

### <a name="WFServices"></a> Uso de expresiones de C# en servicios de flujo de trabajo XAMLX

Las expresiones de C# se admiten en servicios de flujo de trabajo de XAMLX. Cuando un servicio de flujo de trabajo se hospeda en IIS o WAS, no son necesarios pasos adicionales, pero si el servicio de flujo de trabajo de XAML es autohospedado, las expresiones de C# deben compilarse. Para compilar las expresiones de C# en un servicio de flujo de trabajo XAMLX autohospedado, primero hay que cargar el archivo XAMLX en un `WorkflowService`y, a continuación, pase el `Body` de la `WorkflowService` a la `CompileExpressions` método descrito en el anterior [con C# las expresiones de flujos de trabajo de código](csharp-expressions.md#CodeWorkflows) sección. En el ejemplo siguiente, hay un servicio de flujo de trabajo de XAMLX cargado, las expresiones de C# están compiladas y el servicio de flujo de trabajo está abierto y espera solicitudes.

```csharp
// Load the XAMLX workflow service.
WorkflowService workflow1 =
    (WorkflowService)XamlServices.Load(xamlxPath);

// Compile the C# expressions in the workflow by passing the Body to CompileExpressions.
CompileExpressions(workflow1.Body);

// Initialize the WorkflowServiceHost.
var host = new WorkflowServiceHost(workflow1, new Uri("http://localhost:8293/Service1.xamlx"));

// Enable Metadata publishing/
ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
smb.HttpGetEnabled = true;
smb.MetadataExporter.PolicyVersion = PolicyVersion.Policy15;
host.Description.Behaviors.Add(smb);

// Open the WorkflowServiceHost and wait for requests.
host.Open();
Console.WriteLine("Press enter to quit");
Console.ReadLine();
```

Si las expresiones de C# no están compiladas, la operación `Open` se realiza correctamente pero el flujo de trabajo producirá un error al invocarse. La siguiente `CompileExpressions` método es el mismo que el método del anterior [expresiones con C# en flujos de trabajo de código](csharp-expressions.md#CodeWorkflows) sección.

```csharp
static void CompileExpressions(Activity activity)
{
    // activityName is the Namespace.Type of the activity that contains the
    // C# expressions.
    string activityName = activity.GetType().ToString();

    // Split activityName into Namespace and Type.Append _CompiledExpressionRoot to the type name
    // to represent the new type that represents the compiled expressions.
    // Take everything after the last . for the type name.
    string activityType = activityName.Split('.').Last() + "_CompiledExpressionRoot";
    // Take everything before the last . for the namespace.
    string activityNamespace = string.Join(".", activityName.Split('.').Reverse().Skip(1).Reverse());

    // Create a TextExpressionCompilerSettings.
    TextExpressionCompilerSettings settings = new TextExpressionCompilerSettings
    {
        Activity = activity,
        Language = "C#",
        ActivityName = activityType,
        ActivityNamespace = activityNamespace,
        RootNamespace = null,
        GenerateAsPartialClass = false,
        AlwaysGenerateSource = true,
        ForImplementation = false
    };

    // Compile the C# expression.
    TextExpressionCompilerResults results =
        new TextExpressionCompiler(settings).Compile();

    // Any compilation errors are contained in the CompilerMessages.
    if (results.HasErrors)
    {
        throw new Exception("Compilation failed.");
    }

    // Create an instance of the new compiled expression type.
    ICompiledExpressionRoot compiledExpressionRoot =
        Activator.CreateInstance(results.ResultType,
            new object[] { activity }) as ICompiledExpressionRoot;

    // Attach it to the activity.
    CompiledExpressionInvoker.SetCompiledExpressionRoot(
        activity, compiledExpressionRoot);
}
```
