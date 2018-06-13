---
title: Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: d0a82d5724ebe142ae080fc930665733e701e237
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528719"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> trata de un nuevo control que reemplaza el <xref:System.Windows.Forms.DataGrid> control. El <xref:System.Windows.Forms.DataGridView> control proporciona varias características básicas y avanzadas que faltan en el <xref:System.Windows.Forms.DataGrid> control. Además, la arquitectura de la <xref:System.Windows.Forms.DataGridView> control, resulta más fácil ampliar y personalizar que el <xref:System.Windows.Forms.DataGrid> control.  
  
 La tabla siguiente describen algunas de las principales características disponibles en la <xref:System.Windows.Forms.DataGridView> control que faltan en el <xref:System.Windows.Forms.DataGrid> control.  
  
|Característica del control DataGridView|Descripción|  
|----------------------------------|-----------------|  
|Varios tipos de columna|El <xref:System.Windows.Forms.DataGridView> control proporciona los tipos de columna integrados más que el <xref:System.Windows.Forms.DataGrid> control. Estos tipos de columna satisfacer las necesidades de los escenarios más comunes, pero también son más fáciles de ampliar o reemplazar a los tipos de columna en el <xref:System.Windows.Forms.DataGrid> control. Para obtener más información, consulte [tipos de columna en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de mostrar datos|El <xref:System.Windows.Forms.DataGrid> control se limita a mostrar los datos desde un origen de datos externo. El <xref:System.Windows.Forms.DataGridView> control, sin embargo, puede mostrar datos sin enlazar almacenados en el control, los datos de un origen de datos enlazado o datos dependientes e independientes entre sí. También puede implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control para proporcionar una administración de datos personalizados. Para obtener más información, consulte [modos de presentación de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de personalizar la presentación de datos|El <xref:System.Windows.Forms.DataGridView> control proporciona muchas propiedades y eventos que le permiten especificar cómo se da formato y mostrar los datos. Por ejemplo, puede cambiar la apariencia de celdas, filas y columnas dependiendo de los datos que contienen, o puede reemplazar los datos de un tipo de datos con datos equivalentes de otro tipo. Para obtener más información, consulte [formato de los datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Varias opciones para cambiar el comportamiento y apariencia de la celda, fila, columna y encabezado|El <xref:System.Windows.Forms.DataGridView> control le permite trabajar con componentes individuales de la cuadrícula de numerosas maneras. Por ejemplo, puede inmovilizar filas y columnas para evitar que se desplacen; Ocultar filas, columnas y encabezados; cambiar la manera en que se ajustan los tamaños de fila, columna y encabezado; cambiar la manera en que los usuarios realizar selecciones; y proporcionan información sobre herramientas y menús contextuales para las columnas, filas y celdas individuales.|  
  
 El <xref:System.Windows.Forms.DataGrid> control se conserva por compatibilidad con versiones anteriores y para necesidades especiales. Para casi todos los propósitos, debe usar el <xref:System.Windows.Forms.DataGridView> control. La única característica que está disponible en la <xref:System.Windows.Forms.DataGrid> control que no está disponible en el <xref:System.Windows.Forms.DataGridView> control es la presentación jerárquica de información de dos tablas relacionadas en un control único. Debe utilizar dos <xref:System.Windows.Forms.DataGridView> controles para mostrar información de dos tablas que tienen una relación principal-detalle.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Actualización para el Control DataGridView  
 Si tiene aplicaciones existentes que utilicen el <xref:System.Windows.Forms.DataGrid> control en un escenario sencillo de enlace a datos sin personalizaciones, simplemente puede reemplazar el control antiguo con el nuevo control. Ambos controles utilizan la arquitectura de enlace de datos de formularios Windows Forms estándar, por lo que el <xref:System.Windows.Forms.DataGridView> control mostrará los datos enlazados con no necesitan configuraciones adicionales. Quizá desee considerar sacar partido de las mejoras de enlace de datos, sin embargo, enlazando los datos a un <xref:System.Windows.Forms.BindingSource> componente, que, a continuación, puede enlazar a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [BindingSource (componente)](../../../../docs/framework/winforms/controls/bindingsource-component.md).  
  
 Dado que la <xref:System.Windows.Forms.DataGridView> control tiene una arquitectura totalmente nueva, no hay ninguna ruta de conversión sencilla que le permitirá usar <xref:System.Windows.Forms.DataGrid> personalizaciones con el <xref:System.Windows.Forms.DataGridView> control. Muchos <xref:System.Windows.Forms.DataGrid> personalizaciones no son necesarios con el <xref:System.Windows.Forms.DataGridView> controlar, sin embargo, debido a las funciones integradas disponibles en el nuevo control. Si ha creado tipos de columna personalizada para la <xref:System.Windows.Forms.DataGrid> control que desea usar con el <xref:System.Windows.Forms.DataGridView> (control), tendrá que implementarlas utilizando la nueva arquitectura de nuevo. Para obtener más información, consulte [personalizar el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGrid>  
 <xref:System.Windows.Forms.BindingSource>  
 [DataGridView (control)](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Componente BindingSource](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [Tipos de columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Modos de presentación de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Formato de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)  
 [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)  
 [Modos de ordenación de columnas del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Modos de selección en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/selection-modes-in-the-windows-forms-datagridview-control.md)  
 [Personalizar el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
