---
title: Procedimiento para mostrar la hora con el control DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: f1c1a0abaeddadb44b40d56eb2f8a28e4b58f4f5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651767"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a>Procedimiento para mostrar la hora con el control DateTimePicker
Si quiere la aplicación para permitir a los usuarios seleccionar una fecha y hora, y mostrar esa fecha y hora en el formato especificado, utilice el control <xref:System.Windows.Forms.DateTimePicker>. El siguiente procedimiento muestra cómo utilizar el control <xref:System.Windows.Forms.DateTimePicker> para mostrar la hora.  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a>Para mostrar la hora con el control DateTimePicker  
  
1. Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en <xref:System.Windows.Forms.DateTimePickerFormat.Time>.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> para el elemento <xref:System.Windows.Forms.DateTimePicker> en `true`.  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a>Ejemplo  
 El ejemplo de código siguiente muestra cómo crear un <xref:System.Windows.Forms.DateTimePicker> que permita a los usuarios elegir solo una vez.  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.  
  
 Para obtener información sobre cómo compilar este ejemplo desde la línea de comandos para Visual Basic o Visual C#, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [de línea de comandos con csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Vea también

- [Control DateTimePicker](datetimepicker-control-windows-forms.md)
