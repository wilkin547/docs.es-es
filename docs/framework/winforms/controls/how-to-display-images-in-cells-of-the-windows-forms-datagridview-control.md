---
title: Procedimiento para mostrar imágenes en celdas del control DataGridView de formularios Windows Forms
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
ms.openlocfilehash: e3a4c395e86e4091d8344bebcf99ee04474f3295
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64609931"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Procedimiento para mostrar imágenes en celdas del control DataGridView de formularios Windows Forms
Una imagen o gráfico es uno de los valores que se pueden mostrar en una fila de datos. Con frecuencia, estos gráficos adoptan la forma de fotografía de un empleado o un logotipo de empresa.  
  
 Incorporación de imágenes es sencilla cuando se muestran datos dentro de la <xref:System.Windows.Forms.DataGridView> control. El <xref:System.Windows.Forms.DataGridView> control administra de forma nativa cualquier formato de imagen admitido por el <xref:System.Drawing.Image> formato usado por algunas bases de datos de imagen de clase, así como la OLE.  
  
 Si el <xref:System.Windows.Forms.DataGridView> origen de datos del control tiene una columna de imágenes, se mostrará de forma automática el <xref:System.Windows.Forms.DataGridView> control.  
  
 El ejemplo de código siguiente muestra cómo extraer un icono desde un recurso incrustado y convertirlo en un mapa de bits para mostrarla en todas las celdas de una columna de imagen. Para obtener otro ejemplo que reemplaza los valores de celda textual con las imágenes correspondientes, vea [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Control <xref:System.Windows.Forms.DataGridView> denominado `dataGridView1`.  
  
- Un recurso de icono incrustado denominado `tree.ico`.  
  
- Referencias a los ensamblados <xref:System?displayProperty=nameWithType>, <xref:System.Windows.Forms?displayProperty=nameWithType> y <xref:System.Drawing?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Características básicas de columnas, filas y celdas en el control DataGridView de Windows Forms](basic-column-row-and-cell-features-wf-datagridview-control.md)
- [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
