---
description: Más información sobre cómo cargar datos en un conjunto de datos
title: Cargar datos en un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 167a399d17257008e884fbcccc96de17398b8f88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681687"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="0fe88-103">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="0fe88-103">Loading Data Into a DataSet</span></span>

<span data-ttu-id="0fe88-104"><xref:System.Data.DataSet>Primero se debe rellenar un objeto para poder realizar consultas sobre él con LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="0fe88-104">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="0fe88-105">Existen varias formas de rellenar <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0fe88-105">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0fe88-106">Por ejemplo, puede utilizar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="0fe88-106">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0fe88-107">Para más información, vea [LINQ to SQL](./sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="0fe88-107">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="0fe88-108">Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fe88-108">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="0fe88-109">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0fe88-109">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0fe88-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0fe88-110">Example</span></span>  

 <span data-ttu-id="0fe88-111">En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="0fe88-111">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="0fe88-112">Una vez que se ha <xref:System.Data.DataSet> rellenado, puede escribir consultas en él mediante LINQ to DataSet.</span><span class="sxs-lookup"><span data-stu-id="0fe88-112">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="0fe88-113">El `FillDataSet` método de este ejemplo se usa en las consultas de ejemplo de [LINQ to DataSet ejemplos](linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="0fe88-113">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="0fe88-114">Para obtener más información, vea [consultar conjuntos](querying-datasets-linq-to-dataset.md)de datos.</span><span class="sxs-lookup"><span data-stu-id="0fe88-114">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="0fe88-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fe88-115">See also</span></span>

- [<span data-ttu-id="0fe88-116">Información general de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0fe88-116">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="0fe88-117">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="0fe88-117">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="0fe88-118">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="0fe88-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
