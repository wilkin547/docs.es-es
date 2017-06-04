---
title: "Formato de datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "datos [Windows Forms], aplicar formato en cuadrículas"
  - "cuadrículas de datos, aplicar formato a datos"
  - "DataGridView (control) [Windows Forms], aplicar formato a datos"
ms.assetid: 07bf558d-3748-42ba-8ba0-37fdef924081
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Formato de datos en el control DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona la conversión automática entre los valores de celda y los tipos de datos que muestran las columnas primarias.  Por ejemplo, las columnas de cuadro de texto muestran representaciones de cadena de valores de fecha, hora, numéricos y enumeraciones, y convierten los valores de cadena introducidos por el usuario a los tipos requeridos por el almacén de datos.  
  
## Dar formato con la clase DataGridViewCellStyle  
 El control <xref:System.Windows.Forms.DataGridView> proporciona los datos básicos que dan formato a los valores de celda mediante la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  Se puede utilizar la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> para dar formato a los valores de fecha, hora, numéricos y de enumeración para la referencia cultural predeterminada actual mediante los especificadores de formato descritos en [Aplicar formato a tipos](../../../../docs/standard/base-types/formatting-types.md).  También se puede dar formato a estos valores para referencias culturales específicas mediante la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.FormatProvider%2A>.  El formato especificado se utiliza tanto para mostrar datos como para analizar los datos que introduce el usuario en el formato especificado.  
  
 La clase <xref:System.Windows.Forms.DataGridViewCellStyle> proporciona propiedades de formato adicionales para el ajuste automático de líneas, alineación del texto y la presentación personalizada de valores de base de datos NULL.  Para obtener más información, vea [Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md).  
  
## Dar formato con el evento CellFormatting  
 Si el formato básico no satisface sus necesidades, puede proporcionar formato de datos personalizados en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=fullName>.  El <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs> pasado al controlador tiene una propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> que inicialmente contiene el valor de celda.  Por lo general, este valor se convierte automáticamente en el tipo de presentación.  Para convertir el valor, establezca la propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> en un valor del tipo de presentación.  
  
> [!NOTE]
>  Si una cadena de formato está activa en la celda, reemplaza el cambio del valor de propiedad <xref:System.Windows.Forms.ConvertEventArgs.Value%2A> a no ser que se establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellFormattingEventArgs.FormattingApplied%2A> en `true`.  
  
 El evento <xref:System.Windows.Forms.DataGridView.CellFormatting> también es útil cuando desea establecer las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle> para celdas individuales basadas en sus valores.  Para obtener más información, vea [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
 Si el análisis predeterminado de valores especificados por el usuario no satisface sus necesidades, puede controlar el evento <xref:System.Windows.Forms.DataGridView.CellParsing> del control <xref:System.Windows.Forms.DataGridView> para proporcionar un análisis personalizado.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Mostrar datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Dar formato a datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-format-data-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)