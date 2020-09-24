---
title: Enlace de datos y LINQ to DataSet
ms.date: 03/30/2017
ms.assetid: 310bff4a-32dd-4f20-a271-6dbd82912631
ms.openlocfilehash: 3203310029f463e55d7517e79f5a1f0424a0a80c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166877"
---
# <a name="data-binding-and-linq-to-dataset"></a>Enlace de datos y LINQ to DataSet

El *enlace de datos* es el proceso que establece una conexión entre la interfaz de usuario de la aplicación y la lógica de negocios. Si el enlace está configurado correctamente y los datos proporcionan la notificaciones adecuadas, al cambiar los valores de los datos, los elementos enlazados a los mismos reflejarán de manera automática dichos cambios. <xref:System.Data.DataSet> es una representación de datos residente en memoria que proporciona un modelo de programación relacional coherente independientemente del origen de datos que contiene. <xref:System.Data.DataView> de ADO.NET 2.0 permite ordenar y filtrar los datos almacenados en <xref:System.Data.DataTable>. Esta funcionalidad se utiliza con frecuencia en aplicaciones de enlace de datos. Mediante <xref:System.Data.DataView> puede exponer los datos de una tabla con distintos criterios de ordenación y filtrar los datos por el estado de fila o basándose en una expresión de filtro. Para obtener más información sobre el <xref:System.Data.DataView> objeto, vea objetos de [vista](./dataset-datatable-dataview/dataviews.md)de datos.  
  
 LINQ to DataSet permite a los desarrolladores crear consultas complejas y eficaces sobre un <xref:System.Data.DataSet> mediante el uso de Language-Integrated Query (LINQ). Sin embargo, una consulta de LINQ to DataSet devuelve una enumeración de <xref:System.Data.DataRow> objetos, que no se usa fácilmente en un escenario de enlace. Para facilitar el enlace, puede crear un a <xref:System.Data.DataView> partir de una consulta de LINQ to DataSet. <xref:System.Data.DataView>Utiliza el filtrado y la ordenación especificados en la consulta, pero es más adecuado para el enlace de datos. LINQ to DataSet amplía la funcionalidad de al <xref:System.Data.DataView> proporcionar filtrado y ordenación basados en expresiones LINQ, lo que permite operaciones de filtrado y ordenación mucho más complejas y eficaces que el filtrado y la ordenación basados en cadenas.  
  
 Observe que <xref:System.Data.DataView> representa la propia consulta y no es una vista encima de la consulta. <xref:System.Data.DataView> se enlaza a un control de la interfaz de usuario, como <xref:System.Windows.Forms.DataGrid> o <xref:System.Windows.Forms.DataGridView>, proporcionando un modelo de enlace de datos simple. <xref:System.Data.DataView> se puede crear también a partir de <xref:System.Data.DataTable>, proporcionando una vista predeterminada de esa tabla.  
  
## <a name="in-this-section"></a>En esta sección  

 [Creación de un objeto DataView](creating-a-dataview-object-linq-to-dataset.md)  
 Proporciona información sobre creación de <xref:System.Data.DataView>.  
  
 [Filtrado con DataView](filtering-with-dataview-linq-to-dataset.md)  
 Describe cómo filtrar con <xref:System.Data.DataView>.  
  
 [Ordenación con DataView](sorting-with-dataview-linq-to-dataset.md)  
 Describe cómo ordenar con <xref:System.Data.DataView>.  
  
 [Consultar la colección de DataRowView en un objeto DataView](querying-the-datarowview-collection-in-a-dataview.md)  
 Proporciona información sobre cómo consultar la colección <xref:System.Data.DataRowView> expuesta por <xref:System.Data.DataView>.  
  
 [Rendimiento de DataView](dataview-performance.md)  
 Proporciona información sobre <xref:System.Data.DataView> y rendimiento.  
  
 [Procedimiento para enlazar un objeto DataView a un control DataGridView de formularios Windows Forms](how-to-bind-a-dataview-object-to-a-winforms-datagridview-control.md)  
 Describe cómo enlazar un objeto <xref:System.Data.DataView> a <xref:System.Windows.Forms.DataGridView>.  
  
## <a name="see-also"></a>Consulte también

- [Guía de programación](programming-guide-linq-to-dataset.md)
