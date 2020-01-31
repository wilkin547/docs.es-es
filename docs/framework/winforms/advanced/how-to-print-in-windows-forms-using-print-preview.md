---
title: Imprimir con la vista previa de impresión
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], using print preview
- printing [Windows Forms], with print preview
- print preview
ms.assetid: 4a16f7e2-ae10-4485-b0ae-3d558334d0fe
ms.openlocfilehash: 1975c902fdb56326c763f2e2fc11e381ffc7fbd3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740608"
---
# <a name="how-to-print-in-windows-forms-using-print-preview"></a><span data-ttu-id="e884b-102">Cómo: Imprimir en Windows Forms a través de la vista previa de impresión</span><span class="sxs-lookup"><span data-stu-id="e884b-102">How to: Print in Windows Forms Using Print Preview</span></span>
<span data-ttu-id="e884b-103">Es muy habitual en la programación de Windows Forms ofrecer una vista previa de impresión además de los servicios de impresión.</span><span class="sxs-lookup"><span data-stu-id="e884b-103">It is very common in Windows Forms programming to offer print preview in addition to printing services.</span></span> <span data-ttu-id="e884b-104">Una forma sencilla de agregar servicios de vista previa de impresión a la aplicación es usar un control <xref:System.Windows.Forms.PrintPreviewDialog> en combinación con la lógica de control de eventos de <xref:System.Drawing.Printing.PrintDocument.PrintPage> para imprimir un archivo.</span><span class="sxs-lookup"><span data-stu-id="e884b-104">An easy way to add print preview services to your application is to use a <xref:System.Windows.Forms.PrintPreviewDialog> control in combination with the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event-handling logic for printing a file.</span></span>  
  
### <a name="to-preview-a-text-document-with-a-printpreviewdialog-control"></a><span data-ttu-id="e884b-105">Para mostrar una vista previa de un documento de texto con un control PrintPreviewDialog</span><span class="sxs-lookup"><span data-stu-id="e884b-105">To preview a text document with a PrintPreviewDialog control</span></span>  
  
1. <span data-ttu-id="e884b-106">Agregue un <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, y dos cadenas al formulario.</span><span class="sxs-lookup"><span data-stu-id="e884b-106">Add a <xref:System.Windows.Forms.PrintPreviewDialog>, <xref:System.Drawing.Printing.PrintDocument>, and two strings to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#1)]  
  
2. <span data-ttu-id="e884b-107">Establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> en el documento que quiere imprimir y abra y lea el contenido del documento en la cadena que agregó previamente.</span><span class="sxs-lookup"><span data-stu-id="e884b-107">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the document's contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#2)]  
  
3. <span data-ttu-id="e884b-108">Igual que haría para imprimir el documento, en el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage> , use la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> y el contenido del archivo para calcular las líneas por página y representar el contenido del documento.</span><span class="sxs-lookup"><span data-stu-id="e884b-108">As you would for printing the document, in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the file contents to calculate lines per page and render the document's contents.</span></span> <span data-ttu-id="e884b-109">Una vez dibujada cada página, compruebe si es la última página y establezca la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> de <xref:System.Drawing.Printing.PrintPageEventArgs> como corresponda.</span><span class="sxs-lookup"><span data-stu-id="e884b-109">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="e884b-110">El evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> se produce hasta que <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="e884b-110">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="e884b-111">Cuando el documento haya terminado de representarse, restablezca la cadena que se va a representar.</span><span class="sxs-lookup"><span data-stu-id="e884b-111">When the document has finished rendering, reset the string to be rendered.</span></span> <span data-ttu-id="e884b-112">Además, asegúrese de que el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> está asociado con su método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="e884b-112">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e884b-113">Puede que ya haya completado los pasos 2 y 3 si ha implementado la impresión en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e884b-113">You may have already completed steps 2 and 3 if you have implemented printing in your application.</span></span>  
  
     <span data-ttu-id="e884b-114">En el ejemplo de código siguiente, se usa el controlador de eventos para imprimir el archivo "testPage.txt" con la misma fuente que se usa en el formulario.</span><span class="sxs-lookup"><span data-stu-id="e884b-114">In the following code example, the event handler is used to print the "testPage.txt" file in the same font used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#3)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#3)]  
  
4. <span data-ttu-id="e884b-115">Establezca la propiedad <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> del control <xref:System.Windows.Forms.PrintPreviewDialog> en el componente <xref:System.Drawing.Printing.PrintDocument> del formulario.</span><span class="sxs-lookup"><span data-stu-id="e884b-115">Set the <xref:System.Windows.Forms.PrintPreviewDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintPreviewDialog> control to the <xref:System.Drawing.Printing.PrintDocument> component on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#5)]  
  
5. <span data-ttu-id="e884b-116">Llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> en el control <xref:System.Windows.Forms.PrintPreviewDialog> .</span><span class="sxs-lookup"><span data-stu-id="e884b-116">Call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method on the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="e884b-117">Normalmente se llamaría a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> desde el método de control de eventos <xref:System.Windows.Forms.Control.Click> de un botón.</span><span class="sxs-lookup"><span data-stu-id="e884b-117">You would typically call <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> from the <xref:System.Windows.Forms.Control.Click> event-handling method of a button.</span></span> <span data-ttu-id="e884b-118">Al llamar a <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> se genera el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se representa en el control <xref:System.Windows.Forms.PrintPreviewDialog> .</span><span class="sxs-lookup"><span data-stu-id="e884b-118">Calling <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> raises the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event and renders the output to the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="e884b-119">Cuando el usuario hace clic en el icono de impresión del cuadro de diálogo, se vuelve a generar el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> y la salida se envía a la impresora en lugar de al cuadro de diálogo de vista previa.</span><span class="sxs-lookup"><span data-stu-id="e884b-119">When the user clicks the print icon on the dialog, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised again, sending the output to the printer instead of the preview dialog.</span></span> <span data-ttu-id="e884b-120">Este es el motivo por el que la cadena se restablece al final del proceso de representación en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="e884b-120">This is why the string is reset at the end of the rendering process in step 3.</span></span>  
  
     <span data-ttu-id="e884b-121">En el siguiente ejemplo de código se muestra el método de control de eventos <xref:System.Windows.Forms.Control.Click> para un botón del formulario.</span><span class="sxs-lookup"><span data-stu-id="e884b-121">The following code example shows the <xref:System.Windows.Forms.Control.Click> event-handling method for a button on the form.</span></span> <span data-ttu-id="e884b-122">Este método de control de eventos llama a los métodos para leer el documento y mostrar el cuadro de diálogo de vista previa de impresión.</span><span class="sxs-lookup"><span data-stu-id="e884b-122">This event-handling method calls the methods to read the document and show the print preview dialog.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#4)]
     [!code-vb[System.Drawing.Printing.PrintPreviewExample#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="e884b-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e884b-123">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintPreviewExample#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintPreviewExample/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e884b-124">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="e884b-124">Compiling the Code</span></span>  
 <span data-ttu-id="e884b-125">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="e884b-125">This example requires:</span></span>  
  
- <span data-ttu-id="e884b-126">Referencias a los ensamblados System, System.Windows.Forms, System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="e884b-126">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e884b-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="e884b-127">See also</span></span>

- [<span data-ttu-id="e884b-128">Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e884b-128">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- <span data-ttu-id="e884b-129">[Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e884b-129">[Windows Forms Print Support](windows-forms-print-support.md)</span></span>
- [<span data-ttu-id="e884b-130">Impresión más segura en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e884b-130">More Secure Printing in Windows Forms</span></span>](../more-secure-printing-in-windows-forms.md)
