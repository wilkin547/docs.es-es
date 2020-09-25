---
title: Procedimiento para especificar comprobaciones con conflictos de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 7adacdccd12c6493ff7c62c0e6a44058a9719d7d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197214"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="c0ffe-102">Procedimiento para especificar comprobaciones con conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="c0ffe-102">How to: Specify Concurrency-Conflict Checking</span></span>

<span data-ttu-id="c0ffe-103">Puede especificar en qué columnas de la base de datos se deben comprobar los conflictos de simultaneidad al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0ffe-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="c0ffe-104">Para obtener más información, vea [Cómo: especificar en qué miembros se comprueban los conflictos de simultaneidad](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="c0ffe-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c0ffe-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0ffe-105">Example</span></span>  

 <span data-ttu-id="c0ffe-106">El código siguiente especifica que el miembro `HomePage` nunca se debería comprobar durante las búsquedas de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="c0ffe-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="c0ffe-107">Para obtener más información, vea <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="c0ffe-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c0ffe-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0ffe-108">See also</span></span>

- [<span data-ttu-id="c0ffe-109">El modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="c0ffe-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="c0ffe-110">Procedimiento para personalizar clases de entidades con el editor de código</span><span class="sxs-lookup"><span data-stu-id="c0ffe-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
