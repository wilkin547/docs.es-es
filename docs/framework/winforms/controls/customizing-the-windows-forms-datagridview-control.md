---
title: "Personalizar el control DataGridView de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, personalización"
  - "DataGridView (control) [Windows Forms], personalización"
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Personalizar el control DataGridView de formularios Windows Forms
El control `DataGridView` proporciona varias propiedades que puede utilizar para ajustar la apariencia y el comportamiento básico \(el aspecto y el diseño\) de sus celdas, filas y columnas.  Si tiene necesidades especiales que van más allá de los recursos de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, no obstante, puede implementar también el dibujo por el usuario para el control o ampliar sus recursos creando celdas, columnas y filas personalizadas.  
  
 Para dibujar mismo celdas y filas, puede controlar distintos eventos Paint `DataGridView`.  Para modificar la funcionalidad existente o proporcionar una nueva, puede crear sus propios tipos derivados de los tipos `DataGridViewCell``DataGridViewColumn`y `DataGridViewRow` existentes.  También puede proporcionar nuevos recursos creando tipos derivados que muestran un control de su elección cuando una celda está en modo de edición.  
  
## En esta sección  
 [Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 Describe cómo controlar el evento <xref:System.Windows.Forms.DataGridView.CellPainting> para dibujar manualmente las celdas.  
  
 [Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 Describe cómo controlar los eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint> y <xref:System.Windows.Forms.DataGridView.RowPostPaint> para dibujar filas con un fondo degradado personalizado y contenido que abarca varias columnas.  
  
 [Cómo: Personalizar celdas y columnas en el control DataGridView de formularios Windows Forms ampliando su comportamiento y apariencia](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 Describe cómo crear los tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para resaltar las celdas cuando el puntero del mouse se encuentra sobre ellas.  
  
 [Cómo: Deshabilitar botones en una columna de botones del control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 Describe cómo crear tipos personalizados derivados de <xref:System.Windows.Forms.DataGridViewButtonCell> y <xref:System.Windows.Forms.DataGridViewButtonColumn> para mostrar los botones deshabilitados en una columna de botón.  
  
 [Cómo: Alojar controles en celdas DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 Describe cómo implementar la interfaz `IDataGridViewEditingControl` y crear tipos personalizados derivados de `DataGridViewCell` y `DataGridViewColumn` para mostrar un control <xref:System.Windows.Forms.DateTimePicker> cuando una celda está en modo de edición.  
  
## Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewCell>.  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewRow>.  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewColumn>.  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 Proporciona documentación de referencia para la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
## Secciones relacionadas  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 Proporciona temas en los que se describe cómo modificar la apariencia básica del control y el formato de presentación de los datos de las celdas.  
  
## Vea también  
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)   
 [Tipos de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)