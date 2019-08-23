---
title: Procedimiento para crear trabajos de impresión estándar de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 44673e6b26f088e71813aaac26c4b9a03429597a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938240"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Procedimiento para crear trabajos de impresión estándar de formularios Windows Forms
La base de la impresión en Windows Forms es <xref:System.Drawing.Printing.PrintDocument> el componente, más concretamente <xref:System.Drawing.Printing.PrintDocument.PrintPage> , el evento. Al escribir código para controlar el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento, puede especificar lo que se va a imprimir y cómo imprimirlo.  
  
### <a name="to-create-a-print-job"></a>Para crear un trabajo de impresión  
  
1. Agregue un <xref:System.Drawing.Printing.PrintDocument> componente al formulario.  
  
2. Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Tendrá que codificar su propia lógica de impresión. Además, tendrá que especificar el material que se va a imprimir.  
  
     En el ejemplo de código siguiente, se crea un gráfico de ejemplo en la forma de un rectángulo rojo <xref:System.Drawing.Printing.PrintDocument.PrintPage> en el controlador de eventos para que actúe como material que se va a imprimir.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     (Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     También puede escribir código para los <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventos y <xref:System.Drawing.Printing.PrintDocument.EndPrint> , quizás incluir un entero que represente el número total de páginas que se van a imprimir, que se reduce a medida que se imprime cada página.  
  
    > [!NOTE]
    > Puede Agregar un <xref:System.Windows.Forms.PrintDialog> componente a su formulario para proporcionar una interfaz de usuario limpia y eficaz a los usuarios. Establecer la <xref:System.Windows.Forms.PrintDialog.Document%2A> propiedad <xref:System.Windows.Forms.PrintDialog> del componente le permite establecer las propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario. Para obtener más información sobre <xref:System.Windows.Forms.PrintDialog> el componente, vea [PrintDialog (componente](../controls/printdialog-component-windows-forms.md)).  
  
     Para obtener más información acerca de los detalles de los trabajos de impresión Windows Forms, incluido cómo crear un trabajo de impresión mediante <xref:System.Drawing.Printing.PrintPageEventArgs>programación, vea.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
