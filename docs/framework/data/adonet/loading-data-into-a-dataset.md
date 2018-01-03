---
title: Cargar datos en un conjunto de datos
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 471a13b5d209def227bf8bc57b1551550b76a0c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="194a2-102">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="194a2-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="194a2-103">Un objeto <xref:System.Data.DataSet> se debe rellenar primero antes de poderlo consultar con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="194a2-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="194a2-104">Existen varias formas de rellenar <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="194a2-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="194a2-105">Por ejemplo, puede usar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en la <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="194a2-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="194a2-106">Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="194a2-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="194a2-107">Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="194a2-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="194a2-108">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="194a2-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="194a2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="194a2-109">Example</span></span>  
 <span data-ttu-id="194a2-110">En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="194a2-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="194a2-111">Una vez que se ha rellenado <xref:System.Data.DataSet>, se pueden escribir consultas en él mediante [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="194a2-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="194a2-112">El `FillDataSet` método en este ejemplo se utiliza en las consultas de ejemplo de [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="194a2-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="194a2-113">Para obtener más información, consulte [consultar conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="194a2-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="194a2-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="194a2-114">See Also</span></span>  
 [<span data-ttu-id="194a2-115">Información general de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="194a2-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)  
 [<span data-ttu-id="194a2-116">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="194a2-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)  
 [<span data-ttu-id="194a2-117">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="194a2-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
