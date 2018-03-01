---
title: "Cómo: Implementar un modelo de flujo de datos productor-consumidor"
ms.date: 03/30/2017
ms.prod: .net
ms.technology: dotnet-standard
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TPL dataflow library, implementing producer-consumer pattern
- Task Parallel Library, dataflows
- producer-consumer patterns, implementing [TPL]
ms.assetid: 47a1d38c-fe9c-44aa-bd15-937bd5659b0b
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 3758ec77a722a66c6faa287d299e5e9c38858be5
ms.sourcegitcommit: 6a9030eb5bd0f00e1d144f81958adb195cfb1f6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-implement-a-producer-consumer-dataflow-pattern"></a><span data-ttu-id="1ba50-102">Cómo: Implementar un modelo de flujo de datos productor-consumidor</span><span class="sxs-lookup"><span data-stu-id="1ba50-102">How to: Implement a Producer-Consumer Dataflow Pattern</span></span>
<span data-ttu-id="1ba50-103">Este documento describe cómo utilizar la biblioteca de flujos de datos TPL para implementar un modelo productor-consumidor.</span><span class="sxs-lookup"><span data-stu-id="1ba50-103">This document describes how to use the TPL Dataflow Library to implement a producer-consumer pattern.</span></span> <span data-ttu-id="1ba50-104">En este modelo, el *productor* envía mensajes a un bloque de mensajes y el *consumidor* lee los mensajes de este bloque.</span><span class="sxs-lookup"><span data-stu-id="1ba50-104">In this pattern, the *producer* sends messages to a message block, and the *consumer* reads messages from that block.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="example"></a><span data-ttu-id="1ba50-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1ba50-105">Example</span></span>  
 <span data-ttu-id="1ba50-106">En el ejemplo siguiente se muestra un modelo productor-consumidor básico que usa el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1ba50-106">The following example demonstrates a basic producer- consumer model that uses dataflow.</span></span> <span data-ttu-id="1ba50-107">El método `Produce` escribe matrices que contienen bytes de datos aleatorios en un objeto <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> y el método `Consume` lee los bytes de un objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1ba50-107">The `Produce` method writes arrays that contain random bytes of data to a <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601?displayProperty=nameWithType> object and the `Consume` method reads bytes from a <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601?displayProperty=nameWithType> object.</span></span> <span data-ttu-id="1ba50-108">Al actuar en las interfaces <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> y <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601>, en lugar de en sus tipos derivados, puede escribir código reutilizable que puede actuar en una variedad de tipos de bloques de flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="1ba50-108">By acting on the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> and <xref:System.Threading.Tasks.Dataflow.ITargetBlock%601> interfaces, instead of their derived types, you can write reusable code that can act on a variety of dataflow block types.</span></span> <span data-ttu-id="1ba50-109">Este ejemplo utiliza la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="1ba50-109">This example uses the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class.</span></span> <span data-ttu-id="1ba50-110">Puesto que la clase <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> actúa como origen y como un bloque de origen y destino, el productor y el consumidor pueden utilizar un objeto compartido para transferir datos.</span><span class="sxs-lookup"><span data-stu-id="1ba50-110">Because the <xref:System.Threading.Tasks.Dataflow.BufferBlock%601> class acts as both a source block and as a target block, the producer and the consumer can use a shared object to transfer data.</span></span>  
  
 <span data-ttu-id="1ba50-111">El método `Produce` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> en un bucle para escribir datos de forma sincrónica en el bloque de destino.</span><span class="sxs-lookup"><span data-stu-id="1ba50-111">The `Produce` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A> method in a loop to synchronously write data to the target block.</span></span> <span data-ttu-id="1ba50-112">Después de que el método `Produce` escriba todos los datos en el bloque de destino, llama al método <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> para indicar que el bloque nunca tendrá datos adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="1ba50-112">After the `Produce` method writes all data to the target block, it calls the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A> method to indicate that the block will never have additional data available.</span></span> <span data-ttu-id="1ba50-113">El método `Consume` usa los operadores [async](~/docs/csharp/language-reference/keywords/async.md) y [await](~/docs/csharp/language-reference/keywords/await.md) ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) y [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) para calcular de forma asincrónica el número total de bytes recibidos del objeto <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601>.</span><span class="sxs-lookup"><span data-stu-id="1ba50-113">The `Consume` method uses the [async](~/docs/csharp/language-reference/keywords/async.md) and [await](~/docs/csharp/language-reference/keywords/await.md) operators ([Async](~/docs/visual-basic/language-reference/modifiers/async.md) and [Await](~/docs/visual-basic/language-reference/operators/await-operator.md) in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) to asynchronously compute the total number of bytes that are received from the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> object.</span></span> <span data-ttu-id="1ba50-114">Para que actúe de forma asincrónica, el método `Consume` llama al método <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> para recibir una notificación cuando el bloque de origen tiene datos disponibles y cuando el bloque de origen nunca va a tener datos adicionales disponibles.</span><span class="sxs-lookup"><span data-stu-id="1ba50-114">To act asynchronously, the `Consume` method calls the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A> method to receive a notification when the source block has data available and when the source block will never have additional data available.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#1)]
 [!code-vb[TPLDataflow_ProducerConsumer#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ba50-115">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="1ba50-115">Compiling the Code</span></span>  
 <span data-ttu-id="1ba50-116">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="1ba50-116">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowProducerConsumer.cs` (`DataflowProducerConsumer.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="1ba50-117">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span><span class="sxs-lookup"><span data-stu-id="1ba50-117">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="1ba50-118">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span><span class="sxs-lookup"><span data-stu-id="1ba50-118">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowProducerConsumer.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="1ba50-119">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="1ba50-119">Robust Programming</span></span>  
 <span data-ttu-id="1ba50-120">Este ejemplo utiliza un solo consumidor para procesar los datos de origen.</span><span class="sxs-lookup"><span data-stu-id="1ba50-120">This example uses just one consumer to process the source data.</span></span> <span data-ttu-id="1ba50-121">Si tiene varios consumidores en la aplicación, use el método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> para leer datos desde el bloque de origen, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1ba50-121">If you have multiple consumers in your application, use the <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method to read data from the source block, as shown in the following example.</span></span>  
  
 [!code-csharp[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_producerconsumer/cs/dataflowproducerconsumer.cs#2)]
 [!code-vb[TPLDataflow_ProducerConsumer#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_producerconsumer/vb/dataflowproducerconsumer.vb#2)]  
  
 <span data-ttu-id="1ba50-122">El método <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> devuelve `False` cuando no hay datos disponibles.</span><span class="sxs-lookup"><span data-stu-id="1ba50-122">The <xref:System.Threading.Tasks.Dataflow.IReceivableSourceBlock%601.TryReceive%2A> method returns `False` when no data is available.</span></span> <span data-ttu-id="1ba50-123">Cuando varios consumidores deben tener acceso simultáneamente al bloque de origen, este mecanismo garantiza que los datos están disponibles después de la llamada a <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span><span class="sxs-lookup"><span data-stu-id="1ba50-123">When multiple consumers must access the source block concurrently, this mechanism guarantees that data is still available after the call to <xref:System.Threading.Tasks.Dataflow.DataflowBlock.OutputAvailableAsync%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba50-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1ba50-124">See Also</span></span>  
 [<span data-ttu-id="1ba50-125">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="1ba50-125">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
