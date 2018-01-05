---
title: "Cómo: Agregar una marca de agua a un TextBox"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 92d619cb713e22d49e5c62bf7545d946b418dbda
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="294bb-102">Cómo: Agregar una marca de agua a un TextBox</span><span class="sxs-lookup"><span data-stu-id="294bb-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="294bb-103">En el ejemplo siguiente se muestra cómo facilitar el uso de un <xref:System.Windows.Controls.TextBox> , mostrando una imagen de fondo explicativa dentro de la <xref:System.Windows.Controls.TextBox> hasta que el usuario escribe texto, momento en que se quita la imagen.</span><span class="sxs-lookup"><span data-stu-id="294bb-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="294bb-104">Además, la imagen de fondo se restaura de nuevo si el usuario quita su entrada.</span><span class="sxs-lookup"><span data-stu-id="294bb-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="294bb-105">Vea la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="294bb-105">See illustration below.</span></span>  
  
 <span data-ttu-id="294bb-106">![Un cuadro de texto con una imagen de fondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="294bb-106">![A TextBox with a background image](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="294bb-107">El motivo de una imagen de fondo se utiliza en este ejemplo en su lugar, a continuación, simplemente manipular el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox>, es que una imagen de fondo no interfiera con el enlace de datos.</span><span class="sxs-lookup"><span data-stu-id="294bb-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="294bb-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="294bb-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="294bb-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="294bb-109">See Also</span></span>  
 [<span data-ttu-id="294bb-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="294bb-110">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="294bb-111">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="294bb-111">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
