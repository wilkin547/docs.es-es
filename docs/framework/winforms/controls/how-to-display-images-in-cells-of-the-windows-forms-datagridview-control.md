---
title: 'Cómo: Mostrar imágenes en celdas del control DataGridView de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 62a29b9ade4953a1775c2a71b62e4881065f51a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Cómo: Mostrar imágenes en celdas del control DataGridView de formularios Windows Forms
Una imagen o gráfico es uno de los valores que se pueden mostrar en una fila de datos. Con frecuencia, estos gráficos adoptan la forma de fotografía de un empleado o un logotipo de empresa.  
  
 La incorporación de imágenes es sencilla cuando se muestran datos en el <xref:System.Windows.Forms.DataGridView> control. El <xref:System.Windows.Forms.DataGridView> control administra de forma nativa cualquier formato de imagen admitida el <xref:System.Drawing.Image> formato utilizado por algunas bases de datos de imagen de clase, así como la OLE.  
  
 Si el <xref:System.Windows.Forms.DataGridView> origen de datos del control tiene una columna de imágenes, se mostrará de forma automática el <xref:System.Windows.Forms.DataGridView> control.  
  
 En el ejemplo de código siguiente se muestra cómo extraer un icono desde un recurso incrustado y convertirlo en un mapa de bits para mostrarlo en cada celda de una columna de imagen. Para obtener otro ejemplo que reemplaza los valores de celda textuales con las imágenes correspondientes, vea [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
-   Un recurso de icono incrustado denominado `tree.ico`.  
  
-   Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
