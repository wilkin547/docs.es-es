---
description: 'Más información acerca de cómo: usar procedimientos almacenados asignados para formas de resultados secuenciales'
title: Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a73530de-5a4e-4d9c-8d66-abb19c225b11
ms.openlocfilehash: 3b5791875a7beb5a0c702e787e775cd528ab2517
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99738772"
---
# <a name="how-to-use-stored-procedures-mapped-for-sequential-result-shapes"></a><span data-ttu-id="b1729-103">Procedimiento para usar procedimientos almacenados asignados en formas de resultados secuenciales</span><span class="sxs-lookup"><span data-stu-id="b1729-103">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>

<span data-ttu-id="b1729-104">Este tipo de procedimiento almacenado puede generar más de una forma de resultado, pero se sabe en qué orden se devuelven los resultados.</span><span class="sxs-lookup"><span data-stu-id="b1729-104">This kind of stored procedure can generate more than one result shape, but you know in what order the results are returned.</span></span> <span data-ttu-id="b1729-105">Compare este escenario con el escenario donde no se sabe el orden de los resultados devueltos.</span><span class="sxs-lookup"><span data-stu-id="b1729-105">Contrast this scenario with the scenario where you do not know the sequence of the returns.</span></span> <span data-ttu-id="b1729-106">Para obtener más información, vea [Cómo: usar procedimientos almacenados asignados para varias formas de resultados](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span><span class="sxs-lookup"><span data-stu-id="b1729-106">For more information, see [How to: Use Stored Procedures Mapped for Multiple Result Shapes](how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1729-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1729-107">Example</span></span>  

 <span data-ttu-id="b1729-108">A continuación se muestra el código T-SQL de un procedimiento almacenado que devuelve varias formas de resultados secuencialmente:</span><span class="sxs-lookup"><span data-stu-id="b1729-108">Here is the T-SQL of a stored procedure that returns multiple result shapes sequentially:</span></span>  
  
```sql
CREATE PROCEDURE MultipleResultTypesSequentially  
AS  
select * from products  
select * from customers  
```  
  
 [!code-csharp[DLinqSprox#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#6)]
 [!code-vb[DLinqSprox#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="b1729-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1729-109">Example</span></span>  

 <span data-ttu-id="b1729-110">Usaría código similar al siguiente para ejecutar este procedimiento almacenado.</span><span class="sxs-lookup"><span data-stu-id="b1729-110">You would use code similar to the following to execute this stored procedure.</span></span>  
  
 [!code-csharp[DLinqSprox#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#7)]
 [!code-vb[DLinqSprox#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="b1729-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1729-111">See also</span></span>

- [<span data-ttu-id="b1729-112">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="b1729-112">Stored Procedures</span></span>](stored-procedures.md)
