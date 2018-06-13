---
title: Objetos DataTableReader
ms.date: 03/30/2017
ms.assetid: 97546ae2-0e42-4d26-961d-e0b244d81ded
ms.openlocfilehash: 8305629bb267805cd79455e2edf990e72a12dc10
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756103"
---
# <a name="datatablereaders"></a>Objetos DataTableReader
El <xref:System.Data.DataTableReader> presenta el contenido de una <xref:System.Data.DataTable> o un <xref:System.Data.DataSet> con formato de uno o más conjuntos de resultados de solo lectura y de solo avance.  
  
 Cuando se crea un **DataTableReader** desde una **DataTable**, resultante **DataTableReader** objeto contiene un conjunto de resultados con los mismos datos que el  **DataTable** desde que se creó, excepto las filas que se han marcado como eliminada. Las columnas aparecen en el mismo orden que en la versión original **DataTable**.  
  
 A **DataTableReader** puede contener varios conjuntos de resultados si se ha creado mediante una llamada a <xref:System.Data.DataSet.CreateDataReader%2A>. Los resultados están en el mismo orden que el **DataTables** en el **conjunto de datos** del objeto <xref:System.Data.DataSet.Tables%2A> colección.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/creating-a-datareader.md)  
 Describe cómo crear un **DataTableReader** objeto.  
  
 [Navegación por objetos DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/navigating-datatables.md)  
 Describe el uso de la **lectura** método para desplazarse por el contenido de un **DataTableReader**.  
  
## <a name="see-also"></a>Vea también  
 [Recuperar y modificar datos en ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 [Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet](http://go.microsoft.com/fwlink/?LinkId=217917)
