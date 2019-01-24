---
title: Procedimiento Recuperar una selección de texto
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
ms.openlocfilehash: 3e2a4d9938f73cb306e8fd8b0e6b25b5abfa3b4a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517778"
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="ffb9e-102">Procedimiento Recuperar una selección de texto</span><span class="sxs-lookup"><span data-stu-id="ffb9e-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="ffb9e-103">En este ejemplo se muestra una forma de usar el <xref:System.Windows.Controls.TextBox.SelectedText%2A> propiedad para recuperar el texto que el usuario ha seleccionado en un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffb9e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffb9e-104">Example</span></span>  
 <span data-ttu-id="ffb9e-105">La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra la definición de un <xref:System.Windows.Controls.TextBox> control que contiene el texto que desea seleccionar, y un <xref:System.Windows.Controls.Button> control con un determinado <xref:System.Windows.Controls.Button.OnClick%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="ffb9e-106">En este ejemplo, un botón con un asociado <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos se usa para recuperar la selección de texto.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="ffb9e-107">Cuando el usuario hace clic en el botón, el <xref:System.Windows.Controls.Button.OnClick%2A> método copia el texto seleccionado en el cuadro de texto en una cadena.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="ffb9e-108">Las circunstancias concretas de forma que la selección de texto se recupera (hacer clic en un botón), así como la acción realizada con esa selección (copiar la selección de texto en una cadena), puede modificar fácilmente para adaptarse a una amplia variedad de escenarios.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="ffb9e-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ffb9e-109">Example</span></span>  
 <span data-ttu-id="ffb9e-110">La siguiente C# en el ejemplo se muestra un <xref:System.Windows.Controls.Button.OnClick%2A> controlador de eventos para el botón definido en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="ffb9e-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="ffb9e-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ffb9e-111">See also</span></span>
- [<span data-ttu-id="ffb9e-112">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="ffb9e-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- <span data-ttu-id="ffb9e-113">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="ffb9e-113">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
