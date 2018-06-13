---
title: Navegar por objetos DataTable
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 3bd10694512e828354254588361cc009aac6602f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756373"
---
# <a name="navigating-datatables"></a>Navegar por objetos DataTable
El <xref:System.Data.DataTableReader> obtiene el contenido de uno o más objetos <xref:System.Data.DataTable> con formato de uno o más conjuntos de solo lectura y de solo avance.  
  
 Un <xref:System.Data.DataTableReader> puede contener varios conjuntos de resultados si se crea mediante el método <xref:System.Data.DataSet.CreateDataReader%2A>. Si hay más de un conjunto de resultados, el método <xref:System.Data.DataTableReader.NextResult%2A> desplaza el cursor hasta el siguiente conjunto de resultados. Este proceso es de solo avance. No es posible volver a un conjunto de resultados anterior.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente, la `TestConstructor` método crea dos <xref:System.Data.DataTable> instancias. Para mostrar este constructor para la <xref:System.Data.DataTableReader> (clase), el ejemplo se crea un nuevo **DataTableReader** basado en una matriz que contiene las dos **DataTables**y realiza una operación sencilla, Imprime el contenido de las primeras columnas en la ventana de consola.  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Objetos DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
