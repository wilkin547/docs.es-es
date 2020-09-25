---
title: Crear un objeto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: 3af6ae3a8f4ecc3ec34c186ce55c1c77c27514a9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202337"
---
# <a name="creating-a-datareader"></a><span data-ttu-id="d81c9-102">Crear un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="d81c9-102">Creating a DataReader</span></span>

<span data-ttu-id="d81c9-103">Las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet> tienen un método <xref:System.Data.DataTable.CreateDataReader%2A> que devuelve el contenido de la <xref:System.Data.DataTable> o el contenido de la colección <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Tables%2A> como uno o más conjuntos de resultados de solo lectura y solo avance.</span><span class="sxs-lookup"><span data-stu-id="d81c9-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d81c9-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d81c9-104">Example</span></span>  

 <span data-ttu-id="d81c9-105">La siguiente aplicación de consola crea una instancia de <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="d81c9-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="d81c9-106">A continuación, en el ejemplo se pasa el rellenado <xref:System.Data.DataTable> a un procedimiento que llama al <xref:System.Data.DataTable.CreateDataReader%2A> método, que recorre en iteración los resultados contenidos dentro de <xref:System.Data.DataTableReader> .</span><span class="sxs-lookup"><span data-stu-id="d81c9-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="d81c9-107">En el ejemplo se muestra el siguiente resultado en la ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="d81c9-107">The example displays the following output in the console window:</span></span>  
  
```output  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="d81c9-108">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d81c9-108">See also</span></span>

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [<span data-ttu-id="d81c9-109">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="d81c9-109">DataTableReaders</span></span>](datatablereaders.md)
- [<span data-ttu-id="d81c9-110">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d81c9-110">ADO.NET Overview</span></span>](../ado-net-overview.md)
