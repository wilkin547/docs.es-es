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
ms.openlocfilehash: d6446145d34d22503697bbca59bc2cb2cd2619cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="5e4e4-102">Cómo: Recorrer un árbol binario con tareas paralelas</span><span class="sxs-lookup"><span data-stu-id="5e4e4-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="5e4e4-103">En el ejemplo siguiente se muestran dos formas de usar las tareas paralelas para recorrer una estructura de datos en árbol.</span><span class="sxs-lookup"><span data-stu-id="5e4e4-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="5e4e4-104">La creación del árbol se deja como un ejercicio.</span><span class="sxs-lookup"><span data-stu-id="5e4e4-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e4e4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e4e4-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="5e4e4-106">Los dos métodos que se muestran son funcionalmente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="5e4e4-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="5e4e4-107">Con el uso del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> para crear y ejecutar las tareas, estas devuelven un identificador que puede usarse para esperar las tareas y controlar excepciones.</span><span class="sxs-lookup"><span data-stu-id="5e4e4-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e4e4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e4e4-108">See Also</span></span>  
 [<span data-ttu-id="5e4e4-109">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="5e4e4-109">Task Parallel Library (TPL)</span></span>](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
