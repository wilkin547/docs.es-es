---
description: 'Más información sobre: ejemplos de operadores de DataSet-Specific (LINQ to DataSet)'
title: Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 2fd54453621ce180901aaf6fbb5b975067ad9831
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651332"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="d86a7-103">Ejemplos de operadores específicos de conjuntos de datos (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="d86a7-103">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="d86a7-104">Los ejemplos de este tema muestran cómo usar los métodos <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> y la clase <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="d86a7-104">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="d86a7-105">El `FillDataSet` método utilizado en estos ejemplos se especifica en [cargar datos en un conjunto de datos](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="d86a7-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="d86a7-106">Los ejemplos de este tema utilizan las tablas Contact, Address, Product, SalesOrderHeader y SalesOrderDetail en la base de datos de ejemplo de AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d86a7-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="d86a7-107">En los ejemplos de este tema se usan las siguientes `using` / `Imports` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="d86a7-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="d86a7-108">Para obtener más información, vea [Cómo: crear un proyecto de LINQ to DataSet en Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d86a7-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="d86a7-109">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="d86a7-109">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="d86a7-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d86a7-110">Example</span></span>  

 <span data-ttu-id="d86a7-111">En este ejemplo se carga un <xref:System.Data.DataTable> con resultados de consulta utilizando el método <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>.</span><span class="sxs-lookup"><span data-stu-id="d86a7-111">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="d86a7-112">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="d86a7-112">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="d86a7-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d86a7-113">Example</span></span>  

 <span data-ttu-id="d86a7-114">En este ejemplo se comparan dos filas distintas de datos utilizando <xref:System.Data.DataRowComparer>.</span><span class="sxs-lookup"><span data-stu-id="d86a7-114">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="d86a7-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d86a7-115">See also</span></span>

- [<span data-ttu-id="d86a7-116">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="d86a7-116">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="d86a7-117">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="d86a7-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
