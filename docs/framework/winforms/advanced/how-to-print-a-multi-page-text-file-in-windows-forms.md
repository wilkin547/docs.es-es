---
title: 'Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing [Windows Forms], printing multiple pages
- text [Windows Forms], printing Windows Forms
- Windows Forms, printing text
- printing [Windows Forms], text
ms.assetid: 362427f8-03d4-4826-b49f-60ab066ad322
ms.openlocfilehash: 6d6701e5e4b9a0b0fbb677b49f3791075976745a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523008"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a><span data-ttu-id="c4c21-102">Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c4c21-102">How to: Print a Multi-Page Text File in Windows Forms</span></span>
<span data-ttu-id="c4c21-103">Es muy común que las aplicaciones basadas en Windows impriman texto.</span><span class="sxs-lookup"><span data-stu-id="c4c21-103">It is very common for Windows-based applications to print text.</span></span> <span data-ttu-id="c4c21-104">La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar objetos (gráficos o texto) en un dispositivo, como una pantalla o una impresora.</span><span class="sxs-lookup"><span data-stu-id="c4c21-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects (graphics or text) to a device, such as a screen or printer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4c21-105">No se admiten los métodos <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de <xref:System.Windows.Forms.TextRenderer> para la impresión.</span><span class="sxs-lookup"><span data-stu-id="c4c21-105">The <xref:System.Windows.Forms.TextRenderer.DrawText%2A> methods of <xref:System.Windows.Forms.TextRenderer> are not supported for printing.</span></span> <span data-ttu-id="c4c21-106">Debe usar siempre los métodos <xref:System.Drawing.Graphics.DrawString%2A> de <xref:System.Drawing.Graphics>, tal y como se muestra en el siguiente ejemplo de código, para dibujar texto para impresión.</span><span class="sxs-lookup"><span data-stu-id="c4c21-106">You should always use the <xref:System.Drawing.Graphics.DrawString%2A> methods of <xref:System.Drawing.Graphics>, as shown in the following code example, to draw text for printing purposes.</span></span>  
  
### <a name="to-print-text"></a><span data-ttu-id="c4c21-107">Para imprimir texto</span><span class="sxs-lookup"><span data-stu-id="c4c21-107">To print text</span></span>  
  
1.  <span data-ttu-id="c4c21-108">Agregue un componente <xref:System.Drawing.Printing.PrintDocument> y una cadena al formulario.</span><span class="sxs-lookup"><span data-stu-id="c4c21-108">Add a <xref:System.Drawing.Printing.PrintDocument> component and a string to your form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2.  <span data-ttu-id="c4c21-109">Si imprime un documento, establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> en el documento que quiere imprimir y abra y lea el contenido del documento en la cadena que agregó previamente.</span><span class="sxs-lookup"><span data-stu-id="c4c21-109">If printing a document, set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property to the document you wish to print, and open and read the documents contents to the string you added previously.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3.  <span data-ttu-id="c4c21-110">En el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>, use la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> y el contenido del documento para calcular la longitud de la línea y las líneas por página.</span><span class="sxs-lookup"><span data-stu-id="c4c21-110">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class and the document contents to calculate line length and lines per page.</span></span> <span data-ttu-id="c4c21-111">Una vez dibujada cada página, compruebe si es la última página y establezca la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> de <xref:System.Drawing.Printing.PrintPageEventArgs> como corresponda.</span><span class="sxs-lookup"><span data-stu-id="c4c21-111">After each page is drawn, check to see if it is the last page, and set the <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> accordingly.</span></span> <span data-ttu-id="c4c21-112">El evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> se produce hasta que <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> es `false`.</span><span class="sxs-lookup"><span data-stu-id="c4c21-112">The <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is raised until <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> is `false`.</span></span> <span data-ttu-id="c4c21-113">Además, asegúrese de que el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> está asociado con su método de control de eventos.</span><span class="sxs-lookup"><span data-stu-id="c4c21-113">Also, make sure the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event is associated with its event-handling method.</span></span>  
  
     <span data-ttu-id="c4c21-114">En el ejemplo de código siguiente, se usa el controlador de eventos para imprimir el contenido del archivo "testPage.txt" con la misma fuente que se usa en el formulario.</span><span class="sxs-lookup"><span data-stu-id="c4c21-114">In the following code example, the event handler is used to print the contents of the "testPage.txt" file in the same font as is used on the form.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4.  <span data-ttu-id="c4c21-115">Llame al método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para producir el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.</span><span class="sxs-lookup"><span data-stu-id="c4c21-115">Call the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to raise the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="c4c21-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4c21-116">Example</span></span>  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c4c21-117">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="c4c21-117">Compiling the Code</span></span>  
 <span data-ttu-id="c4c21-118">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="c4c21-118">This example requires:</span></span>  
  
-   <span data-ttu-id="c4c21-119">Un archivo de texto llamado testPage.txt que contiene el texto que se va a imprimir y que se encuentra en la raíz de la unidad C:\\.</span><span class="sxs-lookup"><span data-stu-id="c4c21-119">A text file named testPage.txt containing the text to print, located in the root of drive C:\\.</span></span> <span data-ttu-id="c4c21-120">Modifique el código para imprimir un archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="c4c21-120">Edit the code to print a different file.</span></span>  
  
-   <span data-ttu-id="c4c21-121">Referencias a los ensamblados System, System.Windows.Forms, System.Drawing.</span><span class="sxs-lookup"><span data-stu-id="c4c21-121">References to the System, System.Windows.Forms, System.Drawing assemblies.</span></span>  
  
-   <span data-ttu-id="c4c21-122">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c4c21-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c4c21-123">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="c4c21-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="c4c21-124">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="c4c21-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4c21-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4c21-125">See Also</span></span>  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Brush>  
 <span data-ttu-id="c4c21-126">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="c4c21-126">[Windows Forms Print Support](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)</span></span>
