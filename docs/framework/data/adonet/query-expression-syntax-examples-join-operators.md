---
title: 'Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: 637b815553d7c7f9a5fb4ffe644d2975468e1090
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189102"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="f4e94-102">Ejemplos de sintaxis de expresiones de consulta: operadores de combinación (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="f4e94-102">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="f4e94-103">La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="f4e94-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="f4e94-104">Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f4e94-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="f4e94-105">Para obtener más información, vea información general sobre [operadores de consulta estándar (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f4e94-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="f4e94-106">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.GroupJoin%2A> y <xref:System.Linq.Enumerable.Join%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="f4e94-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="f4e94-107">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="f4e94-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="f4e94-108">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="f4e94-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f4e94-109">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="f4e94-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="f4e94-110">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f4e94-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="f4e94-111">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="f4e94-111">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="f4e94-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4e94-112">Example</span></span>  

 <span data-ttu-id="f4e94-113">Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `SalesOrderHeader` y `SalesOrderDetail` para buscar el número de pedidos por cliente.</span><span class="sxs-lookup"><span data-stu-id="f4e94-113">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="f4e94-114">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f4e94-114">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="f4e94-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4e94-115">Example</span></span>  

 <span data-ttu-id="f4e94-116">Este ejemplo realiza un <xref:System.Linq.Enumerable.GroupJoin%2A> en las tablas `Contact` y `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="f4e94-116">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="f4e94-117">Una combinación de grupo es el equivalente a una combinación externa izquierda, que devuelve cada elemento del primer origen de datos (izquierdo), incluso si no hay elementos correlacionados en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="f4e94-117">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="f4e94-118">Join</span><span class="sxs-lookup"><span data-stu-id="f4e94-118">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="f4e94-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f4e94-119">Example</span></span>  

 <span data-ttu-id="f4e94-120">Este ejemplo realiza una combinación en las tablas `SalesOrderHeader` y `SalesOrderDetail` para obtener pedidos en línea del mes de agosto.</span><span class="sxs-lookup"><span data-stu-id="f4e94-120">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="f4e94-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4e94-121">See also</span></span>

- [<span data-ttu-id="f4e94-122">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="f4e94-122">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="f4e94-123">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="f4e94-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="f4e94-124">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="f4e94-124">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="f4e94-125">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4e94-125">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
