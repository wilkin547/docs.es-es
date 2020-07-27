---
title: 'Cómo: Establecer el contenido de texto de un control TextBox'
description: Obtenga información sobre cómo usar la propiedad Text para establecer el contenido de texto inicial de un control TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], setting
- TextBox control [WPF], setting text content
ms.assetid: bcd25fc7-a52f-4453-b802-2c8d2b335ab8
ms.openlocfilehash: 41efb69e297b3c6fdb1203c358dcc72d7a9f806f
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168050"
---
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a>Cómo: Establecer el contenido de texto de un control TextBox

En este ejemplo se muestra cómo utilizar la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad para establecer el contenido de texto inicial de un <xref:System.Windows.Controls.TextBox> control.

> [!NOTE]
> Aunque la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versión del ejemplo podría usar las `<TextBox.Text>` etiquetas alrededor del texto del contenido de cada botón <xref:System.Windows.Controls.TextBox> , no es necesario porque <xref:System.Windows.Controls.TextBox> aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad. Para obtener más información, vea [información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).

## <a name="example"></a>Ejemplo

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a>Ejemplo

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a>Vea también

- [Información general sobre TextBox](textbox-overview.md)
- [Información general sobre el control RichTextBox](richtextbox-overview.md)
