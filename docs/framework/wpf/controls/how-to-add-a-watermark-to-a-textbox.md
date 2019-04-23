---
title: Procedimiento Agregar una marca de agua a un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: ef2536f03ba6ed08e27d2fcf30cd1f72df2cf460
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142420"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="372f2-102">Procedimiento Agregar una marca de agua a un control TextBox</span><span class="sxs-lookup"><span data-stu-id="372f2-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="372f2-103">El ejemplo siguiente muestra cómo facilitar el uso de un <xref:System.Windows.Controls.TextBox> al mostrar una imagen de fondo explicativa dentro de la <xref:System.Windows.Controls.TextBox> hasta que el usuario escribe texto, momento en que se quita la imagen.</span><span class="sxs-lookup"><span data-stu-id="372f2-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="372f2-104">Además, la imagen de fondo se puede restaurar de nuevo si el usuario quita los datos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="372f2-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="372f2-105">Consulte la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="372f2-105">See illustration below.</span></span>  
  
 <span data-ttu-id="372f2-106">![Un cuadro de texto con una imagen de fondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="372f2-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="372f2-107">La razón de una imagen de fondo se usa en este ejemplo en su lugar, a continuación, simplemente manipular el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox>, es que una imagen de fondo no interfiera con el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="372f2-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="372f2-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="372f2-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="372f2-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="372f2-109">See also</span></span>

- [<span data-ttu-id="372f2-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="372f2-110">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="372f2-111">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="372f2-111">[RichTextBox Overview](richtextbox-overview.md)</span></span>
