---
title: Filtrar Imprimir gráficos en Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: cb8c9f291103915c82fb31af5c6668fbd0648f66
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721325"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="31c61-102">Procedimiento Imprimir gráficos en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="31c61-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="31c61-103">Con frecuencia, deseará imprimir gráficos en su aplicación basada en Windows.</span><span class="sxs-lookup"><span data-stu-id="31c61-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="31c61-104">La <xref:System.Drawing.Graphics> clase proporciona métodos para dibujar objetos en un dispositivo, como una pantalla o impresora.</span><span class="sxs-lookup"><span data-stu-id="31c61-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="31c61-105">Para imprimir gráficos</span><span class="sxs-lookup"><span data-stu-id="31c61-105">To print graphics</span></span>  
  
1.  <span data-ttu-id="31c61-106">Agregar un <xref:System.Drawing.Printing.PrintDocument> al formulario.</span><span class="sxs-lookup"><span data-stu-id="31c61-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="31c61-107">En el <xref:System.Drawing.Printing.PrintDocument.PrintPage> controlador de eventos, use el <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> propiedad de la <xref:System.Drawing.Printing.PrintPageEventArgs> clase para indicar a la impresora en el tipo de gráficos para imprimir.</span><span class="sxs-lookup"><span data-stu-id="31c61-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="31c61-108">El ejemplo de código siguiente muestra un controlador de eventos que se usa para crear una elipse azul dentro de un rectángulo delimitador.</span><span class="sxs-lookup"><span data-stu-id="31c61-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="31c61-109">El rectángulo tiene la ubicación y dimensiones siguientes: comenzando en 100, 150 con un ancho de 250 y un alto de 250.</span><span class="sxs-lookup"><span data-stu-id="31c61-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
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
  
     <span data-ttu-id="31c61-110">(Visual C# y [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="31c61-110">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31c61-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="31c61-111">See also</span></span>
- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- <span data-ttu-id="31c61-112">[Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="31c61-112">[Windows Forms Print Support](windows-forms-print-support.md)</span></span>
