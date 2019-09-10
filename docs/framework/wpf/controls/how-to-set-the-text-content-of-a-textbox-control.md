---
title: Procedimiento Establecer el contenido de texto de un control TextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 2e2bc70b108991fd4e3c138bfac5bff942173e33
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70856115"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Procedimiento Establecer el contenido de texto de un control TextBox

En este ejemplo se muestra cómo utilizar <xref:System.Windows.Controls.TextBox.Text%2A> la propiedad para establecer el contenido de texto inicial <xref:System.Windows.Controls.TextBox> de un control.

> [!NOTE]
> Aunque la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versión del ejemplo podría usar las `<TextBox.Text>` etiquetas alrededor del <xref:System.Windows.Controls.TextBox> texto del <xref:System.Windows.Controls.TextBox> contenido de cada botón, no es necesario porque aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad. . Para obtener más información, vea [información general sobre XAML (WPF)](../advanced/xaml-overview-wpf.md).

## <a name="example"></a>Ejemplo

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Ejemplo

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)
