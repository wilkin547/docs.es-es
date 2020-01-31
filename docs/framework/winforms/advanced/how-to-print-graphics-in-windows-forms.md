---
title: 'Cómo: imprimir gráficos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 2435b3bc14747a00d2a0fc03a9ebd21ae43c5369
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740640"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Impresión de gráficos en Windows Forms
Con frecuencia, querrá imprimir gráficos en la aplicación basada en Windows. La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar objetos en un dispositivo, como una pantalla o una impresora.  
  
### <a name="to-print-graphics"></a>Para imprimir gráficos  
  
1. Agregue un componente de <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2. En el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>, utilice la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> para indicar a la impresora qué tipo de gráficos imprimir.  
  
     En el ejemplo de código siguiente se muestra un controlador de eventos que se usa para crear una elipse azul dentro de un rectángulo delimitador. El rectángulo tiene la siguiente ubicación y dimensiones: a partir de 100, 150 con un ancho de 250 y un alto de 250.  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,   
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     (Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
