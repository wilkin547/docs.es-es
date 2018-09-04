---
title: Orígenes de datos compatibles con formularios Windows Forms
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
ms.openlocfilehash: aee15d8d40ddd3f928c8bc5396d8bcbff17ba533
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43562696"
---
# <a name="data-sources-supported-by-windows-forms"></a>Orígenes de datos compatibles con formularios Windows Forms
Tradicionalmente, el enlace de datos se han usado en las aplicaciones para aprovechar las ventajas de los datos almacenados en bases de datos. Con el enlace de datos de Windows Forms, se puede acceder a datos de las bases de datos, así como datos de otras estructuras, como matrices y colecciones, siempre y cuando se cumplen ciertos requisitos mínimos.  
  
## <a name="structures-to-bind-to"></a>Estructuras para enlazar a  
 En Windows Forms, puede enlazar a una amplia variedad de estructuras, desde simples objetos (enlace simple) a las listas complejas como tablas de datos ADO.NET (enlace complejo). Para el enlace sencillo, Windows Forms admite el enlace a las propiedades públicas del objeto simple. Enlace basado en lista de Windows Forms requiere normalmente que el objeto admite el <xref:System.Collections.IList> interfaz o <xref:System.ComponentModel.IListSource> interfaz. Además, si va a enlazar con a través de un <xref:System.Windows.Forms.BindingSource> componente, puede enlazar a un objeto que admite el <xref:System.Collections.IEnumerable> interfaz. Para obtener más información sobre las interfaces relacionadas con el enlace de datos, vea [Interfaces relacionadas con enlace de datos](../../../docs/framework/winforms/interfaces-related-to-data-binding.md).  
  
 La siguiente lista muestra las estructuras que pueden enlazar a en Windows Forms.  
  
 <xref:System.Windows.Forms.BindingSource>  
 Un <xref:System.Windows.Forms.BindingSource> es el origen de datos de Windows Forms más comunes y actúa de proxy entre un origen de datos y controles de formularios Windows Forms. General <xref:System.Windows.Forms.BindingSource> es el patrón de uso enlazar los controles a la <xref:System.Windows.Forms.BindingSource> y enlazar el <xref:System.Windows.Forms.BindingSource> al origen de datos (por ejemplo, una tabla de datos ADO.NET o un objeto de negocios). El <xref:System.Windows.Forms.BindingSource> proporciona servicios que habilitan y mejoran el nivel de compatibilidad con enlaces de datos. Por ejemplo, Windows Forms controles basados en lista, como el <xref:System.Windows.Forms.DataGridView> y <xref:System.Windows.Forms.ComboBox> directamente no admite el enlace a <xref:System.Collections.IEnumerable> orígenes de datos sin embargo, puede habilitar este escenario mediante el enlace a través de un <xref:System.Windows.Forms.BindingSource>. En este caso, el <xref:System.Windows.Forms.BindingSource> convertirá el origen de datos a un <xref:System.Collections.IList>.  
  
 Objetos simples  
 Windows Forms es compatible con las propiedades de control de enlace de datos a las propiedades públicas en la instancia de un objeto mediante el <xref:System.Windows.Forms.Binding> tipo. Windows Forms también admite controles de lista en función de enlace, como un <xref:System.Windows.Forms.ListControl> a un objeto de instancia cuando una <xref:System.Windows.Forms.BindingSource> se utiliza.  
  
 matriz o colección  
 Para actuar como un origen de datos, debe implementar una lista el <xref:System.Collections.IList> interfaz; un ejemplo sería una matriz que es una instancia de la <xref:System.Array> clase. Para obtener más información sobre matrices, vea [Cómo: crear una matriz de objetos (Visual Basic)](https://msdn.microsoft.com/library/6b64e069-0387-400c-9081-3bdc581020c3).  
  
 En general, debe usar <xref:System.ComponentModel.BindingList%601> al crear listas de objetos para el enlace de datos. <xref:System.ComponentModel.BindingList%601> es una versión genérica de la <xref:System.ComponentModel.IBindingList> interfaz. El <xref:System.ComponentModel.IBindingList> interfaz extiende la <xref:System.Collections.IList> interfaz agregando propiedades, métodos y eventos necesarios para el enlace de datos bidireccional.  
  
 <xref:System.Collections.IEnumerable>  
 Controles de formularios Windows Forms se pueden enlazar a orígenes de datos que solo son compatibles con el <xref:System.Collections.IEnumerable> interfaz si se enlazan a través de un <xref:System.Windows.Forms.BindingSource> componente.  
  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] objetos de datos  
 [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] Proporciona una serie de estructuras de datos adecuadas para el enlace. Varía en sofisticación y complejidad.  
  
-   <xref:System.Data.DataColumn>. Un <xref:System.Data.DataColumn> es el bloque de creación fundamental de un <xref:System.Data.DataTable>, ya que un número de columnas componen una tabla. Cada <xref:System.Data.DataColumn> tiene un <xref:System.Data.DataColumn.DataType%2A> propiedad que determina el tipo de datos que contiene la columna (por ejemplo, la marca de un automóvil en una tabla con descripciones de automóviles). Puede sencillo enlazar un control (como un <xref:System.Windows.Forms.TextBox> del control <xref:System.Windows.Forms.Control.Text%2A> propiedad) a una columna dentro de una tabla de datos.  
  
-   <xref:System.Data.DataTable>. Un <xref:System.Data.DataTable> es la representación de una tabla con filas y columnas, en [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]. Una tabla de datos contiene dos colecciones: <xref:System.Data.DataColumn>, que representa las columnas de datos en una tabla determinada (que en última instancia determina los tipos de datos que se pueden escribir en la tabla), y <xref:System.Data.DataRow>, que representa las filas de datos en una tabla determinada. Puede complejo enlazar un control a la información contenida en una tabla de datos (como el enlace de la <xref:System.Windows.Forms.DataGridView> control a una tabla de datos). Sin embargo, al enlazar a un <xref:System.Data.DataTable>, son un enlace realmente a la vista predeterminada de la tabla.  
  
-   <xref:System.Data.DataView>. Un <xref:System.Data.DataView> es una vista personalizada de una tabla de datos única que puede filtrar u ordenar. Una vista de datos es los datos usado por los controles de enlace complejo "instantánea". Puede crear un enlace sencillo o complejo enlazar a los datos dentro de una vista de datos, pero tenga en cuenta que va a enlazar a una "imagen" fija de los datos en lugar de un origen de datos limpio y actualizado.  
  
-   <xref:System.Data.DataSet>. Un <xref:System.Data.DataSet> es una colección de tablas, relaciones y restricciones de los datos en una base de datos. Puede crear un enlace sencillo o complejo enlazar a los datos dentro de un conjunto de datos, pero tenga en cuenta que va a enlazar con el valor predeterminado <xref:System.Data.DataViewManager> para el <xref:System.Data.DataSet> (consulte el siguiente punto).  
  
-   <xref:System.Data.DataViewManager>. Un <xref:System.Data.DataViewManager> es una vista personalizada de todo el <xref:System.Data.DataSet>, análogo a un <xref:System.Data.DataView>, pero con las relaciones incluidas. Con un <xref:System.Data.DataViewManager.DataViewSettings%2A> colección, puede establecer filtros predeterminados y las opciones de ordenación para todas las vistas que el <xref:System.Data.DataViewManager> tiene para una tabla determinada.  
  
## <a name="see-also"></a>Vea también  
 [Notificación de cambios en el enlace de datos de Windows Forms](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [Enlace de datos y Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
