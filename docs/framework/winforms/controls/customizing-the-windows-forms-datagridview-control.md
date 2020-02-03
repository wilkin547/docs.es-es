---
title: Personalizar el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744027"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizar el control DataGridView de formularios Windows Forms
El control `DataGridView` proporciona varias propiedades que puede usar para ajustar la apariencia y el comportamiento básico (apariencia y funcionamiento) de sus celdas, filas y columnas. Sin embargo, si tiene necesidades especiales que van más allá de las capacidades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, también puede implementar el dibujo del propietario para el control o ampliar sus capacidades creando celdas, columnas y filas personalizadas.  
  
 Para pintar las celdas y las filas usted mismo, puede controlar diversos eventos de dibujo de `DataGridView`. Para modificar la funcionalidad existente o proporcionar una nueva funcionalidad, puede crear sus propios tipos derivados de los tipos de `DataGridViewCell`, `DataGridViewColumn`y `DataGridViewRow` existentes. También puede proporcionar nuevas capacidades de edición creando tipos derivados que muestren un control de su elección cuando una celda está en modo de edición.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimiento para personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Describe cómo controlar el evento <xref:System.Windows.Forms.DataGridView.CellPainting> para pintar celdas manualmente.  
  
 [Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Describe cómo controlar los eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> para pintar filas con un fondo de degradado personalizado y contenido que abarca varias columnas.  
  
 [Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Describe cómo crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para resaltar las celdas cuando el puntero del mouse se sitúa sobre ellas.  
  
 [Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Describe cómo crear tipos personalizados derivados de <xref:System.Windows.Forms.DataGridViewButtonCell> y <xref:System.Windows.Forms.DataGridViewButtonColumn> para mostrar botones deshabilitados en una columna de botón.  
  
 [Alojar controles en celdas DataGridView de formularios Windows Forms](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Describe cómo implementar la interfaz de `IDataGridViewEditingControl` y crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para mostrar un control de <xref:System.Windows.Forms.DateTimePicker> cuando una celda está en modo de edición.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewCell>.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewRow>.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Proporciona documentación de referencia para la interfaz de <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.  
  
## <a name="see-also"></a>Consulte también

- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
