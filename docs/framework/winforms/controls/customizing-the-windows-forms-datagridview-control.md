---
title: Personalizar el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 1f9c68ae85d7bad2b8cdcdaa63c1e7b46f9568ed
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703340"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a>Personalizar el control DataGridView de formularios Windows Forms
El `DataGridView` control proporciona varias propiedades que puede usar para ajustar la apariencia y comportamiento básico (apariencia) de sus celdas, filas y columnas. Si tiene necesidades especiales que van más allá de las capacidades de la <xref:System.Windows.Forms.DataGridViewCellStyle> class, sin embargo, también puede implementar para el control de dibujo del propietario o ampliar sus capacidades mediante la creación personalizadas celdas, columnas y filas.  
  
 Para pintar las celdas y filas usted mismo, puede controlar varios `DataGridView` eventos de dibujo. Para modificar la funcionalidad existente o proporcionar nueva funcionalidad, puede crear sus propios tipos derivados de las existentes `DataGridViewCell`, `DataGridViewColumn`, y `DataGridViewRow` tipos. También puede proporcionar nuevas capacidades de edición mediante la creación de tipos derivados que muestran un control de su elección cuando una celda está en modo de edición.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Personalizar la apariencia de celdas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-cells-in-the-datagrid.md)  
 Describe cómo controlar la <xref:System.Windows.Forms.DataGridView.CellPainting> eventos con el fin de dibujar celdas manualmente.  
  
 [Cómo: Personalizar la apariencia de las filas en el Control DataGridView de formularios de Windows](customize-the-appearance-of-rows-in-the-datagrid.md)  
 Describe cómo controlar la <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> eventos con el fin de dibujar filas con un fondo personalizado, degradado y contenido que abarca varias columnas.  
  
 [Cómo: Personalizar celdas y columnas en el Control DataGridView de Windows Forms ampliando su comportamiento y apariencia](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Describe cómo crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` con el fin de resaltar celdas cuando el puntero del mouse se sitúa sobre ellos.  
  
 [Cómo: Deshabilitar botones en una columna de botones en el Control DataGridView de formularios de Windows](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Describe cómo crear tipos personalizados derivados de <xref:System.Windows.Forms.DataGridViewButtonCell> y <xref:System.Windows.Forms.DataGridViewButtonColumn> con el fin de mostrar los botones deshabilitados en una columna de botones.  
  
 [Cómo: Hospedar controles en celdas DataGridView de Windows Forms](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Describe cómo implementar la `IDataGridViewEditingControl` interfaz y crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` con el fin de mostrar un <xref:System.Windows.Forms.DateTimePicker> controlar cuando una celda está en modo de edición.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewCell> clase.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewRow> clase.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Proporciona documentación de referencia para la <xref:System.Windows.Forms.DataGridViewColumn> clase.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Proporciona documentación de referencia para el <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaz.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas que describen cómo modificar la apariencia básica del control y el formato de presentación de los datos de celda.  
  
## <a name="see-also"></a>Vea también
- [DataGridView (control)](datagridview-control-windows-forms.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
