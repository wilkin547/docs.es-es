---
title: ParallelForEach no genérico
ms.date: 03/30/2017
ms.assetid: de17e7a2-257b-48b3-91a1-860e2e9bf6e6
ms.openlocfilehash: ea7f57b8812dca3dfcb4908730dd788182d50c5c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347615"
---
# <a name="non-generic-parallelforeach"></a><span data-ttu-id="a4a11-102">ParallelForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="a4a11-102">Non-generic ParallelForEach</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="a4a11-103">incluye en su cuadro de herramientas un conjunto de actividades Control Flow, como la actividad <xref:System.Activities.Statements.ParallelForEach%601>, que permite recorrer en iteración colecciones <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a4a11-103">ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ParallelForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>

<span data-ttu-id="a4a11-104"><xref:System.Activities.Statements.ParallelForEach%601> requiere que su propiedad <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> sea de tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="a4a11-104"><xref:System.Activities.Statements.ParallelForEach%601> requires its <xref:System.Activities.Statements.ParallelForEach%601.Values%2A> property to be of type  <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="a4a11-105">Esto impide a los usuarios recorrer en iteración estructuras de datos que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> (por ejemplo, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="a4a11-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="a4a11-106">La versión no genérica de <xref:System.Activities.Statements.ParallelForEach%601> supera este requisito, a costa de una mayor complejidad del tiempo de ejecución para garantizar la compatibilidad de los tipos de los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="a4a11-106">The non-generic version of <xref:System.Activities.Statements.ParallelForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>

<span data-ttu-id="a4a11-107">En este ejemplo se muestra cómo implementar una actividad <xref:System.Activities.Statements.ParallelForEach%601> no genérica y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="a4a11-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ParallelForEach%601> activity and its designer.</span></span> <span data-ttu-id="a4a11-108">Esta actividad se puede utilizar para recorrer en iteración <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="a4a11-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>

## <a name="parallelforeach-activity"></a><span data-ttu-id="a4a11-109">Actividad ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="a4a11-109">ParallelForEach activity</span></span>

<span data-ttu-id="a4a11-110">La C#instrucción/visual Basic `foreach` enumera los elementos de una colección y ejecuta una instrucción incrustada para cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="a4a11-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="a4a11-111">Las actividades equivalentes de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] son <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="a4a11-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="a4a11-112">La actividad <xref:System.Activities.Statements.ForEach%601> contiene una lista de valores y un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="a4a11-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="a4a11-113">En el tiempo de ejecución, la lista se recorre en iteración y se ejecuta el cuerpo para cada valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="a4a11-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>

<span data-ttu-id="a4a11-114"><xref:System.Activities.Statements.ParallelForEach%601> tiene una condición <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, para que la actividad <xref:System.Activities.Statements.ParallelForEach%601> se pueda completar antes si la evaluación de la condición <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="a4a11-114"><xref:System.Activities.Statements.ParallelForEach%601> has a <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A>, so that the <xref:System.Activities.Statements.ParallelForEach%601> activity could complete early if the evaluation of the <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> returns `true`.</span></span> <span data-ttu-id="a4a11-115">La propiedad <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> se evalúa después de completar cada iteración.</span><span class="sxs-lookup"><span data-stu-id="a4a11-115">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> is evaluated after each iteration is completed.</span></span>

<span data-ttu-id="a4a11-116">En la mayoría de los casos, la versión genérica de la actividad debe ser la solución preferida, porque abarca la mayoría de los escenarios en los que se utiliza y proporciona comprobación de tipos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="a4a11-116">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it is used and provides type checking at compile time.</span></span> <span data-ttu-id="a4a11-117">La versión no genérica se puede utilizar para recorrer en iteración tipos que implementan la interfaz <xref:System.Collections.IEnumerable> no genérica.</span><span class="sxs-lookup"><span data-stu-id="a4a11-117">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>

## <a name="class-definition"></a><span data-ttu-id="a4a11-118">Definición de clase</span><span class="sxs-lookup"><span data-stu-id="a4a11-118">Class definition</span></span>

<span data-ttu-id="a4a11-119">El siguiente ejemplo de código muestra la definición de una actividad `ParallelForEach` no genérica.</span><span class="sxs-lookup"><span data-stu-id="a4a11-119">The following code example shows the definition of a non-generic `ParallelForEach` activity is.</span></span>

```csharp
[ContentProperty("Body")]
public class ParallelForEach : NativeActivity
{
    [RequiredArgument]
    [DefaultValue(null)]
    InArgument<IEnumerable> Values { get; set; }

    [DefaultValue(null)]
    [DependsOn("Values")]
    public Activity<bool> CompletionCondition
    [DefaultValue(null)]
    [DependsOn("CompletionCondition")]
    ActivityAction<object> Body { get; set; }
}
```

<span data-ttu-id="a4a11-120">Cuerpo (opcional) </span><span class="sxs-lookup"><span data-stu-id="a4a11-120">Body (optional)</span></span>\
<span data-ttu-id="a4a11-121"><xref:System.Activities.ActivityAction> de tipo <xref:System.Object>, que se ejecuta para cada elemento en la colección.</span><span class="sxs-lookup"><span data-stu-id="a4a11-121">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="a4a11-122">Cada elemento individual se pasa al cuerpo a través de su propiedad Argument.</span><span class="sxs-lookup"><span data-stu-id="a4a11-122">Each individual element is passed into the Body through its Argument property.</span></span>

<span data-ttu-id="a4a11-123">Valores (opcional) </span><span class="sxs-lookup"><span data-stu-id="a4a11-123">Values (optional)</span></span>\
<span data-ttu-id="a4a11-124">La colección de elementos que se recorre en iteración.</span><span class="sxs-lookup"><span data-stu-id="a4a11-124">The collection of elements that are iterated over.</span></span> <span data-ttu-id="a4a11-125">La verificación de que todos los elementos de la colección son de tipos compatibles se realiza en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a4a11-125">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>

<span data-ttu-id="a4a11-126">CompletionCondition (opcional) </span><span class="sxs-lookup"><span data-stu-id="a4a11-126">CompletionCondition (optional)</span></span>\
<span data-ttu-id="a4a11-127">La propiedad <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> se evalúa después de completarse cada iteración.</span><span class="sxs-lookup"><span data-stu-id="a4a11-127">The <xref:System.Activities.Statements.ParallelForEach%601.CompletionCondition%2A> property is evaluated after any iteration completes.</span></span> <span data-ttu-id="a4a11-128">Si se evalúa como `true`, se cancelan las iteraciones programadas pendientes.</span><span class="sxs-lookup"><span data-stu-id="a4a11-128">If it evaluates to `true`, then the scheduled pending iterations are canceled.</span></span> <span data-ttu-id="a4a11-129">Si esta propiedad no está establecida, todas las actividades de la colección Branches se ejecutan hasta su finalización.</span><span class="sxs-lookup"><span data-stu-id="a4a11-129">If this property is not set, all activities in the Branches collection execute until completion.</span></span>

## <a name="example-of-using-parallelforeach"></a><span data-ttu-id="a4a11-130">Ejemplo del uso de ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="a4a11-130">Example of using ParallelForEach</span></span>

<span data-ttu-id="a4a11-131">El siguiente código muestra cómo utilizar la actividad ParallelForEach en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="a4a11-131">The following code demonstrates how to use the ParallelForEach activity in an application.</span></span>

```csharp
string[] names = { "bill", "steve", "ray" };

DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };

Activity sampleUsage =
    new ParallelForEach
    {
       Values = new InArgument<IEnumerable>(c=> names),
       Body = new ActivityAction<object>
       {
           Argument = iterationVariable,
           Handler = new WriteLine
           {
               Text = new InArgument<string>(env => string.Format("Hello {0}",                                                               iterationVariable.Get(env)))
           }
       }
   };
```

## <a name="parallelforeach-designer"></a><span data-ttu-id="a4a11-132">Diseñador de ParallelForEach</span><span class="sxs-lookup"><span data-stu-id="a4a11-132">ParallelForEach designer</span></span>

<span data-ttu-id="a4a11-133">El diseñador de actividad del ejemplo es similar en aspecto al diseñador proporcionado para la actividad <xref:System.Activities.Statements.ParallelForEach%601> integrada.</span><span class="sxs-lookup"><span data-stu-id="a4a11-133">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ParallelForEach%601> activity.</span></span> <span data-ttu-id="a4a11-134">El diseñador aparece en el cuadro de herramientas en la categoría **ejemplos**, **actividades no genéricas** .</span><span class="sxs-lookup"><span data-stu-id="a4a11-134">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="a4a11-135">El diseñador se denomina **ParallelForEachWithBodyFactory** en el cuadro de herramientas, porque la actividad expone un <xref:System.Activities.Presentation.IActivityTemplateFactory> en el cuadro de herramientas que crea la actividad con un <xref:System.Activities.ActivityAction>configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="a4a11-135">The designer is named **ParallelForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox that creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>

```csharp
public sealed class ParallelForEachWithBodyFactory : IActivityTemplateFactory
{
    public Activity Create(DependencyObject target)
    {
        return new Microsoft.Samples.Activities.Statements.ParallelForEach()
        {
            Body = new ActivityAction<object>()
            {
                Argument = new DelegateInArgument<object>()
                {
                    Name = "item"
                }
            }
        };
    }
}
```

## <a name="to-run-the-sample"></a><span data-ttu-id="a4a11-136">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4a11-136">To run the sample</span></span>

1. <span data-ttu-id="a4a11-137">Establezca el proyecto que desee como el proyecto de inicio de la solución.</span><span class="sxs-lookup"><span data-stu-id="a4a11-137">Set the project of your choice as the startup project of the solution.</span></span>

    1. <span data-ttu-id="a4a11-138">**CodeTestClient** muestra cómo utilizar la actividad mediante código.</span><span class="sxs-lookup"><span data-stu-id="a4a11-138">**CodeTestClient** shows how to use the activity using code.</span></span>

    2. <span data-ttu-id="a4a11-139">**DesignerTestClient** muestra cómo utilizar la actividad en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="a4a11-139">**DesignerTestClient** shows how to use the activity within the designer.</span></span>

2. <span data-ttu-id="a4a11-140">Cree y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a4a11-140">Build and run the project.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a4a11-141">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a4a11-141">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a4a11-142">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a4a11-142">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="a4a11-143">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a4a11-143">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a4a11-144">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a4a11-144">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericParallelForEach`
