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
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Procedimiento Agregar una marca de agua a un control TextBox
En el ejemplo siguiente se muestra cómo ayudar a la <xref:System.Windows.Controls.TextBox> facilidad de uso de un mediante la presentación de <xref:System.Windows.Controls.TextBox> una imagen de fondo explicativa dentro de hasta que el usuario escribe texto, momento en el que se quita la imagen. Además, la imagen de fondo se restaura de nuevo si el usuario quita su entrada. Vea la ilustración siguiente.  
  
 ![Un cuadro de texto con una imagen de fondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
> La razón por la que se usa una imagen de fondo en este ejemplo en lugar <xref:System.Windows.Controls.TextBox.Text%2A> de simplemente <xref:System.Windows.Controls.TextBox>manipular la propiedad de, es que una imagen de fondo no interfiere con el enlace de datos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
