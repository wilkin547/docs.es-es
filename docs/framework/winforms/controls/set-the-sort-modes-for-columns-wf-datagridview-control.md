---
title: "Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms"
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
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a1c5b0447895b0ca5c67fff054d88da0d0107c5a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms
En el <xref:System.Windows.Forms.DataGridView> columnas del cuadro de texto de control, use la clasificación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente. En ocasiones, deseará invalidar estos valores predeterminados. Por ejemplo, puede mostrar imágenes en lugar de texto, números o valores de celda de enumeración. Mientras no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.  
  
 En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de la propiedad de una columna determina su comportamiento de ordenación.  
  
 El siguiente procedimiento se muestra la `Priority` columna de [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Esta columna es una columna de imagen y no se puede ordenar de forma predeterminada. Contiene valores de celda reales que son cadenas, sin embargo, por lo que se puede ordenar automáticamente.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Para establecer el modo de ordenación para una columna  
  
-   Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [Ordenar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Modos de ordenación de columnas del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [Personalizar la ordenación en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
