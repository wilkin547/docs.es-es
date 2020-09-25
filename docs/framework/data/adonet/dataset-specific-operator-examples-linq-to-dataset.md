---
title: Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 4cd99a103fabee3c87036a9933077a3a967f5a13
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173697"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="87a65-102">Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="87a65-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="87a65-103">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> y la clase <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="87a65-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="87a65-104">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="87a65-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="87a65-105">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="87a65-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="87a65-106">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="87a65-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="87a65-107">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="87a65-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="87a65-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="87a65-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="87a65-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87a65-109">Example</span></span>  

 <span data-ttu-id="87a65-110">En este ejemplo se carga un <xref:System.Data.DataTable> con resultados de consulta utilizando el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="87a65-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="87a65-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="87a65-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="87a65-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87a65-112">Example</span></span>  

 <span data-ttu-id="87a65-113">En este ejemplo se comparan dos filas distintas de datos utilizando <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="87a65-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="87a65-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87a65-114">See also</span></span>

- [<span data-ttu-id="87a65-115">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="87a65-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="87a65-116">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="87a65-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
