---
title: Emular la ruptura en una actividad While
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddff715d-d623-4b54-b841-60bacbc3ca21
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: edac8893ab2bb51fd97148e4b80f94d6566b8a54
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="emulating-breaking-in-a-while-activity"></a><span data-ttu-id="60f27-102">Emular la ruptura en una actividad While</span><span class="sxs-lookup"><span data-stu-id="60f27-102">Emulating breaking in a While activity</span></span>
<span data-ttu-id="60f27-103">En este ejemplo se muestra cómo interrumpir el mecanismo de bucle de las siguientes actividades: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>y <xref:System.Activities.Statements.ParallelForEach%601>.</span><span class="sxs-lookup"><span data-stu-id="60f27-103">This sample demonstrates how to break the looping mechanism of the following activities: <xref:System.Activities.Statements.DoWhile>, <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.While>, and <xref:System.Activities.Statements.ParallelForEach%601>.</span></span>  
  
 <span data-ttu-id="60f27-104">Esto resulta útil porque [!INCLUDE[wf](../../../../includes/wf-md.md)] no incluye ninguna actividad para interrumpir la ejecución de estos bucles.</span><span class="sxs-lookup"><span data-stu-id="60f27-104">This is useful because [!INCLUDE[wf](../../../../includes/wf-md.md)] does not include any activity to break the execution of these loops.</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="60f27-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="60f27-105">Scenario</span></span>  
 <span data-ttu-id="60f27-106">En el ejemplo se encuentra el primer proveedor de confianza en una lista de proveedores (instancias de la clase `Vendor`).</span><span class="sxs-lookup"><span data-stu-id="60f27-106">The sample finds the first reliable vendor from a list of vendors (instances of the `Vendor` class).</span></span> <span data-ttu-id="60f27-107">Cada proveedor tiene un `ID`, un `Name` y un valor de confiabilidad numérico que determina la fiabilidad del proveedor.</span><span class="sxs-lookup"><span data-stu-id="60f27-107">Each vendor has an `ID`, a `Name` and a numeric reliability value that determines how dependable the vendor is.</span></span> <span data-ttu-id="60f27-108">En el ejemplo se crea una actividad personalizada llamada `FindReliableVendor` que recibe dos parámetros de entrada (una lista de proveedores y un valor de confiabilidad mínimo) y devuelve el primer proveedor de la lista que coincide con los criterios proporcionados.</span><span class="sxs-lookup"><span data-stu-id="60f27-108">The sample creates a custom activity called `FindReliableVendor` that receives two input parameters (a list of vendors and a minimum reliability value) and returns the first vendor of the list that matches the supplied criteria.</span></span>  
  
## <a name="breaking-a-loop"></a><span data-ttu-id="60f27-109">Interrumpir un bucle</span><span class="sxs-lookup"><span data-stu-id="60f27-109">Breaking a Loop</span></span>  
 [!INCLUDE[wf](../../../../includes/wf-md.md)]<span data-ttu-id="60f27-110"> no incluye ninguna actividad para interrumpir un bucle.</span><span class="sxs-lookup"><span data-stu-id="60f27-110"> does not include an activity to break a loop.</span></span> <span data-ttu-id="60f27-111">El ejemplo de código logra interrumpir un bucle utilizando una actividad <xref:System.Activities.Statements.If> y diferentes variables.</span><span class="sxs-lookup"><span data-stu-id="60f27-111">The code sample accomplishes breaking a loop by using an <xref:System.Activities.Statements.If> activity and several variables.</span></span> <span data-ttu-id="60f27-112">En el ejemplo, la actividad <xref:System.Activities.Statements.While> se interrumpe cuando se asigna a la variable `reliableVendor` un valor distinto de `null`.</span><span class="sxs-lookup"><span data-stu-id="60f27-112">In the sample, the <xref:System.Activities.Statements.While> activity is broken once the `reliableVendor` variable is assigned a value other than `null`.</span></span>  
  
 <span data-ttu-id="60f27-113">El siguiente ejemplo de código muestra cómo el ejemplo interrumpe un bucle while.</span><span class="sxs-lookup"><span data-stu-id="60f27-113">The following code example demonstrates how the sample breaks a while loop.</span></span>  
  
```csharp  
// Iterates while the "i" variable is lower than the size of the list   
// and any reliable Vendor is found.        
new While(env => i.Get(env) < this.Vendors.Get(env).Count && reliableVendor.Get(env) == null)  
{  
    DisplayName = "Main loop. Breaks when a reliable vendor is found",  
    Body = new Sequence  
    {                              
        Activities =  
        {  
            // This is the if used for setting the value of the break value…  
            new If  
            {  
                DisplayName = "Check for a reliable vendor",  
  
                //  If a vendor satisfies the reliability level…  
                Condition = new InArgument<bool>(env =>   
                           this.Vendors.Get(env)[i.Get(env)].Reliability >   
                           this.MinimumReliability.Get(env)),  
  
                // then assign that vendor to the reliable vendor variable and   
                // the while condition becomes false (exit the loop).  
                Then = new Assign<Vendor>  
                {  
                    To = reliableVendor,  
                    Value = new InArgument<Vendor>(env =>   
                                  this.Vendors.Get(env)[i.Get(env)])  
                }  
            },  
  
            // Increment the iteration variable.   
            new Assign<int>  
            {  
                DisplayName = "Increment iteration variable",  
                To = i,  
                Value = new InArgument<int>(env => i.Get(env) + 1)  
            }   
        }  
    }  
}  
```  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="60f27-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="60f27-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="60f27-115">Abra el archivo de solución EmulatingBreakInWhile.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="60f27-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the EmulatingBreakInWhile.sln solution file.</span></span>  
  
2.  <span data-ttu-id="60f27-116">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="60f27-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="60f27-117">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="60f27-117">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="60f27-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="60f27-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="60f27-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="60f27-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="60f27-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="60f27-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="60f27-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="60f27-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\EmulatingBreakInWhile`