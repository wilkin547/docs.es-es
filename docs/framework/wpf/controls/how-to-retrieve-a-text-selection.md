---
title: 'Cómo: Recuperar una selección de texto'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], retrieving
- TextBox control [WPF], retrieving text
- retrieving text [WPF]
ms.assetid: d5793172-1e11-4a39-9be0-73f336ed858d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d010d0c5bbe5ba3cad826df74d054af4c9b8f452
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-retrieve-a-text-selection"></a><span data-ttu-id="e0aed-102">Cómo: Recuperar una selección de texto</span><span class="sxs-lookup"><span data-stu-id="e0aed-102">How to: Retrieve a Text Selection</span></span>
<span data-ttu-id="e0aed-103">Este ejemplo muestra cómo usar la <xref:System.Windows.Controls.TextBox.SelectedText%2A> propiedad que se va a recuperar el texto que el usuario ha seleccionado en un <xref:System.Windows.Controls.TextBox> control.</span><span class="sxs-lookup"><span data-stu-id="e0aed-103">This example shows one way to use the <xref:System.Windows.Controls.TextBox.SelectedText%2A> property to retrieve text that the user has selected in a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0aed-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0aed-104">Example</span></span>  
 <span data-ttu-id="e0aed-105">El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se muestra la definición de un <xref:System.Windows.Controls.TextBox> control que contiene el texto que desea seleccionar, y un <xref:System.Windows.Controls.Button> control con un determinado <xref:System.Windows.Controls.Button.OnClick%2A> método.</span><span class="sxs-lookup"><span data-stu-id="e0aed-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example shows the definition of a <xref:System.Windows.Controls.TextBox> control that contains some text to select, and a <xref:System.Windows.Controls.Button> control with a specified <xref:System.Windows.Controls.Button.OnClick%2A> method.</span></span>  
  
 <span data-ttu-id="e0aed-106">En este ejemplo, un botón con un asociado <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos se usa para recuperar la selección de texto.</span><span class="sxs-lookup"><span data-stu-id="e0aed-106">In this example, a button with an associated <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler is used to retrieve the text selection.</span></span> <span data-ttu-id="e0aed-107">Cuando el usuario hace clic en el botón, el <xref:System.Windows.Controls.Button.OnClick%2A> método copia cualquier texto seleccionado en el cuadro de texto en una cadena.</span><span class="sxs-lookup"><span data-stu-id="e0aed-107">When the user clicks the button, the <xref:System.Windows.Controls.Button.OnClick%2A> method copies any selected text in the textbox into a string.</span></span> <span data-ttu-id="e0aed-108">Los casos especiales de forma que la selección de texto se recupera (hacer clic en un botón), así como la acción realizada con esa selección (copiar la selección de texto en una cadena), pueden modificarse fácilmente para adaptarse a una amplia variedad de escenarios.</span><span class="sxs-lookup"><span data-stu-id="e0aed-108">The particular circumstances by which the text selection is retrieved (clicking a button), as well as the action taken with that selection (copying the text selection to a string), can easily be modified to accommodate a wide variety of scenarios.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxSelectTextXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxselecttextxaml)]  
  
## <a name="example"></a><span data-ttu-id="e0aed-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0aed-109">Example</span></span>  
 <span data-ttu-id="e0aed-110">C# ejemplo siguiente se muestra un <xref:System.Windows.Controls.Button.OnClick%2A> controlador de eventos para el botón definido en el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e0aed-110">The following C# example shows an <xref:System.Windows.Controls.Button.OnClick%2A> event handler for the button defined in the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] for this example.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_SelectText](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_selecttext)]
 [!code-vb[TextBox_MiscCode#_SelectText](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_selecttext)]  
  
## <a name="see-also"></a><span data-ttu-id="e0aed-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0aed-111">See Also</span></span>  
 [<span data-ttu-id="e0aed-112">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="e0aed-112">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="e0aed-113">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="e0aed-113">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
