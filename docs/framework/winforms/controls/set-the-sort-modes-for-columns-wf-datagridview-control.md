---
title: Procedimiento Establecer modos de ordenación de columnas en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 43ee1f43dfed0a9612ef0b460e5633262c9b6a5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674890"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Procedimiento Establecer modos de ordenación de columnas en el Control DataGridView de Windows Forms
En el <xref:System.Windows.Forms.DataGridView> las columnas del cuadro de texto de control, utilizan la clasificación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente. A veces desea invalidar estos valores predeterminados. Por ejemplo, puede mostrar imágenes en lugar de texto, números o valores de celda de la enumeración. Mientras no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.  
  
 En el <xref:System.Windows.Forms.DataGridView> (control), el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de propiedad de una columna determina su comportamiento de ordenación.  
  
 El procedimiento siguiente se muestra el `Priority` columna desde [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Esta columna es una columna de imagen y no se puede ordenar de forma predeterminada. Contiene valores de celda reales que son cadenas, sin embargo, por lo que pueden ordenarse automáticamente.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Para establecer el modo de ordenación para una columna  
  
-   Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Ordenar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)
- [Modos de ordenación de columnas del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Cómo: Personalizar la ordenación en el Control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
