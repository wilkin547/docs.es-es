---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 1ff7868b59c6fdc4e6c443be1b831accc84f36a6
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203820"
---
# <a name="datatablereaders"></a><span data-ttu-id="223ec-102">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="223ec-102">DataTableReaders</span></span>
<span data-ttu-id="223ec-103">El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="223ec-103">The <xref:System.Data.DataTableReader> presents the contents of a <xref:System.Data.DataTable> or a <xref:System.Data.DataSet> in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="223ec-104">Cuando se crea un **DataTableReader** a partir de una **DataTable**, el objeto **DataTableReader** resultante contiene un conjunto de resultados con los mismos datos que la **DataTable** desde la que se creó, excepto para las filas que se han marcado como borró.</span><span class="sxs-lookup"><span data-stu-id="223ec-104">When you create a **DataTableReader** from a **DataTable**, the resulting **DataTableReader** object contains one result set with the same data as the **DataTable** from which it was created, except for any rows that have been marked as deleted.</span></span> <span data-ttu-id="223ec-105">Las columnas aparecen en el mismo orden que en la **DataTable**original.</span><span class="sxs-lookup"><span data-stu-id="223ec-105">The columns appear in the same order as in the original **DataTable**.</span></span>  
  
 <span data-ttu-id="223ec-106">Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una <xref:System.Data.DataSet.CreateDataReader%2A>llamada a.</span><span class="sxs-lookup"><span data-stu-id="223ec-106">A **DataTableReader** may contain multiple result sets if it was created by calling <xref:System.Data.DataSet.CreateDataReader%2A>.</span></span> <span data-ttu-id="223ec-107">Los resultados están en el mismo orden que los objetos **DataTable** de la colección del <xref:System.Data.DataSet.Tables%2A> objeto DataSet.</span><span class="sxs-lookup"><span data-stu-id="223ec-107">The results are in the same order as the **DataTables** in the **DataSet** object's <xref:System.Data.DataSet.Tables%2A> collection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="223ec-108">En esta sección</span><span class="sxs-lookup"><span data-stu-id="223ec-108">In This Section</span></span>  
 [<span data-ttu-id="223ec-109">Creación de un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="223ec-109">Creating a DataReader</span></span>](creating-a-datareader.md)  
 <span data-ttu-id="223ec-110">Describe cómo crear un objeto **DataTableReader** .</span><span class="sxs-lookup"><span data-stu-id="223ec-110">Discusses how to create a **DataTableReader** object.</span></span>  
  
 [<span data-ttu-id="223ec-111">Navegación por objetos DataTables</span><span class="sxs-lookup"><span data-stu-id="223ec-111">Navigating DataTables</span></span>](navigating-datatables.md)  
 <span data-ttu-id="223ec-112">Describe el uso del método **Read** para desplazarse por el contenido de un **DataTableReader**.</span><span class="sxs-lookup"><span data-stu-id="223ec-112">Describes the use of the **Read** method to move through the contents of a **DataTableReader**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="223ec-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="223ec-113">See also</span></span>

- [<span data-ttu-id="223ec-114">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="223ec-114">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="223ec-115">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="223ec-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
