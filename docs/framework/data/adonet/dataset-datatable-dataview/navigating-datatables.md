---
title: Navegar por objetos DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 9b7ed4ef1dbe141d8f6a1b6c6b9af2fd89e6c7af
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91148313"
---
# <a name="navigating-datatables"></a><span data-ttu-id="b9078-102">Navegar por objetos DataTable</span><span class="sxs-lookup"><span data-stu-id="b9078-102">Navigating DataTables</span></span>

<span data-ttu-id="b9078-103">El <xref:System.Data.DataTableReader> obtiene el contenido de uno o más objetos <xref:System.Data.DataTable> con formato de uno o más conjuntos de solo lectura y de solo avance.</span><span class="sxs-lookup"><span data-stu-id="b9078-103">The <xref:System.Data.DataTableReader> obtains the contents of one or more <xref:System.Data.DataTable> objects in the form of one or more read-only, forward-only result sets.</span></span>  
  
 <span data-ttu-id="b9078-104">Un <xref:System.Data.DataTableReader> puede contener varios conjuntos de resultados si se crea mediante el método <xref:System.Data.DataSet.CreateDataReader%2A>.</span><span class="sxs-lookup"><span data-stu-id="b9078-104">A <xref:System.Data.DataTableReader> may contain multiple result sets if it is created by using the <xref:System.Data.DataSet.CreateDataReader%2A> method.</span></span> <span data-ttu-id="b9078-105">Si hay más de un conjunto de resultados, el método <xref:System.Data.DataTableReader.NextResult%2A> desplaza el cursor hasta el siguiente conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b9078-105">When there is more than one result set, the <xref:System.Data.DataTableReader.NextResult%2A> method advances the cursor to the next result set.</span></span> <span data-ttu-id="b9078-106">Este proceso es de solo avance.</span><span class="sxs-lookup"><span data-stu-id="b9078-106">This is a forward-only process.</span></span> <span data-ttu-id="b9078-107">No es posible volver a un conjunto de resultados anterior.</span><span class="sxs-lookup"><span data-stu-id="b9078-107">It is not possible to return to a previous result set.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9078-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9078-108">Example</span></span>  

 <span data-ttu-id="b9078-109">En el ejemplo siguiente, el `TestConstructor` método crea dos <xref:System.Data.DataTable> instancias de.</span><span class="sxs-lookup"><span data-stu-id="b9078-109">In the following example, the `TestConstructor` method creates two <xref:System.Data.DataTable> instances.</span></span> <span data-ttu-id="b9078-110">Para mostrar este constructor para la <xref:System.Data.DataTableReader> clase, el ejemplo crea un nuevo **DataTableReader** basado en una matriz que contiene las dos **DataTables**y realiza una operación sencilla, imprimiendo el contenido de las primeras columnas en la ventana de la consola.</span><span class="sxs-lookup"><span data-stu-id="b9078-110">In order to demonstrate this constructor for the <xref:System.Data.DataTableReader> class, the sample creates a new **DataTableReader** based on an array that contains the two **DataTables**, and performs a simple operation, printing the contents from the first few columns to the console window.</span></span>  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b9078-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9078-111">See also</span></span>

- [<span data-ttu-id="b9078-112">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="b9078-112">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="b9078-113">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b9078-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
