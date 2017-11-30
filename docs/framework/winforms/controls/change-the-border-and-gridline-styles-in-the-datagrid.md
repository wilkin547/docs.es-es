---
title: "Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- gridlines [Windows Forms], changing styles
- data grids [Windows Forms], changing gridline styles
- DataGridView control [Windows Forms], border styles
- data grids [Windows Forms], changing border styles
- DataGridView control [Windows Forms], gridline styles
ms.assetid: 2f413c7a-4025-4171-8e3a-66ef908ea583
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ebe73e0c29a211e3319998ef7acd14e78e4eb14
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-border-and-gridline-styles-in-the-windows-forms-datagridview-control"></a>Cómo: Cambiar los estilos de borde y línea de la cuadrícula en el control DataGridView de formularios Windows Forms
Con el <xref:System.Windows.Forms.DataGridView> control, puede personalizar la apariencia del borde del control y el líneas de cuadrícula para mejorar la experiencia del usuario. Puede modificar el color de las líneas de cuadrícula y el estilo de borde del control además de los estilos de borde para las celdas de dentro del control. También puede aplicar estilos de borde de celda diferentes para las celdas normales, las celdas de encabezado de fila y las celdas de encabezado de columna.  
  
> [!NOTE]
>  El color de las líneas de cuadrícula se utiliza únicamente con el <xref:System.Windows.Forms.DataGridViewCellBorderStyle.Single>, <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleHorizontal>, y <xref:System.Windows.Forms.DataGridViewCellBorderStyle.SingleVertical> valores de la <xref:System.Windows.Forms.DataGridViewCellBorderStyle> enumeración y <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle.Single> valor de la <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle> enumeración. Los demás valores de estas enumeraciones utilizan los colores especificados por el sistema operativo. Además, cuando los estilos visuales están habilitados en Windows XP y la familia de Windows Server 2003 a través de la <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> método, el <xref:System.Windows.Forms.DataGridView.GridColor%2A> no se utiliza el valor de propiedad.  
  
### <a name="to-change-the-gridline-color-programmatically"></a>Para cambiar el color de las líneas de cuadrícula mediante programación  
  
-   Establecer la propiedad <xref:System.Windows.Forms.DataGridView.GridColor%2A>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#031)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#031](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#031)]  
  
### <a name="to-change-the-border-style-of-the-entire-datagridview-control-programmatically"></a>Para cambiar el estilo de borde de todo el control DataGridView mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridView.BorderStyle%2A> en uno de los valores de enumeración <xref:System.Windows.Forms.BorderStyle>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#032)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#032](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#032)]  
  
### <a name="to-change-the-border-styles-for-datagridview-cells-programmatically"></a>Para cambiar los estilos de borde para las celdas de DataGridView mediante programación  
  
-   Establecer el <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A>, <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A>, y <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A> propiedades.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#033)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#033](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#033)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#030)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#030](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#030)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.BorderStyle>  
 <xref:System.Windows.Forms.DataGridView.BorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ColumnHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.GridColor%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.RowHeadersBorderStyle%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCellBorderStyle>  
 <xref:System.Windows.Forms.DataGridViewHeaderBorderStyle>  
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
