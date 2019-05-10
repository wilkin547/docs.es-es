---
title: Información general del control DataGridView (Formularios Windows Forms)
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
ms.openlocfilehash: 4db2a8b0e30a6bb3db0c5c629d868bc01dc15a8c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648079"
---
# <a name="datagridview-control-overview-windows-forms"></a>Información general del control DataGridView (Formularios Windows Forms)
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Con el <xref:System.Windows.Forms.DataGridView> control, puede mostrar y editar datos tabulares desde muchos tipos diferentes de orígenes de datos.  
  
 Enlazar datos a la <xref:System.Windows.Forms.DataGridView> control es sencillo e intuitivo y en muchos casos es tan sencillo como la configuración de la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad. Al enlazar a un origen de datos que contiene varias listas o tablas, establecer el <xref:System.Windows.Forms.DataGridView.DataMember%2A> propiedad en una cadena que especifica la lista o tabla para enlazar a.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el modelo de enlace de datos de Windows Forms estándar, por lo que se enlazará a las instancias de las clases descritas en la lista siguiente:  
  
- Cualquier clase que implementa el <xref:System.Collections.IList> interfaz, incluidas las matrices unidimensionales.  
  
- Cualquier clase que implementa el <xref:System.ComponentModel.IListSource> interfaz, como el <xref:System.Data.DataTable> y <xref:System.Data.DataSet> clases.  
  
- Cualquier clase que implementa el <xref:System.ComponentModel.IBindingList> interfaz, como la <xref:System.ComponentModel.BindingList%601> clase.  
  
- Cualquier clase que implementa el <xref:System.ComponentModel.IBindingListView> interfaz, como la <xref:System.Windows.Forms.BindingSource> clase.  
  
 El <xref:System.Windows.Forms.DataGridView> control admite el enlace de datos a las propiedades públicas de los objetos devueltos por estas interfaces o a la colección de propiedades devuelto por una <xref:System.ComponentModel.ICustomTypeDescriptor> interfaz, si se implementa en los objetos devueltos.  
  
 Normalmente, se enlazará a un <xref:System.Windows.Forms.BindingSource> componente y enlace el <xref:System.Windows.Forms.BindingSource> componente a otro origen de datos o rellenarlo con objetos de negocios. El <xref:System.Windows.Forms.BindingSource> componente es el origen de datos preferido porque puede enlazar a una amplia variedad de orígenes de datos y puede resolver automáticamente muchos problemas de enlace de datos. Para obtener más información, consulte [componente BindingSource](bindingsource-component.md).  
  
 El <xref:System.Windows.Forms.DataGridView> control también puede usarse en *independiente* modo con ningún almacén de datos subyacente. Para obtener un ejemplo de código que usa un independiente <xref:System.Windows.Forms.DataGridView> control, vea [Tutorial: Crear una independiente de Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).  
  
 El <xref:System.Windows.Forms.DataGridView> control es altamente configurable y extensible, y proporciona muchas propiedades, métodos y eventos para personalizar su apariencia y comportamiento. Si desea que la aplicación de Windows Forms para mostrar datos tabulares, considere el uso de la <xref:System.Windows.Forms.DataGridView> control antes que otras (por ejemplo, <xref:System.Windows.Forms.DataGrid>). Si va a mostrar una cuadrícula pequeña de valores de solo lectura, o si va a habilitar un usuario editar una tabla con millones de registros, la <xref:System.Windows.Forms.DataGridView> control le proporcionará una solución de bajo consumo de memoria, fácilmente programable.  
  
## <a name="in-this-section"></a>En esta sección  
 [Resumen de tecnologías para el control DataGridView](datagridview-control-technology-summary-windows-forms.md)  
 Resume <xref:System.Windows.Forms.DataGridView> controlar los conceptos y el uso de las clases relacionadas.  
  
 [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)  
 Describe la arquitectura de la <xref:System.Windows.Forms.DataGridView> control, explicando su estructura de jerarquía y herencia de tipo.  
  
 [Escenarios del control DataGridView](datagridview-control-scenarios-windows-forms.md)  
 Describe los escenarios más comunes en el que <xref:System.Windows.Forms.DataGridView> se usan los controles.  
  
 [Directorio de código del control DataGridView](datagridview-control-code-directory-windows-forms.md)  
 Proporciona vínculos a ejemplos de código en la documentación para distintos <xref:System.Windows.Forms.DataGridView> tareas. Estos ejemplos se dividen por categorías de tipo de tarea.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)  
 Describe los tipos de columna en los formularios de Windows <xref:System.Windows.Forms.DataGridView> control utilizado para mostrar información y permitir a los usuarios modificar o agregar información.  
  
 [Mostrar datos en el control DataGridView de Windows Forms](displaying-data-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo rellenar el control con datos manualmente o desde un origen de datos externo.  
  
 [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, y la creación de tipos derivados de celda, columna y fila.  
  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo usar eficazmente el control para evitar problemas de rendimiento cuando se trabaja con grandes cantidades de datos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Funcionalidad predeterminada en el control DataGridView de Windows Forms](default-functionality-in-the-windows-forms-datagridview-control.md)
- [Control predeterminado de teclado y mouse en el control DataGridView de Windows Forms](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
