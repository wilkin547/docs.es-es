---
title: 'Cómo: Recorrer un árbol binario con tareas paralelas'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
ms.openlocfilehash: ca70021c7d071abe480cb4ed866e34f171cc3b45
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94825538"
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a><span data-ttu-id="ff5c2-102">Cómo: Recorrer un árbol binario con tareas paralelas</span><span class="sxs-lookup"><span data-stu-id="ff5c2-102">How to: Traverse a Binary Tree with Parallel Tasks</span></span>
<span data-ttu-id="ff5c2-103">En el ejemplo siguiente se muestran dos formas de usar las tareas paralelas para recorrer una estructura de datos en árbol.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-103">The following example shows two ways in which parallel tasks can be used to traverse a tree data structure.</span></span> <span data-ttu-id="ff5c2-104">La creación del árbol se deja como un ejercicio.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-104">The creation of the tree itself is left as an exercise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ff5c2-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ff5c2-105">Example</span></span>  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 <span data-ttu-id="ff5c2-106">Los dos métodos que se muestran son funcionalmente equivalentes.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-106">The two methods shown are functionally equivalent.</span></span> <span data-ttu-id="ff5c2-107">Con el uso del método <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> para crear y ejecutar las tareas, estas devuelven un identificador que puede usarse para esperar las tareas y controlar excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff5c2-107">By using the <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> method to create and run the tasks, you get a handle back from the tasks which can be used to wait on the tasks and handle exceptions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff5c2-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff5c2-108">See also</span></span>

- [<span data-ttu-id="ff5c2-109">Biblioteca TPL</span><span class="sxs-lookup"><span data-stu-id="ff5c2-109">Task Parallel Library (TPL)</span></span>](task-parallel-library-tpl.md)
