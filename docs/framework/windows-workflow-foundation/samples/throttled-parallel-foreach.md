---
title: Throttled Parallel ForEach
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7155c4f33cb29c5778e59124dd924005e4ef52f6
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="6d51d-102">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="6d51d-102">Throttled Parallel ForEach</span></span>
<span data-ttu-id="6d51d-103">El `ThrottleParallelForEach` actividad es similar a la <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` actividad con la única excepción que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="6d51d-103">The `ThrottleParallelForEach` activity is similar to the <!--zz <xref:System.Activities.Statements.ParallelForEach>--> `System.Activities.Statements.ParallelForEach` activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="6d51d-104">La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades (las actividades secundarias) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="6d51d-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>  
  
## <a name="projects"></a><span data-ttu-id="6d51d-105">Proyectos</span><span class="sxs-lookup"><span data-stu-id="6d51d-105">Projects</span></span>  
  
|<span data-ttu-id="6d51d-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="6d51d-106">**ProjectName**</span></span>|<span data-ttu-id="6d51d-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="6d51d-107">**Description**</span></span>|<span data-ttu-id="6d51d-108">**Archivos principales**</span><span class="sxs-lookup"><span data-stu-id="6d51d-108">**Main Files**</span></span>|  
|-|-|-|  
|<span data-ttu-id="6d51d-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="6d51d-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="6d51d-110">Contiene la actividad `ThrottledParallelForEach` y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="6d51d-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="6d51d-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="6d51d-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="6d51d-112">La definición de actividad de `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="6d51d-112">The `ThrottledParallelForEach` activity definition.</span></span>|  
|<span data-ttu-id="6d51d-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="6d51d-113">CodeTestClient</span></span>|<span data-ttu-id="6d51d-114">Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.</span><span class="sxs-lookup"><span data-stu-id="6d51d-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="6d51d-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="6d51d-115">Program.cs</span></span><br /><br /> <span data-ttu-id="6d51d-116">Define y ejecuta una instancia del flujo de trabajo de muestra.</span><span class="sxs-lookup"><span data-stu-id="6d51d-116">Defines and runs an instance of the sample workflow.</span></span>|  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="6d51d-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d51d-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="6d51d-118">Abra el archivo ThrottledParallelForEach.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6d51d-118">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ThrottledParallelForEach.sln file.</span></span>  
  
2.  <span data-ttu-id="6d51d-119">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="6d51d-119">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="6d51d-120">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="6d51d-120">To run the solution, press F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6d51d-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="6d51d-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6d51d-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="6d51d-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6d51d-123">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6d51d-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6d51d-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="6d51d-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`