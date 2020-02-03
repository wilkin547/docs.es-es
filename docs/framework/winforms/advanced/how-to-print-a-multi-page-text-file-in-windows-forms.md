---
title: 'Cómo: imprimir un archivo de texto de varias páginas'
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
ms.openlocfilehash: 51e30706bb7693988d611701d013792c82dccd0b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76740664"
---
# <a name="how-to-print-a-multi-page-text-file-in-windows-forms"></a>Cómo: Imprimir un archivo de texto de varias páginas en formularios Windows Forms
Es muy común que las aplicaciones basadas en Windows impriman texto. La clase <xref:System.Drawing.Graphics> proporciona métodos para dibujar objetos (gráficos o texto) en un dispositivo, como una pantalla o una impresora.  
  
> [!NOTE]
> No se admiten los métodos <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de <xref:System.Windows.Forms.TextRenderer> para la impresión. Debe usar siempre los métodos <xref:System.Drawing.Graphics.DrawString%2A> de <xref:System.Drawing.Graphics>, tal y como se muestra en el siguiente ejemplo de código, para dibujar texto para impresión.  
  
### <a name="to-print-text"></a>Para imprimir texto  
  
1. Agregue un componente <xref:System.Drawing.Printing.PrintDocument> y una cadena al formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#8)]
     [!code-vb[System.Drawing.Printing.PrintExamples#8](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#8)]  
  
2. Si imprime un documento, establezca la propiedad <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> en el documento que quiere imprimir y abra y lea el contenido del documento en la cadena que agregó previamente.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#1)]
     [!code-vb[System.Drawing.Printing.PrintExamples#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#1)]  
  
3. En el controlador de eventos <xref:System.Drawing.Printing.PrintDocument.PrintPage>, use la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> de la clase <xref:System.Drawing.Printing.PrintPageEventArgs> y el contenido del documento para calcular la longitud de la línea y las líneas por página. Una vez dibujada cada página, compruebe si es la última página y establezca la propiedad <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> de <xref:System.Drawing.Printing.PrintPageEventArgs> como corresponda. El evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> se produce hasta que <xref:System.Drawing.Printing.PrintPageEventArgs.HasMorePages%2A> es `false`. Además, asegúrese de que el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage> está asociado con su método de control de eventos.  
  
     En el ejemplo de código siguiente, se usa el controlador de eventos para imprimir el contenido del archivo "testPage.txt" con la misma fuente que se usa en el formulario.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#2)]
     [!code-vb[System.Drawing.Printing.PrintExamples#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#2)]  
  
4. Llame al método <xref:System.Drawing.Printing.PrintDocument.Print%2A> para producir el evento <xref:System.Drawing.Printing.PrintDocument.PrintPage>.  
  
     [!code-csharp[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#5)]
     [!code-vb[System.Drawing.Printing.PrintExamples#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#5)]  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/CS/Form1.cs#0)]
 [!code-vb[System.Drawing.Printing.PrintExamples#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Printing.PrintExamples/VB/Form1.vb#0)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Un archivo de texto llamado testPage.txt que contiene el texto que se va a imprimir y que se encuentra en la raíz de la unidad C:\\. Modifique el código para imprimir un archivo diferente.  
  
- Referencias a los ensamblados System, System.Windows.Forms, System.Drawing.  
  
- Para obtener información sobre cómo compilar este ejemplo desde la línea de C#comandos para Visual Basic o visual, vea [compilar desde la línea de comandos](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [compilar desde la línea de comandos con CSC. exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [Windows Forms Print Support](windows-forms-print-support.md) (Funcionalidad para imprimir en Windows Forms)
