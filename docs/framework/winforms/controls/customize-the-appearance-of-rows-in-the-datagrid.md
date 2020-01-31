---
title: Personalizar la apariencia de las filas en el control DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- rows [Windows Forms], customizing in DataGridView control
- DataGridView control [Windows Forms], customizing rows
ms.assetid: d40b53d2-7e7c-48c5-8570-6e79d15c3bbb
ms.openlocfilehash: 099b2104e7a4887aa846c4d65273db2dd4f60559
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744039"
---
# <a name="how-to-customize-the-appearance-of-rows-in-the-windows-forms-datagridview-control"></a>Cómo: Personalizar la apariencia de las filas en el control DataGridView de formularios Windows Forms
Puede controlar la apariencia de las filas de <xref:System.Windows.Forms.DataGridView> controlando el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>, o ambos. Estos eventos están diseñados para que pueda representar solo lo que se desea mientras permite que el control <xref:System.Windows.Forms.DataGridView> represente el resto. Por ejemplo, si quiere representar un fondo personalizado, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType> y dejar que las celdas individuales representen su propio contenido de primer plano. También tiene la opción de dejar que las celdas se representen a sí mismas y agregar contenido de primer plano personalizado en un controlador para el evento <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>. Además, puede deshabilitar la representación de las celdas y representar todo usted mismo en un controlador de eventos <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>.  
  
 En el ejemplo de código siguiente, se implementan controladores de ambos eventos para ofrecer un fondo de selección de degradado y algún contenido de primer plano personalizado que abarca varias columnas.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/CS/datagridviewrowpainting.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewRowPainting#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewRowPainting/VB/datagridviewrowpainting.vb#00)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.RowPrePaint?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowPostPaint?displayProperty=nameWithType>
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
