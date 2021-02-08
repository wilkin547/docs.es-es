---
description: Más información acerca de cómo usar la actividad Pick
title: Uso de la actividad Pick
ms.date: 03/30/2017
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
ms.openlocfilehash: 3c7a96c6250db8b9301dfeba858568d5638a29f1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787752"
---
# <a name="using-the-pick-activity"></a><span data-ttu-id="5dae0-103">Uso de la actividad Pick</span><span class="sxs-lookup"><span data-stu-id="5dae0-103">Using the Pick Activity</span></span>

<span data-ttu-id="5dae0-104">En este ejemplo se muestra cómo utilizar la actividad <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="5dae0-104">This sample demonstrates how to use the <xref:System.Activities.Statements.Pick> activity.</span></span>

 <span data-ttu-id="5dae0-105">La actividad <xref:System.Activities.Statements.Pick> proporciona un modelado de control basado en eventos.</span><span class="sxs-lookup"><span data-stu-id="5dae0-105">The <xref:System.Activities.Statements.Pick> activity provides event-based control modeling.</span></span> <span data-ttu-id="5dae0-106">Se comporta de forma similar a la instrucción `switch` de C#, que ejecuta solo una de las bifurcaciones en la instrucción `switch`.</span><span class="sxs-lookup"><span data-stu-id="5dae0-106">It behaves similar to the C# `switch` statement, which executes only one of the branches in the `switch` statement.</span></span> <span data-ttu-id="5dae0-107">A diferencia de la instrucción `switch`, en la que se ejecuta una bifurcación basada en un valor, la actividad <xref:System.Activities.Statements.Pick> ejecuta una bifurcación en base a la manera en que se completa una actividad.</span><span class="sxs-lookup"><span data-stu-id="5dae0-107">Unlike the `switch` statement in which a branch is executed based upon on a value, the <xref:System.Activities.Statements.Pick> activity executes a branch based upon how an activity completes.</span></span>

 <span data-ttu-id="5dae0-108">En este ejemplo se pide a un usuario que escriba su nombre en la consola dentro de un determinado período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="5dae0-108">This sample prompts a user to type in their name on the console within a given time period.</span></span> <span data-ttu-id="5dae0-109">La actividad <xref:System.Activities.Statements.Pick> del ejemplo tiene dos bifurcaciones cuya ejecución depende de si el usuario escribe su nombre en un intervalo de 5 segundos o no.</span><span class="sxs-lookup"><span data-stu-id="5dae0-109">The <xref:System.Activities.Statements.Pick> activity in the sample has two branches that are executed based upon whether the user types in their name within 5 seconds or not.</span></span> <span data-ttu-id="5dae0-110">Si el usuario escribe su nombre en 5 segundos, se ejecuta la primera bifurcación, que contiene una actividad `ReadLine` personalizada; de lo contrario, se ejecuta la otra bifurcación, que contiene una actividad <xref:System.Activities.Statements.Delay>.</span><span class="sxs-lookup"><span data-stu-id="5dae0-110">If the user types in their name within 5 seconds, the first branch is executed, which contains a custom `ReadLine` activity; otherwise the other branch is executed, which contains a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="5dae0-111">Una vez escrito el nombre de un usuario en la consola, se imprime en la consola.</span><span class="sxs-lookup"><span data-stu-id="5dae0-111">Once a user’s name is typed in on the console, the user’s name is printed on the console.</span></span> <span data-ttu-id="5dae0-112">Si no se escribe ninguna entrada en 5 segundos, la operación agota el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="5dae0-112">If an input is not entered within 5 seconds, the operation is timed out.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5dae0-113">Muestra</span><span class="sxs-lookup"><span data-stu-id="5dae0-113">Demonstrates</span></span>

 <span data-ttu-id="5dae0-114">Actividad <xref:System.Activities.Statements.Pick>.</span><span class="sxs-lookup"><span data-stu-id="5dae0-114"><xref:System.Activities.Statements.Pick> activity.</span></span>

## <a name="discussion"></a><span data-ttu-id="5dae0-115">Debate</span><span class="sxs-lookup"><span data-stu-id="5dae0-115">Discussion</span></span>

 <span data-ttu-id="5dae0-116">En este ejemplo se incluyen un flujo de trabajo de diseñador y un flujo de trabajo codificado.</span><span class="sxs-lookup"><span data-stu-id="5dae0-116">The sample includes a Designer workflow and coded workflow.</span></span>

 <span data-ttu-id="5dae0-117">Flujo de trabajo del diseñador la versión del diseñador del ejemplo muestra cómo crear un flujo de trabajo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="5dae0-117">Designer Workflow The Designer version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="5dae0-118">Están incluidos los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="5dae0-118">The following files are included:</span></span>

- <span data-ttu-id="5dae0-119">Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5dae0-119">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="5dae0-120">ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.</span><span class="sxs-lookup"><span data-stu-id="5dae0-120">ReadString.cs: A custom activity that reads some input from the console.</span></span>

- <span data-ttu-id="5dae0-121">Sequence1.xaml: un flujo de trabajo creado mediante el diseñador que utiliza Pick.</span><span class="sxs-lookup"><span data-stu-id="5dae0-121">Sequence1.xaml: A workflow created using the designer that uses Pick.</span></span>

 <span data-ttu-id="5dae0-122">Flujo de trabajo codificado la versión codificada del ejemplo muestra cómo crear un flujo de trabajo en el diseñador.</span><span class="sxs-lookup"><span data-stu-id="5dae0-122">Coded Workflow The coded version of the sample demonstrates how to create a workflow in the designer.</span></span> <span data-ttu-id="5dae0-123">Están incluidos los siguientes archivos:</span><span class="sxs-lookup"><span data-stu-id="5dae0-123">The following files are included:</span></span>

- <span data-ttu-id="5dae0-124">Program.cs: incluye la función `Main` que ejecuta el flujo de trabajo del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="5dae0-124">Program.cs : Includes the `Main` function that executes the sample workflow.</span></span>

- <span data-ttu-id="5dae0-125">ReadString.cs: una actividad personalizada que lee alguna entrada de la consola.</span><span class="sxs-lookup"><span data-stu-id="5dae0-125">ReadString.cs: A custom activity that reads some input from the console.</span></span>

#### <a name="to-use-this-sample"></a><span data-ttu-id="5dae0-126">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="5dae0-126">To use this sample</span></span>

1. <span data-ttu-id="5dae0-127">Con Visual Studio 2010, abra el archivo de solución Pick. sln.</span><span class="sxs-lookup"><span data-stu-id="5dae0-127">Using Visual Studio 2010, open the Pick.sln solution file.</span></span>

2. <span data-ttu-id="5dae0-128">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="5dae0-128">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="5dae0-129">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="5dae0-129">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5dae0-130">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="5dae0-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5dae0-131">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="5dae0-131">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="5dae0-132">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="5dae0-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5dae0-133">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="5dae0-133">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`
