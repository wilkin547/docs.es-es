---
title: Información general del control DataGridView
description: Aprenda a usar el control DataGridView Windows Forms para mostrar y editar datos tabulares de muchos tipos diferentes de orígenes de datos.
ms.date: 03/30/2017
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
ms.openlocfilehash: 3e68f536853081453f6ba746d342bc016bc8ca17
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174619"
---
# <a name="datagridview-control-overview-windows-forms"></a>Información general del control DataGridView (Formularios Windows Forms)
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Con el <xref:System.Windows.Forms.DataGridView> control, puede mostrar y editar los datos tabulares de muchos tipos diferentes de orígenes de datos.  
  
 Enlazar datos al <xref:System.Windows.Forms.DataGridView> control es sencillo e intuitivo y, en muchos casos, es tan sencillo como establecer la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad. Al enlazar a un origen de datos que contiene varias listas o tablas, establezca la <xref:System.Windows.Forms.DataGridView.DataMember%2A> propiedad en una cadena que especifique la lista o la tabla a la que se va a enlazar.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a las instancias de clases descritas en la lista siguiente:  
  
- Cualquier clase que implementa la <xref:System.Collections.IList> interfaz, incluidas las matrices unidimensionales.  
  
- Cualquier clase que implementa la <xref:System.ComponentModel.IListSource> interfaz, como las <xref:System.Data.DataTable> <xref:System.Data.DataSet> clases y.  
  
- Cualquier clase que implementa la <xref:System.ComponentModel.IBindingList> interfaz, como la <xref:System.ComponentModel.BindingList%601> clase.  
  
- Cualquier clase que implementa la <xref:System.ComponentModel.IBindingListView> interfaz, como la <xref:System.Windows.Forms.BindingSource> clase.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el enlace de datos a las propiedades públicas de los objetos devueltos por estas interfaces o a la colección de propiedades devuelta por una <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz, si se implementa en los objetos devueltos.  
  
 Normalmente, se enlazará a un <xref:System.Windows.Forms.BindingSource> componente y se enlazará el <xref:System.Windows.Forms.BindingSource> componente a otro origen de datos o se rellenará con objetos comerciales. El <xref:System.Windows.Forms.BindingSource> componente es el origen de datos preferido porque puede enlazar con una amplia variedad de orígenes de datos y puede resolver muchos problemas de enlace de datos automáticamente. Para obtener más información, vea [BindingSource (componente](bindingsource-component.md)).  
  
 El <xref:System.Windows.Forms.DataGridView> control también se puede utilizar en el modo sin *enlazar* , sin almacén de datos subyacente. Para obtener un ejemplo de código que usa un <xref:System.Windows.Forms.DataGridView> control independiente, vea [Tutorial: crear un control DataGridView de Windows Forms independiente](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 El <xref:System.Windows.Forms.DataGridView> control es muy configurable y extensible, y proporciona muchas propiedades, métodos y eventos para personalizar su apariencia y comportamiento. Si desea que la aplicación Windows Forms muestre datos tabulares, considere la posibilidad de usar el <xref:System.Windows.Forms.DataGridView> control antes que otros (por ejemplo, <xref:System.Windows.Forms.DataGrid> ). Si va a mostrar una cuadrícula pequeña de valores de solo lectura, o si va a permitir que un usuario edite una tabla con millones de registros, el <xref:System.Windows.Forms.DataGridView> control le proporcionará una solución fácil de programar y eficiente en memoria.  
  
## <a name="in-this-section"></a>En esta sección  
 [Resumen de tecnologías para el control DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Resume <xref:System.Windows.Forms.DataGridView> los conceptos de control y el uso de clases relacionadas.  
  
 [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)  
 Describe la arquitectura del <xref:System.Windows.Forms.DataGridView> control, que explica su jerarquía de tipos y su estructura de herencia.  
  
 [Escenarios del control DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Describe los escenarios más comunes en los que <xref:System.Windows.Forms.DataGridView> se usan controles.  
  
 [Directorio de código del control DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Proporciona vínculos a ejemplos de código en la documentación de varias <xref:System.Windows.Forms.DataGridView> tareas. Estos ejemplos se dividen por categorías de tipo de tarea.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna del control Windows Forms <xref:System.Windows.Forms.DataGridView> que se usan para mostrar información y permitir a los usuarios modificar o agregar información.  
  
 [Mostrar datos en el control DataGridView de formularios Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.  
  
 [Personalizar el control DataGridView de formularios Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en formularios Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [Control DataGridView](datagridview-control-windows-forms.md)
- [Funcionalidad predeterminada en el control DataGridView de formularios Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
