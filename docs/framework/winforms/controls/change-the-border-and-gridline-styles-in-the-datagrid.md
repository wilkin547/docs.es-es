---
title: "C&#243;mo: Cambiar los estilos de borde y l&#237;nea de la cuadr&#237;cula en el control DataGridView de formularios Windows Forms | Microsoft Docs"
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
  - "cuadrículas de datos, cambiar estilos de borde"
  - "cuadrículas de datos, cambiar estilo de líneas de cuadrícula"
  - "DataGridView (control) [Windows Forms], estilos de borde"
  - "DataGridView (control) [Windows Forms], estilos de línea de cuadrícula"
  - "líneas de cuadrículas, cambiar estilos"
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Cambiar los estilos de borde y l&#237;nea de la cuadr&#237;cula en el control DataGridView de formularios Windows Forms
Con el control <xref:System.Windows.Forms.DataGridView>, se puede personalizar la apariencia del borde y de las líneas de la cuadrícula del control para mejorar la experiencia del usuario.  Se puede modificar además del color de la cuadrícula y el estilo de borde del control además de los estilos de borde de las celdas en el control.  También puede aplicar estilos de borde de celda diferentes para las celdas normales, celdas del encabezado de filas y celdas del encabezado de columnas.  
  
> [!NOTE]
>  El color de la línea de la cuadrícula se utiliza únicamente con los valores <xref:System.Windows.Forms.DataGridViewCellBorderStyle>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle> y <xref:System.Windows.Forms.DataGridViewCellBorderStyle> de la enumeración <xref:System.Windows.Forms.DataGridViewCellBorderStyle> y con el valor <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> de la enumeración <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>.  Los demás valores de estas enumeraciones utilizan los colores especificados por el sistema operativo.  Además, cuando se habilitan estilos visuales en Windows XP y en la familia Windows Server 2003 mediante el método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName>, no se utiliza el valor de propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.  
  
### Para cambiar mediante programación el color de la línea de la cuadrícula  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### Para cambiar mediante programación el estilo de borde de todo el control DataGridView  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> en uno de los valores de enumeración <xref:System.Windows.Forms.BorderStyle>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### Para cambiar mediante programación los estilos de borde para las celdas del control DataGridView  
  
-   Utilice las propiedades <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A> y <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=fullName>, <xref:System.Windows.Forms?displayProperty=fullName> y <xref:System.Drawing?displayProperty=fullName>.  
  
## Vea también  
 <xref:System.Windows.Forms.BorderStyle>   
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=fullName>   
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>   
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)