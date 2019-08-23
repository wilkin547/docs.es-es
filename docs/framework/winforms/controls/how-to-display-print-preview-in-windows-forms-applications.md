---
title: Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: 8252906de9a574f49617609a4cb08a1e8aa6a992
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929004"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="b3876-102">Procedimiento para mostrar la vista preliminar en aplicaciones de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3876-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="b3876-103">Puede usar el <xref:System.Windows.Forms.PrintPreviewDialog> control para permitir que los usuarios muestren un documento, a menudo antes de que se imprima.</span><span class="sxs-lookup"><span data-stu-id="b3876-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="b3876-104">Para ello, debe especificar una instancia de la <xref:System.Drawing.Printing.PrintDocument> clase; este es el documento que se va a imprimir.</span><span class="sxs-lookup"><span data-stu-id="b3876-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="b3876-105">Para obtener más información acerca del uso de la <xref:System.Drawing.Printing.PrintDocument> vista previa de [impresión con el componente, consulte Cómo: Imprimir en Windows Forms con la vista](../advanced/how-to-print-in-windows-forms-using-print-preview.md)previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="b3876-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3876-106">Para usar el <xref:System.Windows.Forms.PrintPreviewDialog> control en tiempo de ejecución, los usuarios deben tener una impresora instalada en su equipo, ya sea de forma local o a través de una red, <xref:System.Windows.Forms.PrintPreviewDialog> ya que esto es en parte cómo el componente determina la apariencia de un documento cuando se imprime.</span><span class="sxs-lookup"><span data-stu-id="b3876-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="b3876-107">El <xref:System.Windows.Forms.PrintPreviewDialog> control utiliza la <xref:System.Drawing.Printing.PrinterSettings> clase.</span><span class="sxs-lookup"><span data-stu-id="b3876-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="b3876-108">Además, el <xref:System.Windows.Forms.PrintPreviewDialog> control utiliza la <xref:System.Drawing.Printing.PageSettings> clase, del mismo modo <xref:System.Windows.Forms.PrintPreviewDialog> que el componente.</span><span class="sxs-lookup"><span data-stu-id="b3876-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="b3876-109">El documento de impresión especificado en <xref:System.Windows.Forms.PrintPreviewDialog> la propiedad <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> del control hace referencia a las instancias <xref:System.Drawing.Printing.PrinterSettings> de <xref:System.Drawing.Printing.PageSettings> las clases y, y se usan para representar el documento en la ventana de vista previa.</span><span class="sxs-lookup"><span data-stu-id="b3876-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="b3876-110">Para ver páginas mediante el control PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="b3876-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="b3876-111">Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="b3876-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="b3876-112">En el ejemplo de código siguiente, <xref:System.Windows.Forms.Button> el controlador <xref:System.Windows.Forms.Control.Click> de eventos del control <xref:System.Windows.Forms.PrintPreviewDialog> abre una instancia del control.</span><span class="sxs-lookup"><span data-stu-id="b3876-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="b3876-113">El documento de impresión se especifica en <xref:System.Windows.Forms.PrintDialog.Document%2A> la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b3876-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="b3876-114">En el ejemplo siguiente, no se especifica ningún documento de impresión.</span><span class="sxs-lookup"><span data-stu-id="b3876-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="b3876-115">El ejemplo requiere que el formulario tenga un <xref:System.Windows.Forms.Button> control, un <xref:System.Drawing.Printing.PrintDocument> componente denominado `myDocument`y un <xref:System.Windows.Forms.PrintPreviewDialog> control.</span><span class="sxs-lookup"><span data-stu-id="b3876-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="b3876-116">(Visual C#, visual C++) Coloque el siguiente código en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="b3876-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b3876-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3876-117">See also</span></span>

- [<span data-ttu-id="b3876-118">PrintDocument (Componente, Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b3876-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="b3876-119">PrintPreviewDialog (control)</span><span class="sxs-lookup"><span data-stu-id="b3876-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- <span data-ttu-id="b3876-120">[Windows Forms Print Support](../advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b3876-120">[Windows Forms Print Support](../advanced/windows-forms-print-support.md)</span></span>
- [<span data-ttu-id="b3876-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b3876-121">Windows Forms</span></span>](../index.md)
