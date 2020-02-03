---
title: Diferencias entre los controles DataGridView y DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 3552abe55d8e2c1cb4ae372ca64c7ca21f1fed0e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745956"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Diferencias entre los controles DataGridView y DataGrid de Windows Forms
El control <xref:System.Windows.Forms.DataGridView> es un nuevo control que reemplaza el control <xref:System.Windows.Forms.DataGrid>. El control <xref:System.Windows.Forms.DataGridView> proporciona numerosas características básicas y avanzadas que faltan en el control <xref:System.Windows.Forms.DataGrid>. Además, la arquitectura del control <xref:System.Windows.Forms.DataGridView> hace que sea mucho más fácil extender y personalizar que el control <xref:System.Windows.Forms.DataGrid>.  
  
 En la tabla siguiente se describen algunas de las características principales disponibles en el control <xref:System.Windows.Forms.DataGridView> que faltan en el control <xref:System.Windows.Forms.DataGrid>.  
  
|Característica de control DataGridView|Descripción|  
|----------------------------------|-----------------|  
|Varios tipos de columna|El control <xref:System.Windows.Forms.DataGridView> proporciona más tipos de columna integrados que el control <xref:System.Windows.Forms.DataGrid>. Estos tipos de columna satisfacen las necesidades de los escenarios más comunes, pero también son más fáciles de ampliar o reemplazar que los tipos de columna del control <xref:System.Windows.Forms.DataGrid>. Para obtener más información, vea [tipos de columna en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Varias formas de Mostrar datos|El control <xref:System.Windows.Forms.DataGrid> se limita a mostrar los datos de un origen de datos externo. Sin embargo, el control <xref:System.Windows.Forms.DataGridView> puede mostrar los datos no enlazados almacenados en el control, los datos de un origen de datos enlazado, o los datos enlazados y sin enlazar juntos. También puede implementar el modo virtual en el control <xref:System.Windows.Forms.DataGridView> para proporcionar administración de datos personalizada. Para obtener más información, vea [modos de presentación de datos en el control DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de personalizar la presentación de datos|El control <xref:System.Windows.Forms.DataGridView> proporciona muchas propiedades y eventos que le permiten especificar cómo se da formato a los datos y cómo se muestran. Por ejemplo, puede cambiar la apariencia de las celdas, filas y columnas en función de los datos que contienen, o puede reemplazar los datos de un tipo de datos por datos equivalentes de otro tipo. Para obtener más información, vea [formato de datos en el control DataGridView de Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Varias opciones para cambiar la apariencia y el comportamiento de las celdas, filas, columnas y encabezados|El control <xref:System.Windows.Forms.DataGridView> permite trabajar con componentes de cuadrícula individuales de varias maneras. Por ejemplo, puede inmovilizar filas y columnas para evitar que se desplacen; ocultar filas, columnas y encabezados; cambiar la manera en que se ajustan los tamaños de fila, columna y encabezado; cambiar la manera en que los usuarios realizan selecciones; y proporcionan información sobre herramientas y menús contextuales para celdas, filas y columnas individuales.|  
  
 El control <xref:System.Windows.Forms.DataGrid> se conserva por compatibilidad con versiones anteriores y para las necesidades especiales. En casi todos los casos, debe usar el control <xref:System.Windows.Forms.DataGridView>. La única característica que está disponible en el control <xref:System.Windows.Forms.DataGrid> que no está disponible en el control de <xref:System.Windows.Forms.DataGridView> es la presentación jerárquica de información de dos tablas relacionadas en un único control. Debe utilizar dos controles <xref:System.Windows.Forms.DataGridView> para mostrar información de dos tablas que se encuentran en una relación principal-detalle.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Actualizar al control DataGridView  
 Si tiene aplicaciones existentes que usan el control de <xref:System.Windows.Forms.DataGrid> en un escenario de enlace de datos simple sin personalizaciones, puede reemplazar simplemente el control anterior por el nuevo control. Ambos controles usan la arquitectura de enlace de datos estándar Windows Forms, por lo que el control <xref:System.Windows.Forms.DataGridView> mostrará los datos enlazados sin necesidad de configuración adicional. Sin embargo, es posible que desee aprovechar las mejoras de enlace de datos enlazando los datos a un componente de <xref:System.Windows.Forms.BindingSource>, que puede enlazar a la <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [BindingSource (componente](bindingsource-component.md)).  
  
 Dado que el control de <xref:System.Windows.Forms.DataGridView> tiene una arquitectura completamente nueva, no hay ninguna ruta de conversión sencilla que le permita usar las personalizaciones de <xref:System.Windows.Forms.DataGrid> con el control de <xref:System.Windows.Forms.DataGridView>. Sin embargo, muchas de las personalizaciones de <xref:System.Windows.Forms.DataGrid> no son necesarias con el control <xref:System.Windows.Forms.DataGridView>, debido a las características integradas disponibles en el nuevo control. Si ha creado tipos de columna personalizados para el control <xref:System.Windows.Forms.DataGrid> que desea utilizar con el control <xref:System.Windows.Forms.DataGridView>, tendrá que implementarlos de nuevo con la nueva arquitectura. Para obtener más información, vea [personalizar el control DataGridView Windows Forms](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Consulte también

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
