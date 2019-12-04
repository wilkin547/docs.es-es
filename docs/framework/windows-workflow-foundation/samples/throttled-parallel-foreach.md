---
title: Throttled Parallel ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: 340e4ff154b63221ec911c872a1154bdb672cf8c
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715919"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="85702-102">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="85702-102">Throttled Parallel ForEach</span></span>

<span data-ttu-id="85702-103">La actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="85702-103">The `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="85702-104">La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades (las actividades secundarias) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="85702-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="85702-105">Proyectos</span><span class="sxs-lookup"><span data-stu-id="85702-105">Projects</span></span>

|<span data-ttu-id="85702-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="85702-106">**ProjectName**</span></span>|<span data-ttu-id="85702-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="85702-107">**Description**</span></span>|<span data-ttu-id="85702-108">**Archivos principales**</span><span class="sxs-lookup"><span data-stu-id="85702-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="85702-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="85702-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="85702-110">Contiene la actividad `ThrottledParallelForEach` y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="85702-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="85702-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="85702-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="85702-112">La definición de actividad de `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="85702-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="85702-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="85702-113">CodeTestClient</span></span>|<span data-ttu-id="85702-114">Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.</span><span class="sxs-lookup"><span data-stu-id="85702-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="85702-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="85702-115">Program.cs</span></span><br /><br /> <span data-ttu-id="85702-116">Define y ejecuta una instancia del flujo de trabajo de muestra.</span><span class="sxs-lookup"><span data-stu-id="85702-116">Defines and runs an instance of the sample workflow.</span></span>|

## <a name="to-use-this-sample"></a><span data-ttu-id="85702-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="85702-117">To use this sample</span></span>

1. <span data-ttu-id="85702-118">Con Visual Studio 2010, abra el archivo ThrottledParallelForEach. sln.</span><span class="sxs-lookup"><span data-stu-id="85702-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2. <span data-ttu-id="85702-119">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="85702-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="85702-120">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="85702-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85702-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="85702-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="85702-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="85702-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="85702-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="85702-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="85702-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="85702-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`
