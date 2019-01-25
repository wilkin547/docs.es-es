---
title: Procedimiento Agregar una marca de agua a un TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: 1ab8c0f9274f4d461c9c2be04ec0aaca5e753c7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54531137"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="e2ba1-102">Procedimiento Agregar una marca de agua a un TextBox</span><span class="sxs-lookup"><span data-stu-id="e2ba1-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="e2ba1-103">El ejemplo siguiente muestra cómo facilitar el uso de un <xref:System.Windows.Controls.TextBox> al mostrar una imagen de fondo explicativa dentro de la <xref:System.Windows.Controls.TextBox> hasta que el usuario escribe texto, momento en que se quita la imagen.</span><span class="sxs-lookup"><span data-stu-id="e2ba1-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="e2ba1-104">Además, la imagen de fondo se puede restaurar de nuevo si el usuario quita los datos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="e2ba1-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="e2ba1-105">Consulte la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="e2ba1-105">See illustration below.</span></span>  
  
 <span data-ttu-id="e2ba1-106">![Un cuadro de texto con una imagen de fondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="e2ba1-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2ba1-107">La razón de una imagen de fondo se usa en este ejemplo en su lugar, a continuación, simplemente manipular el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox>, es que una imagen de fondo no interfiera con el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="e2ba1-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2ba1-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e2ba1-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e2ba1-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2ba1-109">See also</span></span>
- [<span data-ttu-id="e2ba1-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="e2ba1-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- <span data-ttu-id="e2ba1-111">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="e2ba1-111">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
