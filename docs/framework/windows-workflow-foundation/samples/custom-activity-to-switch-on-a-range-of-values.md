---
title: Actividad personalizada para cambiar en un intervalo de valores
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 441e0a17-421f-430c-ba97-59e4cc6c88e3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4dcaf023960aab1989493475fe4e5306623adf8e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="custom-activity-to-switch-on-a-range-of-values"></a><span data-ttu-id="1205c-102">Actividad personalizada para cambiar en un intervalo de valores</span><span class="sxs-lookup"><span data-stu-id="1205c-102">Custom Activity to Switch on a Range of Values</span></span>
<span data-ttu-id="1205c-103">En este ejemplo se muestra cómo crear una actividad personalizada que amplía el uso de una instrucción <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="1205c-103">This sample demonstrates how to create a custom activity that extends the use of a <xref:System.Activities.Statements.Switch%601>.</span></span> <span data-ttu-id="1205c-104">Una instrucción <xref:System.Activities.Statements.Switch%601> convencional permite el cambio en función de un único valor.</span><span class="sxs-lookup"><span data-stu-id="1205c-104">A conventional <xref:System.Activities.Statements.Switch%601> statement allows switching based upon a single value.</span></span> <span data-ttu-id="1205c-105">Sin embargo, existen escenarios empresariales donde una actividad debe cambiar en función de un intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="1205c-105">But, there are business scenarios where an activity must switch based upon a range of values.</span></span> <span data-ttu-id="1205c-106">Por ejemplo, una actividad podría ejecutar una acción cuando el valor de cambio se sitúa entre 1 y 5, otra acción cuando el valor se sitúa entre 6 y 10 y una acción predeterminada para los demás valores.</span><span class="sxs-lookup"><span data-stu-id="1205c-106">For example, an activity might execute one action when the value being switched upon is between 1 and 5, another action when the value is between 6 and 10, and a default action for all other values.</span></span> <span data-ttu-id="1205c-107">Esta actividad personalizada permite exactamente ese escenario.</span><span class="sxs-lookup"><span data-stu-id="1205c-107">This custom activity enables exactly that scenario.</span></span>  
  
## <a name="the-switchrange-activity"></a><span data-ttu-id="1205c-108">Actividad SwitchRange</span><span class="sxs-lookup"><span data-stu-id="1205c-108">The SwitchRange Activity</span></span>  
 <span data-ttu-id="1205c-109">La actividad `SwitchRange` programa una actividad secundaria cuando el valor de resultado de su expresión está incluido dentro del intervalo de uno de `Cases`.</span><span class="sxs-lookup"><span data-stu-id="1205c-109">The `SwitchRange` activity schedules a child activity when the result value of its expression is included within the range of one of its `Cases`.</span></span>  
  
 <span data-ttu-id="1205c-110">El siguiente ejemplo de código es una actividad personalizada que cambia en función de un intervalo de valores.</span><span class="sxs-lookup"><span data-stu-id="1205c-110">The following code example is a custom activity that switches based upon a range of values.</span></span>  
  
```csharp  
public sealed class SwitchRange<T> : NativeActivity where T : IComparable  
{  
   [RequiredArgument]  
   [DefaultValue(null)]  
   public InArgument<T> Expression { get; set; }  
  
   public IList<CaseRange<T>> Cases  
  
   [DefaultValue(null)]  
   public Activity Default { get; set; }}  
}  
```  
  
|<span data-ttu-id="1205c-111">Propiedad</span><span class="sxs-lookup"><span data-stu-id="1205c-111">Property</span></span>|<span data-ttu-id="1205c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1205c-112">Description</span></span>|  
|-|-|  
|<span data-ttu-id="1205c-113">Expresión</span><span class="sxs-lookup"><span data-stu-id="1205c-113">Expression</span></span>|<span data-ttu-id="1205c-114">Es la expresión que se va a evaluar y comparar con los intervalos de la lista Cases.</span><span class="sxs-lookup"><span data-stu-id="1205c-114">This is the expression to be evaluated and compared against the ranges in the Cases list.</span></span> <span data-ttu-id="1205c-115">El resultado de la expresión es de tipo T.</span><span class="sxs-lookup"><span data-stu-id="1205c-115">The result of the expression is of type T.</span></span>|  
|<span data-ttu-id="1205c-116">Cases</span><span class="sxs-lookup"><span data-stu-id="1205c-116">Cases</span></span>|<span data-ttu-id="1205c-117">Cada caso consta de un intervalo (From y To) y una actividad (Body).</span><span class="sxs-lookup"><span data-stu-id="1205c-117">Each case consists of a range (From and To) and an activity (Body).</span></span> <span data-ttu-id="1205c-118">La expresión se evalúa y se compara con los intervalos.</span><span class="sxs-lookup"><span data-stu-id="1205c-118">The expression is evaluated and compared against the ranges.</span></span> <span data-ttu-id="1205c-119">Si el resultado de la expresión se sitúa dentro del intervalo de uno de los casos, se ejecuta la actividad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1205c-119">If the result of the expression is within the range of one of the cases, the corresponding activity is executed.</span></span>|  
|<span data-ttu-id="1205c-120">Default</span><span class="sxs-lookup"><span data-stu-id="1205c-120">Default</span></span>|<span data-ttu-id="1205c-121">La actividad que se ejecuta cuando no coincide ningún caso.</span><span class="sxs-lookup"><span data-stu-id="1205c-121">The activity that is executed when no case is matched.</span></span> <span data-ttu-id="1205c-122">Cuando se establece en `null`, no se realiza ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="1205c-122">When set to `null`, no action is taken.</span></span>|  
  
## <a name="caserange-class"></a><span data-ttu-id="1205c-123">Clase CaseRange</span><span class="sxs-lookup"><span data-stu-id="1205c-123">CaseRange Class</span></span>  
 <span data-ttu-id="1205c-124">La clase `CaseRange` representa un intervalo dentro de una actividad `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="1205c-124">The `CaseRange` class represents a range within a `SwitchRange` activity.</span></span> <span data-ttu-id="1205c-125">Cada instancia de `CaseRange` contiene un intervalo (compuesto de `From` y `To`) y una actividad `Body` que se programan si la expresión de `SwitchRange` se evalúa dentro del intervalo.</span><span class="sxs-lookup"><span data-stu-id="1205c-125">Every instance of `CaseRange` contains a range (composed of a `From` and a `To`) and a `Body` activity that is scheduled if the expression in the `SwitchRange` is evaluated within the range.</span></span>  
  
 <span data-ttu-id="1205c-126">El ejemplo de código siguiente es la definición de la clase `CaseRange`.</span><span class="sxs-lookup"><span data-stu-id="1205c-126">The following code example is the definition for the `CaseRange` class.</span></span>  
  
```  
public class CaseRange<T> where T : IComparable  
{  
    public T From { get; set; }  
  
    public T To { get; set; }  
  
    public Activity Action { get; set; }  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="1205c-127">Las clases `SwitchRange` y `CaseRange` que se definen en el ejemplo son clases genéricas que pueden funcionar con cualquier tipo que implemente `IComparable`, como la clase <xref:System.Activities.Statements.Switch%601>.</span><span class="sxs-lookup"><span data-stu-id="1205c-127">Both the `SwitchRange` and `CaseRange` classes, which are defined in the sample are generic classes that can work with any type that implements `IComparable`, like the <xref:System.Activities.Statements.Switch%601> class.</span></span>  
  
## <a name="sample-usage"></a><span data-ttu-id="1205c-128">Uso del ejemplo</span><span class="sxs-lookup"><span data-stu-id="1205c-128">Sample Usage</span></span>  
 <span data-ttu-id="1205c-129">En el ejemplo de código siguiente se muestra cómo utilizar la actividad `SwitchRange`.</span><span class="sxs-lookup"><span data-stu-id="1205c-129">The following code example demonstrates how to use the `SwitchRange` activity.</span></span>  
  
```csharp  
Activity SwitchRange = new SwitchRange<int>  
{  
    Expression = new InArgument<int>(value),  
    Cases =   
    {  
        new CaseRange<int>                      
        {  
            From = 1,  
            To = 5,  
            Action = new WriteLine  
            {  
                Text = "Case 1-5 selected",  
            }  
        },  
        new CaseRange<int>  
        {  
            From = 6,  
            To = 10,  
            Action = new WriteLine  
            {  
                Text = "Case 6-10 selected",  
            }  
        }  
    },  
    Default = new WriteLine { Text = "Default Case selected" }  
};  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="1205c-130">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="1205c-130">To use this sample</span></span>  
  
1.  <span data-ttu-id="1205c-131">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución SwitchRange.sln.</span><span class="sxs-lookup"><span data-stu-id="1205c-131">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the SwitchRange.sln solution file.</span></span>  
  
2.  <span data-ttu-id="1205c-132">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="1205c-132">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="1205c-133">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="1205c-133">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1205c-134">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1205c-134">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1205c-135">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1205c-135">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="1205c-136">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="1205c-136">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1205c-137">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1205c-137">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SwitchRange`