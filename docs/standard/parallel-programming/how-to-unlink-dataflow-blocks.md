---
title: "Cómo: Desvincular bloques de flujos de datos"
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
- dataflow blocks, unlinking in TPL
- Task Parallel Library, dataflows
- TPL dataflow library, unlinking dataflow blocks
ms.assetid: 40f0208d-4618-47f7-85cf-4913d07d2d7d
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41f1b83fab6ff44e69ac2f010f70e6e254341f5e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-unlink-dataflow-blocks"></a><span data-ttu-id="3b7dd-102">Cómo: Desvincular bloques de flujos de datos</span><span class="sxs-lookup"><span data-stu-id="3b7dd-102">How to: Unlink Dataflow Blocks</span></span>
<span data-ttu-id="3b7dd-103">Este documento describe cómo desvincular un bloque de flujo de datos de destino de su origen.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-103">This document describes how to unlink a target dataflow block from its source.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="3b7dd-104">La biblioteca de flujos de datos TPL (espacio de nombres <xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType>) no se distribuye con [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3b7dd-104">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="3b7dd-105">Para instalar el <xref:System.Threading.Tasks.Dataflow> espacio de nombres, abra el proyecto en [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], elija **administrar paquetes de NuGet** en el menú proyecto y busque en línea el `Microsoft.Tpl.Dataflow` paquete.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-105">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b7dd-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3b7dd-106">Example</span></span>  
 <span data-ttu-id="3b7dd-107">En el ejemplo siguiente se crea tres <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objetos, cada uno de los que llama el `TrySolution` método para calcular un valor.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-107">The following example creates three <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objects, each of which calls the `TrySolution` method to compute a value.</span></span> <span data-ttu-id="3b7dd-108">Este ejemplo requiere sólo el resultado de la primera llamada a `TrySolution` para finalizar.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-108">This example requires only the result from the first call to `TrySolution` to finish.</span></span>  
  
 [!code-csharp[TPLDataflow_ReceiveAny#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_receiveany/cs/dataflowreceiveany.cs#1)]
 [!code-vb[TPLDataflow_ReceiveAny#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_receiveany/vb/dataflowreceiveany.vb#1)]  
  
 <span data-ttu-id="3b7dd-109">Para recibir el valor de la primera <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> objeto que termina, este ejemplo se define la `ReceiveFromAny(T)` método.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-109">To receive the value from the first <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> object that finishes, this example defines the `ReceiveFromAny(T)` method.</span></span> <span data-ttu-id="3b7dd-110">El `ReceiveFromAny(T)` método acepta una matriz de <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objetos y vincula cada uno de estos objetos a un <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-110">The `ReceiveFromAny(T)` method accepts an array of <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601> objects and links each of these objects to a <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="3b7dd-111">Cuando se usa el <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método para vincular un bloque de flujo de datos de origen a un bloque de destino, el origen propaga mensajes al destino tal y como los datos están disponibles.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-111">When you use the <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method to link a source dataflow block to a target block, the source propagates messages to the target as data becomes available.</span></span> <span data-ttu-id="3b7dd-112">Dado que el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> clase acepta solo el primer mensaje que ofrece, el `ReceiveFromAny(T)` método genera su resultado mediante una llamada a la <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> (método).</span><span class="sxs-lookup"><span data-stu-id="3b7dd-112">Because the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> class accepts only the first message that it is offered, the `ReceiveFromAny(T)` method produces its result by calling the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A> method.</span></span> <span data-ttu-id="3b7dd-113">Esto produce el primer mensaje que se ofrece a los <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-113">This produces the first message that is offered to the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object.</span></span> <span data-ttu-id="3b7dd-114">El <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> método tiene una versión sobrecargada que toma un <xref:System.Boolean> parámetro, `unlinkAfterOne` que, cuando se establece en `True`, indica el bloque de origen para desvincular desde el destino después de que el destino recibe un mensaje desde el origen.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-114">The <xref:System.Threading.Tasks.Dataflow.ISourceBlock%601.LinkTo%2A> method has an overloaded version that takes a <xref:System.Boolean> parameter, `unlinkAfterOne` that, when it is set to `True`, instructs the source block to unlink from the target after the target receives one message from the source.</span></span> <span data-ttu-id="3b7dd-115">Es importante para la <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto desvinculación de sus orígenes porque la relación entre la matriz de los orígenes y el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> objeto ya no es necesario una vez el <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object recibe un mensaje.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-115">It is important for the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object to unlink from its sources because the relationship between the array of sources and the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object is no longer required after the <xref:System.Threading.Tasks.Dataflow.WriteOnceBlock%601> object receives a message.</span></span>  
  
 <span data-ttu-id="3b7dd-116">Para habilitar las llamadas restantes a `TrySolution` a finalizar después de que uno de ellos calcula un valor, el `TrySolution` método toma un <xref:System.Threading.CancellationToken> objeto que se cancela después de llamar a `ReceiveFromAny(T)` devuelve.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-116">To enable the remaining calls to `TrySolution` to end after one of them computes a value, the `TrySolution` method takes a <xref:System.Threading.CancellationToken> object that is canceled after the call to `ReceiveFromAny(T)` returns.</span></span> <span data-ttu-id="3b7dd-117">El <xref:System.Threading.SpinWait.SpinUntil%2A> método devuelve cuando esto <xref:System.Threading.CancellationToken> objeto está cancelado.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-117">The <xref:System.Threading.SpinWait.SpinUntil%2A> method returns when this <xref:System.Threading.CancellationToken> object is canceled.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3b7dd-118">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="3b7dd-118">Compiling the Code</span></span>  
 <span data-ttu-id="3b7dd-119">Copie el código de ejemplo y péguelo en un proyecto de Visual Studio o en un archivo denominado `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) y, a continuación, ejecute el siguiente comando en una ventana del símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="3b7dd-119">Copy the example code and paste it in a Visual Studio project, or paste it in a file that is named `DataflowReceiveAny.cs` (`DataflowReceiveAny.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="3b7dd-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span><span class="sxs-lookup"><span data-stu-id="3b7dd-120">**csc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="3b7dd-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span><span class="sxs-lookup"><span data-stu-id="3b7dd-121">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll DataflowReceiveAny.vb**</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3b7dd-122">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="3b7dd-122">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7dd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b7dd-123">See Also</span></span>  
 [<span data-ttu-id="3b7dd-124">Flujo de datos</span><span class="sxs-lookup"><span data-stu-id="3b7dd-124">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
