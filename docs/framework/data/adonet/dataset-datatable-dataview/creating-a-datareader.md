---
title: Crear un objeto DataReader
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
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 169f290ba41e7efe1ceb7c57f0821fdc0a886c5e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-datareader"></a><span data-ttu-id="53ef6-102">Crear un objeto DataReader</span><span class="sxs-lookup"><span data-stu-id="53ef6-102">Creating a DataReader</span></span>
<span data-ttu-id="53ef6-103">Las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet> tienen un método <xref:System.Data.DataTable.CreateDataReader%2A> que devuelve el contenido de la <xref:System.Data.DataTable> o el contenido de la colección <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Tables%2A> como uno o más conjuntos de resultados de solo lectura y solo avance.</span><span class="sxs-lookup"><span data-stu-id="53ef6-103">The <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes have a <xref:System.Data.DataTable.CreateDataReader%2A> method that returns the contents of the <xref:System.Data.DataTable> or the contents of the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Tables%2A> collection as one or more read-only, forward-only result sets.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53ef6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53ef6-104">Example</span></span>  
 <span data-ttu-id="53ef6-105">La siguiente aplicación de consola crea una instancia de <xref:System.Data.DataTable>.</span><span class="sxs-lookup"><span data-stu-id="53ef6-105">The following console application creates a <xref:System.Data.DataTable> instance.</span></span> <span data-ttu-id="53ef6-106">En el ejemplo a continuación, pasa el relleno <xref:System.Data.DataTable> a un procedimiento que llama el <xref:System.Data.DataTable.CreateDataReader%2A> método, que recorre en iteración los resultados incluidos en el <xref:System.Data.DataTableReader>.</span><span class="sxs-lookup"><span data-stu-id="53ef6-106">The example then passes the filled <xref:System.Data.DataTable> to a procedure that calls the <xref:System.Data.DataTable.CreateDataReader%2A> method, which iterates through the results contained within the <xref:System.Data.DataTableReader>.</span></span>  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 <span data-ttu-id="53ef6-107">En el ejemplo se muestra el siguiente resultado en la ventana de consola:</span><span class="sxs-lookup"><span data-stu-id="53ef6-107">The example displays the following output in the console window:</span></span>  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a><span data-ttu-id="53ef6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="53ef6-108">See Also</span></span>  
 <xref:System.Data.DataTable.CreateDataReader%2A>  
 <xref:System.Data.DataSet.CreateDataReader%2A>  
 [<span data-ttu-id="53ef6-109">Objetos DataTableReader</span><span class="sxs-lookup"><span data-stu-id="53ef6-109">DataTableReaders</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [<span data-ttu-id="53ef6-110">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="53ef6-110">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
