---
title: ForEach no genérico
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 08dbac3974915f823a4f6e39f35927453a7c4b3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142711"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="8ab66-102">ForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="8ab66-102">Non-Generic ForEach</span></span>
[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="8ab66-103">incluye en su cuadro de herramientas un conjunto de actividades Control Flow, como la actividad <xref:System.Activities.Statements.ForEach%601>, que permite recorrer en iteración colecciones <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8ab66-103">ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="8ab66-104"><xref:System.Activities.Statements.ForEach%601> requiere que su propiedad <xref:System.Activities.Statements.ForEach%601.Values%2A> sea del tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8ab66-104"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="8ab66-105">Esto impide a los usuarios recorrer en iteración estructuras de datos que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> (por ejemplo, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="8ab66-105">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="8ab66-106">La versión no genérica de <xref:System.Activities.Statements.ForEach%601> supera este requisito, a costa de una mayor complejidad del tiempo de ejecución para garantizar la compatibilidad de los tipos de los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="8ab66-106">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="8ab66-107">En este ejemplo se muestra cómo implementar una actividad <xref:System.Activities.Statements.ForEach%601> no genérica y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="8ab66-107">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="8ab66-108">Esta actividad se puede utilizar para recorrer en iteración <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="8ab66-108">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="8ab66-109">Actividad ForEach</span><span class="sxs-lookup"><span data-stu-id="8ab66-109">ForEach Activity</span></span>  
 <span data-ttu-id="8ab66-110">La instrucción c/Visual Basic `foreach` enumera los elementos de una colección, ejecutando una instrucción incrustada para cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="8ab66-110">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="8ab66-111">Las actividades equivalentes de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] de `foreach` son <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="8ab66-111">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="8ab66-112">La actividad <xref:System.Activities.Statements.ForEach%601> contiene una lista de valores y un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8ab66-112">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="8ab66-113">En el tiempo de ejecución, la lista se recorre en iteración y se ejecuta el cuerpo para cada valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="8ab66-113">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="8ab66-114">En la mayoría de los casos, la versión genérica de la actividad debe ser la solución preferida, porque abarca la mayoría de los escenarios en los que se puede utilizar y proporciona comprobación de tipos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8ab66-114">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="8ab66-115">La versión no genérica se puede utilizar para recorrer en iteración tipos que implementan la interfaz <xref:System.Collections.IEnumerable> no genérica.</span><span class="sxs-lookup"><span data-stu-id="8ab66-115">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="8ab66-116">Definición de clase</span><span class="sxs-lookup"><span data-stu-id="8ab66-116">Class Definition</span></span>  
 <span data-ttu-id="8ab66-117">El siguiente ejemplo de código muestra la definición de una actividad `ForEach` no genérica.</span><span class="sxs-lookup"><span data-stu-id="8ab66-117">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
```csharp  
[ContentProperty("Body")]  
public class ForEach : NativeActivity  
{  
    [RequiredArgument]  
    [DefaultValue(null)]  
    InArgument<IEnumerable> Values { get; set; }  
  
    [DefaultValue(null)]  
    [DependsOn("Values")]  
    ActivityAction<object> Body { get; set; }
}  
```  
  
 <span data-ttu-id="8ab66-118">Cuerpo (opcional)</span><span class="sxs-lookup"><span data-stu-id="8ab66-118">Body (optional)</span></span>  
 <span data-ttu-id="8ab66-119"><xref:System.Activities.ActivityAction> de tipo <xref:System.Object>, que se ejecuta para cada elemento en la colección.</span><span class="sxs-lookup"><span data-stu-id="8ab66-119">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="8ab66-120">Cada elemento individual se pasa al cuerpo a través de su propiedad `Argument`.</span><span class="sxs-lookup"><span data-stu-id="8ab66-120">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="8ab66-121">Valores (opcional)</span><span class="sxs-lookup"><span data-stu-id="8ab66-121">Values (optional)</span></span>  
 <span data-ttu-id="8ab66-122">La colección de elementos que se recorre en iteración.</span><span class="sxs-lookup"><span data-stu-id="8ab66-122">The collection of elements that are iterated over.</span></span> <span data-ttu-id="8ab66-123">La verificación de que todos los elementos de la colección son de tipos compatibles se realiza en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8ab66-123">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="8ab66-124">Ejemplo de uso de ForEach</span><span class="sxs-lookup"><span data-stu-id="8ab66-124">Example of Using ForEach</span></span>  
 <span data-ttu-id="8ab66-125">El siguiente código muestra cómo utilizar la actividad ForEach en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="8ab66-125">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
```csharp  
string[] names = { "bill", "steve", "ray" };  
  
DelegateInArgument<object> iterationVariable = new DelegateInArgument<object>() { Name = "iterationVariable" };  
  
Activity sampleUsage =  
    new ForEach  
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
  
|<span data-ttu-id="8ab66-126">Condición</span><span class="sxs-lookup"><span data-stu-id="8ab66-126">Condition</span></span>|<span data-ttu-id="8ab66-127">Message</span><span class="sxs-lookup"><span data-stu-id="8ab66-127">Message</span></span>|<span data-ttu-id="8ab66-128">severity</span><span class="sxs-lookup"><span data-stu-id="8ab66-128">Severity</span></span>|<span data-ttu-id="8ab66-129">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="8ab66-129">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="8ab66-130">Los valores son `null`</span><span class="sxs-lookup"><span data-stu-id="8ab66-130">Values is `null`</span></span>|<span data-ttu-id="8ab66-131">No se proporcionó el valor para un argumento de actividad necesario 'Values'.</span><span class="sxs-lookup"><span data-stu-id="8ab66-131">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="8ab66-132">Error</span><span class="sxs-lookup"><span data-stu-id="8ab66-132">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="8ab66-133">Diseñador de ForEach</span><span class="sxs-lookup"><span data-stu-id="8ab66-133">ForEach Designer</span></span>  
 <span data-ttu-id="8ab66-134">El diseñador de actividad del ejemplo es similar en aspecto al diseñador proporcionado para la actividad <xref:System.Activities.Statements.ForEach%601> integrada.</span><span class="sxs-lookup"><span data-stu-id="8ab66-134">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="8ab66-135">El diseñador aparece en el cuadro de herramientas de la categoría **Ejemplos**, **Actividades no genéricas.**</span><span class="sxs-lookup"><span data-stu-id="8ab66-135">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="8ab66-136">El diseñador se denomina **ForEachWithBodyFactory** en el cuadro <xref:System.Activities.Presentation.IActivityTemplateFactory> de herramientas, porque la actividad <xref:System.Activities.ActivityAction>expone un en el cuadro de herramientas, que crea la actividad con un .</span><span class="sxs-lookup"><span data-stu-id="8ab66-136">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
```csharp  
public sealed class ForEachWithBodyFactory : IActivityTemplateFactory  
{  
    public Activity Create(DependencyObject target)  
    {  
        return new Microsoft.Samples.Activities.Statements.ForEach()  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="8ab66-137">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8ab66-137">To run this sample</span></span>  
  
1. <span data-ttu-id="8ab66-138">Establezca el proyecto que desee como el proyecto de inicio de la solución:</span><span class="sxs-lookup"><span data-stu-id="8ab66-138">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1. <span data-ttu-id="8ab66-139">**CodeTestClient** muestra cómo usar la actividad mediante código.</span><span class="sxs-lookup"><span data-stu-id="8ab66-139">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2. <span data-ttu-id="8ab66-140">**DesignerTestClient** muestra cómo usar la actividad dentro del diseñador.</span><span class="sxs-lookup"><span data-stu-id="8ab66-140">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2. <span data-ttu-id="8ab66-141">Compile y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8ab66-141">Build and run the project.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8ab66-142">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8ab66-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8ab66-143">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8ab66-143">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8ab66-144">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="8ab66-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8ab66-145">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8ab66-145">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
