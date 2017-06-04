---
title: "C&#243;mo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, estilos de color"
  - "cuadrículas de datos, personalizar celdas"
  - "cuadrículas de datos, estilos de fuente"
  - "DataGridView (control) [Windows Forms], personalización de celdas"
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms
Para especificar la apariencia visual de las celdas dentro de un control <xref:System.Windows.Forms.DataGridView>, establezca las propiedades de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>.  Puede recuperar instancias de esta clase desde distintas propiedades de la clase <xref:System.Windows.Forms.DataGridView> y sus clases complementarias, o puede crear instancias de objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para la asignación de estas propiedades.  
  
 Los procedimientos siguientes muestran cómo realizar una personalización básica de la apariencia de las celdas mediante la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>.  Cada celda del control hereda los estilos especificados mediante esta propiedad, a menos que se invaliden en el nivel de celda, fila o columna.  Para obtener un ejemplo de herencia de estilos, consulte [Cómo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md).  Para obtener información sobre otros adicionales de la clase <xref:System.Windows.Forms.DataGridViewCellStyle>, consulte los temas de la sección Consulte también.  
  
 Visual Studio es altamente compatible con esta tarea.  Consulte también [Cómo: Establecer estilos de celda y formatos de datos predeterminados para el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/95y5fz2x%20\(v=vs.110\)).  
  
### Para especificar la fuente que usan las celdas de DataGridView  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.  El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> para establecer la fuente para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### Para especificar los colores de primer plano y de fondo de las celdas de DataGridView  
  
-   Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.  El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### Para especificar los colores de primer plano y de fondo de las celdas seleccionadas de DataGridView  
  
-   Establezca las propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> y <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> de un <xref:System.Windows.Forms.DataGridViewCellStyle>.  El siguiente ejemplo de código usa la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName> para establecer estos estilos para todo el control.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Programación eficaz  
 Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado.  Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)