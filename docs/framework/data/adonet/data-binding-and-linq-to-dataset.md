---
title: Enlace de datos y LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: e82cc5ecfc1272cfb4594cb556fa9455a7ea7813
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="data-binding-and-linq-to-dataset"></a>Enlace de datos y LINQ to DataSet
*Enlace de datos* es el proceso que establece una conexión entre la aplicación de interfaz de usuario y la lógica de negocios. Si el enlace está configurado correctamente y los datos proporcionan la notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los mismos reflejarán de manera automática dichos cambios. <xref:System.Data.DataSet> es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene. <xref:System.Data.DataView> de ADO.NET 2.0 permite ordenar y filtrar los datos almacenados en <xref:System.Data.DataTable>. Esta funcionalidad se utiliza con frecuencia en aplicaciones de enlace de datos. Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro. Para obtener más información sobre la <xref:System.Data.DataView> de objetos, consulte [DataView](../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md).  
  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] permite a los programadores crear consultas complejas y eficaces sobre un <xref:System.Data.DataSet> utilizando [!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)]. Sin embargo, un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta devuelve una enumeración de <xref:System.Data.DataRow> objetos, que no se utiliza con facilidad en un escenario de enlace. Para facilitar el enlace, puede crear un <xref:System.Data.DataView> desde un [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] consulta. Esto <xref:System.Data.DataView> usa el filtrado y ordenación especificados en la consulta, pero es más adecuado para el enlace de datos. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] extiende la funcionalidad de la <xref:System.Data.DataView> proporcionando [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] basadas en expresiones de filtro y ordenación, lo que permite mucho más complejas y eficaces, filtrar y ordenar las operaciones de cadena en función de filtrado y ordenación.  
  
 Observe que <xref:System.Data.DataView> representa la propia consulta y no es una vista encima de la consulta. <xref:System.Data.DataView> se enlaza a un control de la interfaz de usuario, como <xref:System.Windows.Forms.DataGrid> o <xref:System.Windows.Forms.DataGridView>, proporcionando un modelo de enlace de datos simple. <xref:System.Data.DataView> se puede crear también a partir de <xref:System.Data.DataTable>, proporcionando una vista predeterminada de esa tabla.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de un objeto DataView](../../../../docs/framework/data/adonet/creating-a-dataview-object-linq-to-dataset.md)  
 Proporciona información sobre creación de <xref:System.Data.DataView>.  
  
 [Filtrado con DataView](../../../../docs/framework/data/adonet/filtering-with-dataview-linq-to-dataset.md)  
 Describe cómo filtrar con <xref:System.Data.DataView>.  
  
 [Ordenación con DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)  
 Describe cómo ordenar con <xref:System.Data.DataView>.  
  
 [Consulta de la colección de DataRowView en un objeto DataView](../../../../docs/framework/data/adonet/querying-the-datarowview-collection-in-a-dataview.md)  
 Proporciona información sobre cómo consultar la colección <xref:System.Data.DataRowView> expuesta por <xref:System.Data.DataView>.  
  
 [Rendimiento de DataView](../../../../docs/framework/data/adonet/dataview-performance.md)  
 Proporciona información sobre <xref:System.Data.DataView> y rendimiento.  
  
 [Enlace de un objeto DataView a un control DataGridView de Windows Forms](../../../../docs/framework/data/adonet/how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Describe cómo enlazar un objeto <xref:System.Data.DataView> a <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../../../docs/framework/data/adonet/programming-guide-linq-to-dataset.md)
