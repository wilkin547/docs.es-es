---
title: Procedimiento para alojar controles en celdas DataGridView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], hosting in cells
- DataGridView control [Windows Forms], hosting controls in cells
- cells [Windows Forms], hosting controls
ms.assetid: e79a9d4e-64ec-41f5-93ec-f5492633cbb2
ms.openlocfilehash: 008b6da56c3428d0edcc44778b4d3bef1a52c443
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194206"
---
# <a name="how-to-host-controls-in-windows-forms-datagridview-cells"></a>Procedimiento para alojar controles en celdas DataGridView de formularios Windows Forms
El control <xref:System.Windows.Forms.DataGridView> proporciona varios tipos de columna, permitiendo a sus usuarios escribir y editar valores de varias maneras. No obstante, si estos tipos de columna no satisfacen sus necesidades de entrada de datos, puede crear sus propios tipos de columna con celdas que alojen los controles que elija. Para ello, debe definir clases que deriven de <xref:System.Windows.Forms.DataGridViewColumn> y <xref:System.Windows.Forms.DataGridViewCell>. También debe definir una clase que derive de <xref:System.Windows.Forms.Control> e implemente la interfaz <xref:System.Windows.Forms.IDataGridViewEditingControl>.  
  
 El ejemplo de código siguiente muestra cómo crear una columna de calendario. Las celdas de esta columna muestran fechas en celdas de cuadro de texto normales, pero cuando el usuario edita una celda, aparece un control <xref:System.Windows.Forms.DateTimePicker>. Para evitar tener que implementar nuevamente la funcionalidad de visualización de cuadro de texto, la clase `CalendarCell` deriva de la clase <xref:System.Windows.Forms.DataGridViewTextBoxCell>, en lugar de heredar directamente la clase <xref:System.Windows.Forms.DataGridViewCell>.  
  
> [!NOTE]
>  Al derivar de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewColumn> y agregar nuevas propiedades a la clase derivada, asegúrese de invalidar el método `Clone` para copiar las nuevas propiedades durante las operaciones de clonación. También debe llamar al método `Clone` de la clase base para copiar las propiedades de la clase base a la nueva celda o columna.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/CS/datagridviewcalendarcolumn.cs#000)]
 [!code-vb[System.Windows.Forms.DataGridViewCalendarColumn#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCalendarColumn/VB/datagridviewcalendarcolumn.vb#000)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo siguiente requiere:  
  
-   Referencias a los ensamblados System y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>
- <xref:System.Windows.Forms.IDataGridViewEditingControl>
- <xref:System.Windows.Forms.DateTimePicker>
- [Personalizar el control DataGridView de Windows Forms](customizing-the-windows-forms-datagridview-control.md)
- [Arquitectura del control DataGridView](datagridview-control-architecture-windows-forms.md)
- [Tipos de columnas en el control DataGridView de Windows Forms](column-types-in-the-windows-forms-datagridview-control.md)
