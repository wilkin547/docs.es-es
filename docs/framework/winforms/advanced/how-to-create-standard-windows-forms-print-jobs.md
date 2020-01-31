---
title: Crear trabajos de impresión estándar
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
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741522"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Cómo: Crear trabajos de impresión estándar de formularios Windows Forms
La base de la impresión en Windows Forms es el componente <xref:System.Drawing.Printing.PrintDocument>, más concretamente, el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>. Al escribir código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>, puede especificar lo que se va a imprimir y cómo imprimirlo.  
  
### <a name="to-create-a-print-job"></a>Para crear un trabajo de impresión  
  
1. Agregue un componente de <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2. Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Tendrá que codificar su propia lógica de impresión. Además, tendrá que especificar el material que se va a imprimir.  
  
     En el ejemplo de código siguiente, se crea un gráfico de ejemplo en la forma de un rectángulo rojo en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage> para que actúe como material que se va a imprimir.  
  
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
  
     También puede que desee escribir código para los eventos <xref:System.Drawing.Printing.PrintDocument.BeginPrint> y <xref:System.Drawing.Printing.PrintDocument.EndPrint>, quizás incluir un entero que represente el número total de páginas que se van a imprimir, que se reduce a medida que se imprime cada página.  
  
    > [!NOTE]
    > Puede Agregar un componente de <xref:System.Windows.Forms.PrintDialog> a su formulario para proporcionar una interfaz de usuario limpia y eficaz a los usuarios. El establecimiento de la propiedad <xref:System.Windows.Forms.PrintDialog.Document%2A> del componente <xref:System.Windows.Forms.PrintDialog> le permite establecer propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario. Para obtener más información sobre el componente de <xref:System.Windows.Forms.PrintDialog>, vea [PrintDialog (componente](../controls/printdialog-component-windows-forms.md)).  
  
     Para obtener más información acerca de los detalles de los trabajos de impresión Windows Forms, incluido cómo crear un trabajo de impresión mediante programación, vea <xref:System.Drawing.Printing.PrintPageEventArgs>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
