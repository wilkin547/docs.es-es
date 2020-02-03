---
title: Información general del control DataGridView
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
ms.openlocfilehash: 74de5b449525be9ff93fcbef0ddabd041470177c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742493"
---
# <a name="datagridview-control-overview-windows-forms"></a>Información general del control DataGridView (Windows Forms)
> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Con el control de <xref:System.Windows.Forms.DataGridView>, puede mostrar y editar los datos tabulares de muchos tipos diferentes de orígenes de datos.  
  
 Enlazar datos al control <xref:System.Windows.Forms.DataGridView> es sencillo e intuitivo y, en muchos casos, es tan sencillo como establecer la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>. Al enlazar a un origen de datos que contiene varias listas o tablas, establezca la propiedad <xref:System.Windows.Forms.DataGridView.DataMember%2A> en una cadena que especifique la lista o la tabla a la que se va a enlazar.  
  
 El control <xref:System.Windows.Forms.DataGridView> admite el modelo de enlace de datos Windows Forms estándar, por lo que se enlazará a las instancias de clases descritas en la siguiente lista:  
  
- Cualquier clase que implementa la interfaz <xref:System.Collections.IList>, incluidas las matrices unidimensionales.  
  
- Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IListSource>, como las clases <xref:System.Data.DataTable> y <xref:System.Data.DataSet>.  
  
- Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IBindingList>, como la clase <xref:System.ComponentModel.BindingList%601>.  
  
- Cualquier clase que implementa la interfaz <xref:System.ComponentModel.IBindingListView>, como la clase <xref:System.Windows.Forms.BindingSource>.  
  
 El control <xref:System.Windows.Forms.DataGridView> admite el enlace de datos a las propiedades públicas de los objetos devueltos por estas interfaces o a la colección de propiedades devuelta por una interfaz <xref:System.ComponentModel.ICustomTypeDescriptor>, si se implementa en los objetos devueltos.  
  
 Normalmente, se enlazará a un componente de <xref:System.Windows.Forms.BindingSource> y enlazará el componente de <xref:System.Windows.Forms.BindingSource> a otro origen de datos o lo rellenará con objetos comerciales. El componente <xref:System.Windows.Forms.BindingSource> es el origen de datos preferido, ya que puede enlazarse a una gran variedad de orígenes de datos y puede resolver muchos problemas de enlace de datos automáticamente. Para obtener más información, vea [BindingSource (componente](bindingsource-component.md)).  
  
 El control <xref:System.Windows.Forms.DataGridView> también se puede utilizar en el modo sin *enlazar* , sin almacén de datos subyacente. Para obtener un ejemplo de código que usa un control de <xref:System.Windows.Forms.DataGridView> independiente, vea [Tutorial: crear un control DataGridView de Windows Forms independiente](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 El control <xref:System.Windows.Forms.DataGridView> es muy configurable y extensible, y proporciona muchas propiedades, métodos y eventos para personalizar su apariencia y comportamiento. Si desea que la aplicación Windows Forms muestre datos tabulares, considere la posibilidad de usar el control <xref:System.Windows.Forms.DataGridView> antes que otros (por ejemplo, <xref:System.Windows.Forms.DataGrid>). Si va a mostrar una cuadrícula pequeña de valores de solo lectura, o si está habilitando a un usuario para que edite una tabla con millones de registros, el control <xref:System.Windows.Forms.DataGridView> le proporcionará una solución eficaz y programable en memoria.  
  
## <a name="in-this-section"></a>En esta sección  
 [Resumen de tecnologías para el control DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Resume <xref:System.Windows.Forms.DataGridView> conceptos de control y el uso de clases relacionadas.  
  
 [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)  
 Describe la arquitectura del control <xref:System.Windows.Forms.DataGridView>, que explica su jerarquía de tipos y su estructura de herencia.  
  
 [Escenarios del control DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Describe los escenarios más comunes en los que se utilizan <xref:System.Windows.Forms.DataGridView> controles.  
  
 [Directorio de código del control DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Proporciona vínculos a ejemplos de código en la documentación de varias tareas de <xref:System.Windows.Forms.DataGridView>. Estos ejemplos se dividen por categorías de tipo de tarea.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna del control Windows Forms <xref:System.Windows.Forms.DataGridView> que se usa para mostrar información y permitir que los usuarios modifiquen o agreguen información.  
  
 [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.  
  
 [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Funcionalidad predeterminada en el control DataGridView de Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
