---
title: Establecer los modos de ordenación de las columnas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742999"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>Cómo: Establecer modos de ordenación de columnas en el control DataGridView de formularios Windows Forms
En el control <xref:System.Windows.Forms.DataGridView>, las columnas del cuadro de texto utilizan la ordenación automática de forma predeterminada, mientras que otros tipos de columna no se ordenan automáticamente. A veces, querrá invalidar estos valores predeterminados. Por ejemplo, puede mostrar imágenes en lugar de los valores de celda de texto, números o enumeración. Aunque no se pueden ordenar las imágenes, se pueden ordenar los valores subyacentes que representan.  
  
 En el control <xref:System.Windows.Forms.DataGridView>, el valor de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de una columna determina su comportamiento de ordenación.  
  
 En el procedimiento siguiente se muestra la `Priority` columna de [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md). Esta columna es una columna de imagen y no se ordena de forma predeterminada. No obstante, contiene valores de celda reales que son cadenas, por lo que se puede ordenar automáticamente.  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>Para establecer el modo de ordenación de una columna  
  
- Establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un control <xref:System.Windows.Forms.DataGridView> llamado `dataGridView1` que contiene una columna llamada `Priority`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [Ordenar datos en el control DataGridView de Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Modos de ordenación de columnas del control DataGridView de Windows Forms](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [Personalizar la ordenación en el control DataGridView de formularios Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
