---
title: Cargar datos en un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166721"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="2e20c-102">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="2e20c-102">Loading Data Into a DataSet</span></span>

<span data-ttu-id="2e20c-103"><xref:System.Data.DataSet>Primero se debe rellenar un objeto para poder realizar consultas sobre él con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="2e20c-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="2e20c-104">Existen varias formas de rellenar <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="2e20c-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2e20c-105">Por ejemplo, puede utilizar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="2e20c-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2e20c-106">Para más información, vea [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="2e20c-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="2e20c-107">Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="2e20c-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="2e20c-108">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e20c-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e20c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2e20c-109">Example</span></span>  

 <span data-ttu-id="2e20c-110">En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="2e20c-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2e20c-111">Una vez que se ha <xref:System.Data.DataSet> rellenado, puede escribir consultas en él mediante LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="2e20c-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="2e20c-112">El `FillDataSet` método de este ejemplo se usa en las consultas de ejemplo de [LINQ to DataSet ejemplos](linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="2e20c-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="2e20c-113">Para obtener más información, vea [consultar conjuntos](querying-datasets-linq-to-dataset.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="2e20c-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="2e20c-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2e20c-114">See also</span></span>

- [<span data-ttu-id="2e20c-115">Información general de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2e20c-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="2e20c-116">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="2e20c-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="2e20c-117">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="2e20c-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
