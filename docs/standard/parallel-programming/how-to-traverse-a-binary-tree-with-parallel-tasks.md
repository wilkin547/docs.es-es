---
title: 'Cómo: Recorrer un árbol binario con tareas paralelas'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8fd937d6ce2edf0c47fce78d48a90ec1aa409eef
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2018
ms.locfileid: "44196652"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="74115-102">Cómo: Recorrer un árbol binario con tareas paralelas</span><span class="sxs-lookup"><span data-stu-id="74115-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="74115-103">En el ejemplo siguiente se muestran dos formas de usar las tareas paralelas para recorrer una estructura de datos en árbol.</span><span class="sxs-lookup"><span data-stu-id="74115-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="74115-104">La creación del árbol se deja como un ejercicio.</span><span class="sxs-lookup"><span data-stu-id="74115-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74115-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="74115-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="74115-106">Los dos métodos que se muestran son funcionalmente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="74115-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="74115-107">Con el uso del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> para crear y ejecutar las tareas, estas devuelven un identificador que puede usarse para esperar las tareas y controlar excepciones.</span><span class="sxs-lookup"><span data-stu-id="74115-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74115-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="74115-108">See also</span></span>

- [<span data-ttu-id="74115-109">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="74115-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
