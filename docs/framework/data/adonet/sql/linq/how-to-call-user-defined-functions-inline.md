---
title: Procedimiento para llamar a funciones alineadas definidas por el usuario
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f80d4327-b6a5-4aa8-a743-e95d09a2a02e
ms.openlocfilehash: e9808856543e20b8904be812b15b32154eab56e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782109"
---
# <a name="how-to-call-user-defined-functions-inline"></a><span data-ttu-id="b9d23-102">Procedimiento para llamar a funciones alineadas definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="b9d23-102">How to: Call User-Defined Functions Inline</span></span>
<span data-ttu-id="b9d23-103">Aunque se puede llamar a funciones alineadas definidas por el usuario, las funciones que se incluyen en una consulta cuya ejecución está diferida no se ejecutan hasta que se ejecute la consulta.</span><span class="sxs-lookup"><span data-stu-id="b9d23-103">Although you can call user-defined functions inline, functions that are included in a query whose execution is deferred are not executed until the query is executed.</span></span> <span data-ttu-id="b9d23-104">Para obtener más información, vea [Introduction to LINQ queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md) [Introducción a las consultas LINQ (C#)].</span><span class="sxs-lookup"><span data-stu-id="b9d23-104">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="b9d23-105">Al llamar a la misma función fuera de una consulta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] crea una consulta simple a partir de la expresión de llamada al método.</span><span class="sxs-lookup"><span data-stu-id="b9d23-105">When you call the same function outside a query, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates a simple query from the method call expression.</span></span> <span data-ttu-id="b9d23-106">A continuación se muestra la sintaxis de SQL (el parámetro `@p0` se enlaza a la constante pasada):</span><span class="sxs-lookup"><span data-stu-id="b9d23-106">The following is the SQL syntax (the parameter `@p0` is bound to the constant passed in):</span></span>  
  
```  
SELECT dbo.ReverseCustName(@p0)  
```  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="b9d23-107">crea lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9d23-107">creates the following:</span></span>  
  
 [!code-csharp[DLinqUDFS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#4)]
 [!code-vb[DLinqUDFS#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="b9d23-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9d23-108">Example</span></span>  
 <span data-ttu-id="b9d23-109">En la consulta [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] siguiente, puede ver una llamada insertada al método `ReverseCustName`de función definida por el usuario generado.</span><span class="sxs-lookup"><span data-stu-id="b9d23-109">In the following [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query, you can see an inline call to the generated user-defined function method `ReverseCustName`.</span></span> <span data-ttu-id="b9d23-110">La función no se ejecuta inmediatamente, porque la ejecución de la consulta está diferida.</span><span class="sxs-lookup"><span data-stu-id="b9d23-110">The function is not executed immediately because query execution is deferred.</span></span> <span data-ttu-id="b9d23-111">El código SQL compilado para esta consulta realiza la conversión a una llamada a la función definida por el usuario en la base de datos (vea el código SQL que se encuentra después de la consulta).</span><span class="sxs-lookup"><span data-stu-id="b9d23-111">The SQL built for this query translates to a call to the user-defined function in the database (see the SQL code following the query).</span></span>  
  
 [!code-csharp[DLinqUDFS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqUDFS/cs/Program.cs#5)]
 [!code-vb[DLinqUDFS#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqUDFS/vb/Module1.vb#5)]  
  
```  
SELECT [t0].[ContactName],  
    dbo.ReverseCustName([t0].[ContactTitle]) AS [Title]  
FROM [Customers] AS [t0]  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9d23-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9d23-112">See also</span></span>

- [<span data-ttu-id="b9d23-113">Funciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="b9d23-113">User-Defined Functions</span></span>](user-defined-functions.md)
