---
description: 'Más información acerca de cómo: usar procedimientos almacenados que toman parámetros'
title: Procedimiento para usar procedimientos almacenados que toman parámetros
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b935fd84-cb9c-4205-8c48-658d5db2ec93
ms.openlocfilehash: eaa2e9c602e2e6baae82648a4237d1098e89896a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785801"
---
# <a name="how-to-use-stored-procedures-that-take-parameters"></a><span data-ttu-id="3a930-103">Procedimiento para usar procedimientos almacenados que toman parámetros</span><span class="sxs-lookup"><span data-stu-id="3a930-103">How to: Use Stored Procedures that Take Parameters</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="3a930-104">asigna los parámetros de salida a parámetros de referencia y, para los tipos de valor, declara el parámetro como que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="3a930-104">maps output parameters to reference parameters, and for value types declares the parameter as nullable.</span></span>  
  
 <span data-ttu-id="3a930-105">Para obtener un ejemplo de cómo usar un parámetro de entrada en una consulta que devuelve un conjunto de filas, vea [Cómo: devolver conjuntos de filas](how-to-return-rowsets.md).</span><span class="sxs-lookup"><span data-stu-id="3a930-105">For an example of how to use an input parameter in a query that returns a rowset, see [How to: Return Rowsets](how-to-return-rowsets.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a930-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a930-106">Example</span></span>  

 <span data-ttu-id="3a930-107">En el ejemplo siguiente se utiliza un parámetro de entrada único (el identificador de cliente) y se devuelve un parámetro de salida (las ventas totales para ese cliente).</span><span class="sxs-lookup"><span data-stu-id="3a930-107">The following example takes a single input parameter (the customer ID) and returns an out parameter (the total sales for that customer).</span></span>  
  
```sql
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
  
## <a name="example"></a><span data-ttu-id="3a930-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a930-108">Example</span></span>  

 <span data-ttu-id="3a930-109">La llamada a este procedimiento almacenado sería como sigue:</span><span class="sxs-lookup"><span data-stu-id="3a930-109">You would call this stored procedure as follows:</span></span>  
  
 [!code-csharp[DLinqSprox#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSprox/cs/Program.cs#3)]
 [!code-vb[DLinqSprox#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSprox/vb/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="3a930-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a930-110">See also</span></span>

- [<span data-ttu-id="3a930-111">Procedimientos almacenados</span><span class="sxs-lookup"><span data-stu-id="3a930-111">Stored Procedures</span></span>](stored-procedures.md)
- [<span data-ttu-id="3a930-112">Descargar bases de datos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a930-112">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="3a930-113">Tipos de valor que aceptan valores NULL (C#)</span><span class="sxs-lookup"><span data-stu-id="3a930-113">Nullable Value Types (C#)</span></span>](../../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
- [<span data-ttu-id="3a930-114">Tipos que admiten valores null (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3a930-114">Nullable Value Types (Visual Basic)</span></span>](../../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
