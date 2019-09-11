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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="51616-102">Procedimiento Establecer el contenido de texto de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="51616-102">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="51616-103">En este ejemplo se muestra cómo utilizar <xref:System.Windows.Controls.TextBox.Text%2A> la propiedad para establecer el contenido de texto inicial <xref:System.Windows.Controls.TextBox> de un control.</span><span class="sxs-lookup"><span data-stu-id="51616-103">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="51616-104">Aunque la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versión del ejemplo podría usar las `<TextBox.Text>` etiquetas alrededor del <xref:System.Windows.Controls.TextBox> texto del <xref:System.Windows.Controls.TextBox> contenido de cada botón, no es necesario porque aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad. .</span><span class="sxs-lookup"><span data-stu-id="51616-104">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="51616-105">Para obtener más información, vea [información general sobre XAML (WPF)](../advanced/xaml-overview-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="51616-105">For more information, see [XAML Overview (WPF)](../advanced/xaml-overview-wpf.md).</span></span>

## <a name="example"></a><span data-ttu-id="51616-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51616-106">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="51616-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="51616-107">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="51616-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="51616-108">See also</span></span>

- [<span data-ttu-id="51616-109">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="51616-109">TextBox Overview</span></span>](textbox-overview.md)
- <span data-ttu-id="51616-110">[RichTextBox Overview](richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="51616-110">[RichTextBox Overview](richtextbox-overview.md)</span></span>
