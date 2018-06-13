---
title: Controlador de cancelación en una actividad compensable
ms.date: 03/30/2017
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
ms.openlocfilehash: ce4d67b26a2b4c6a9b507715b48e75e328c5b100
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515006"
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="a335b-102">Controlador de cancelación en una actividad compensable</span><span class="sxs-lookup"><span data-stu-id="a335b-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="a335b-103">En este ejemplo se muestra el uso de un controlador de cancelación en un objeto <xref:System.Activities.Statements.CompensableActivity>.</span><span class="sxs-lookup"><span data-stu-id="a335b-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="a335b-104">Este ejemplo incluye dos escenarios que muestran el uso de la cancelación de <xref:System.Activities.Statements.CompensableActivity>. El primero contiene una actividad compensable raíz que contiene tres actividades compensables secundarias.</span><span class="sxs-lookup"><span data-stu-id="a335b-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="a335b-105">Dos actividades secundarias terminan de ejecutar sus cuerpos de actividad correctamente.</span><span class="sxs-lookup"><span data-stu-id="a335b-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="a335b-106">Cuando el cuerpo de la tercera actividad secundaria se ejecuta, encuentra una excepción que se controla cancelando el proceso de la tercera actividad, tras lo cual se activa la cancelación de la actividad raíz.</span><span class="sxs-lookup"><span data-stu-id="a335b-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="a335b-107">La lógica de la actividad raíz de este ejemplo es compensar las otras dos actividades secundarias que se completaron anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a335b-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="a335b-108">El segundo escenario muestra cómo ejecutar <xref:System.Activities.Statements.TryCatch> en paralelo con <xref:System.Activities.Statements.Delay>, que finaliza antes de la bifurcación <xref:System.Activities.Statements.TryCatch>.</span><span class="sxs-lookup"><span data-stu-id="a335b-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="a335b-109">La condición de la realización se establece en `true` una vez finalizada la primera bifurcación, lo que causa la cancelación de la otra bifurcación.</span><span class="sxs-lookup"><span data-stu-id="a335b-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="a335b-110">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="a335b-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="a335b-111">Abra CompensationCancellation.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a335b-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="a335b-112">Compile el ejemplo presionando CTRL+SHIFT+B o seleccione "Compilar solución" en el menú Compilar.</span><span class="sxs-lookup"><span data-stu-id="a335b-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="a335b-113">Ejecute el ejemplo presionando F5 o seleccione "Iniciar depuración" en el menú Depurar.</span><span class="sxs-lookup"><span data-stu-id="a335b-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="a335b-114">También, puede presionar Ctrl+F5 o seleccionar "Iniciar sin depurar" en el menú Depurar.</span><span class="sxs-lookup"><span data-stu-id="a335b-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a335b-115">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="a335b-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="a335b-116">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="a335b-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="a335b-117">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="a335b-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="a335b-118">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="a335b-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`