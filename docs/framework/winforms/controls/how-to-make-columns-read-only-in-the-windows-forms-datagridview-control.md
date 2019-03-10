---
title: Procedimiento Que las columnas de sólo lectura en el Control DataGridView de Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
ms.openlocfilehash: cad80a7b242622802b5897d9903c765a877e6fd4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718368"
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>Filtrar Que las columnas de sólo lectura en el Control DataGridView de Windows Forms
No todos los datos están diseñados para ser editados. En el control <xref:System.Windows.Forms.DataGridView>, el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> de la columna determina si los usuarios pueden editar las celdas de esa columna. Para obtener información acerca de cómo hacer que el control sea de sólo lectura, vea [Cómo: Impedir la adición de la fila y la eliminación en la Windows Forms DataGridView Control](prevent-row-addition-and-deletion-datagridview.md).  
  
 Visual Studio es compatible con esta tarea.  Consulte también [Cómo: Crear columnas de sólo lectura en la Windows Forms Control DataGridView de formularios mediante el diseñador](make-columns-read-only-in-the-datagrid-using-the-designer.md).  
  
### <a name="to-make-a-column-read-only-programmatically"></a>Para que hacer que una columna sea de solo lectura mediante programación  
  
-   Establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1` con una columna denominada `CompanyName`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>
- [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Cómo: Impedir la adición de fila y eliminación en el Control DataGridView de Windows Forms](prevent-row-addition-and-deletion-datagridview.md)
