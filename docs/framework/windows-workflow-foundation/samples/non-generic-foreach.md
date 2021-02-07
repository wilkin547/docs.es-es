---
description: 'Más información acerca de: ForEach no genérico'
title: ForEach no genérico
ms.date: 03/30/2017
ms.assetid: 576cd07a-d58d-4536-b514-77bad60bff38
ms.openlocfilehash: 16635da4ef57ff7b59e178f5954465d8b86bf488
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741957"
---
# <a name="non-generic-foreach"></a><span data-ttu-id="8d011-103">ForEach no genérico</span><span class="sxs-lookup"><span data-stu-id="8d011-103">Non-Generic ForEach</span></span>

[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] <span data-ttu-id="8d011-104">incluye en su cuadro de herramientas un conjunto de actividades Control Flow, como la actividad <xref:System.Activities.Statements.ForEach%601>, que permite recorrer en iteración colecciones <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8d011-104">ships in its toolbox a set of Control Flow activities, including <xref:System.Activities.Statements.ForEach%601>, which allows iterating through <xref:System.Collections.Generic.IEnumerable%601> collections.</span></span>  
  
 <span data-ttu-id="8d011-105"><xref:System.Activities.Statements.ForEach%601> requiere que su propiedad <xref:System.Activities.Statements.ForEach%601.Values%2A> sea del tipo <xref:System.Collections.Generic.IEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="8d011-105"><xref:System.Activities.Statements.ForEach%601> requires its <xref:System.Activities.Statements.ForEach%601.Values%2A> property to be of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="8d011-106">Esto impide a los usuarios recorrer en iteración estructuras de datos que implementan la interfaz <xref:System.Collections.Generic.IEnumerable%601> (por ejemplo, <xref:System.Collections.ArrayList>).</span><span class="sxs-lookup"><span data-stu-id="8d011-106">This precludes users from iterating over data structures that implement <xref:System.Collections.Generic.IEnumerable%601> interface (for example, <xref:System.Collections.ArrayList>).</span></span> <span data-ttu-id="8d011-107">La versión no genérica de <xref:System.Activities.Statements.ForEach%601> supera este requisito, a costa de una mayor complejidad del tiempo de ejecución para garantizar la compatibilidad de los tipos de los valores de la colección.</span><span class="sxs-lookup"><span data-stu-id="8d011-107">The non-generic version of <xref:System.Activities.Statements.ForEach%601> overcomes this requirement, at the expense of more run-time complexity for ensuring the compatibility of the types of the values in the collection.</span></span>  
  
 <span data-ttu-id="8d011-108">En este ejemplo se muestra cómo implementar una actividad <xref:System.Activities.Statements.ForEach%601> no genérica y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="8d011-108">This sample shows how to implement a non-generic <xref:System.Activities.Statements.ForEach%601> activity and its designer.</span></span> <span data-ttu-id="8d011-109">Esta actividad se puede utilizar para recorrer en iteración <xref:System.Collections.ArrayList>.</span><span class="sxs-lookup"><span data-stu-id="8d011-109">This activity can be used to iterate through <xref:System.Collections.ArrayList>.</span></span>  
  
## <a name="foreach-activity"></a><span data-ttu-id="8d011-110">Actividad ForEach</span><span class="sxs-lookup"><span data-stu-id="8d011-110">ForEach Activity</span></span>  

 <span data-ttu-id="8d011-111">La instrucción de C#/Visual Basic `foreach` enumera los elementos de una colección y ejecuta una instrucción incrustada para cada elemento de la colección.</span><span class="sxs-lookup"><span data-stu-id="8d011-111">The C#/Visual Basic `foreach` statement enumerates the elements of a collection, executing an embedded statement for each element of the collection.</span></span> <span data-ttu-id="8d011-112">Las actividades equivalentes de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] de `foreach` son <xref:System.Activities.Statements.ForEach%601> y <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="8d011-112">The [!INCLUDE[wf1](../../../../includes/wf1-md.md)] equivalent activities of `foreach` are <xref:System.Activities.Statements.ForEach%601> and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span> <span data-ttu-id="8d011-113">La actividad <xref:System.Activities.Statements.ForEach%601> contiene una lista de valores y un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="8d011-113">The <xref:System.Activities.Statements.ForEach%601> activity contains a list of values and a body.</span></span> <span data-ttu-id="8d011-114">En el tiempo de ejecución, la lista se recorre en iteración y se ejecuta el cuerpo para cada valor de la lista.</span><span class="sxs-lookup"><span data-stu-id="8d011-114">At runtime, the list is iterated and the body is executed for each value in the list.</span></span>  
  
 <span data-ttu-id="8d011-115">En la mayoría de los casos, la versión genérica de la actividad debe ser la solución preferida, porque abarca la mayoría de los escenarios en los que se puede utilizar y proporciona comprobación de tipos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="8d011-115">For most cases, the generic version of the activity should be the preferred solution, because it covers most of the scenarios in which it would be used, and provides type checking at compile time.</span></span> <span data-ttu-id="8d011-116">La versión no genérica se puede utilizar para recorrer en iteración tipos que implementan la interfaz <xref:System.Collections.IEnumerable> no genérica.</span><span class="sxs-lookup"><span data-stu-id="8d011-116">The non-generic version can be used for iterating through types that implement the non-generic <xref:System.Collections.IEnumerable> interface.</span></span>  
  
## <a name="class-definition"></a><span data-ttu-id="8d011-117">Definición de clase</span><span class="sxs-lookup"><span data-stu-id="8d011-117">Class Definition</span></span>  

 <span data-ttu-id="8d011-118">El siguiente ejemplo de código muestra la definición de una actividad `ForEach` no genérica.</span><span class="sxs-lookup"><span data-stu-id="8d011-118">The following code example shows the definition of a non-generic `ForEach` activity.</span></span>  
  
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
  
 <span data-ttu-id="8d011-119">Cuerpo (opcional)</span><span class="sxs-lookup"><span data-stu-id="8d011-119">Body (optional)</span></span>  
 <span data-ttu-id="8d011-120"><xref:System.Activities.ActivityAction> de tipo <xref:System.Object>, que se ejecuta para cada elemento en la colección.</span><span class="sxs-lookup"><span data-stu-id="8d011-120">The <xref:System.Activities.ActivityAction> of type <xref:System.Object>, which is executed for each element in the collection.</span></span> <span data-ttu-id="8d011-121">Cada elemento individual se pasa al cuerpo a través de su propiedad `Argument`.</span><span class="sxs-lookup"><span data-stu-id="8d011-121">Each individual element is passed into the Body through its `Argument` property.</span></span>  
  
 <span data-ttu-id="8d011-122">Valores (opcional)</span><span class="sxs-lookup"><span data-stu-id="8d011-122">Values (optional)</span></span>  
 <span data-ttu-id="8d011-123">La colección de elementos que se recorre en iteración.</span><span class="sxs-lookup"><span data-stu-id="8d011-123">The collection of elements that are iterated over.</span></span> <span data-ttu-id="8d011-124">La verificación de que todos los elementos de la colección son de tipos compatibles se realiza en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="8d011-124">Ensuring that all elements of the collection are of compatible types is done at run-time.</span></span>  
  
## <a name="example-of-using-foreach"></a><span data-ttu-id="8d011-125">Ejemplo de uso de ForEach</span><span class="sxs-lookup"><span data-stu-id="8d011-125">Example of Using ForEach</span></span>  

 <span data-ttu-id="8d011-126">El siguiente código muestra cómo utilizar la actividad ForEach en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d011-126">The following code demonstrates how to use the ForEach activity in an application.</span></span>  
  
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
  
|<span data-ttu-id="8d011-127">Condición</span><span class="sxs-lookup"><span data-stu-id="8d011-127">Condition</span></span>|<span data-ttu-id="8d011-128">Message</span><span class="sxs-lookup"><span data-stu-id="8d011-128">Message</span></span>|<span data-ttu-id="8d011-129">severity</span><span class="sxs-lookup"><span data-stu-id="8d011-129">Severity</span></span>|<span data-ttu-id="8d011-130">Tipo de excepción</span><span class="sxs-lookup"><span data-stu-id="8d011-130">Exception Type</span></span>|  
|---------------|-------------|--------------|--------------------|  
|<span data-ttu-id="8d011-131">Los valores son `null`</span><span class="sxs-lookup"><span data-stu-id="8d011-131">Values is `null`</span></span>|<span data-ttu-id="8d011-132">No se proporcionó el valor para un argumento de actividad necesario 'Values'.</span><span class="sxs-lookup"><span data-stu-id="8d011-132">Value for a required activity argument 'Values' was not supplied.</span></span>|<span data-ttu-id="8d011-133">Error</span><span class="sxs-lookup"><span data-stu-id="8d011-133">Error</span></span>|<xref:System.InvalidOperationException>|  
  
## <a name="foreach-designer"></a><span data-ttu-id="8d011-134">Diseñador de ForEach</span><span class="sxs-lookup"><span data-stu-id="8d011-134">ForEach Designer</span></span>  

 <span data-ttu-id="8d011-135">El diseñador de actividad del ejemplo es similar en aspecto al diseñador proporcionado para la actividad <xref:System.Activities.Statements.ForEach%601> integrada.</span><span class="sxs-lookup"><span data-stu-id="8d011-135">The activity designer for the sample is similar in appearance to the designer provided for the built-in <xref:System.Activities.Statements.ForEach%601> activity.</span></span> <span data-ttu-id="8d011-136">El diseñador aparece en el cuadro de herramientas en la categoría **ejemplos**, **actividades no genéricas** .</span><span class="sxs-lookup"><span data-stu-id="8d011-136">The designer appears in the toolbox in the **Samples**, **Non-Generic Activities** category.</span></span> <span data-ttu-id="8d011-137">El diseñador se denomina **ForEachWithBodyFactory** en el cuadro de herramientas, porque la actividad expone un <xref:System.Activities.Presentation.IActivityTemplateFactory> en el cuadro de herramientas, que crea la actividad con un configurado correctamente <xref:System.Activities.ActivityAction> .</span><span class="sxs-lookup"><span data-stu-id="8d011-137">The designer is named **ForEachWithBodyFactory** in the toolbox, because the activity exposes an <xref:System.Activities.Presentation.IActivityTemplateFactory> in the toolbox, which creates the activity with a properly configured <xref:System.Activities.ActivityAction>.</span></span>  
  
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
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="8d011-138">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8d011-138">To run this sample</span></span>  
  
1. <span data-ttu-id="8d011-139">Establezca el proyecto que desee como el proyecto de inicio de la solución:</span><span class="sxs-lookup"><span data-stu-id="8d011-139">Set the project of your choice as the start-up project of the solution:</span></span>  
  
    1. <span data-ttu-id="8d011-140">**CodeTestClient** muestra cómo utilizar la actividad mediante código.</span><span class="sxs-lookup"><span data-stu-id="8d011-140">**CodeTestClient** shows how to use the activity using code.</span></span>  
  
    2. <span data-ttu-id="8d011-141">**DesignerTestClient** muestra cómo utilizar la actividad en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="8d011-141">**DesignerTestClient** shows how to use the activity within the designer.</span></span>  
  
2. <span data-ttu-id="8d011-142">Compile y ejecute el proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d011-142">Build and run the project.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8d011-143">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8d011-143">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8d011-144">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8d011-144">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="8d011-145">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="8d011-145">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8d011-146">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8d011-146">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\NonGenericForEach`
