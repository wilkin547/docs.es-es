---
title: "Cómo: Recorrer un árbol binario con tareas paralelas"
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
helpviewer_keywords: tasks, how to traverse a tree
ms.assetid: 4265d169-6c69-4f36-b10d-b7ae7f72f4df
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4c029a763faaa0b4d6ea5612efe079e47415b6fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-traverse-a-binary-tree-with-parallel-tasks"></a>Cómo: Recorrer un árbol binario con tareas paralelas
En el ejemplo siguiente se muestra dos maneras en que pueden utilizarse tareas paralelas para recorrer una estructura de datos de árbol. La creación del propio árbol se deja como un ejercicio.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[TPL#16](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl/cs/tpl.cs#16)]
 [!code-vb[TPL#16](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl/vb/treewalk.vb#16)]  
  
 Los dos métodos que se muestran son funcionalmente equivalentes. Mediante el uso de la <xref:System.Threading.Tasks.TaskFactory.StartNew%2A> método para crear y ejecutar las tareas, se recibe un identificador de las tareas que se pueden usar para esperar a que las tareas y controlar excepciones.  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca TPL](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)
