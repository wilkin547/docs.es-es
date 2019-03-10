---
title: Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: b7d97431bfdbdafd5e87bfbfb9c5badd9ba273ea
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720493"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control es un control nuevo que reemplaza el <xref:System.Windows.Forms.DataGrid> control. El <xref:System.Windows.Forms.DataGridView> control proporciona numerosas características básicas y avanzadas que faltan en el <xref:System.Windows.Forms.DataGrid> control. Además, la arquitectura de la <xref:System.Windows.Forms.DataGridView> control facilita mucho más fáciles de ampliar y personalizar que el <xref:System.Windows.Forms.DataGrid> control.  
  
 En la tabla siguiente se describe algunas de las principales características disponibles en el <xref:System.Windows.Forms.DataGridView> control que faltan en el <xref:System.Windows.Forms.DataGrid> control.  
  
|Característica del control DataGridView|Descripción|  
|----------------------------------|-----------------|  
|Varios tipos de columna|El <xref:System.Windows.Forms.DataGridView> control proporciona tipos de columna más integrados que el <xref:System.Windows.Forms.DataGrid> control. Estos tipos de columna satisfacer las necesidades de los escenarios más comunes, pero también son más fáciles de ampliar o reemplazar a los tipos de columna en el <xref:System.Windows.Forms.DataGrid> control. Para obtener más información, consulte [tipos de columna en el DataGridView Control de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Varias formas de mostrar datos|El <xref:System.Windows.Forms.DataGrid> control se limita a mostrar los datos desde un origen de datos externo. El <xref:System.Windows.Forms.DataGridView> control, sin embargo, puede mostrar datos independientes que se almacenan juntos en el control, datos de un origen de datos enlazados o datos dependientes e independientes. También puede implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control para proporcionar administración de datos personalizado. Para obtener más información, consulte [modos de presentación de datos en el DataGridView Control de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Varias formas de personalizar la visualización de datos|El <xref:System.Windows.Forms.DataGridView> control proporciona muchas propiedades y eventos que le permiten especificar cómo se da formato y mostrar los datos. Por ejemplo, puede cambiar la apariencia de celdas, filas y columnas según los datos que contienen, o puede reemplazar los datos de un tipo de datos con datos equivalentes de otro tipo. Para obtener más información, consulte [formato de los datos en el DataGridView Control de formularios de Windows](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Varias opciones para cambiar el comportamiento y apariencia de la celda, fila, columna y encabezado|El <xref:System.Windows.Forms.DataGridView> control le permite trabajar con los componentes individuales de la cuadrícula de muchas formas. Por ejemplo, puede inmovilizar filas y columnas para evitar que se desplacen; Ocultar filas, columnas y encabezados; cambiar la forma en que se ajustan los tamaños de fila, columna y encabezado; cambiar la forma en que los usuarios realizar selecciones; y proporcionan información sobre herramientas y menús contextuales para las columnas, filas y celdas individuales.|  
  
 El <xref:System.Windows.Forms.DataGrid> control se conserva por compatibilidad con versiones anteriores y para necesidades especiales. Para casi todos los propósitos, debe usar el <xref:System.Windows.Forms.DataGridView> control. La única característica que está disponible en el <xref:System.Windows.Forms.DataGrid> control que no está disponible en el <xref:System.Windows.Forms.DataGridView> control es la presentación jerárquica de información de dos tablas relacionadas en un único control. Debe utilizar dos <xref:System.Windows.Forms.DataGridView> controles para mostrar información de dos tablas que tienen una relación principal-detalle.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Actualización para el Control DataGridView  
 Si tiene aplicaciones existentes que utilicen el <xref:System.Windows.Forms.DataGrid> control en un escenario enlazado a datos sencillo sin personalizaciones, simplemente puede reemplazar el antiguo control con el nuevo control. Ambos controles utilizan la arquitectura de enlace de datos de Windows Forms estándar, por lo que el <xref:System.Windows.Forms.DataGridView> control mostrará los datos enlazados no necesitan configuraciones adicionales. Es posible que desee considerar que aprovecha las mejoras de enlace de datos, sin embargo, al enlazar los datos a un <xref:System.Windows.Forms.BindingSource> componente, que, a continuación, puede enlazar a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, consulte [componente BindingSource](bindingsource-component.md).  
  
 Dado que el <xref:System.Windows.Forms.DataGridView> control tiene una arquitectura totalmente nueva, no hay ninguna ruta de conversión sencilla que le permitirá usar <xref:System.Windows.Forms.DataGrid> personalizaciones con el <xref:System.Windows.Forms.DataGridView> control. Muchos <xref:System.Windows.Forms.DataGrid> personalizaciones no son necesarios con el <xref:System.Windows.Forms.DataGridView> controlar, sin embargo, debido a las funciones integradas disponibles en el nuevo control. Si ha creado tipos de columna personalizado para el <xref:System.Windows.Forms.DataGrid> control que se va a usar con el <xref:System.Windows.Forms.DataGridView> (control), tendrá que implementarlos de nuevo con la nueva arquitectura. Para obtener más información, consulte [personalizar el DataGridView Control de formularios de Windows](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Modos de selección en el control DataGridView de formularios Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
