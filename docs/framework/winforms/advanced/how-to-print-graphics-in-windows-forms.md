---
title: Procedimiento para imprimir gráficos en formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 347c7064c199e953b496c9505f08c9e12c1ae670
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052815"
---
# <a name="how-to-print-graphics-in-windows-forms"></a>Procedimiento para imprimir gráficos en formularios Windows Forms
Con frecuencia, deseará imprimir gráficos en su aplicación basada en Windows. La <xref:System.Drawing.Graphics> clase proporciona métodos para dibujar objetos en un dispositivo, como una pantalla o impresora.  
  
### <a name="to-print-graphics"></a>Para imprimir gráficos  
  
1. Agregar un <xref:System.Drawing.Printing.PrintDocument> al formulario.  
  
2. En el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos, use el <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> clase para indicar a la impresora en el tipo de gráficos para imprimir.  
  
     El ejemplo de código siguiente muestra un controlador de eventos que se usa para crear una elipse azul dentro de un rectángulo delimitador. El rectángulo tiene la ubicación y dimensiones siguientes: comenzando en 100, 150 con un ancho de 250 y un alto de 250.  
  
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
  
     (Visual C# y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.  
  
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
