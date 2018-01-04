---
title: Usar la clase WorkflowInvoker
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0a966164-3990-4e78-8aa2-c6797ebbee94
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 553367916ff249118a8fcdd8273382402b90cfcc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-workflowinvoker-class"></a><span data-ttu-id="ea510-102">Usar la clase WorkflowInvoker</span><span class="sxs-lookup"><span data-stu-id="ea510-102">Using the WorkflowInvoker Class</span></span>
<span data-ttu-id="ea510-103">En este ejemplo se muestra cómo utilizar la clase <xref:System.Activities.WorkflowInvoker> para invocar una actividad como si fuera un método.</span><span class="sxs-lookup"><span data-stu-id="ea510-103">This sample demonstrates how to use the <xref:System.Activities.WorkflowInvoker> class to invoke an activity as if it were a method.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="ea510-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea510-104">Sample Details</span></span>  
 <span data-ttu-id="ea510-105">Utilizar la clase <xref:System.Activities.WorkflowInvoker> es la manera más simple de ejecutar una actividad.</span><span class="sxs-lookup"><span data-stu-id="ea510-105">Using the <xref:System.Activities.WorkflowInvoker> class is the simplest way to execute an activity.</span></span> <span data-ttu-id="ea510-106">Está diseñada para ejecutar una actividad directamente como si fuese una llamada a un método.</span><span class="sxs-lookup"><span data-stu-id="ea510-106">It is designed for directly running an activity as if it were a method call.</span></span> <span data-ttu-id="ea510-107">Es una API ligera, con alto rendimiento y sencilla de usar para utilizar en escenarios donde la ejecución de una actividad no requiere la infraestructura de control que proporcionan otras variaciones de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="ea510-107">It is a lightweight, high-performing, easy to use API for use in scenarios where an activity’s execution does not require the control infrastructure provided by other hosting variations.</span></span>  
  
 <span data-ttu-id="ea510-108">El ejemplo usa una actividad personalizada que deriva de <xref:System.Activities.CodeActivity%601>< Int32\> denominado `Add` que suma dos <xref:System.Activities.InArgument%601>, `X` y `Y`y devuelve un `Result` <xref:System.Activities.OutArgument%601>.</span><span class="sxs-lookup"><span data-stu-id="ea510-108">The sample uses a custom activity that derives from <xref:System.Activities.CodeActivity%601><Int32\> named `Add` that adds two <xref:System.Activities.InArgument%601>, `X` and `Y`, and returns a `Result`<xref:System.Activities.OutArgument%601>.</span></span> <span data-ttu-id="ea510-109">(<xref:System.Activities.CodeActivity%601>\<T > deriva <xref:System.Activities.Activity%601>< T\>, que tiene un <xref:System.Activities.OutArgument%601> \<T > denominado `Result`.) A `Dictionary` \<cadena, objeto > se usa para pasar argumentos a una actividad que se invoca mediante <xref:System.Activities.WorkflowInvoker>.</span><span class="sxs-lookup"><span data-stu-id="ea510-109">(<xref:System.Activities.CodeActivity%601>\<T> derives from <xref:System.Activities.Activity%601><T\>, which has an <xref:System.Activities.OutArgument%601>\<T> named `Result`.) A `Dictionary`\<string, object> is used to pass arguments into an activity being invoked through <xref:System.Activities.WorkflowInvoker>.</span></span> <span data-ttu-id="ea510-110">La clave del diccionario corresponde al nombre de un argumento de la actividad invocada.</span><span class="sxs-lookup"><span data-stu-id="ea510-110">The key of the dictionary corresponds to the name of an argument on the invoked activity.</span></span> <span data-ttu-id="ea510-111">El valor asociado a una clave determinada se enlaza al argumento identificado por la clave.</span><span class="sxs-lookup"><span data-stu-id="ea510-111">The value associated with a particular key is bound to the argument identified by the key.</span></span>  
  
 <span data-ttu-id="ea510-112">En el ejemplo se llama a <xref:System.Activities.WorkflowInvoker.Invoke%2A> y se pasa un diccionario que contiene valores para `X` e `Y`.</span><span class="sxs-lookup"><span data-stu-id="ea510-112">The sample calls <xref:System.Activities.WorkflowInvoker.Invoke%2A> and passes a dictionary that contains values for `X` and `Y`.</span></span> <span data-ttu-id="ea510-113">La clase <xref:System.Activities.WorkflowInvoker> enlaza estos valores a los argumentos de la actividad `Add`, ejecuta la actividad y devuelve el resultado.</span><span class="sxs-lookup"><span data-stu-id="ea510-113">The <xref:System.Activities.WorkflowInvoker> class binds these values to the `Add` activity’s arguments, executes the activity, and returns the result.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="ea510-114">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="ea510-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="ea510-115">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución Invoker.sln.</span><span class="sxs-lookup"><span data-stu-id="ea510-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Invoker.sln solution file.</span></span>  
  
2.  <span data-ttu-id="ea510-116">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="ea510-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="ea510-117">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="ea510-117">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ea510-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="ea510-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ea510-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="ea510-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ea510-120">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="ea510-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ea510-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="ea510-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\WorkflowInvoker`