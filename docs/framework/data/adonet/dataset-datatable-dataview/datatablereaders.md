---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 911a45dad3d5d82ab5e5752b1c12f7d8a6ab1563
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202323"
---
# <a name="datatablereaders"></a><span data-ttu-id="134d1-102">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="134d1-102">DataTableReaders</span></span>

<span data-ttu-id="134d1-103">El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="134d1-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="134d1-104">Cuando se crea un **DataTableReader** a partir de un **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como eliminadas.</span><span class="sxs-lookup"><span data-stu-id="134d1-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="134d1-105">Las columnas aparecen en el mismo orden que en la **DataTable**original.</span><span class="sxs-lookup"><span data-stu-id="134d1-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="134d1-106">Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A> .</span><span class="sxs-lookup"><span data-stu-id="134d1-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="134d1-107">Los resultados están en el mismo orden que los objetos **DataTable** de la colección del objeto **DataSet** <xref:System.Data.DataSet.Tables%2A> .</span><span class="sxs-lookup"><span data-stu-id="134d1-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="134d1-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="134d1-108">In This Section</span></span>  

 [<span data-ttu-id="134d1-109">Crear un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="134d1-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="134d1-110">Describe cómo crear un objeto **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="134d1-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="134d1-111">Navegar por objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="134d1-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="134d1-112">Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="134d1-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="134d1-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="134d1-113">See also</span></span>

- [<span data-ttu-id="134d1-114">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="134d1-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="134d1-115">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="134d1-115">ADO.NET Overview</span></span>](../ado-net-overview.md)
