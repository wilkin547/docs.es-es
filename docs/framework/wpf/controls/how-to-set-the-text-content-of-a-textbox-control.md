---
title: 'Cómo: Establecer el contenido de texto de un control TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 9b16f2d99295a28725255361b0be3ef7f4245fd2
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459305"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Cómo: Establecer el contenido de texto de un control TextBox

En este ejemplo se muestra cómo utilizar la propiedad <xref:System.Windows.Controls.TextBox.Text%2A> para establecer el contenido de texto inicial de un control <xref:System.Windows.Controls.TextBox>.

> [!NOTE]
> Aunque la versión [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] del ejemplo podría usar las etiquetas de `<TextBox.Text>` alrededor del texto del contenido de <xref:System.Windows.Controls.TextBox> de cada botón, no es necesario porque el <xref:System.Windows.Controls.TextBox> aplica el atributo <xref:System.Windows.Markup.ContentPropertyAttribute> a la propiedad <xref:System.Windows.Controls.TextBox.Text%2A>. Para obtener más información, vea [información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Ejemplo

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Ejemplo

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
