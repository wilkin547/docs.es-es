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
# <a name="datatablereaders"></a>Objetos DataTableReader
El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando creas un **DataTableReader** desde un **DataTable**, resultante **DataTableReader** objeto contiene un conjunto de resultados con los mismos datos que el  **DataTable** desde que se creó, excepto para las filas que se han marcado como eliminado. Las columnas aparecen en el mismo orden que en el original **DataTable**.  
  
 Un **DataTableReader** puede contener varios conjuntos de resultados si se creó mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A>. Los resultados están en el mismo orden que el **DataTables** en el **DataSet** del objeto <xref:System.Data.DataSet.Tables%2A> colección.  
  
## <a name="in-this-section"></a>En esta sección  
 [Crear un objeto DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Describe cómo crear un **DataTableReader** objeto.  
  
 [Navegar por objetos DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Describe el uso de la **lectura** método para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Vea también

- [Recuperar y modificar datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [Proveedores administrados de ADO.NET y centro de desarrolladores de DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
