---
title: Serializar flujos de trabajo y actividades a y de XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 72956d1044ae6b99134665ef296b5d347673deab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="7d3b5-102">Serializar flujos de trabajo y actividades a y de XAML</span><span class="sxs-lookup"><span data-stu-id="7d3b5-102">Serializing Workflows and Activities to and from XAML</span></span>
<span data-ttu-id="7d3b5-103">Además de compilarse en tipos incluidos en ensamblados, las definiciones de flujo de trabajo también se pueden serializar en XAML.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="7d3b5-104">Estas definiciones serializadas se pueden recargar para edición o inspección, pasar a un sistema de compilación para compilación, o bien cargar e invocar.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="7d3b5-105">En este tema se proporciona información general sobre la serialización de definiciones de flujo de trabajo y el trabajo con definiciones de flujo de trabajo de XAML.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>  
  
## <a name="working-with-xaml-workflow-definitions"></a><span data-ttu-id="7d3b5-106">Trabajar con definiciones de flujo de trabajo de XAML</span><span class="sxs-lookup"><span data-stu-id="7d3b5-106">Working with XAML Workflow Definitions</span></span>  
 <span data-ttu-id="7d3b5-107">Para crear una definición de flujo de trabajo para la serialización, se utiliza la clase <xref:System.Activities.ActivityBuilder>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="7d3b5-108">La creación de una clase <xref:System.Activities.ActivityBuilder> es muy similar a la creación de una clase <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="7d3b5-109">Se especifican los argumento deseados y se configuran las actividades que constituyen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="7d3b5-110">En el siguiente ejemplo, se crea una actividad `Add` que toma dos argumentos de entrada, los suma y devuelve el resultado.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="7d3b5-111">Dado que esta actividad devuelve un resultado, se utiliza la clase <xref:System.Activities.ActivityBuilder%601> la genérica.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 <span data-ttu-id="7d3b5-112">Cada una de las instancias de <xref:System.Activities.DynamicActivityProperty> representa uno de los argumentos de entrada al flujo de trabajo y la propiedad <xref:System.Activities.ActivityBuilder.Implementation%2A> contiene las actividades que constituyen la lógica del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="7d3b5-113">Observe que las expresiones de valor de r de este ejemplo son expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="7d3b5-114">Las expresiones lambda no son serializables en XAML a menos que se use <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="7d3b5-115">Si los flujos de trabajo serializados están pensados para abrirse o editarse en el diseñador de flujo de trabajo, se deben usar expresiones de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-115">If the serialized workflows are intended to be opened or edited in the workflow designer then Visual Basic expressions should be used.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7d3b5-116">[Crear flujos de trabajo, actividades y expresiones mediante código imperativo](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="7d3b5-116"> [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
 <span data-ttu-id="7d3b5-117">Para serializar la definición de flujo de trabajo representada por la instancia de <xref:System.Activities.ActivityBuilder> en XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> para crear <xref:System.Xaml.XamlWriter> y use después <xref:System.Xaml.XamlServices> para serializar la definición de flujo de trabajo mediante <xref:System.Xaml.XamlWriter>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="7d3b5-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> tiene métodos para asignar instancias de <xref:System.Activities.ActivityBuilder> en XAML y viceversa, y cargar flujos de trabajo de XAML y devolver <xref:System.Activities.DynamicActivity> que se pueda invocar.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML, and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="7d3b5-119">En el siguiente ejemplo, la instancia de <xref:System.Activities.ActivityBuilder> del ejemplo anterior se serializa en una cadena y también se guarda en un archivo.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string, and also saved to a file.</span></span>  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 <span data-ttu-id="7d3b5-120">En el siguiente ejemplo se representa el flujo de trabajo serializado.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-120">The following example represents the serialized workflow.</span></span>  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <span data-ttu-id="7d3b5-121">Para cargar un flujo de trabajo serializado, el <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> se utiliza el método.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-121">To load a serialized workflow, the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method is used.</span></span> <span data-ttu-id="7d3b5-122">Este método toma la definición de flujo de trabajo serializada y devuelve una clase <xref:System.Activities.DynamicActivity> que representa la definición de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="7d3b5-123">Observe que el XAML no se deserializa hasta que se llama al método <xref:System.Activities.Activity.CacheMetadata%2A> en el cuerpo de la clase <xref:System.Activities.DynamicActivity> durante el proceso de validación.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="7d3b5-124">Si no se llama a la validación explícitamente, se realiza cuando se invoca el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-124">If validation is not explicitly called then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="7d3b5-125">Si la definición de flujo de trabajo de XAML no es válida, se produce una excepción <xref:System.Argument>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-125">If the XAML workflow definition is invalid, then an <xref:System.Argument> exception is thrown.</span></span> <span data-ttu-id="7d3b5-126">Las excepciones que se producen desde el método <xref:System.Activities.Activity.CacheMetadata%2A> escapan de la llamada al método <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> y deben ser administradas por el autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="7d3b5-127">En el siguiente ejemplo, el flujo de trabajo serializado del ejemplo anterior se carga y se invoca utilizando <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 <span data-ttu-id="7d3b5-128">Cuando se invoca este flujo de trabajo, en la consola se muestra el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-128">When this workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="7d3b5-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="7d3b5-129">**25 + 15**</span></span>  
<span data-ttu-id="7d3b5-130">**40**</span><span class="sxs-lookup"><span data-stu-id="7d3b5-130">**40**</span></span>    
> [!NOTE]
>  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7d3b5-131">invocar flujos de trabajo con argumentos de entrada y salidos, vea [usar WorkflowInvoker y WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) y <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-131"> invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>  
  
 <span data-ttu-id="7d3b5-132">Si el flujo de trabajo serializado contiene expresiones de C#, un <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instancia con su <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> propiedad establecida en `true` debe pasarse como un parámetro a <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, en caso contrario un <xref:System.NotSupportedException> se producirá un mensaje similar a la Después: `Expression Activity type 'CSharpValue`1' requiere compilación para poder ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="7d3b5-133">Asegúrese de que se ha compilado el flujo de trabajo. "</span><span class="sxs-lookup"><span data-stu-id="7d3b5-133">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7d3b5-134">[Expresiones de C#](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="7d3b5-134"> [C# Expressions](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="7d3b5-135">También se puede cargar una definición de flujo de trabajo serializado en una <xref:System.Activities.ActivityBuilder> instancia mediante el uso de la <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> método.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-135">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="7d3b5-136">Una vez cargado un flujo de trabajo serializado en una instancia de <xref:System.Activities.ActivityBuilder>, se puede inspeccionar y modificar.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-136">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance it can be inspected and modified.</span></span> <span data-ttu-id="7d3b5-137">Esto resulta útil para los autores de diseñadores de flujo de trabajo personalizados y proporciona un mecanismo para guardar y recargar las definiciones de flujo de trabajo durante el proceso del diseño.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-137">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="7d3b5-138">En el siguiente ejemplo, se carga la definición de flujo de trabajo serializada del ejemplo anterior y se inspeccionan sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="7d3b5-138">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
