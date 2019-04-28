---
title: Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: e51ebacb3f6be849f7b871f2d12db3ea7476b117
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61877076"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="bddf6-102">Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="bddf6-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>
<span data-ttu-id="bddf6-103">Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="bddf6-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="bddf6-104">Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="bddf6-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="bddf6-105">Para obtener más información, vea [Cómo: Usar procedimientos almacenados asignados en varias formas de resultados](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="bddf6-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bddf6-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bddf6-106">Example</span></span>  
 <span data-ttu-id="bddf6-107">A continuación se muestra el código T-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:</span><span class="sxs-lookup"><span data-stu-id="bddf6-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```  
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="bddf6-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bddf6-108">Example</span></span>  
 <span data-ttu-id="bddf6-109">Usaría código similar al siguiente para ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="bddf6-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="bddf6-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="bddf6-110">See also</span></span>

- [<span data-ttu-id="bddf6-111">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="bddf6-111">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
