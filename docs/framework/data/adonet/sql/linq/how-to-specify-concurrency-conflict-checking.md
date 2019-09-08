---
title: Procedimiento para especificar comprobaciones con conflictos de simultaneidad
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2547fcb-58eb-4377-9948-1b8d76a0f3d7
ms.openlocfilehash: fd3db5eb5dc9b74d8ea33af56dd522cf2f3fecdb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781589"
---
# <a name="how-to-specify-concurrency-conflict-checking"></a><span data-ttu-id="eceec-102">Procedimiento para especificar comprobaciones con conflictos de simultaneidad</span><span class="sxs-lookup"><span data-stu-id="eceec-102">How to: Specify Concurrency-Conflict Checking</span></span>
<span data-ttu-id="eceec-103">Puede especificar en qué columnas de la base de datos se deben comprobar los conflictos de simultaneidad al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="eceec-103">You can specify which columns of the database are to be checked for concurrency conflicts when you call <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span></span> <span data-ttu-id="eceec-104">Para obtener más información, consulte [Cómo Especifique los miembros que se van a probar para](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)detectar conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="eceec-104">For more information, see [How to: Specify Which Members are Tested for Concurrency Conflicts](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="eceec-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eceec-105">Example</span></span>  
 <span data-ttu-id="eceec-106">El código siguiente especifica que el miembro `HomePage` nunca se debería comprobar durante las búsquedas de actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="eceec-106">The following code specifies that the `HomePage` member should never be tested during update checks.</span></span> <span data-ttu-id="eceec-107">Para obtener más información, consulta <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span><span class="sxs-lookup"><span data-stu-id="eceec-107">For more information, see <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A>.</span></span>  
  
 [!code-csharp[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.mapping.updatecheck/cs/northwind.cs#1)]
 [!code-vb[System.Data.Linq.Mapping.UpdateCheck#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.mapping.updatecheck/vb/northwind.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="eceec-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="eceec-108">See also</span></span>

- [<span data-ttu-id="eceec-109">Modelo de objetos de LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="eceec-109">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="eceec-110">Procedimientos: Personalización de clases de entidad mediante el editor de código</span><span class="sxs-lookup"><span data-stu-id="eceec-110">How to: Customize Entity Classes by Using the Code Editor</span></span>](how-to-customize-entity-classes-by-using-the-code-editor.md)
