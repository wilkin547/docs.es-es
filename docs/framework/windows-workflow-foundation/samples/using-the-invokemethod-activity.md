---
title: Uso de la actividad InvokeMethod
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6643550-d043-4ac7-8069-9c55ebbb4233
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d3f6734f9d6a3b0e2279b2bb6cca71141c8f5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-the-invokemethod-activity"></a><span data-ttu-id="8da7e-102">Uso de la actividad InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="8da7e-102">Using the InvokeMethod Activity</span></span>
<span data-ttu-id="8da7e-103">Este ejemplo muestra cómo utilizar el <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) actividad para invocar métodos públicos en clases públicas.</span><span class="sxs-lookup"><span data-stu-id="8da7e-103">This sample demonstrates how to use the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity to invoke public methods in public classes.</span></span> <span data-ttu-id="8da7e-104">El <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) actividad permite un flujo de trabajo llamar a métodos contra objetos, pasar parámetros, obtener el valor devuelto, especificar tipos para métodos genéricos y especificar si el método es sincrónico o asincrónica.</span><span class="sxs-lookup"><span data-stu-id="8da7e-104">The <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity allows a workflow to call methods against objects, pass in parameters, get the return value, specify types for generic methods, and specify whether the method is synchronous or asynchronous.</span></span> 
  
<span data-ttu-id="8da7e-105">Hay una versión no genérica de la <xref:System.Activities.Statements.InvokeMethod> actividad donde se establece el valor devuelto para la <xref:System.Activities.Statements.InvokeMethod.Result%2A> propiedad y una versión genérica de la <!--zz <xref:System.Activities.Statements.InvokeMethod%601> --> [ <code>System.Activities.Statements.InvokeMethod\`1</code> ](https://msdn.microsoft.com/library/dd647677.aspx) actividad que se devuelve el valor devuelto a través de la <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> --> [ <code>System.Activities.Statements.InvokeMethod\`1.Result</code> ](https://msdn.microsoft.com/library/dd987724.aspx) propiedad de tipo `TResult`.</span><span class="sxs-lookup"><span data-stu-id="8da7e-105">There is a non-generic version of the <xref:System.Activities.Statements.InvokeMethod> activity where the return value is set to the <xref:System.Activities.Statements.InvokeMethod.Result%2A> property and a generic version of the <!--zz <xref:System.Activities.Statements.InvokeMethod%601> -->[<code>System.Activities.Statements.InvokeMethod\`1</code>](https://msdn.microsoft.com/library/dd647677.aspx) activity where the return value is returned through the <!--zz <xref:System.Activities.Statements.InvokeMethod.Result%601.Result%2A> -->[<code>System.Activities.Statements.InvokeMethod\`1.Result</code>](https://msdn.microsoft.com/library/dd987724.aspx) property of type `TResult`.</span></span> 
  
 <span data-ttu-id="8da7e-106">En este ejemplo se muestra cómo llamar a varios tipos de método.</span><span class="sxs-lookup"><span data-stu-id="8da7e-106">This sample demonstrates how to call various method types.</span></span> <span data-ttu-id="8da7e-107">La siguiente lista detalla los tipos de método mostrados en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8da7e-107">The following list details the method types demonstrated in this sample:</span></span>  
  
-   <span data-ttu-id="8da7e-108">Invoque un método de instancia sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="8da7e-108">Invoke an instance method without parameters.</span></span>  
  
-   <span data-ttu-id="8da7e-109">Invoque un método de instancia con dos parámetros (System.String y System.Int32).</span><span class="sxs-lookup"><span data-stu-id="8da7e-109">Invoke an instance method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="8da7e-110">Invoque un método de instancia con dos parámetros (System.String y System.Int32) y una matriz de parámetros de tipo System.String [].</span><span class="sxs-lookup"><span data-stu-id="8da7e-110">Invoke an instance method with two parameters (System.String and System.Int32) and a parameter array of type System.String[].</span></span>  
  
-   <span data-ttu-id="8da7e-111">Invoque un método de instancia con dos parámetros (dos números de System.Int32) y un resultado de tipo System.Int32.</span><span class="sxs-lookup"><span data-stu-id="8da7e-111">Invoke an instance method with two parameters (two System.Int32 numbers) and a result of type System.Int32.</span></span>  
  
     <span data-ttu-id="8da7e-112">El valor devuelto se enlaza a una variable y se imprime en la consola mediante la actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="8da7e-112">The return value is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="8da7e-113">Invoque un método estático con dos parámetros (System.String y System.Int32).</span><span class="sxs-lookup"><span data-stu-id="8da7e-113">Invoke a static method with two parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="8da7e-114">Invoque un método de instancia con un parámetro genérico (System.String).</span><span class="sxs-lookup"><span data-stu-id="8da7e-114">Invoke an instance method with one generic parameter (System.String).</span></span>  
  
-   <span data-ttu-id="8da7e-115">Invoque un método estático con dos parámetros genéricos (System.String y System.Int32).</span><span class="sxs-lookup"><span data-stu-id="8da7e-115">Invoke a static method with two generic parameters (System.String and System.Int32).</span></span>  
  
-   <span data-ttu-id="8da7e-116">Invoque un método de instancia que tenga un parámetro pasado por referencia (System.String).</span><span class="sxs-lookup"><span data-stu-id="8da7e-116">Invoke an instance method that has one parameter passed by reference (System.String).</span></span>  
  
     <span data-ttu-id="8da7e-117">El parámetro al que se hace referencia se enlaza a una variable y se imprime en la consola utilizando la actividad <xref:System.Activities.Statements.WriteLine>.</span><span class="sxs-lookup"><span data-stu-id="8da7e-117">The referenced parameter is bound to a variable and printed to the console using the <xref:System.Activities.Statements.WriteLine> activity.</span></span>  
  
-   <span data-ttu-id="8da7e-118">Invoque un método de instancia asincrónico.</span><span class="sxs-lookup"><span data-stu-id="8da7e-118">Invoke an asynchronous instance method.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="8da7e-119">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="8da7e-119">To use this sample</span></span>  
  
1.  <span data-ttu-id="8da7e-120">Abra el archivo de solución InvokeMethodUsage.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8da7e-120">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InvokeMethodUsage.sln solution file.</span></span>  
  
2.  <span data-ttu-id="8da7e-121">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="8da7e-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="8da7e-122">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="8da7e-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8da7e-123">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8da7e-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8da7e-124">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8da7e-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8da7e-125">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8da7e-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8da7e-126">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8da7e-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InvokeMethod`