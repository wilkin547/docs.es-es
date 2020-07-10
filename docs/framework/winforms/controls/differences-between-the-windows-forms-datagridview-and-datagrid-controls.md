---
title: Diferencias entre los controles DataGridView y DataGrid
description: Obtenga información sobre las distintas diferencias entre Windows Forms características de controles DataGridView y DataGrid, así como las diferencias en su arquitectura.
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms
- DataGrid control [Windows Forms], DataGridView control compared
- DataGridView control [Windows Forms], DataGrid control compared
ms.assetid: d412c786-140e-4210-8a56-a68467530a55
ms.openlocfilehash: 1438182d764097ae4f8fd7df046ad72c9213da19
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174593"
---
# <a name="differences-between-the-windows-forms-datagridview-and-datagrid-controls"></a>Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control es un nuevo control que reemplaza el <xref:System.Windows.Forms.DataGrid> control. El <xref:System.Windows.Forms.DataGridView> control proporciona numerosas características básicas y avanzadas que faltan en el <xref:System.Windows.Forms.DataGrid> control. Además, la arquitectura del <xref:System.Windows.Forms.DataGridView> control hace que sea mucho más fácil extender y personalizar que el <xref:System.Windows.Forms.DataGrid> control.  
  
 En la tabla siguiente se describen algunas de las características principales disponibles en el <xref:System.Windows.Forms.DataGridView> control que faltan en el <xref:System.Windows.Forms.DataGrid> control.  
  
|Característica de control DataGridView|Descripción|  
|----------------------------------|-----------------|  
|Varios tipos de columna|El <xref:System.Windows.Forms.DataGridView> control proporciona más tipos de columna integrados que el <xref:System.Windows.Forms.DataGrid> control. Estos tipos de columna satisfacen las necesidades de los escenarios más comunes, pero también son más fáciles de ampliar o reemplazar que los tipos de columna del <xref:System.Windows.Forms.DataGrid> control. Para obtener más información, vea [tipos de columna en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md).|  
|Varias formas de Mostrar datos|El <xref:System.Windows.Forms.DataGrid> control está limitado a mostrar los datos de un origen de datos externo. <xref:System.Windows.Forms.DataGridView>Sin embargo, el control puede mostrar los datos no enlazados almacenados en el control, los datos de un origen de datos enlazado, o los datos enlazados y sin enlazar juntos. También puede implementar el modo virtual en el <xref:System.Windows.Forms.DataGridView> control para proporcionar administración de datos personalizada. Para obtener más información, vea [modos de presentación de datos en el control DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).|  
|Varias maneras de personalizar la presentación de datos|El <xref:System.Windows.Forms.DataGridView> control proporciona muchas propiedades y eventos que le permiten especificar cómo se da formato a los datos y cómo se muestran. Por ejemplo, puede cambiar la apariencia de las celdas, filas y columnas en función de los datos que contienen, o puede reemplazar los datos de un tipo de datos por datos equivalentes de otro tipo. Para obtener más información, vea [formato de datos en el control DataGridView de Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md).|  
|Varias opciones para cambiar la apariencia y el comportamiento de las celdas, filas, columnas y encabezados|El <xref:System.Windows.Forms.DataGridView> control le permite trabajar con componentes de cuadrícula individuales de varias maneras. Por ejemplo, puede inmovilizar filas y columnas para evitar que se desplacen; ocultar filas, columnas y encabezados; cambiar la manera en que se ajustan los tamaños de fila, columna y encabezado; cambiar la manera en que los usuarios realizan selecciones; y proporcionan información sobre herramientas y menús contextuales para celdas, filas y columnas individuales.|  
  
 El <xref:System.Windows.Forms.DataGrid> control se conserva por compatibilidad con versiones anteriores y para las necesidades especiales. Para casi todos los propósitos, debe utilizar el <xref:System.Windows.Forms.DataGridView> control. La única característica que está disponible en el <xref:System.Windows.Forms.DataGrid> control que no está disponible en el <xref:System.Windows.Forms.DataGridView> control es la presentación jerárquica de información de dos tablas relacionadas en un único control. Debe utilizar dos <xref:System.Windows.Forms.DataGridView> controles para mostrar información de dos tablas que se encuentran en una relación principal-detalle.  
  
## <a name="upgrading-to-the-datagridview-control"></a>Actualizar al control DataGridView  
 Si tiene aplicaciones existentes que usan el <xref:System.Windows.Forms.DataGrid> control en un escenario simple enlazado a datos sin personalizaciones, puede reemplazar simplemente el control anterior por el nuevo control. Ambos controles usan la arquitectura de enlace de datos estándar Windows Forms, por lo que el <xref:System.Windows.Forms.DataGridView> control mostrará los datos enlazados sin necesidad de configuración adicional. Sin embargo, es posible que desee aprovechar las mejoras de enlace de datos enlazando los datos a un <xref:System.Windows.Forms.BindingSource> componente, que puede enlazar al <xref:System.Windows.Forms.DataGridView> control. Para obtener más información, vea [BindingSource (componente](bindingsource-component.md)).  
  
 Dado <xref:System.Windows.Forms.DataGridView> que el control tiene una arquitectura completamente nueva, no hay ninguna ruta de acceso de conversión sencilla que le permita utilizar <xref:System.Windows.Forms.DataGrid> personalizaciones con el <xref:System.Windows.Forms.DataGridView> control. <xref:System.Windows.Forms.DataGrid>Sin embargo, muchas personalizaciones no son necesarias con el <xref:System.Windows.Forms.DataGridView> control, debido a las características integradas disponibles en el nuevo control. Si ha creado tipos de columna personalizados para el <xref:System.Windows.Forms.DataGrid> control que desea usar con el <xref:System.Windows.Forms.DataGridView> control, tendrá que implementarlos de nuevo con la nueva arquitectura. Para obtener más información, vea [personalizar el control DataGridView Windows Forms](customizing-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGrid>
- <xref:System.Windows.Forms.BindingSource>
- [Control DataGridView](datagridview-control-windows-forms.md)
- [Control DataGrid](datagrid-control-windows-forms.md)
- [Componente BindingSource](bindingsource-component.md)
- [Tipos de columnas en el control DataGridView de formularios Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de formularios Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de formularios Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Formato de datos en el control DataGridView de formularios Windows Forms](data-formatting-in-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
- [Modos de ordenación de columnas del control DataGridView de formularios Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Modos de selección en el control DataGridView de formularios Windows Forms](selection-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizar el control DataGridView de formularios Windows Forms](customizing-the-windows-forms-datagridview-control.md)
