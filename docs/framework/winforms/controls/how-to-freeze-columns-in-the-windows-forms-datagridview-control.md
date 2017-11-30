---
title: "Cómo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms"
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
- columns [Windows Forms], freezing
- DataGridView control [Windows Forms], freezing columns
- DataGridView control [Windows Forms], columns always in view
ms.assetid: 2ef8b1de-782e-4867-af8d-58171ab5c106
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: baf2b0218c1818d6a92ca7790c8c50bd94ecfd9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-freeze-columns-in-the-windows-forms-datagridview-control"></a>Cómo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms
Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de Windows Forms, a veces deben hacer referencia a una sola columna o a un conjunto de columnas con frecuencia. Por ejemplo, cuando se muestra una tabla de información de clientes que contiene muchas columnas, resulta útil mostrar el nombre del cliente y dejar que otras columnas puedan desplazarse fuera del área visible.  
  
 Para conseguir este comportamiento, puede inmovilizar las columnas en el control. Al inmovilizar una columna, también se inmovilizan todas las columnas situadas a su izquierda (o a su derecha en los scripts de idioma de derecha a izquierda). Las columnas inmovilizadas permanecen en su lugar mientras que todas las demás columnas se pueden desplazar.  
  
> [!NOTE]
>  Si se habilita la reordenación de columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas. Los usuarios pueden cambiar la ubicación de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.  
  
 La propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> de una columna determina si la columna es visible siempre dentro de la cuadrícula.  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Inmovilizar columnas en el Control Windows Forms DataGridView mediante el diseñador](http://msdn.microsoft.com/library/717ss6s6\(v=vs.110\)).  
  
### <a name="to-freeze-a-column-programmatically"></a>Para inmovilizar una columna mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#061)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#061](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#061)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `AddToCartButton`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView>  
 [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)
