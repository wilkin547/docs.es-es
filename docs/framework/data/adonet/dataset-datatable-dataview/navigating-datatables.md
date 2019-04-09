---
title: Navegar por objetos DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 91db42acb0e09b8fc99b0ee710a60800d40938ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59112858"
---
# <a name="navigating-datatables"></a><span data-ttu-id="56530-102">Navegar por objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="56530-102">Navigating DataTables</span></span>
<span data-ttu-id="56530-103">El <xref:System.Data.DataTableReader> obtiene el contenido de uno o más objetos <xref:System.Data.DataTable> con formato de uno o más conjuntos de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="56530-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="56530-104">Un <xref:System.Data.DataTableReader> puede contener varios conjuntos de resultados si se crea mediante el método <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="56530-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="56530-105">Si hay más de un conjunto de resultados, el método <xref:System.Data.DataTableReader.NextResult%2A> desplaza el cursor hasta el siguiente conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="56530-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="56530-106">Este proceso es de solo avance.</span><span class="sxs-lookup"><span data-stu-id="56530-106">This is a forward-only process.</span></span> <span data-ttu-id="56530-107">No es posible volver a un conjunto de resultados anterior.</span><span class="sxs-lookup"><span data-stu-id="56530-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56530-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="56530-108">Example</span></span>  
 <span data-ttu-id="56530-109">En el ejemplo siguiente, la `TestConstructor` método crea dos <xref:System.Data.DataTable> instancias.</span><span class="sxs-lookup"><span data-stu-id="56530-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="56530-110">Para mostrar este constructor para la <xref:System.Data.DataTableReader> (clase), el ejemplo se crea un nuevo **DataTableReader** basándose en una matriz que contiene los dos **DataTables**y realiza una operación sencilla, Imprime el contenido de las primeras columnas en la ventana de consola.</span><span class="sxs-lookup"><span data-stu-id="56530-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="56530-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="56530-111">See also</span></span>

- [<span data-ttu-id="56530-112">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="56530-112">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)
- [<span data-ttu-id="56530-113">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="56530-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
