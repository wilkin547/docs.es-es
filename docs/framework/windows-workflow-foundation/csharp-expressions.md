---
title: Expresiones de C#
ms.date: 03/30/2017
ms.assetid: 29110be7-f4e3-407e-8dbe-78102eb21115
ms.openlocfilehash: d1728758a4f1af76c2d08695a83c0f9acc3dde3e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2019
ms.locfileid: "74140099"
---
# <a name="c-expressions"></a><span data-ttu-id="d9618-102">Expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="d9618-102">C# Expressions</span></span>
<span data-ttu-id="d9618-103">A partir de .NET Framework 4,5 C# , se admiten expresiones en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="d9618-103">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="d9618-104">Los C# nuevos proyectos de flujo de trabajo creados en Visual Studio 2012 que C# tienen como destino .NET Framework 4,5 expresiones de uso y Visual Basic proyectos de flujo de trabajo usan expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d9618-104">New C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, and Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="d9618-105">Los proyectos de flujo de trabajo de .NET Framework 4 existentes que usan expresiones de Visual Basic se pueden migrar a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] independientemente del lenguaje del proyecto y se admitan.</span><span class="sxs-lookup"><span data-stu-id="d9618-105">Existing .NET Framework 4 workflow projects that use Visual Basic expressions can be migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] regardless of the project language and are supported.</span></span> <span data-ttu-id="d9618-106">En este tema se proporciona información general sobre las expresiones de C# en [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9618-106">This topic provides an overview of C# expressions in [!INCLUDE[wf1](../../../includes/wf1-md.md)].</span></span>

## <a name="using-c-expressions-in-workflows"></a><span data-ttu-id="d9618-107">Uso de expresiones de C# en los flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="d9618-107">Using C# expressions in workflows</span></span>

- [<span data-ttu-id="d9618-108">Usar C# expresiones en el diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d9618-108">Using C# expressions in the Workflow Designer</span></span>](csharp-expressions.md#WFDesigner)

  - [<span data-ttu-id="d9618-109">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="d9618-109">Backwards compatibility</span></span>](csharp-expressions.md#BackwardCompat)

- [<span data-ttu-id="d9618-110">Usar C# expresiones en flujos de trabajo de código</span><span class="sxs-lookup"><span data-stu-id="d9618-110">Using C# expressions in code workflows</span></span>](csharp-expressions.md#CodeWorkflows)

- [<span data-ttu-id="d9618-111">Usar C# expresiones en flujos de trabajo XAML</span><span class="sxs-lookup"><span data-stu-id="d9618-111">Using C# expressions in XAML workflows</span></span>](csharp-expressions.md#XamlWorkflows)

  - [<span data-ttu-id="d9618-112">XAML compilado</span><span class="sxs-lookup"><span data-stu-id="d9618-112">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

  - [<span data-ttu-id="d9618-113">XAML dinámico</span><span class="sxs-lookup"><span data-stu-id="d9618-113">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

- [<span data-ttu-id="d9618-114">Usar C# expresiones en servicios de flujo de trabajo de XAMLX</span><span class="sxs-lookup"><span data-stu-id="d9618-114">Using C# expressions in XAMLX workflow services</span></span>](csharp-expressions.md#WFServices)

### <a name="WFDesigner"></a><span data-ttu-id="d9618-115">Usar C# expresiones en el diseñador de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="d9618-115">Using C# expressions in the Workflow Designer</span></span>

<span data-ttu-id="d9618-116">A partir de .NET Framework 4,5 C# , se admiten expresiones en Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="d9618-116">Starting with .NET Framework 4.5, C# expressions are supported in Windows Workflow Foundation (WF).</span></span> <span data-ttu-id="d9618-117">C#los proyectos de flujo de trabajo creados en Visual Studio 2012 que C# tienen como destino .NET Framework 4,5 usan expresiones, mientras que los proyectos de flujo de trabajo de Visual Basic usan expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d9618-117">C# workflow projects created in Visual Studio 2012 that target .NET Framework 4.5 use C# expressions, while Visual Basic workflow projects use Visual Basic expressions.</span></span> <span data-ttu-id="d9618-118">Para especificar la expresión C# deseada, escríbala en el cuadro con la etiqueta **Escriba C# una expresión**.</span><span class="sxs-lookup"><span data-stu-id="d9618-118">To specify the desired C# expression, type it into the box labeled **Enter a C# expression**.</span></span> <span data-ttu-id="d9618-119">Esta etiqueta se muestra en la ventana de propiedades cuando se selecciona la actividad en el diseñador o en la actividad en el diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9618-119">This label is displayed in the properties window when the activity is selected in the designer, or on the activity in the workflow designer.</span></span> <span data-ttu-id="d9618-120">En el ejemplo siguiente, se incluyen dos actividades `WriteLine` en un `Sequence` dentro de `NoPersistScope`.</span><span class="sxs-lookup"><span data-stu-id="d9618-120">In the following example, two `WriteLine` activities are contained within a `Sequence` inside a `NoPersistScope`.</span></span>

![Captura de pantalla que muestra una actividad de secuencia creada automáticamente.](./media/csharp-expressions/auto-surround-sequence-activity.png)

> [!NOTE]
> <span data-ttu-id="d9618-122">C#las expresiones solo se admiten en Visual Studio y no se admiten en el diseñador de flujo de trabajo rehospedado.</span><span class="sxs-lookup"><span data-stu-id="d9618-122">C# expressions are supported only in Visual Studio, and are not supported in the re-hosted workflow designer.</span></span> <span data-ttu-id="d9618-123">Para obtener más información acerca de las nuevas características de WF45 admitidas en el diseñador rehospedado, consulte [compatibilidad con las nuevas características de Workflow Foundation 4,5 en el diseñador de flujo de trabajo hospedado en otro host](wf-features-in-the-rehosted-workflow-designer.md).</span><span class="sxs-lookup"><span data-stu-id="d9618-123">For more information about new WF45 features supported in the re-hosted designer, see [Support for New Workflow Foundation 4.5 Features in the Rehosted Workflow Designer](wf-features-in-the-rehosted-workflow-designer.md).</span></span>

#### <a name="BackwardCompat"></a><span data-ttu-id="d9618-124">Compatibilidad con versiones anteriores</span><span class="sxs-lookup"><span data-stu-id="d9618-124">Backwards compatibility</span></span>

<span data-ttu-id="d9618-125">Se admiten Visual Basic expresiones de C# proyectos de flujo de trabajo de .NET Framework 4 existentes que se han migrado a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9618-125">Visual Basic expressions in existing .NET Framework 4 C# workflow projects that have been migrated to [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] are supported.</span></span> <span data-ttu-id="d9618-126">Cuando las expresiones de Visual Basic se ven en el diseñador de flujo de trabajo, el texto de la expresión de Visual Basic existente se reemplaza por el **valor se estableció en XAML**, C# a menos que la expresión de Visual Basic sea una sintaxis válida.</span><span class="sxs-lookup"><span data-stu-id="d9618-126">When the Visual Basic expressions are viewed in the workflow designer, the text of the existing Visual Basic expression is replaced with **Value was set in XAML**, unless the Visual Basic expression is valid C# syntax.</span></span> <span data-ttu-id="d9618-127">Si la expresión Visual Basic corresponde a una sintaxis de C# válida, se muestra la expresión.</span><span class="sxs-lookup"><span data-stu-id="d9618-127">If the Visual Basic expression is valid C# syntax, then the expression is displayed.</span></span> <span data-ttu-id="d9618-128">Para actualizar las expresiones de Visual Basic a C#, puede editarlas en el diseñador de flujo de trabajo y especificar la expresión equivalente en C#.</span><span class="sxs-lookup"><span data-stu-id="d9618-128">To update the Visual Basic expressions to C#, you can edit them in the workflow designer and specify the equivalent C# expression.</span></span> <span data-ttu-id="d9618-129">No es necesario actualizar las expresiones de Visual Basic a C#, pero una vez las expresiones están actualizadas en el diseñador de flujo de trabajo, se convierten a C# y no pueden volver a Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d9618-129">It is not required to update the Visual Basic expressions to C#, but once the expressions are updated in the workflow designer they are converted to C# and may not be reverted to Visual Basic.</span></span>

### <a name="CodeWorkflows"></a><span data-ttu-id="d9618-130">Usar C# expresiones en flujos de trabajo de código</span><span class="sxs-lookup"><span data-stu-id="d9618-130">Using C# expressions in code workflows</span></span>

<span data-ttu-id="d9618-131">Las expresiones de C# se admiten en los flujos de trabajo basados en código de [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], pero para poder invocar el flujo de trabajo, es necesario compilar las expresiones de C# mediante <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9618-131">C# expressions are supported in [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] code based workflows, but before the workflow can be invoked the C# expressions must be compiled using <xref:System.Activities.XamlIntegration.TextExpressionCompiler.Compile%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d9618-132">Los autores de flujo de trabajo pueden usar `CSharpValue` para representar el valor r de una expresión y `CSharpReference` para representar el valor l de una expresión.</span><span class="sxs-lookup"><span data-stu-id="d9618-132">Workflow authors can use `CSharpValue` to represent the r-value of an expression, and `CSharpReference` to represent the l-value of an expression.</span></span> <span data-ttu-id="d9618-133">En el siguiente ejemplo, se crea un flujo de trabajo con una actividad `Assign` y una actividad `WriteLine` incluida en una actividad `Sequence`.</span><span class="sxs-lookup"><span data-stu-id="d9618-133">In the following example, a workflow is created with an `Assign` activity and a `WriteLine` activity contained in a `Sequence` activity.</span></span> <span data-ttu-id="d9618-134">Se especifica `CSharpReference` para el argumento `To` de `Assign` y representa el valor l de la expresión.</span><span class="sxs-lookup"><span data-stu-id="d9618-134">A `CSharpReference` is specified for the `To` argument of the `Assign`, and represents the l-value of the expression.</span></span> <span data-ttu-id="d9618-135">Se especifica `CSharpValue` para el argumento de `Value` de `Assign`, y para el argumento `Text` de `WriteLine`, y representa el valor r para esas dos expresiones.</span><span class="sxs-lookup"><span data-stu-id="d9618-135">A `CSharpValue` is specified for the `Value` argument of the `Assign`, and for the `Text` argument of the `WriteLine`, and represents the r-value for those two expressions.</span></span>

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

<span data-ttu-id="d9618-136">Cuando ya se ha creado el flujo de trabajo, se compilan las expresiones de C# mediante una llamada al método del asistente `CompileExpressions` y, a continuación, se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9618-136">After the workflow is constructed, the C# expressions are compiled by calling the `CompileExpressions` helper method and then the workflow is invoked.</span></span> <span data-ttu-id="d9618-137">El siguiente ejemplo es el método `CompileExpressions`.</span><span class="sxs-lookup"><span data-stu-id="d9618-137">The following example is the `CompileExpressions` method.</span></span>

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
> <span data-ttu-id="d9618-138">Si no C# se compilan las expresiones, se produce una <xref:System.NotSupportedException> cuando el flujo de trabajo se invoca con un mensaje similar al siguiente: `Expression Activity type 'CSharpValue`1 ' requiere compilación para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d9618-138">If the C# expressions are not compiled, a <xref:System.NotSupportedException> is thrown when the workflow is invoked with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="d9618-139">Asegúrese de que se ha compilado el flujo de trabajo. "</span><span class="sxs-lookup"><span data-stu-id="d9618-139">Please ensure that the workflow has been compiled.\`</span></span>

<span data-ttu-id="d9618-140">Si el flujo de trabajo personalizado basado en código usa `DynamicActivity`, son necesarios algunos cambios en el método `CompileExpressions`, tal como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9618-140">If your custom code based workflow uses `DynamicActivity`, then some changes to the `CompileExpressions` method are required, as demonstrated in the following code example.</span></span>

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

<span data-ttu-id="d9618-141">Hay varias diferencias en la sobrecarga de `CompileExpressions` que compila expresiones de C# en una actividad dinámica.</span><span class="sxs-lookup"><span data-stu-id="d9618-141">There are several differences in the `CompileExpressions` overload that compiles the C# expressions in a dynamic activity.</span></span>

- <span data-ttu-id="d9618-142">El parámetro en `CompileExpressions` es un objeto `DynamicActivity`.</span><span class="sxs-lookup"><span data-stu-id="d9618-142">The parameter to `CompileExpressions` is a `DynamicActivity`.</span></span>

- <span data-ttu-id="d9618-143">El nombre de tipo y el espacio de nombres se recuperan mediante la propiedad `DynamicActivity.Name`.</span><span class="sxs-lookup"><span data-stu-id="d9618-143">The type name and namespace are retrieved using the `DynamicActivity.Name` property.</span></span>

- <span data-ttu-id="d9618-144">El valor de `TextExpressionCompilerSettings.ForImplementation` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="d9618-144">`TextExpressionCompilerSettings.ForImplementation` is set to `true`.</span></span>

- <span data-ttu-id="d9618-145">Se llama a `CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` en lugar de a `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span><span class="sxs-lookup"><span data-stu-id="d9618-145">`CompiledExpressionInvoker.SetCompiledExpressionRootForImplementation` is called instead of `CompiledExpressionInvoker.SetCompiledExpressionRoot`.</span></span>

<span data-ttu-id="d9618-146">Para obtener más información sobre cómo trabajar con expresiones en el código, vea [crear flujos de trabajo, actividades y expresiones mediante código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="d9618-146">For more information about working with expressions in code, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

### <a name="XamlWorkflows"></a><span data-ttu-id="d9618-147">Usar C# expresiones en flujos de trabajo XAML</span><span class="sxs-lookup"><span data-stu-id="d9618-147">Using C# expressions in XAML workflows</span></span>

<span data-ttu-id="d9618-148">Las expresiones de C# se admiten en los flujos de trabajo de XAML.</span><span class="sxs-lookup"><span data-stu-id="d9618-148">C# expressions are supported in XAML workflows.</span></span> <span data-ttu-id="d9618-149">Los flujos de trabajo de XAML compilados se compilan en un tipo, mientras que el runtime carga los flujos de trabajo de XAML dinámico que se compilan en un árbol de actividades cuando se ejecuta el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d9618-149">Compiled XAML workflows are compiled into a type, and loose XAML workflows are loaded by the runtime and compiled into an activity tree when the workflow is executed.</span></span>

- [<span data-ttu-id="d9618-150">XAML compilado</span><span class="sxs-lookup"><span data-stu-id="d9618-150">Compiled Xaml</span></span>](csharp-expressions.md#CompiledXaml)

- [<span data-ttu-id="d9618-151">XAML dinámico</span><span class="sxs-lookup"><span data-stu-id="d9618-151">Loose Xaml</span></span>](csharp-expressions.md#LooseXaml)

#### <a name="CompiledXaml"></a><span data-ttu-id="d9618-152">XAML compilado</span><span class="sxs-lookup"><span data-stu-id="d9618-152">Compiled Xaml</span></span>

<span data-ttu-id="d9618-153">Las expresiones de C# se admiten en flujos de trabajo de XAML compilado que se compilan en un tipo como parte de un proyecto de flujo de trabajo de C# que está destinado a [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9618-153">C# expressions are supported in compiled XAML workflows that are compiled to a type as part of a C# workflow project that targets [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)].</span></span> <span data-ttu-id="d9618-154">XAML compilado es el tipo predeterminado de creación de flujos de trabajo en Visual Studio C# y los proyectos de flujo de trabajo creados en Visual C# Studio que tienen como destino [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] usar expresiones.</span><span class="sxs-lookup"><span data-stu-id="d9618-154">Compiled XAML is the default type of workflow authoring in Visual Studio, and C# workflow projects created in Visual Studio that target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] use C# expressions.</span></span>

#### <a name="LooseXaml"></a><span data-ttu-id="d9618-155">XAML dinámico</span><span class="sxs-lookup"><span data-stu-id="d9618-155">Loose Xaml</span></span>

<span data-ttu-id="d9618-156">Las expresiones de C# se admiten en los flujos de trabajo de XAML dinámico.</span><span class="sxs-lookup"><span data-stu-id="d9618-156">C# expressions are supported in loose XAML workflows.</span></span> <span data-ttu-id="d9618-157">El programa host de flujo de trabajo que carga e invoca el flujo de trabajo de XAML dinámico debe tener como destino [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] y <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> debe estar establecido en `true` (el valor predeterminado es `false`).</span><span class="sxs-lookup"><span data-stu-id="d9618-157">The workflow host program that loads and invokes the loose XAML workflow must target [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], and <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> must be set to `true` (the default is `false`).</span></span> <span data-ttu-id="d9618-158">Para establecer <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> en `true`, cree una instancia de <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> con la propiedad <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> establecida en `true` y pásela como un parámetro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d9618-158">To set <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> to `true`, create an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true`, and pass it as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="d9618-159">Si `CompileExpressions` no se establece en `true`, se producirá una <xref:System.NotSupportedException> con un mensaje similar al siguiente: `Expression Activity type 'CSharpValue`1 ' requiere compilación para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="d9618-159">If `CompileExpressions` Is not set to `true`, a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="d9618-160">Asegúrese de que se ha compilado el flujo de trabajo. "</span><span class="sxs-lookup"><span data-stu-id="d9618-160">Please ensure that the workflow has been compiled.\`</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="d9618-161">Para obtener más información sobre cómo trabajar con flujos de trabajo de XAML, vea [serializar flujos de trabajo y actividades a y desde XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="d9618-161">For more information about working with XAML workflows, see [Serializing Workflows and Activities to and from XAML](serializing-workflows-and-activities-to-and-from-xaml.md).</span></span>

### <a name="WFServices"></a><span data-ttu-id="d9618-162">Usar C# expresiones en servicios de flujo de trabajo de XAMLX</span><span class="sxs-lookup"><span data-stu-id="d9618-162">Using C# expressions in XAMLX workflow services</span></span>

<span data-ttu-id="d9618-163">Las expresiones de C# se admiten en servicios de flujo de trabajo de XAMLX.</span><span class="sxs-lookup"><span data-stu-id="d9618-163">C# expressions are supported in XAMLX workflow services.</span></span> <span data-ttu-id="d9618-164">Cuando un servicio de flujo de trabajo se hospeda en IIS o WAS, no son necesarios pasos adicionales, pero si el servicio de flujo de trabajo de XAML es autohospedado, las expresiones de C# deben compilarse.</span><span class="sxs-lookup"><span data-stu-id="d9618-164">When a workflow service is hosted in IIS or WAS then no additional steps are required, but if the XAML workflow service is self-hosted, then the C# expressions must be compiled.</span></span> <span data-ttu-id="d9618-165">Para compilar las C# expresiones en un servicio de flujo de trabajo de XAMLX autohospedado, cargue primero el archivo XAMLX en un `WorkflowService`y, a continuación, pase el `Body` de la `WorkflowService` al método `CompileExpressions` descrito en la sección [uso C# de expresiones anteriores en flujos de trabajo de código](csharp-expressions.md#CodeWorkflows) .</span><span class="sxs-lookup"><span data-stu-id="d9618-165">To compile the C# expressions in a self-hosted XAMLX workflow service, first load the XAMLX file into a `WorkflowService`, and then pass the `Body` of the `WorkflowService` to the `CompileExpressions` method described in the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span> <span data-ttu-id="d9618-166">En el ejemplo siguiente, hay un servicio de flujo de trabajo de XAMLX cargado, las expresiones de C# están compiladas y el servicio de flujo de trabajo está abierto y espera solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d9618-166">In the following example, a XAMLX workflow service is loaded, the C# expressions are compiled, and then the workflow service is opened and waits for requests.</span></span>

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

<span data-ttu-id="d9618-167">Si las expresiones de C# no están compiladas, la operación `Open` se realiza correctamente pero el flujo de trabajo producirá un error al invocarse.</span><span class="sxs-lookup"><span data-stu-id="d9618-167">If the C# expressions are not compiled, the `Open` operation succeeds but the workflow will fail when it is invoked.</span></span> <span data-ttu-id="d9618-168">El siguiente método de `CompileExpressions` es igual que el método de la sección [anterior C# expresiones Using en flujos de trabajo de código](csharp-expressions.md#CodeWorkflows) .</span><span class="sxs-lookup"><span data-stu-id="d9618-168">The following `CompileExpressions` method is the same as the method from the previous [Using C# expressions in code workflows](csharp-expressions.md#CodeWorkflows) section.</span></span>

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
