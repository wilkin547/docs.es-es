---
title: Mostrar imágenes en celdas del control DataGridView
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
ms.openlocfilehash: e0e125c816877875b80e0f20887d9beee443577a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740275"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>Cómo: Mostrar imágenes en celdas del control DataGridView de formularios Windows Forms
Una imagen o un gráfico es uno de los valores que se pueden mostrar en una fila de datos. Con frecuencia, estos gráficos adoptan la forma de la fotografía de un empleado o el logotipo de la empresa.  
  
 La incorporación de imágenes es sencilla cuando se muestran datos en el control <xref:System.Windows.Forms.DataGridView>. El control <xref:System.Windows.Forms.DataGridView> controla de forma nativa cualquier formato de imagen admitido por la clase <xref:System.Drawing.Image>, así como el formato de imagen OLE utilizado por algunas bases de datos.  
  
 Si el origen de datos del control <xref:System.Windows.Forms.DataGridView> tiene una columna de imágenes, el control <xref:System.Windows.Forms.DataGridView> mostrará automáticamente.  
  
 En el ejemplo de código siguiente se muestra cómo extraer un icono de un recurso incrustado y convertirlo en un mapa de bits para su presentación en cada celda de una columna de imagen. Para ver otro ejemplo en el que se reemplazan los valores de celda textual por las imágenes correspondientes, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
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
- [Personalizar el formato de los datos en el control DataGridView de formularios Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
