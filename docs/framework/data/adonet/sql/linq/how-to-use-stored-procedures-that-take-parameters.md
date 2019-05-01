---
title: Procedimiento para usar procedimientos almacenados que toman parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: 8dd463c895efcddfe288fe1dc8571981872d9d80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033618"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="2cd74-102">Procedimiento para usar procedimientos almacenados que toman parámetros</span><span class="sxs-lookup"><span data-stu-id="2cd74-102">How to: Use Stored Procedures that Take Parameters</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="2cd74-103">asigna los parámetros de salida a parámetros de referencia y, para los tipos de valor, declara el parámetro como que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="2cd74-103">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="2cd74-104">Para obtener un ejemplo de cómo usar un parámetro de entrada en una consulta que devuelve un conjunto de filas, vea [Cómo: Devolver conjuntos de filas](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="2cd74-104">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cd74-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd74-105">Example</span></span>  
 <span data-ttu-id="2cd74-106">En el ejemplo siguiente se utiliza un parámetro de entrada único (el identificador de cliente) y se devuelve un parámetro de salida (las ventas totales para ese cliente).</span><span class="sxs-lookup"><span data-stu-id="2cd74-106">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```  
CREATE PROCEDURE [dbo].[CustOrderTotal]   
@CustomerID nchar(5),  
@TotalSales money OUTPUT  
AS  
SELECT @TotalSales = SUM(OD.UNITPRICE*(1-OD.DISCOUNT) * OD.QUANTITY)  
FROM ORDERS O, "ORDER DETAILS" OD  
where O.CUSTOMERID = @CustomerID AND O.ORDERID = OD.ORDERID  
```  
  
 [!code-csharp[DLinqSprox#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/northwind-sprox.cs#2)]
 [!code-vb[DLinqSprox#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/northwind-sprox.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="2cd74-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd74-107">Example</span></span>  
 <span data-ttu-id="2cd74-108">La llamada a este procedimiento almacenado sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="2cd74-108">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="2cd74-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="2cd74-109">See also</span></span>

- [<span data-ttu-id="2cd74-110">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="2cd74-110">Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md)
- [<span data-ttu-id="2cd74-111">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="2cd74-111">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [<span data-ttu-id="2cd74-112">Utilizar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="2cd74-112">Using Nullable Types</span></span>](~/docs/csharp/programming-guide/nullable-types/using-nullable-types.md)
- [<span data-ttu-id="2cd74-113">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="2cd74-113">Nullable Value Types</span></span>](~/docs/visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
