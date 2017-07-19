---
title: "C&#243;mo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "celdas, personalizar en el control DataGridView"
  - "cuadrículas de datos, personalizar celdas"
  - "DataGridView (control) [Windows Forms], personalizar celdas"
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms
Puede personalizar la apariencia de cualquier celda mediante el control del evento <xref:System.Windows.Forms.DataGridView.CellPainting> del control <xref:System.Windows.Forms.DataGridView>.  Puede extraer el <xref:System.Drawing.Graphics> del control <xref:System.Windows.Forms.DataGridView> de la propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> de <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>.  Con <xref:System.Drawing.Graphics>, puede modificar la apariencia de todo el control <xref:System.Windows.Forms.DataGridView>, pero normalmente querrá modificar sólo a la apariencia de la celda que se está pintando actualmente.  La propiedad <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> de <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir sus operaciones de representación a la celda que está pintando.  
  
 En el ejemplo de código siguiente, pintará todas las celdas en una columna `ContactName` mediante la combinación de colores del control <xref:System.Windows.Forms.DataGridView>.  El contenido de texto de cada celda se pinta en la propiedad <xref:System.Drawing.Color.Crimson%2A> y se dibuja un rectángulo de bajorrelieve en el mismo color que la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A> del control <xref:System.Windows.Forms.DataGridView>.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna `ContactName` como la de la tabla Customers de la base de datos de ejemplo Northwind.  
  
-   Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.CellPainting>   
 [Personalizar el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)