---
title: Crear un objeto DataReader
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49d4422a-7464-4ab8-8ec7-90185fde3ecf
ms.openlocfilehash: cb39ead1fe15e3bfcf67370e4675dcae3bbf9801
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203900"
---
# <a name="creating-a-datareader"></a>Crear un objeto DataReader
Las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet> tienen un método <xref:System.Data.DataTable.CreateDataReader%2A> que devuelve el contenido de la <xref:System.Data.DataTable> o el contenido de la colección <xref:System.Data.DataSet> del objeto <xref:System.Data.DataSet.Tables%2A> como uno o más conjuntos de resultados de solo lectura y solo avance.  
  
## <a name="example"></a>Ejemplo  
 La siguiente aplicación de consola crea una instancia de <xref:System.Data.DataTable>. A continuación, en el ejemplo <xref:System.Data.DataTable> se pasa el rellenado <xref:System.Data.DataTable.CreateDataReader%2A> a un procedimiento que llama al método, que recorre <xref:System.Data.DataTableReader>en iteración los resultados contenidos dentro de.  
  
 [!code-csharp[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/CS/source.cs#1)]
 [!code-vb[DataWorks DataTable.CreateDataReader#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTable.CreateDataReader/VB/source.vb#1)]  
  
 En el ejemplo se muestra el siguiente resultado en la ventana de consola:  
  
```  
1 Mary  
2 Andy  
3 Peter  
4 Russ  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Data.DataTable.CreateDataReader%2A>
- <xref:System.Data.DataSet.CreateDataReader%2A>
- [Objetos DataTableReader](datatablereaders.md)
- [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
