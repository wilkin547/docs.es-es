---
description: 'Más información acerca de: objetos DataTableReader'
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: b3e85ae05c07af18fe6219602b5b40f50a9fbc8a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652606"
---
# <a name="datatablereaders"></a><span data-ttu-id="b5352-103">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="b5352-103">DataTableReaders</span></span>

<span data-ttu-id="b5352-104">El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="b5352-104">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="b5352-105">Cuando se crea un **DataTableReader** a partir de un **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como eliminadas.</span><span class="sxs-lookup"><span data-stu-id="b5352-105">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="b5352-106">Las columnas aparecen en el mismo orden que en la **DataTable** original.</span><span class="sxs-lookup"><span data-stu-id="b5352-106">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="b5352-107">Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5352-107">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="b5352-108">Los resultados están en el mismo orden que los objetos **DataTable** de la colección del objeto **DataSet** <xref:System.Data.DataSet.Tables%2A> .</span><span class="sxs-lookup"><span data-stu-id="b5352-108">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5352-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b5352-109">In This Section</span></span>  

 [<span data-ttu-id="b5352-110">Crear un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="b5352-110">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="b5352-111">Describe cómo crear un objeto **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="b5352-111">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="b5352-112">Navegar por objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="b5352-112">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="b5352-113">Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="b5352-113">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5352-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b5352-114">See also</span></span>

- [<span data-ttu-id="b5352-115">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b5352-115">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="b5352-116">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b5352-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
