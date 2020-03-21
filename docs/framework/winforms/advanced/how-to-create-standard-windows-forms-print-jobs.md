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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182567"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>Cómo: Crear trabajos de impresión estándar de formularios Windows Forms
La base de la impresión en formularios Windows Forms es el <xref:System.Drawing.Printing.PrintDocument> componente, más específicamente, el <xref:System.Drawing.Printing.PrintDocument.PrintPage> evento. Al escribir código <xref:System.Drawing.Printing.PrintDocument.PrintPage> para controlar el evento, puede especificar qué imprimir y cómo imprimirlo.  
  
### <a name="to-create-a-print-job"></a>Para crear un trabajo de impresión  
  
1. Agregue <xref:System.Drawing.Printing.PrintDocument> un componente al formulario.  
  
2. Escriba código para controlar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> .  
  
     Tendrá que codificar su propia lógica de impresión. Además, tendrá que especificar el material que se va a imprimir.  
  
     En el ejemplo de código siguiente, se crea un gráfico <xref:System.Drawing.Printing.PrintDocument.PrintPage> de ejemplo con la forma de un rectángulo rojo en el controlador de eventos para que actúe como material que se va a imprimir.  
  
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
  
     (Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
     También es posible que desee escribir código para los <xref:System.Drawing.Printing.PrintDocument.BeginPrint> eventos y, <xref:System.Drawing.Printing.PrintDocument.EndPrint> tal vez, incluido un entero que representa el número total de páginas para imprimir que se reduce a medida que se imprime cada página.  
  
    > [!NOTE]
    > Puede agregar <xref:System.Windows.Forms.PrintDialog> un componente al formulario para proporcionar una interfaz de usuario (UI) limpia y eficaz a los usuarios. Establecer <xref:System.Windows.Forms.PrintDialog.Document%2A> la propiedad <xref:System.Windows.Forms.PrintDialog> del componente le permite establecer propiedades relacionadas con el documento de impresión con el que está trabajando en el formulario. Para obtener más <xref:System.Windows.Forms.PrintDialog> información sobre el componente, vea [Componente PrintDialog](../controls/printdialog-component-windows-forms.md).  
  
     Para obtener más información acerca de los detalles de los trabajos <xref:System.Drawing.Printing.PrintPageEventArgs>de impresión de formularios Windows Forms, incluido cómo crear un trabajo de impresión mediante programación, vea .  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Printing.PrintDocument>
- [Funcionalidad para imprimir en formularios Windows Forms](windows-forms-print-support.md)
