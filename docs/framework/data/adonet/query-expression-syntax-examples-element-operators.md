---
title: 'Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ca392dda-16e3-45c7-8d87-12d8d4ee0578
ms.openlocfilehash: ae29ed3d61489b9da24a34e2e99ee32bd67c6d5c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783031"
---
# <a name="query-expression-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="66f7d-102">Ejemplos de sintaxis de expresiones de consulta: Operadores de elementos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="66f7d-102">Query Expression Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="66f7d-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Linq.Enumerable.First%2A> y <xref:System.Linq.Enumerable.ElementAt%2A> para obtener elementos <xref:System.Data.DataRow> de un <xref:System.Data.DataSet> usando la sintaxis de expresiones de consulta.</span><span class="sxs-lookup"><span data-stu-id="66f7d-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="66f7d-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="66f7d-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="66f7d-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="66f7d-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="66f7d-106">En los ejemplos de este tema se usan `using` las siguientes / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="66f7d-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="66f7d-107">Para obtener más información, vea [Cómo: Cree un proyecto de LINQ to DataSet en Visual](how-to-create-a-linq-to-dataset-project-in-vs.md)Studio.</span><span class="sxs-lookup"><span data-stu-id="66f7d-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="66f7d-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="66f7d-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="66f7d-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66f7d-109">Example</span></span>  
 <span data-ttu-id="66f7d-110">Este ejemplo usa el método <xref:System.Linq.Enumerable.ElementAt%2A> para recuperar la quinta dirección donde `PostalCode` == "M4B 1V7".</span><span class="sxs-lookup"><span data-stu-id="66f7d-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
 [!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]  
  
## <a name="first"></a><span data-ttu-id="66f7d-111">Primero</span><span class="sxs-lookup"><span data-stu-id="66f7d-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="66f7d-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66f7d-112">Example</span></span>  
 <span data-ttu-id="66f7d-113">Este ejemplo usar el método <xref:System.Linq.Enumerable.First%2A> para devolver el primer contacto cuyo nombre es 'Brooke'.</span><span class="sxs-lookup"><span data-stu-id="66f7d-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="66f7d-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="66f7d-114">See also</span></span>

- [<span data-ttu-id="66f7d-115">Carga de datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="66f7d-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="66f7d-116">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="66f7d-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- <span data-ttu-id="66f7d-117">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) (Información general sobre operadores de consulta estándar (C#))</span><span class="sxs-lookup"><span data-stu-id="66f7d-117">[Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)</span></span>
- [<span data-ttu-id="66f7d-118">Información general sobre operadores de consulta estándar (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66f7d-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
