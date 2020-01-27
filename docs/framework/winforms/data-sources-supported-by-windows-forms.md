---
title: Orígenes de datos admitidos
ms.date: 03/30/2017
helpviewer_keywords:
- collections [Windows Forms], binding to
- OLE DB providers [Windows Forms], Windows Forms
- DataTable class [Windows Forms], binding and Windows Forms
- Windows Forms, data binding
- DataView class [Windows Forms], binding and Windows Forms
- DataViewManager class [Windows Forms], binding and Windows Forms
- Windows Forms, source data
- arrays [Windows Forms]
- data sources [Windows Forms]
- data providers [Windows Forms]
- DataSet class [Windows Forms], binding and Windows Forms
- data [Windows Forms], data providers
ms.assetid: 3d2c43f6-462b-4d35-9c86-13e9afe012e1
ms.openlocfilehash: 83ce4bb0d6f0bf81bcad4e38af212dccc3483ca5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742314"
---
# <a name="data-sources-supported-by-windows-forms"></a>Orígenes de datos compatibles con Windows Forms
Tradicionalmente, el enlace de datos se ha usado en las aplicaciones para aprovechar los datos almacenados en las bases de datos. Con Windows Forms enlace de datos, puede tener acceso a los datos de las bases de datos, así como a los datos de otras estructuras, como matrices y colecciones, siempre y cuando se cumplan ciertos requisitos mínimos.  
  
## <a name="structures-to-bind-to"></a>Estructuras a las que se va a enlazar  
 En Windows Forms, puede enlazar a una gran variedad de estructuras, desde objetos simples (enlace simple) hasta listas complejas como tablas de datos ADO.NET (enlace complejo). En el caso del enlace simple, Windows Forms admite el enlace a las propiedades públicas en el objeto simple. Windows Forms enlace basado en lista generalmente requiere que el objeto admita la interfaz de <xref:System.Collections.IList> o la interfaz <xref:System.ComponentModel.IListSource>. Además, si enlaza con a través de un componente de <xref:System.Windows.Forms.BindingSource>, puede enlazar a un objeto que admita la interfaz de <xref:System.Collections.IEnumerable>. Para obtener más información sobre las interfaces relacionadas con el enlace de datos, vea [interfaces relacionadas con el enlace de datos](interfaces-related-to-data-binding.md).  
  
 En la lista siguiente se muestran las estructuras a las que se puede enlazar en Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Un <xref:System.Windows.Forms.BindingSource> es el origen de datos Windows Forms más común y actúa como un proxy entre un origen de datos y los controles de Windows Forms. El patrón de uso general <xref:System.Windows.Forms.BindingSource> es enlazar los controles al <xref:System.Windows.Forms.BindingSource> y enlazar el <xref:System.Windows.Forms.BindingSource> al origen de datos (por ejemplo, una tabla de datos ADO.NET o un objeto comercial). El <xref:System.Windows.Forms.BindingSource> proporciona servicios que habilitan y mejoran el nivel de compatibilidad con el enlace de datos. Por ejemplo, Windows Forms lista de controles basados en, como los <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.ComboBox> no admiten directamente el enlace a los orígenes de datos de <xref:System.Collections.IEnumerable>. sin embargo, puede habilitar este escenario enlazando a través de un <xref:System.Windows.Forms.BindingSource>. En este caso, el <xref:System.Windows.Forms.BindingSource> convertirá el origen de datos en un <xref:System.Collections.IList>.  
  
 Objetos simples  
 Windows Forms admite las propiedades de control de enlace de datos en las propiedades públicas de la instancia de un objeto utilizando el tipo de <xref:System.Windows.Forms.Binding>. Windows Forms también admite controles basados en la lista de enlace, como un <xref:System.Windows.Forms.ListControl> a una instancia de objeto cuando se utiliza una <xref:System.Windows.Forms.BindingSource>.  
  
 matriz o colección  
 Para actuar como origen de datos, una lista debe implementar la interfaz <xref:System.Collections.IList>; un ejemplo sería una matriz que es una instancia de la clase <xref:System.Array>. Para obtener más información sobre las matrices, vea [Cómo: crear una matriz de objetos (Visual Basic)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/487y7874(v=vs.100)).  
  
 En general, debe usar <xref:System.ComponentModel.BindingList%601> al crear listas de objetos para el enlace de datos. <xref:System.ComponentModel.BindingList%601> es una versión genérica de la interfaz <xref:System.ComponentModel.IBindingList>. La interfaz de <xref:System.ComponentModel.IBindingList> amplía la interfaz de <xref:System.Collections.IList> agregando propiedades, métodos y eventos necesarios para el enlace de datos bidireccional.  
  
 <xref:System.Collections.IEnumerable>  
 Windows Forms controles se pueden enlazar a orígenes de datos que solo admiten la interfaz de <xref:System.Collections.IEnumerable> si se enlazan a través de un componente <xref:System.Windows.Forms.BindingSource>.  
  
 Objetos de datos ADO.NET  
 ADO.NET proporciona varias estructuras de datos adecuadas para el enlace a. Cada uno varía en su sofisticación y complejidad.  
  
- <xref:System.Data.DataColumn>. Un <xref:System.Data.DataColumn> es el bloque de creación esencial de un <xref:System.Data.DataTable>, en el que varias columnas componen una tabla. Cada <xref:System.Data.DataColumn> tiene una propiedad <xref:System.Data.DataColumn.DataType%2A> que determina el tipo de datos que contiene la columna (por ejemplo, la marca de un automóvil en una tabla que describe los automóviles). Puede enlazar de forma simple un control (como una propiedad <xref:System.Windows.Forms.Control.Text%2A> del control <xref:System.Windows.Forms.TextBox>) a una columna de una tabla de datos.  
  
- <xref:System.Data.DataTable>. Un <xref:System.Data.DataTable> es la representación de una tabla, con filas y columnas, en ADO.NET. Una tabla de datos contiene dos colecciones: <xref:System.Data.DataColumn>, que representan las columnas de datos de una tabla determinada (que, en última instancia, determinan los tipos de datos que se pueden escribir en esa tabla) y <xref:System.Data.DataRow>, que representan las filas de datos de una tabla determinada. Puede enlazar de forma compleja un control a la información contenida en una tabla de datos (como enlazar el control de <xref:System.Windows.Forms.DataGridView> a una tabla de datos). Sin embargo, cuando se enlaza a un <xref:System.Data.DataTable>, se está enlazando realmente a la vista predeterminada de la tabla.  
  
- <xref:System.Data.DataView>. Un <xref:System.Data.DataView> es una vista personalizada de una sola tabla de datos que se puede filtrar u ordenar. Una vista de datos es la "instantánea" de datos utilizada por los controles enlazados de forma compleja. Puede enlazar de forma simple o compleja a los datos de una vista de datos, pero tenga en cuenta que está enlazando a una "imagen" fija de los datos en lugar de a un origen de datos limpio y de actualización.  
  
- <xref:System.Data.DataSet>. Un <xref:System.Data.DataSet> es una colección de tablas, relaciones y restricciones de los datos de una base de datos. Puede realizar un enlace simple o un enlace complejo a los datos de un conjunto de datos, pero tenga en cuenta que está enlazando a la <xref:System.Data.DataViewManager> predeterminada del <xref:System.Data.DataSet> (vea el siguiente punto de viñeta).  
  
- <xref:System.Data.DataViewManager>. Un <xref:System.Data.DataViewManager> es una vista personalizada de toda la <xref:System.Data.DataSet>, análoga a un <xref:System.Data.DataView>, pero con relaciones incluidas. Con una colección de <xref:System.Data.DataViewManager.DataViewSettings%2A>, puede establecer filtros predeterminados y las opciones de ordenación de las vistas que el <xref:System.Data.DataViewManager> tenga para una tabla determinada.  
  
## <a name="see-also"></a>Vea también

- [Notificación de cambios en el enlace de datos de Windows Forms](change-notification-in-windows-forms-data-binding.md)
- [Enlace de datos y Windows Forms](data-binding-and-windows-forms.md)
- [Enlace de datos en Windows Forms](windows-forms-data-binding.md)
