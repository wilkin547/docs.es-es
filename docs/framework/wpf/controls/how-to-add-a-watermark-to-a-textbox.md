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
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Procedimiento Agregar una marca de agua a un TextBox
El ejemplo siguiente muestra cómo facilitar el uso de un <xref:System.Windows.Controls.TextBox> al mostrar una imagen de fondo explicativa dentro de la <xref:System.Windows.Controls.TextBox> hasta que el usuario escribe texto, momento en que se quita la imagen. Además, la imagen de fondo se puede restaurar de nuevo si el usuario quita los datos proporcionados. Consulte la siguiente ilustración.  
  
 ![Un cuadro de texto con una imagen de fondo](../../../../docs/framework/wpf/controls/media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
>  La razón de una imagen de fondo se usa en este ejemplo en su lugar, a continuación, simplemente manipular el <xref:System.Windows.Controls.TextBox.Text%2A> propiedad de <xref:System.Windows.Controls.TextBox>, es que una imagen de fondo no interfiera con el enlace de datos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre TextBox](../../../../docs/framework/wpf/controls/textbox-overview.md)
- [RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)
