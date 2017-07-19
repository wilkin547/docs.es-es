---
title: "C&#243;mo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, estilos"
  - "cuadrículas de datos, estilos de celda"
  - "DataGridView (control) [Windows Forms], estilos de celda"
ms.assetid: 1aaaca43-5340-447e-99c0-9177d9776aa1
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms
Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar los estilos de celda predeterminados para todo el control y para columnas y filas específicas.  Estos valores predeterminados filtran desde el nivel de control al nivel de columna, después al nivel de fila y, después, al nivel de celda.  Si una determinada propiedad <xref:System.Windows.Forms.DataGridViewCellStyle> no está establecida en el nivel de celda, se usa el valor de propiedad predeterminado en el nivel de fila.  Si la propiedad tampoco está establecida en el nivel de fila, se usa el valor de columna predeterminado.  Por último, si la propiedad tampoco está establecida en el nivel de columna, se usa el valor predeterminado de <xref:System.Windows.Forms.DataGridView>.  Con esta configuración, puede evitar tener que duplicar los valores de propiedad en varios niveles.  En cada nivel, simplemente hay que especificar los estilos que difieren de los niveles situados por encima de él.  Para obtener más información, consulte [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 Visual Studio es altamente compatible con esta tarea.  Consulte también [Cómo: Establecer estilos de celda y formatos de datos predeterminados para el control DataGridView de Windows Forms mediante el Diseñador](http://msdn.microsoft.com/library/95y5fz2x%20\(v=vs.110\)).  
  
### Para establecer los estilos de celda predeterminados mediante programación  
  
1.  Establezca las propiedades del <xref:System.Windows.Forms.DataGridViewCellStyle> recuperado a través de la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#141)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#141](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#141)]  
  
2.  Cree e inicialice los nuevos objetos <xref:System.Windows.Forms.DataGridViewCellStyle> para que los usen varias filas y columnas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#142)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#142](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#142)]  
  
3.  Establezca la propiedad `DefaultCellStyle` de filas y columnas específicas.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#143)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#143](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#143)]  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#140)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#140](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#140)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Drawing?displayProperty=fullName> y <xref:System.Windows.Forms?displayProperty=fullName>.  
  
## Programación eficaz  
 Para lograr la máxima escalabilidad al trabajar con conjuntos de datos muy grandes, se recomienda compartir objetos <xref:System.Windows.Forms.DataGridViewCellStyle> entre varias filas, columnas o celdas que usen los mismos estilos, en lugar de establecer las propiedades de estilo de cada elemento individual por separado.  Además, debe crear filas compartidas y acceder a ellas mediante la propiedad <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=fullName>.  Para obtener más información, consulte [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewCellStyle>   
 <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewBand.DefaultCellStyle%2A?displayProperty=fullName>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/best-practices-for-scaling-the-windows-forms-datagridview-control.md)   
 [Cómo: Establecer estilos de fila alternos para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)