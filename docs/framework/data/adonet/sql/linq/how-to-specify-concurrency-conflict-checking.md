---
title: Procedimiento para especificar comprobaciones con conflictos de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: 53d3ba6969705940c403795d3764c021f0829c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033688"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="4b167-102">Procedimiento para especificar comprobaciones con conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="4b167-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="4b167-103">Puede especificar en qué columnas de la base de datos se deben comprobar los conflictos de simultaneidad al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b167-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="4b167-104">Para obtener más información, vea [Cómo: Especificar qué miembros se comprueban los conflictos de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span><span class="sxs-lookup"><span data-stu-id="4b167-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b167-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b167-105">Example</span></span>  
 <span data-ttu-id="4b167-106">El código siguiente especifica que el miembro `HomePage` nunca se debería comprobar durante las búsquedas de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="4b167-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="4b167-107">Para obtener más información, consulta <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="4b167-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4b167-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b167-108">See also</span></span>

- [<span data-ttu-id="4b167-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4b167-109">The LINQ to SQL Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [<span data-ttu-id="4b167-110">Cómo: Personalizar las clases de entidad mediante el Editor de código</span><span class="sxs-lookup"><span data-stu-id="4b167-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
