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
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923574"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="f3204-102">Procedimiento Agregar una marca de agua a un control TextBox</span><span class="sxs-lookup"><span data-stu-id="f3204-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="f3204-103">En el ejemplo siguiente se muestra cómo ayudar a la <xref:System.Windows.Controls.TextBox> facilidad de uso de un mediante la presentación de <xref:System.Windows.Controls.TextBox> una imagen de fondo explicativa dentro de hasta que el usuario escribe texto, momento en el que se quita la imagen.</span><span class="sxs-lookup"><span data-stu-id="f3204-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="f3204-104">Además, la imagen de fondo se restaura de nuevo si el usuario quita su entrada.</span><span class="sxs-lookup"><span data-stu-id="f3204-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="f3204-105">Vea la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="f3204-105">See illustration below.</span></span>  
  
 <span data-ttu-id="f3204-106">![Un cuadro de texto con una imagen de fondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="f3204-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f3204-107">La razón por la que se usa una imagen de fondo en este ejemplo en lugar <xref:System.Windows.Controls.TextBox.Text%2A> de simplemente <xref:System.Windows.Controls.TextBox>manipular la propiedad de, es que una imagen de fondo no interfiere con el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="f3204-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f3204-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f3204-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f3204-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3204-109">See also</span></span>

- [<span data-ttu-id="f3204-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="f3204-110">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="f3204-111">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="f3204-111">[RichTextBox Overview](richtextbox-overview.md)</span></span>
