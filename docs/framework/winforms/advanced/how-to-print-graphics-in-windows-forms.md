---
title: 'Cómo: Imprimir gráficos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182537"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Cómo: Imprimir gráficos en formularios Windows Forms
Con frecuencia, querrá imprimir gráficos en su aplicación basada en Windows. La <xref:System.Drawing.Graphics> clase proporciona métodos para dibujar objetos en un dispositivo, como una pantalla o una impresora.  
  
### <a name="to-print-graphics"></a>Para imprimir gráficos  
  
1. Agregue <xref:System.Drawing.Printing.PrintDocument> un componente al formulario.  
  
2. En <xref:System.Drawing.Printing.PrintDocument.PrintPage> el controlador de <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> eventos, <xref:System.Drawing.Printing.PrintPageEventArgs> utilice la propiedad de la clase para indicar a la impresora qué tipo de gráficos imprimir.  
  
     En el ejemplo de código siguiente se muestra un controlador de eventos utilizado para crear una elipse azul dentro de un rectángulo delimitador. El rectángulo tiene la siguiente ubicación y dimensiones: comenzando en 100, 150 con un ancho de 250 y una altura de 250.  
  
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
  
     (Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Funcionalidad para imprimir en formularios Windows Forms](windows-forms-print-support.md)
