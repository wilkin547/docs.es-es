---
title: Throttled Parallel ForEach
ms.date: 03/30/2017
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
ms.openlocfilehash: fd30a1ac587359a054a273b3deca2e9bb8bc2798
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55261833"
---
# <a name="throttled-parallel-foreach"></a><span data-ttu-id="89eca-102">Throttled Parallel ForEach</span><span class="sxs-lookup"><span data-stu-id="89eca-102">Throttled Parallel ForEach</span></span>

<span data-ttu-id="89eca-103">La actividad `ThrottleParallelForEach` es similar a la actividad <xref:System.Activities.Statements.ParallelForEach%601> con la única excepción de que permite establecer un factor de simultaneidad para restringir el número de bifurcaciones simultáneas que se ejecutará.</span><span class="sxs-lookup"><span data-stu-id="89eca-103">The `ThrottleParallelForEach` activity is similar to the <xref:System.Activities.Statements.ParallelForEach%601> activity with the one exception that it allows setting a concurrency factor to restrict the number of simultaneous branches to execute.</span></span> <span data-ttu-id="89eca-104">La actividad `ThrottleParallelForEach` se deriva de <xref:System.Activities.NativeActivity>, porque necesita programar otras actividades (las actividades secundarias) y el único acceso posible es a través de la clase <xref:System.Activities.NativeActivityContext>.</span><span class="sxs-lookup"><span data-stu-id="89eca-104">The `ThrottleParallelForEach` activity derives from <xref:System.Activities.NativeActivity>, because it needs to schedule other activities (the child activities) and this is only accessible through the <xref:System.Activities.NativeActivityContext> class.</span></span>

## <a name="projects"></a><span data-ttu-id="89eca-105">Proyectos</span><span class="sxs-lookup"><span data-stu-id="89eca-105">Projects</span></span>

|<span data-ttu-id="89eca-106">**ProjectName**</span><span class="sxs-lookup"><span data-stu-id="89eca-106">**ProjectName**</span></span>|<span data-ttu-id="89eca-107">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="89eca-107">**Description**</span></span>|<span data-ttu-id="89eca-108">**Archivos principales**</span><span class="sxs-lookup"><span data-stu-id="89eca-108">**Main Files**</span></span>|
|-|-|-|
|<span data-ttu-id="89eca-109">ThrottledParallelForEach</span><span class="sxs-lookup"><span data-stu-id="89eca-109">ThrottledParallelForEach</span></span>|<span data-ttu-id="89eca-110">Contiene la actividad `ThrottledParallelForEach` y su diseñador.</span><span class="sxs-lookup"><span data-stu-id="89eca-110">Contains `ThrottledParallelForEach` activity and its designer.</span></span>|<span data-ttu-id="89eca-111">ThrottledParallelForEach.cs</span><span class="sxs-lookup"><span data-stu-id="89eca-111">ThrottledParallelForEach.cs</span></span><br /><br /> <span data-ttu-id="89eca-112">La definición de actividad de `ThrottledParallelForEach`.</span><span class="sxs-lookup"><span data-stu-id="89eca-112">The `ThrottledParallelForEach` activity definition.</span></span>|
|<span data-ttu-id="89eca-113">CodeTestClient</span><span class="sxs-lookup"><span data-stu-id="89eca-113">CodeTestClient</span></span>|<span data-ttu-id="89eca-114">Aplicación cliente de ejemplo que configura y ejecuta un flujo de trabajo con una actividad `ThrottledParallelForEach` utilizando código imperativo.</span><span class="sxs-lookup"><span data-stu-id="89eca-114">Sample client application that configures and runs a workflow with a `ThrottledParallelForEach` using imperative code.</span></span>|<span data-ttu-id="89eca-115">Program.cs</span><span class="sxs-lookup"><span data-stu-id="89eca-115">Program.cs</span></span><br /><br /> <span data-ttu-id="89eca-116">Define y ejecuta una instancia del flujo de trabajo de muestra.</span><span class="sxs-lookup"><span data-stu-id="89eca-116">Defines and runs an instance of the sample workflow.</span></span>|

## <a name="to-use-this-sample"></a><span data-ttu-id="89eca-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="89eca-117">To use this sample</span></span>

1. <span data-ttu-id="89eca-118">Con Visual Studio 2010, abra el archivo ThrottledParallelForEach.sln.</span><span class="sxs-lookup"><span data-stu-id="89eca-118">Using Visual Studio 2010, open the ThrottledParallelForEach.sln file.</span></span>

2. <span data-ttu-id="89eca-119">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="89eca-119">To build the solution, press CTRL+SHIFT+B.</span></span>

3. <span data-ttu-id="89eca-120">Presione F5 para ejecutar la solución.</span><span class="sxs-lookup"><span data-stu-id="89eca-120">To run the solution, press F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89eca-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="89eca-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="89eca-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="89eca-122">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="89eca-123">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="89eca-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="89eca-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="89eca-124">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`