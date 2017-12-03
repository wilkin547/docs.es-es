---
title: Uso de la actividad Pick
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18c8af9717cb03bd262ceb0a62c91dbc778071c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="b2197-102">Uso de la actividad Pick</span><span class="sxs-lookup"><span data-stu-id="b2197-102">Using the Pick Activity</span></span>
<span data-ttu-id="b2197-103">En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="b2197-103">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>  
  
 <span data-ttu-id="b2197-104">La actividad <xref:System.Activities.Statements.Pick> proporciona un modelado de control basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="b2197-104">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="b2197-105">Se comporta de forma similar a la instrucción `switch` de C#, que ejecuta solo una de las bifurcaciones en la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="b2197-105">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="b2197-106">A diferencia de la instrucción `switch`, en la que se ejecuta una bifurcación basada en un valor, la actividad <xref:System.Activities.Statements.Pick> ejecuta una bifurcación en base a la manera en que se completa una actividad.</span><span class="sxs-lookup"><span data-stu-id="b2197-106">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>  
  
 <span data-ttu-id="b2197-107">En este ejemplo se pide a un usuario que escriba su nombre en la consola dentro de un determinado período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="b2197-107">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="b2197-108">La actividad <xref:System.Activities.Statements.Pick> del ejemplo tiene dos bifurcaciones cuya ejecución depende de si el usuario escribe su nombre en un intervalo de 5 segundos o no.</span><span class="sxs-lookup"><span data-stu-id="b2197-108">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="b2197-109">Si el usuario escribe su nombre en 5 segundos, se ejecuta la primera bifurcación, que contiene una actividad `ReadLine` personalizada; de lo contrario, se ejecuta la otra bifurcación, que contiene una actividad <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="b2197-109">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="b2197-110">Una vez escrito el nombre de un usuario en la consola, se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="b2197-110">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="b2197-111">Si no se escribe ninguna entrada en 5 segundos, la operación agota el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="b2197-111">If an input is not entered within 5 seconds, the operation is timed out.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="b2197-112">Demostraciones</span><span class="sxs-lookup"><span data-stu-id="b2197-112">Demonstrates</span></span>  
 <span data-ttu-id="b2197-113">Actividad <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="b2197-113"><xref:System.Activities.Statements.Pick> activity.</span></span>  
  
## <a name="discussion"></a><span data-ttu-id="b2197-114">Explicación</span><span class="sxs-lookup"><span data-stu-id="b2197-114">Discussion</span></span>  
 <span data-ttu-id="b2197-115">En este ejemplo se incluyen un flujo de trabajo de diseñador y un flujo de trabajo codificado.</span><span class="sxs-lookup"><span data-stu-id="b2197-115">The sample includes a Designer workflow and coded workflow.</span></span>  
  
 <span data-ttu-id="b2197-116">Flujo de trabajo de diseñador</span><span class="sxs-lookup"><span data-stu-id="b2197-116">Designer Workflow</span></span>  
 <span data-ttu-id="b2197-117">La versión del diseñador del ejemplo muestra cómo crear un flujo de trabajo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b2197-117">The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="b2197-118">Están incluidos los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="b2197-118">The following files are included:</span></span>  
  
-   <span data-ttu-id="b2197-119">Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b2197-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="b2197-120">ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.</span><span class="sxs-lookup"><span data-stu-id="b2197-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
-   <span data-ttu-id="b2197-121">Sequence1.xaml: un flujo de trabajo creado mediante el diseñador que utiliza Pick.</span><span class="sxs-lookup"><span data-stu-id="b2197-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>  
  
 <span data-ttu-id="b2197-122">Flujo de trabajo codificado</span><span class="sxs-lookup"><span data-stu-id="b2197-122">Coded Workflow</span></span>  
 <span data-ttu-id="b2197-123">La versión codificada del ejemplo muestra cómo crear un flujo de trabajo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="b2197-123">The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="b2197-124">Están incluidos los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="b2197-124">The following files are included:</span></span>  
  
-   <span data-ttu-id="b2197-125">Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b2197-125">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>  
  
-   <span data-ttu-id="b2197-126">ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.</span><span class="sxs-lookup"><span data-stu-id="b2197-126">ReadString.cs: A custom activity that reads some input from the console.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="b2197-127">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="b2197-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="b2197-128">Abra el archivo de solución Pick.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b2197-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Pick.sln solution file.</span></span>  
  
2.  <span data-ttu-id="b2197-129">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="b2197-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="b2197-130">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="b2197-130">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b2197-131">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b2197-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b2197-132">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b2197-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b2197-133">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b2197-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b2197-134">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b2197-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`