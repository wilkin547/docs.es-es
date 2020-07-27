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
# <a name="how-to-set-the-text-content-of-a-textbox-control"></a><span data-ttu-id="c95d3-103">Cómo: Establecer el contenido de texto de un control TextBox</span><span class="sxs-lookup"><span data-stu-id="c95d3-103">How to: Set the Text Content of a TextBox Control</span></span>

<span data-ttu-id="c95d3-104">En este ejemplo se muestra cómo utilizar la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad para establecer el contenido de texto inicial de un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="c95d3-104">This example shows how to use the <xref:System.Windows.Controls.TextBox.Text%2A> property to set the initial text contents of a <xref:System.Windows.Controls.TextBox> control.</span></span>

> [!NOTE]
> <span data-ttu-id="c95d3-105">Aunque la [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] versión del ejemplo podría usar las `<TextBox.Text>` etiquetas alrededor del texto del contenido de cada botón <xref:System.Windows.Controls.TextBox> , no es necesario porque <xref:System.Windows.Controls.TextBox> aplica el <xref:System.Windows.Markup.ContentPropertyAttribute> atributo a la <xref:System.Windows.Controls.TextBox.Text%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c95d3-105">Although the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] version of the example could use the `<TextBox.Text>` tags around the text of each button's <xref:System.Windows.Controls.TextBox> content, it is not necessary because the <xref:System.Windows.Controls.TextBox> applies the <xref:System.Windows.Markup.ContentPropertyAttribute> attribute to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="c95d3-106">Para obtener más información, vea [información general sobre XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span><span class="sxs-lookup"><span data-stu-id="c95d3-106">For more information, see [XAML Overview (WPF)](../../../desktop-wpf/fundamentals/xaml.md).</span></span>

## <a name="example"></a><span data-ttu-id="c95d3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c95d3-107">Example</span></span>

[!code-xaml[TextBox_MiscCode#_TextBoxSetTextXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxsettextxaml)]

## <a name="example"></a><span data-ttu-id="c95d3-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c95d3-108">Example</span></span>

[!code-csharp[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_textboxsettext)]
[!code-vb[TextBox_MiscCode#_TextBoxSetText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_textboxsettext)]

## <a name="see-also"></a><span data-ttu-id="c95d3-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="c95d3-109">See also</span></span>

- [<span data-ttu-id="c95d3-110">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="c95d3-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="c95d3-111">Información general sobre el control RichTextBox</span><span class="sxs-lookup"><span data-stu-id="c95d3-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
