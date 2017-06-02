---
title: "Estilo y formato b&#225;sicos del control DataGridView en formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cuadrículas de datos, aplicar formato"
  - "DataGridView (control) [Windows Forms], aplicar formato y estilo"
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# Estilo y formato b&#225;sicos del control DataGridView en formularios Windows Forms
El control `DataGridView` facilita definir la apariencia básica de celdas y el formato de presentación de los valores de celda.  Puede definir la apariencia y los estilos de formato para celdas individuales, para celdas de columnas y filas concretas o para todas las celdas del control estableciendo las propiedades de los objetos `DataGridViewCellStyle` a las que se obtiene acceso a través de distintas propiedades del control `DataGridView`.  Además, puede modificar dinámicamente estos estilos basándose en factores como el valor de celda controlando el evento `CellFormatting`.  
  
## En esta sección  
 [Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/change-the-border-and-gridline-styles-in-the-datagrid.md)  
 Describe cómo establecer propiedades `DataGridView` que definen la apariencia del borde del control y las lineas de límite entre las celdas.  
  
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 Describe la clase `DataGridViewCellStyle` y cómo interactúan las propiedades de ese tipo para definir cómo se muestran las celdas en el control.  
  
 [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar las propiedades de `DataGridViewCellStyle` para definir la apariencia predeterminada de celdas en filas y columnas concretas y en el control completo.  
  
 [Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 Describe cómo dar formato a valores de presentación de celdas utilizando las propiedades de `DataGridViewCellStyle`.  
  
 [Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 Describe cómo utilizar la propiedad `DefaultCellStyle` para establecer las características de presentación básicas para todas las celdas del control.  
  
 [Cómo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 Describe cómo crear un efecto como de doble carta en el control con filas alternativas que se muestran de manera distinta.  
  
 [Cómo: Utilizar la plantilla de filas para personalizar filas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 Describe cómo utilizar la propiedad `RowTemplate` para establecer propiedades de fila que se utilizarán para todas las filas del control.  
  
## Referencia  
 <xref:System.Windows.Forms.DataGridView>  
 Proporciona documentación de referencia para el control <xref:System.Windows.Forms.DataGridView>.  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 Proporciona documentación de referencia para la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 Proporciona documentación de referencia para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 Proporciona documentación de referencia para la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.  
  
## Secciones relacionadas  
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 Proporciona temas en los que se describe el dibujo personalizado de celdas y filas de <xref:System.Windows.Forms.DataGridView>, así como la creación de tipos derivados de celda, columna y fila.  
  
 [Características básicas de columnas, filas y celdas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 Proporciona temas que describen las propiedades de celda, fila y columna más utilizadas.  
  
## Vea también  
 [Control DataGridView](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)