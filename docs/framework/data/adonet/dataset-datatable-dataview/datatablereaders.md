---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: a790335a25327563e3dab6093449345b99afd048
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214006"
---
# <a name="datatablereaders"></a><span data-ttu-id="7ca03-102">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="7ca03-102">DataTableReaders</span></span>
<span data-ttu-id="7ca03-103">El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="7ca03-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="7ca03-104">Cuando creas un **DataTableReader** desde un **DataTable**, resultante **DataTableReader** objeto contiene un conjunto de resultados con los mismos datos que el  **DataTable** desde que se creó, excepto para las filas que se han marcado como eliminado.</span><span class="sxs-lookup"><span data-stu-id="7ca03-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="7ca03-105">Las columnas aparecen en el mismo orden que en el original **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="7ca03-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="7ca03-106">Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="7ca03-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="7ca03-107">Los resultados están en el mismo orden que el **DataTables** en el **DataSet** del objeto <xref:System.Data.DataSet.Tables%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="7ca03-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7ca03-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="7ca03-108">In This Section</span></span>  
 [<span data-ttu-id="7ca03-109">Crear un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="7ca03-109">Creating a DataReader</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 <span data-ttu-id="7ca03-110">Describe cómo crear un **DataTableReader** objeto.</span><span class="sxs-lookup"><span data-stu-id="7ca03-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="7ca03-111">Navegar por objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="7ca03-111">Navigating DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 <span data-ttu-id="7ca03-112">Describe el uso de la **lectura** método para desplazarse por el contenido de un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="7ca03-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ca03-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ca03-113">See also</span></span>

- [<span data-ttu-id="7ca03-114">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7ca03-114">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="7ca03-115">Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="7ca03-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
