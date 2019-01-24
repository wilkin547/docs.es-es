---
title: Procedimiento Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: a15563560615f5b857220c0b548fc57f31ee4e09
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54527671"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a>Procedimiento Captura de datos de usuario de un componente PrintDialog en tiempo de ejecución
Aunque se pueden establecer las opciones relacionadas con la impresión en tiempo de diseño, en ocasiones, deseará cambiar estas opciones en tiempo de ejecución, probablemente debido a las opciones elegidas por el usuario. Puede capturar la entrada del usuario para imprimir un documento mediante el <xref:System.Windows.Forms.PrintDialog> y <xref:System.Drawing.Printing.PrintDocument> componentes.  
  
### <a name="to-change-print-options-programmatically"></a>Para cambiar las opciones de impresión mediante programación  
  
1.  Agregar un <xref:System.Windows.Forms.PrintDialog> y un <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2.  Establecer el <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad de la <xref:System.Windows.Forms.PrintDialog> a la <xref:System.Drawing.Printing.PrintDocument> agregado al formulario.  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  Mostrar el <xref:System.Windows.Forms.PrintDialog> componente mediante el uso de la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  Opciones de impresión del usuario en el cuadro de diálogo se copiarán en el <xref:System.Drawing.Printing.PrinterSettings> propiedad de la <xref:System.Drawing.Printing.PrintDocument> componente.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Imprimir un archivo de texto de varias páginas en Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
