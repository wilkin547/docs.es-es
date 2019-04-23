---
title: Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 107ec75257907b934412d9ee333b00d5df05a99c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110324"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>Procedimiento para personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms
Puede controlar la apariencia de las filas de <xref:System.Windows.Forms.DataGridView> controlando el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>, o ambos. Estos eventos están diseñados para que pueda representar solo lo que se desea mientras permite que el control <xref:System.Windows.Forms.DataGridView> represente el resto. Por ejemplo, si quiere representar un fondo personalizado, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> y dejar que las celdas individuales representen su propio contenido de primer plano. También tiene la opción de dejar que las celdas se representen a sí mismas y agregar contenido de primer plano personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Además, puede deshabilitar la representación de las celdas y representar todo usted mismo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.  
  
 En el ejemplo de código siguiente, se implementan controladores de ambos eventos para ofrecer un fondo de selección de degradado y algún contenido de primer plano personalizado que abarca varias columnas.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
