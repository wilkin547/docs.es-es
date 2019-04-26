---
title: Cargar datos en un conjunto de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: cb5578d790e5d3f54f75f964bb3288d861c9d7c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61878545"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="df0b9-102">Cargar datos en un conjunto de datos</span><span class="sxs-lookup"><span data-stu-id="df0b9-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="df0b9-103">Un objeto <xref:System.Data.DataSet> se debe rellenar primero antes de poderlo consultar con [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df0b9-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="df0b9-104">Existen varias formas de rellenar <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="df0b9-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="df0b9-105">Por ejemplo, puede usar [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] para consultar la base de datos y cargar los resultados en el <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="df0b9-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="df0b9-106">Para más información, vea [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span><span class="sxs-lookup"><span data-stu-id="df0b9-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="df0b9-107">Otra forma habitual de cargar datos en <xref:System.Data.DataSet> es utilizar la clase <xref:System.Data.Common.DataAdapter> para recuperar datos desde la base de datos.</span><span class="sxs-lookup"><span data-stu-id="df0b9-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="df0b9-108">Esto se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="df0b9-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df0b9-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="df0b9-109">Example</span></span>  
 <span data-ttu-id="df0b9-110">En este ejemplo se utiliza <xref:System.Data.Common.DataAdapter> para consultar en la base de datos AdventureWorks la información de ventas del año 2002, y cargar los resultados en un <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="df0b9-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="df0b9-111">Una vez que se ha rellenado <xref:System.Data.DataSet>, se pueden escribir consultas en él mediante [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span><span class="sxs-lookup"><span data-stu-id="df0b9-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)].</span></span> <span data-ttu-id="df0b9-112">El `FillDataSet` método en este ejemplo se utiliza en las consultas de ejemplo en [conjunto de datos de ejemplos de LINQ to](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span><span class="sxs-lookup"><span data-stu-id="df0b9-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="df0b9-113">Para obtener más información, consulte [consultar conjuntos de datos](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="df0b9-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="df0b9-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="df0b9-114">See also</span></span>

- [<span data-ttu-id="df0b9-115">Información general de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="df0b9-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="df0b9-116">Consulta de conjuntos de datos</span><span class="sxs-lookup"><span data-stu-id="df0b9-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="df0b9-117">Ejemplos de LINQ to DataSet</span><span class="sxs-lookup"><span data-stu-id="df0b9-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
