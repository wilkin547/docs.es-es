---
title: 'Ejemplos de sintaxis de expresiones de consulta: Creación de particiones (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: beb5f361-1ac8-44fb-afa1-2aacea15f166
ms.openlocfilehash: 6a00c5d49acc02c476895c999687aa944ba26aff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795098"
---
# <a name="query-expression-syntax-examples-partitioning-linq-to-dataset"></a><span data-ttu-id="a8207-102">Ejemplos de sintaxis de expresiones de consulta: Creación de particiones (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="a8207-102">Query Expression Syntax Examples: Partitioning (LINQ to DataSet)</span></span>
<span data-ttu-id="a8207-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.Skip%2A> y <xref:System.Linq.Enumerable.Take%2A> para consultar un <xref:System.Data.DataSet> usando la sintaxis de expresión de consultas.</span><span class="sxs-lookup"><span data-stu-id="a8207-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="a8207-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="a8207-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="a8207-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="a8207-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="a8207-106">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a8207-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="a8207-107">Para obtener más información, consulte [Cómo Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="a8207-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="a8207-108">Skip</span><span class="sxs-lookup"><span data-stu-id="a8207-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="a8207-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8207-109">Example</span></span>  
 <span data-ttu-id="a8207-110">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Skip%2A> para obtener las dos primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="a8207-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="a8207-111">Take</span><span class="sxs-lookup"><span data-stu-id="a8207-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="a8207-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8207-112">Example</span></span>  
 <span data-ttu-id="a8207-113">En este ejemplo se utiliza el método <xref:System.Linq.Enumerable.Take%2A> para obtener las tres primeras direcciones de Seattle.</span><span class="sxs-lookup"><span data-stu-id="a8207-113">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="a8207-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8207-114">See also</span></span>

- [<span data-ttu-id="a8207-115">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="a8207-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="a8207-116">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="a8207-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- <span data-ttu-id="a8207-117">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="a8207-117">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="a8207-118">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a8207-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
