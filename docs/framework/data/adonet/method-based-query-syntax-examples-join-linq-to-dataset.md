---
title: 'Ejemplos de sintaxis de consulta basada en métodos: Join (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: ba6e33f98e063aab946db27b97106272c5adef63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783672"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="af5e3-102">Ejemplos de sintaxis de consulta basada en métodos: Join (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="af5e3-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="af5e3-103">La combinación es una operación importante de las consultas dirigidas a orígenes de datos que no tienen relaciones navegables entre ellos, como las tablas de bases de datos relacionales.</span><span class="sxs-lookup"><span data-stu-id="af5e3-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="af5e3-104">Una combinación de dos orígenes de datos es la asociación de objetos en un origen de datos con objetos que comparten un atributo común en el otro origen de datos.</span><span class="sxs-lookup"><span data-stu-id="af5e3-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="af5e3-105">Para obtener más información, vea información general [sobre operadoresC#de consulta estándar ()](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) o [información general sobre operadores de consulta estándar (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span><span class="sxs-lookup"><span data-stu-id="af5e3-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="af5e3-106">Los ejemplos de este tema muestran cómo usar el método<xref:System.Linq.Enumerable.Join%2A> para consultar <xref:System.Data.DataSet> usando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="af5e3-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="af5e3-107">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="af5e3-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="af5e3-108">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="af5e3-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="af5e3-109">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="af5e3-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="af5e3-110">Para obtener más información, consulte [Cómo Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="af5e3-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="af5e3-111">Unir</span><span class="sxs-lookup"><span data-stu-id="af5e3-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="af5e3-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af5e3-112">Example</span></span>  
 <span data-ttu-id="af5e3-113">En este ejemplo se realiza una combinación en las tablas `Contact` y `SalesOrderHeader`.</span><span class="sxs-lookup"><span data-stu-id="af5e3-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="af5e3-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af5e3-114">Example</span></span>  
 <span data-ttu-id="af5e3-115">En este ejemplo se realiza una combinación en las tablas `Contact` y `SalesOrderHeader`, agrupando los resultados por id. de contacto.</span><span class="sxs-lookup"><span data-stu-id="af5e3-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="af5e3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="af5e3-116">See also</span></span>

- [<span data-ttu-id="af5e3-117">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="af5e3-117">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="af5e3-118">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="af5e3-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- <span data-ttu-id="af5e3-119">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="af5e3-119">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="af5e3-120">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="af5e3-120">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="af5e3-121">Ejemplos de combinación</span><span class="sxs-lookup"><span data-stu-id="af5e3-121">Join Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187357)
- [<span data-ttu-id="af5e3-122">Ejemplos de conjuntos de DataSet</span><span class="sxs-lookup"><span data-stu-id="af5e3-122">Dataset Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187358)
