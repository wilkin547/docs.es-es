---
title: Usar variables con un conjunto de reglas de .NET Framework 3.5
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2656cc5d8add0027d6bf038d5de735ebccd2d96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="using-variables-with-a-net-framework-35-ruleset"></a><span data-ttu-id="24319-102">Usar variables con un conjunto de reglas de .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="24319-102">Using Variables with a .NET Framework 3.5 Ruleset</span></span>
<span data-ttu-id="24319-103">En este ejemplo se muestra cómo crear un flujo de trabajo que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar una actividad personalizada escrita en [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] que utiliza directiva y reglas.</span><span class="sxs-lookup"><span data-stu-id="24319-103">This sample demonstrates how to create a workflow that uses the <xref:System.Activities.Statements.Interop> activity to integrate a custom activity written in [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)] that uses policy and rules.</span></span> <span data-ttu-id="24319-104">El flujo de trabajo pasa datos a la actividad personalizada enlazando las variables a las propiedades de dependencia expuestas por la actividad personalizada.</span><span class="sxs-lookup"><span data-stu-id="24319-104">The workflow passes data to the custom activity by binding variables to the dependency properties exposed by the custom activity.</span></span>  
  
## <a name="sample-walkthrough"></a><span data-ttu-id="24319-105">Ejemplo de tutorial</span><span class="sxs-lookup"><span data-stu-id="24319-105">Sample walkthrough</span></span>  
  
#### <a name="to-examine-travelrulelibrary"></a><span data-ttu-id="24319-106">Para examinar TravelRuleLibrary</span><span class="sxs-lookup"><span data-stu-id="24319-106">To examine TravelRuleLibrary</span></span>  
  
1.  <span data-ttu-id="24319-107">Con [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], abra el archivo de solución InteropWith35RuleSet.sln.</span><span class="sxs-lookup"><span data-stu-id="24319-107">Using [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="24319-108">Abra TravelRuleSet.cs en el diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="24319-108">Open the TravelRuleSet.cs in the workflow designer.</span></span>  
  
     <span data-ttu-id="24319-109">Se muestra una actividad secuencial personalizada que contiene una actividad <xref:System.Workflow.Activities.PolicyActivity>.</span><span class="sxs-lookup"><span data-stu-id="24319-109">A custom sequential activity that contains a <xref:System.Workflow.Activities.PolicyActivity> is displayed.</span></span>  
  
3.  <span data-ttu-id="24319-110">Haga doble clic en la actividad de directiva DiscountPolicy para examinar las reglas.</span><span class="sxs-lookup"><span data-stu-id="24319-110">Double-click the DiscountPolicy policy activity to examine the rules.</span></span>  
  
     <span data-ttu-id="24319-111">Aparece el editor de reglas para mostrar las reglas.</span><span class="sxs-lookup"><span data-stu-id="24319-111">The Rules editor pops up to show the rules.</span></span>  
  
4.  <span data-ttu-id="24319-112">Haga clic con el `DiscountPolicy` y seleccione la **ver código** opción para examinar el código C# lateral de la actividad.</span><span class="sxs-lookup"><span data-stu-id="24319-112">Right click the `DiscountPolicy` and select the **View Code** option to examine the code beside C# code for the activity.</span></span>  
  
     <span data-ttu-id="24319-113">Observe el valor de propiedad de dependencia para `DiscountLevel`.</span><span class="sxs-lookup"><span data-stu-id="24319-113">Observe the dependency property setting for `DiscountLevel`.</span></span> <span data-ttu-id="24319-114">Esto equivale a los argumentos en [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="24319-114">This is equivalent to arguments in [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)].</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="24319-115">argumentos, vea [Variables y argumentos](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span><span class="sxs-lookup"><span data-stu-id="24319-115"> arguments, see [Variables and Arguments](../../../../docs/framework/windows-workflow-foundation/variables-and-arguments.md).</span></span>  
  
## <a name="interopwith35ruleset"></a><span data-ttu-id="24319-116">InteropWith35RuleSet</span><span class="sxs-lookup"><span data-stu-id="24319-116">InteropWith35RuleSet</span></span>  
 <span data-ttu-id="24319-117">Es un proyecto de flujo de trabajo secuencial que utiliza la actividad <xref:System.Activities.Statements.Interop> para integrar con el conjunto de reglas personalizado creado en el proyecto `TravelRuleLibrary`.</span><span class="sxs-lookup"><span data-stu-id="24319-117">This is a sequential workflow project that uses the <xref:System.Activities.Statements.Interop> activity to integrate with the custom Rule set created in the `TravelRuleLibrary` project.</span></span> <span data-ttu-id="24319-118">Las variables se crean en la actividad <xref:System.Activities.Statements.Sequence> de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="24319-118">Variables are created on the top level <xref:System.Activities.Statements.Sequence> activity.</span></span> <span data-ttu-id="24319-119">La actividad <xref:System.Activities.Statements.Interop> se utiliza para la integración con la actividad `TravelRuleSet`.</span><span class="sxs-lookup"><span data-stu-id="24319-119">The <xref:System.Activities.Statements.Interop> activity is used to integrate with the `TravelRuleSet` activity.</span></span> <span data-ttu-id="24319-120">Las variables que se declaran en <xref:System.Activities.Statements.Sequence> se utilizan para enlazar con las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="24319-120">The variables that are declared on the <xref:System.Activities.Statements.Sequence> are used to bind to the dependency properties.</span></span>  
  
## <a name="to-use-this-sample"></a><span data-ttu-id="24319-121">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="24319-121">To use this sample</span></span>  
  
1.  <span data-ttu-id="24319-122">Con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], abra el archivo de solución InteropWith35RuleSet.sln.</span><span class="sxs-lookup"><span data-stu-id="24319-122">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the InteropWith35RuleSet.sln solution file.</span></span>  
  
2.  <span data-ttu-id="24319-123">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="24319-123">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="24319-124">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="24319-124">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="24319-125">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="24319-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="24319-126">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="24319-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="24319-127">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="24319-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="24319-128">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="24319-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`