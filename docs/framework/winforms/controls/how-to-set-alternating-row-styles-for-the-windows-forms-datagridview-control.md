---
title: "C&#243;mo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, estilos de fila"
  - "DataGridView (control) [Windows Forms], estilos de fila"
  - "filas, cuadrículas de datos"
ms.assetid: 699ef759-458c-426d-ac87-7c7e71b018ae
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms
Los datos tabulares suelen presentarse a los usuarios en un formato de doble carta en el que las filas alternas tienen distintos colores de fondo.  Este formato permite a los usuarios saber fácilmente qué celdas están en cada fila, especialmente con tablas anchas que tienen muchas columnas.  
  
 Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar la información de estilo completa para las filas alternas.  Esto permite usar características de estilo tales como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Establecer estilos de fila alternos en el control DataGridView de Windows Forms mediante el diseñador](http://msdn.microsoft.com/library/3z9sk148%20\(v=vs.110\)).  
  
### Para establecer estilos de fila alternos mediante programación  
  
-   Establezca las propiedades de los objetos <xref:System.Windows.Forms.DataGridViewCellStyle> devueltos por las propiedades <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> de <xref:System.Windows.Forms.DataGridView>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#068)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#068](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#068)]  
  
    > [!NOTE]
    >  Los estilos especificados con las propiedades <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> y <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A> invalidan los estilos especificados en el nivel de columna y de <xref:System.Windows.Forms.DataGridView>, pero son invalidados por los estilos establecidos en el nivel de cada fila y celda.  Para obtener más información, consulte [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Programación eficaz  
 Para conseguir la máxima escalabilidad, debe compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento por separado.  Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer estilos de colores y fuentes en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)