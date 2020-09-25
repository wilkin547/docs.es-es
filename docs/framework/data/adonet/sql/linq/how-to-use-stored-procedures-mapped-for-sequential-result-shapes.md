---
title: Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: a53b2afcfce33c654b06b237cc55ad966c030568
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91184955"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="e53da-102">Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="e53da-102">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>

<span data-ttu-id="e53da-103">Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="e53da-103">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="e53da-104">Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="e53da-104">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="e53da-105">Para obtener más información, vea [Cómo: usar procedimientos almacenados asignados para varias formas de resultados](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="e53da-105">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e53da-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e53da-106">Example</span></span>  

 <span data-ttu-id="e53da-107">A continuación se muestra el código T-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:</span><span class="sxs-lookup"><span data-stu-id="e53da-107">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```sql
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="e53da-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e53da-108">Example</span></span>  

 <span data-ttu-id="e53da-109">Usaría código similar al siguiente para ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="e53da-109">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="e53da-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e53da-110">See also</span></span>

- [<span data-ttu-id="e53da-111">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="e53da-111">Stored Procedures</span></span>](stored-procedures.md)
