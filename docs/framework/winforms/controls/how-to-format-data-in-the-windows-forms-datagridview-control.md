---
title: "C&#243;mo: Dar formato a datos en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, alineación de texto"
  - "valores actuales, aplicar formato en cuadrículas de datos"
  - "datos [Windows Forms], aplicar formato en el control DataGridView"
  - "cuadrículas de datos, valores actuales"
  - "cuadrículas de datos, valores de fecha"
  - "cuadrículas de datos, habilitar ajuste de línea"
  - "cuadrículas de datos, aplicar formato a datos"
  - "cuadrículas de datos, alineación de texto"
  - "DataGridView (control) [Windows Forms], aplicar formato a datos"
ms.assetid: 8c33543c-9c08-4636-a65a-fdf714a529b7
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Dar formato a datos en el control DataGridView de formularios Windows Forms
Los procedimientos siguientes muestran el formato básico de los valores de celda mediante la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A> de un control <xref:System.Windows.Forms.DataGridView> y de columnas determinadas en un control.  Para obtener información sobre el formato avanzado de datos, vea [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
### Para dar formato a valores de divisa y fecha  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de un control <xref:System.Windows.Forms.DataGridViewCellStyle>.  En el ejemplo de código siguiente se establece el formato para columnas determinadas mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> de las columnas.  Los valores de la columna  `UnitPrice`  aparecen en el formato de divisa específico de la referencia cultural actual, con valores negativos rodeados por paréntesis.  Los valores de la columna  `ShipDate`  aparecen en el formato de fecha breve específico de la referencia cultural actual.  Para obtener más información acerca de los valores de <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A>, vea [Aplicar formato a tipos](../../../../docs/standard/base-types/formatting-types.md).  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#071)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#071](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#071)]  
  
### Para personalizar la presentación de valores de base de datos null  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.NullValue%2A> de un control <xref:System.Windows.Forms.DataGridViewCellStyle>.  En el ejemplo de código siguiente se utiliza la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> para mostrar "ninguna entrada" en todas las celdas que contienen valores iguales a <xref:System.DBNull.Value?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#073)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#073](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#073)]  
  
### Para habilitar el ajuste automático de líneas en celdas basadas en texto  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.WrapMode%2A> de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los valores de enumeración de <xref:System.Windows.Forms.DataGridViewTriState>.  En el ejemplo de código siguiente se utiliza la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> para establecer el modo de ajuste para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#074)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#074](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#074)]  
  
### Para especificar la alineación del texto de celdas de DataGridView  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Alignment%2A> de <xref:System.Windows.Forms.DataGridViewCellStyle> en uno de los valores de enumeración de <xref:System.Windows.Forms.DataGridViewContentAlignment>.  En el ejemplo de código siguiente se establece la alineación para una columna concreta utilizando la propiedad <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> de la columna.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#072)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#072](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#072)]  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#070)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#070](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#070)]  
  
## Compilar el código  
 Estos ejemplos necesitan:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` que contiene una columna denominada `UnitPrice`, una columna denominada `ShipDate` y una columna denominada `CustomerName`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Programación eficaz  
 Para conseguir una máxima escalabilidad, se deben compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre las distintas filas, columnas o celdas que utilicen los mismos estilos, en lugar de establecer por separado las propiedades de estilo para cada elemento.  Para obtener más información, vea [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Formato de datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Cómo: Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)   
 [Aplicar formato a tipos](../../../../docs/standard/base-types/formatting-types.md)