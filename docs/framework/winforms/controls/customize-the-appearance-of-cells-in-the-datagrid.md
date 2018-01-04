---
title: "Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms"
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
- data grids [Windows Forms], customizing cells
- DataGridView control [Windows Forms], customizing cells
- cells [Windows Forms], customizing in DataGridView control
ms.assetid: 478b20c9-625c-4116-9c5c-5a16e6f4ec67
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61b2a39943dfca412afa4b66265aabbf65b9ccf0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-customize-the-appearance-of-cells-in-the-windows-forms-datagridview-control"></a>Cómo: Personalizar la apariencia de las celdas en el control DataGridView de formularios Windows Forms
Puede personalizar la apariencia de cualquier celda controlando el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.CellPainting> eventos. Puede extraer el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Drawing.Graphics> desde el <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.Graphics%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs>. Con esto <xref:System.Drawing.Graphics>, pueden afectar a la apariencia de todo el <xref:System.Windows.Forms.DataGridView> control, pero normalmente es conveniente afectan únicamente a la apariencia de la celda que se está dibujando actualmente. El <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs.ClipBounds%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewCellPaintingEventArgs> le permite restringir las operaciones de dibujo a la celda que se está dibujando actualmente.  
  
 En el ejemplo de código siguiente, se dibujará todas las celdas en una `ContactName` de columna con el <xref:System.Windows.Forms.DataGridView> combinación de colores del control. El contenido de texto de cada celda se pinta en <xref:System.Drawing.Color.Crimson%2A>, y se dibuja un rectángulo de bajorrelieve en el mismo color que el <xref:System.Windows.Forms.DataGridView> del control <xref:System.Windows.Forms.DataGridView.GridColor%2A> propiedad.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/CS/form1.cs#10)]
 [!code-vb[System.Windows.Forms.DataGridViewCellPainting#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCellPainting/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   A <xref:System.Windows.Forms.DataGridView> control denominado `dataGridView1` con un `ContactName` columna como la de la tabla Customers de la base de datos de ejemplo Northwind.  
  
-   Referencias a los ensamblados System, System.Windows.Forms y System.Drawing.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.CellPainting>  
 [Personalizar el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)
