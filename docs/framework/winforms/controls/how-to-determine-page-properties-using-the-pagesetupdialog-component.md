---
title: 'Cómo: Determinar las propiedades de página mediante el componente PageSetupDialog'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- page properties
- page setup
- PageSetupDialog component
ms.assetid: 6dae05bc-c0fd-4357-bb93-841a1631d98f
ms.openlocfilehash: 8a015c199193dfd9c43bec53cc93cbf9dc201413
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142048"
---
# <a name="how-to-determine-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="f4ef3-102">Cómo: Determinar las propiedades de página mediante el componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="f4ef3-102">How to: Determine Page Properties Using the PageSetupDialog Component</span></span>
<span data-ttu-id="f4ef3-103">El componente [PageSetupDialog](pagesetupdialog-component-windows-forms.md) presenta al usuario un diseño, un tamaño de papel y otras opciones de diseño de página para un documento.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-103">The [PageSetupDialog](pagesetupdialog-component-windows-forms.md) component presents layout, paper size, and other page layout choices to the user for a document.</span></span>  
  
 <span data-ttu-id="f4ef3-104">Debe especificar una instancia de la clase <xref:System.Drawing.Printing.PrintDocument> (el documento que se va a imprimir).</span><span class="sxs-lookup"><span data-stu-id="f4ef3-104">You need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class—this is the document to be printed.</span></span> <span data-ttu-id="f4ef3-105">Además, los usuarios deben tener una impresora instalada en su equipo, ya sea de forma local o a través de una red, ya que en parte así es como determina el componente <xref:System.Windows.Forms.PageSetupDialog> las opciones de formato de página que se presentan al usuario.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-105">Additionally, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PageSetupDialog> component determines the page formatting choices presented to the user.</span></span>  
  
 <span data-ttu-id="f4ef3-106">Un aspecto importante a la hora de trabajar con el componente <xref:System.Windows.Forms.PageSetupDialog> es cómo interactúa con la clase <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="f4ef3-106">An important aspect of working with the <xref:System.Windows.Forms.PageSetupDialog> component is how it interacts with the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="f4ef3-107">La clase <xref:System.Drawing.Printing.PageSettings> se usa para especificar la configuración que modifica la manera en que se imprimirá una página, como la orientación del papel, el tamaño de la página o los márgenes.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-107">The <xref:System.Drawing.Printing.PageSettings> class is used to specify settings that modify the way a page will be printed, such as paper orientation, the size of the page, and the margins.</span></span> <span data-ttu-id="f4ef3-108">Cada una de estas opciones se representan como una propiedad de la clase <xref:System.Drawing.Printing.PageSettings> .</span><span class="sxs-lookup"><span data-stu-id="f4ef3-108">Each of these settings is represented as a property of the <xref:System.Drawing.Printing.PageSettings> class.</span></span> <span data-ttu-id="f4ef3-109">La clase <xref:System.Windows.Forms.PageSetupDialog> modifica estos valores de propiedad para una instancia determinada de la clase <xref:System.Drawing.Printing.PageSettings> , que está asociada con el documento (y que se representa como una propiedad <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> ).</span><span class="sxs-lookup"><span data-stu-id="f4ef3-109">The <xref:System.Windows.Forms.PageSetupDialog> class modifies these property values for a given instance of the <xref:System.Drawing.Printing.PageSettings> class that is associated with the document (and is represented as a <xref:System.Drawing.Printing.PrintDocument.DefaultPageSettings%2A> property).</span></span>  
  
### <a name="to-set-page-properties-using-the-pagesetupdialog-component"></a><span data-ttu-id="f4ef3-110">Para establecer las propiedades de página con el componente PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="f4ef3-110">To set page properties using the PageSetupDialog component</span></span>  
  
1. <span data-ttu-id="f4ef3-111">Use el método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> para mostrar el cuadro de diálogo, especificando el <xref:System.Drawing.Printing.PrintDocument> que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="f4ef3-112">En el siguiente ejemplo, el controlador de eventos <xref:System.Windows.Forms.Button> del control <xref:System.Windows.Forms.Control.Click> abre una instancia del componente <xref:System.Windows.Forms.PageSetupDialog> .</span><span class="sxs-lookup"><span data-stu-id="f4ef3-112">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PageSetupDialog> component.</span></span> <span data-ttu-id="f4ef3-113">Se especifica un documento existente en la propiedad <xref:System.Windows.Forms.PageSetupDialog.Document%2A> y su propiedad <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> se establece en `false`.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-113">An existing document is specified in the <xref:System.Windows.Forms.PageSetupDialog.Document%2A> property, and its <xref:System.Drawing.Printing.PageSettings.Color%2A?displayProperty=nameWithType> property is set to `false`.</span></span>  
  
     <span data-ttu-id="f4ef3-114">En el ejemplo se <xref:System.Windows.Forms.Button> supone que <xref:System.Drawing.Printing.PrintDocument> el `myDocument`formulario <xref:System.Windows.Forms.PageSetupDialog> tiene un control, un componente denominado y un componente.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-114">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PageSetupDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       'You will have to specify your own print document.  
       PageSetupDialog1.Document = myDocument  
       ' Sets the print document's color setting to false,  
       ' so that the page will not be printed in color.  
       PageSetupDialog1.Document.DefaultPageSettings.Color = False  
       PageSetupDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       pageSetupDialog1.Document = myDocument;  
       // Sets the print document's color setting to false,  
       // so that the page will not be printed in color.  
       pageSetupDialog1.Document.DefaultPageSettings.Color = false;  
       pageSetupDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void button1_Click(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          pageSetupDialog1->Document = myDocument;  
          // Sets the print document's color setting to false,  
          // so that the page will not be printed in color.  
          pageSetupDialog1->Document->DefaultPageSettings->Color = false;  
          pageSetupDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="f4ef3-115">(Visual C- y Visual C++) Coloque el código siguiente en el constructor del formulario para registrar el controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="f4ef3-115">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f4ef3-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f4ef3-116">See also</span></span>

- <xref:System.Windows.Forms.PageSetupDialog>
- [<span data-ttu-id="f4ef3-117">Cómo: Crear trabajos de impresión estándar de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f4ef3-117">How to: Create Standard Windows Forms Print Jobs</span></span>](../advanced/how-to-create-standard-windows-forms-print-jobs.md)
- [<span data-ttu-id="f4ef3-118">PageSetupDialog Component</span><span class="sxs-lookup"><span data-stu-id="f4ef3-118">PageSetupDialog Component</span></span>](pagesetupdialog-component-windows-forms.md)
