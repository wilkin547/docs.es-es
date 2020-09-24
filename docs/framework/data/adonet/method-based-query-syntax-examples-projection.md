---
title: 'Ejemplos de sintaxis de consultas basadas en métodos: Proyección (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0fc2c8f0-1967-4f30-8b20-39b8dccfb82f
ms.openlocfilehash: 2790ed3e7f8fc2fe6a5c920be8a79402692d6282
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147910"
---
# <a name="method-based-query-syntax-examples-projection-linq-to-dataset"></a><span data-ttu-id="ce520-102">Ejemplos de sintaxis de consultas basadas en métodos: Proyección (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="ce520-102">Method-Based Query Syntax Examples: Projection (LINQ to DataSet)</span></span>

<span data-ttu-id="ce520-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Select%2A> y <xref:System.Linq.Enumerable.SelectMany%2A> para consultar <xref:System.Data.DataSet> usando la sintaxis de consulta basada en métodos.</span><span class="sxs-lookup"><span data-stu-id="ce520-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the method-based query syntax.</span></span>  
  
 <span data-ttu-id="ce520-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="ce520-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="ce520-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="ce520-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="ce520-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="ce520-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="ce520-107">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="ce520-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="ce520-108">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="ce520-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="ce520-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce520-109">Example</span></span>  

 <span data-ttu-id="ce520-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Select%2A> para proyectar las propiedades `Name`, `ProductNumber` y `ListPrice` en una secuencia de tipos anónimos.</span><span class="sxs-lookup"><span data-stu-id="ce520-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to project the `Name`, `ProductNumber`, and `ListPrice` properties to a sequence of anonymous types.</span></span>  <span data-ttu-id="ce520-111">El nombre de la propiedad `ListPrice` se cambia a `Price` en el tipo resultante.</span><span class="sxs-lookup"><span data-stu-id="ce520-111">The `ListPrice` property is also renamed to `Price` in the resulting type.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectAnonymousTypes_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="ce520-112">SelectMany</span><span class="sxs-lookup"><span data-stu-id="ce520-112">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="ce520-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce520-113">Example</span></span>  

 <span data-ttu-id="ce520-114">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.SelectMany%2A> para seleccionar todos los pedidos en los que `TotalDue` es inferior a 500,00.</span><span class="sxs-lookup"><span data-stu-id="ce520-114">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="ce520-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ce520-115">Example</span></span>  

 <span data-ttu-id="ce520-116">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.SelectMany%2A> para seleccionar todos los pedidos efectuados a partir del 1 de octubre.</span><span class="sxs-lookup"><span data-stu-id="ce520-116">This example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="ce520-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce520-117">See also</span></span>

- [<span data-ttu-id="ce520-118">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="ce520-118">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="ce520-119">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="ce520-119">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="ce520-120">Información general sobre operadores de consulta estándar (C#)</span><span class="sxs-lookup"><span data-stu-id="ce520-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="ce520-121">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce520-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
