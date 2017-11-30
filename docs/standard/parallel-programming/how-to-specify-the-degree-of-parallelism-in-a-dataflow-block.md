---
title: "Cómo: Especificar el grado de paralelismo en un bloque de flujos de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow block, specifying parallelism in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, specifying parallelism
ms.assetid: e4088541-ee05-40db-95f5-147cfe62fde7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c1ccd64a9acbc75a30984719671af2dc7dda6922
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-the-degree-of-parallelism-in-a-dataflow-block"></a><span data-ttu-id="d5874-102">Cómo: Especificar el grado de paralelismo en un bloque de flujos de datos</span><span class="sxs-lookup"><span data-stu-id="d5874-102">How to: Specify the Degree of Parallelism in a Dataflow Block</span></span>
<span data-ttu-id="d5874-103">En este documento se describe cómo establecer la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> para que un bloque de flujo de datos de ejecución pueda procesar más de un mensaje al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d5874-103">This document describes how to set the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A?displayProperty=nameWithType> property to enable an execution dataflow block to process more than one message at a time.</span></span> <span data-ttu-id="d5874-104">Esto resulta útil cuando tiene un bloque de flujo de datos que realiza un cálculo de ejecución prolongada y se puede beneficiar del procesamiento de mensajes en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d5874-104">Doing this is useful when you have a dataflow block that performs a long-running computation and can benefit from processing messages in parallel.</span></span> <span data-ttu-id="d5874-105">En el ejemplo se usa la clase <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> para llevar a cabo varias operaciones de flujo de datos simultáneamente; sin embargo, puede especificar el grado máximo de paralelismo en cualquiera de los tipos de bloque de ejecución predefinidos que la biblioteca de flujo de datos TPL proporciona, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType> y <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5874-105">This example uses the <xref:System.Threading.Tasks.Dataflow.ActionBlock%601?displayProperty=nameWithType> class to perform multiple dataflow operations concurrently; however, you can specify the maximum degree of parallelism in any of the predefined execution block types that the TPL Dataflow Library provides, <xref:System.Threading.Tasks.Dataflow.ActionBlock%601>, <xref:System.Threading.Tasks.Dataflow.TransformBlock%602?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602?displayProperty=nameWithType>.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="d5874-106">La biblioteca de flujos de datos TPL (el espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5874-106">The TPL Dataflow Library (the <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="d5874-107">Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.</span><span class="sxs-lookup"><span data-stu-id="d5874-107">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5874-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5874-108">Example</span></span>  
 <span data-ttu-id="d5874-109">En el ejemplo siguiente se realizan dos cálculos de flujo de datos y se imprime el tiempo transcurrido que se necesita para cada cálculo.</span><span class="sxs-lookup"><span data-stu-id="d5874-109">The following example performs two dataflow computations and prints the elapsed time that is required for each computation.</span></span> <span data-ttu-id="d5874-110">El primer cálculo especifica un grado máximo de paralelismo de 1, que es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d5874-110">The first computation specifies a maximum degree of parallelism of 1, which is the default.</span></span> <span data-ttu-id="d5874-111">Un grado máximo de paralelismo de 1 hace que el bloque de flujo de datos procese los mensajes en serie.</span><span class="sxs-lookup"><span data-stu-id="d5874-111">A maximum degree of parallelism of 1 causes the dataflow block to process messages serially.</span></span> <span data-ttu-id="d5874-112">El segundo cálculo es similar al primero, excepto que especifica un grado máximo de paralelismo igual al número de procesadores disponibles.</span><span class="sxs-lookup"><span data-stu-id="d5874-112">The second computation resembles the first, except that it specifies a maximum degree of parallelism that is equal to the number of available processors.</span></span> <span data-ttu-id="d5874-113">Esto permite que el bloque de flujo de datos realice varias operaciones en paralelo.</span><span class="sxs-lookup"><span data-stu-id="d5874-113">This enables the dataflow block to perform multiple operations in parallel.</span></span>  
  
 [!code-csharp[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_degreeofparallelism/cs/dataflowdegreeofparallelism.cs#1)]
 [!code-vb[TPLDataflow_DegreeOfParallelism#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_degreeofparallelism/vb/dataflowdegreeofparallelism.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d5874-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="d5874-114">Compiling the Code</span></span>  
 <span data-ttu-id="d5874-115">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="d5874-115">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowDegreeOfParallelism.cs` (`DataflowDegreeOfParallelism.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="d5874-116">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span><span class="sxs-lookup"><span data-stu-id="d5874-116">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="d5874-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span><span class="sxs-lookup"><span data-stu-id="d5874-117">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowDegreeOfParallelism.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="d5874-118">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="d5874-118">Robust Programming</span></span>  
 <span data-ttu-id="d5874-119">De forma predeterminada, cada bloque de flujo de datos predefinido propaga los mensajes en el orden con que se reciben.</span><span class="sxs-lookup"><span data-stu-id="d5874-119">By default, each predefined dataflow block propagates out messages in the order in which the messages are received.</span></span>  <span data-ttu-id="d5874-120">Aunque cuando se especifica un grado máximo de paralelismo mayor que 1 se procesan simultáneamente varios mensajes, se siguen propagando en el orden con que se reciben.</span><span class="sxs-lookup"><span data-stu-id="d5874-120">Although multiple messages are processed simultaneously when you specify a maximum degree of parallelism that is greater than 1, they are still propagated out in the order in which they are received.</span></span>  
  
 <span data-ttu-id="d5874-121">Dado que la propiedad <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> representa el grado máximo de paralelismo, el bloque de flujo de datos puede ejecutarse con un menor grado de paralelismo que el especificado.</span><span class="sxs-lookup"><span data-stu-id="d5874-121">Because the <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions.MaxDegreeOfParallelism%2A> property represents the maximum degree of parallelism, the dataflow block might execute with a lesser degree of parallelism than you specify.</span></span> <span data-ttu-id="d5874-122">El bloque de flujo de datos puede usar un grado de paralelismo menor para cumplir los requisitos funcionales o porque hay una falta de recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="d5874-122">The dataflow block can use a lesser degree of parallelism to meet its functional requirements or to account for a lack of available system resources.</span></span> <span data-ttu-id="d5874-123">Un bloque de flujo de datos nunca elige un grado de paralelismo mayor que el especificado.</span><span class="sxs-lookup"><span data-stu-id="d5874-123">A dataflow block never chooses a greater degree of parallelism than you specify.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5874-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5874-124">See Also</span></span>  
 [<span data-ttu-id="d5874-125">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="d5874-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
