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
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="f1be6-102">Impresión de gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f1be6-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="f1be6-103">Con frecuencia, querrá imprimir gráficos en la aplicación basada en Windows.</span><span class="sxs-lookup"><span data-stu-id="f1be6-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="f1be6-104">La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar objetos en un dispositivo, como una pantalla o una impresora.</span><span class="sxs-lookup"><span data-stu-id="f1be6-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="f1be6-105">Para imprimir gráficos</span><span class="sxs-lookup"><span data-stu-id="f1be6-105">To print graphics</span></span>  
  
1. <span data-ttu-id="f1be6-106">Agregue un componente de <xref:System.Drawing.Printing.PrintDocument> al formulario.</span><span class="sxs-lookup"><span data-stu-id="f1be6-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="f1be6-107">En el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>, utilice la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> para indicar a la impresora qué tipo de gráficos imprimir.</span><span class="sxs-lookup"><span data-stu-id="f1be6-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="f1be6-108">En el ejemplo de código siguiente se muestra un controlador de eventos que se usa para crear una elipse azul dentro de un rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="f1be6-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="f1be6-109">El rectángulo tiene la siguiente ubicación y dimensiones: a partir de 100, 150 con un ancho de 250 y un alto de 250.</span><span class="sxs-lookup"><span data-stu-id="f1be6-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="f1be6-110">(Visual C# y visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f1be6-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1be6-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f1be6-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- <span data-ttu-id="f1be6-112">[Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f1be6-112">[Windows Forms Print Support](windows-forms-print-support.md)</span></span>
