---
description: 'Más información acerca de: ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)'
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: c405f111ce4461f246782283fe39146092fce424
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663617"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="39a9f-103">Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="39a9f-103">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="39a9f-104">La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="39a9f-104">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="39a9f-105">Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="39a9f-105">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="39a9f-106">Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="39a9f-106">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="39a9f-107">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="39a9f-107">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="39a9f-108">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="39a9f-108">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="39a9f-109">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="39a9f-109">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="39a9f-110">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="39a9f-110">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="39a9f-111">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="39a9f-111">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="39a9f-112">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="39a9f-112">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="39a9f-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39a9f-113">Example</span></span>  

 <span data-ttu-id="39a9f-114">Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `SalesOrderHeader` y `SalesOrderDetail` para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="39a9f-114">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="39a9f-115">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="39a9f-115">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="39a9f-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39a9f-116">Example</span></span>  

 <span data-ttu-id="39a9f-117">Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `Contact` y `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="39a9f-117">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="39a9f-118">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="39a9f-118">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="39a9f-119">Join</span><span class="sxs-lookup"><span data-stu-id="39a9f-119">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="39a9f-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="39a9f-120">Example</span></span>  

 <span data-ttu-id="39a9f-121">Este ejemplo realiza una combinación en las tablas `SalesOrderHeader` y `SalesOrderDetail` para obtener pedidos en línea del mes de agosto.</span><span class="sxs-lookup"><span data-stu-id="39a9f-121">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="39a9f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="39a9f-122">See also</span></span>

- [<span data-ttu-id="39a9f-123">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="39a9f-123">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="39a9f-124">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="39a9f-124">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="39a9f-125">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="39a9f-125">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="39a9f-126">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39a9f-126">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
