---
title: Procedimiento Usar procedimientos almacenados asignados en varias formas de resultados
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c2b84dfe-7fec-489a-92de-45215cec4518
ms.openlocfilehash: 6ea318e89cf91dcbf16747117b8000dfa3f9571d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54573678"
---
# <a name="how-to-use-stored-procedures-mapped-for-multiple-result-shapes"></a><span data-ttu-id="dcb92-102">Procedimiento Usar procedimientos almacenados asignados en varias formas de resultados</span><span class="sxs-lookup"><span data-stu-id="dcb92-102">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>
<span data-ttu-id="dcb92-103">Cuando un procedimiento almacenado puede devolver varias formas de resultados, el tipo de valor devuelto no puede estar fuertemente tipado para una forma de proyección única.</span><span class="sxs-lookup"><span data-stu-id="dcb92-103">When a stored procedure can return multiple result shapes, the return type cannot be strongly typed to a single projection shape.</span></span> <span data-ttu-id="dcb92-104">Aunque [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] puede generar todos los tipos de proyección posibles, no puede saber el orden en el que se devolverán.</span><span class="sxs-lookup"><span data-stu-id="dcb92-104">Although [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can generate all possible projection types, it cannot know the order in which they will be returned.</span></span>  
  
 <span data-ttu-id="dcb92-105">Compare este escenario con los procedimientos almacenados que generan varias formas de resultados secuencialmente.</span><span class="sxs-lookup"><span data-stu-id="dcb92-105">Contrast this scenario with stored procedures that produce multiple result shapes sequentially.</span></span> <span data-ttu-id="dcb92-106">Para obtener más información, vea [Cómo: Usar procedimientos almacenados asignados en formas de resultados secuenciales](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="dcb92-106">For more information, see [How to: Use Stored Procedures Mapped for Sequential Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md).</span></span>  
  
 <span data-ttu-id="dcb92-107">El atributo <xref:System.Data.Linq.Mapping.ResultTypeAttribute> se aplica a los procedimientos almacenados que devuelven varios tipos de resultados para especificar el conjunto de tipos que el procedimiento puede devolver.</span><span class="sxs-lookup"><span data-stu-id="dcb92-107">The <xref:System.Data.Linq.Mapping.ResultTypeAttribute> attribute is applied to stored procedures that return multiple result types to specify the set of types the procedure can return.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcb92-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcb92-108">Example</span></span>  
 <span data-ttu-id="dcb92-109">En el siguiente ejemplo de código SQL, la forma del resultado depende de la entrada (`shape =1` o `shape = 2`).</span><span class="sxs-lookup"><span data-stu-id="dcb92-109">In the following SQL code example, the result shape depends on the input (`shape =1` or `shape = 2`).</span></span> <span data-ttu-id="dcb92-110">No se sabe qué proyección se devolverá primero.</span><span class="sxs-lookup"><span data-stu-id="dcb92-110">You do not know which projection will be returned first.</span></span>  
  
```  
CREATE PROCEDURE VariableResultShapes(@shape int)  
AS  
if(@shape = 1)  
    select CustomerID, ContactTitle, CompanyName from customers  
else if(@shape = 2)  
    select OrderID, ShipName from orders  
```  
  
 [!code-csharp[DLinqSprox#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#4)]
 [!code-vb[DLinqSprox#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="dcb92-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dcb92-111">Example</span></span>  
 <span data-ttu-id="dcb92-112">Usaría código similar al siguiente para ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="dcb92-112">You would use code similar to the following to execute this stored procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dcb92-113">Debe utilizar el patrón <xref:System.Data.Linq.IMultipleResults.GetResult%2A> para obtener un enumerador del tipo correcto, basado en su conocimiento del procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="dcb92-113">You must use the <xref:System.Data.Linq.IMultipleResults.GetResult%2A> pattern to obtain an enumerator of the correct type, based on your knowledge of the stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#5)]
 [!code-vb[DLinqSprox#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="dcb92-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcb92-114">See also</span></span>
- [<span data-ttu-id="dcb92-115">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="dcb92-115">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
