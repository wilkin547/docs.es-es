---
title: 'Cómo: Usar un menú contextual personalizado con un control TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- context menus [WPF], custom
- menus [WPF], custom
- custom context menus [WPF]
- TextBox control [WPF], custom content menus
ms.assetid: 842d3cd5-6fa0-4be4-8d90-6c7466213b1c
ms.openlocfilehash: edcf6bdf381ae51a3354f9bc0b3c91d86e1f8f44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552784"
---
# <a name="how-to-use-a-custom-context-menu-with-a-textbox"></a><span data-ttu-id="e743d-102">Cómo: Usar un menú contextual personalizado con un control TextBox</span><span class="sxs-lookup"><span data-stu-id="e743d-102">How to: Use a Custom Context Menu with a TextBox</span></span>
<span data-ttu-id="e743d-103">Este ejemplo muestra cómo definir e implementar un menú contextual personalizado simple para una <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="e743d-103">This example shows how to define and implement a simple custom context menu for a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e743d-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e743d-104">Example</span></span>  
 <span data-ttu-id="e743d-105">El siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en el ejemplo se define un <xref:System.Windows.Controls.TextBox> control que incluye un menú contextual personalizado.</span><span class="sxs-lookup"><span data-stu-id="e743d-105">The following [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] example defines a <xref:System.Windows.Controls.TextBox> control that includes a custom context menu.</span></span>  
  
 <span data-ttu-id="e743d-106">El menú contextual se define utilizando un <xref:System.Windows.Controls.ContextMenu> elemento.</span><span class="sxs-lookup"><span data-stu-id="e743d-106">The context menu is defined using a <xref:System.Windows.Controls.ContextMenu> element.</span></span>  <span data-ttu-id="e743d-107">El propio menú contextual está formada por una serie de <xref:System.Windows.Controls.MenuItem> elementos y <xref:System.Windows.Controls.Separator> elementos.</span><span class="sxs-lookup"><span data-stu-id="e743d-107">The context menu itself consists of a series of <xref:System.Windows.Controls.MenuItem> elements and <xref:System.Windows.Controls.Separator> elements.</span></span>  <span data-ttu-id="e743d-108">Cada <xref:System.Windows.Controls.MenuItem> elemento define un comando en el menú contextual; la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> atributo define el texto de presentación para el comando de menú y el <xref:System.Windows.Controls.MenuItem.Click> atributo especifica un método de controlador para cada elemento de menú.</span><span class="sxs-lookup"><span data-stu-id="e743d-108">Each <xref:System.Windows.Controls.MenuItem> element defines a command in the context menu; the <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> attribute defines the display text for the menu command, and the <xref:System.Windows.Controls.MenuItem.Click> attribute specifies a handler method for each menu item.</span></span>  <span data-ttu-id="e743d-109">El <xref:System.Windows.Controls.Separator> elemento simplemente hace que una línea de separación para representarse entre los elementos de menú anteriores y posteriores.</span><span class="sxs-lookup"><span data-stu-id="e743d-109">The <xref:System.Windows.Controls.Separator> element simply causes a separating line to be rendered between the previous and subsequent menu items.</span></span>  
  
 [!code-xaml[TextBox_ContextMenu#_TextBox_ContextMenuXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml#_textbox_contextmenuxaml)]  
  
## <a name="example"></a><span data-ttu-id="e743d-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e743d-110">Example</span></span>  
 <span data-ttu-id="e743d-111">En el ejemplo siguiente se muestra el código de implementación para la definición de menú contextual anterior, así como el código que habilita y deshabilita el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e743d-111">The following example shows the implementation code for the preceding context menu definition, as well as the code that enables and disables the context menu.</span></span>  <span data-ttu-id="e743d-112">El <xref:System.Windows.Controls.ContextMenu.Opened> eventos se usan para habilitar o deshabilitar determinados comandos según el estado actual de dinámicamente el <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="e743d-112">The <xref:System.Windows.Controls.ContextMenu.Opened> event is used to dynamically enable or disable certain commands depending on the current state of the <xref:System.Windows.Controls.TextBox>.</span></span>  
  
 <span data-ttu-id="e743d-113">Para restaurar el menú contextual predeterminado, utilice la <xref:System.Windows.DependencyObject.ClearValue%2A> método para borrar el valor de la <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e743d-113">To restore the default context menu, use the <xref:System.Windows.DependencyObject.ClearValue%2A> method to clear the value of the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property.</span></span>  <span data-ttu-id="e743d-114">Para deshabilitar por completo el menú contextual, establezca la <xref:System.Windows.FrameworkElement.ContextMenu%2A> propiedad en una referencia nula (`Nothing` en Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="e743d-114">To disable the context menu altogether, set the <xref:System.Windows.FrameworkElement.ContextMenu%2A> property to a null reference (`Nothing` in Visual Basic).</span></span>  
  
 [!code-csharp[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBox_ContextMenu/CSharp/Window1.xaml.cs#_textbox_contextmenu)]
 [!code-vb[TextBox_ContextMenu#_TextBox_ContextMenu](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_ContextMenu/VisualBasic/Window1.xaml.vb#_textbox_contextmenu)]  
  
## <a name="see-also"></a><span data-ttu-id="e743d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e743d-115">See Also</span></span>  
 [<span data-ttu-id="e743d-116">Usar el corrector ortográfico con un menú contextual</span><span class="sxs-lookup"><span data-stu-id="e743d-116">Use Spell Checking with a Context Menu</span></span>](../../../../docs/framework/wpf/controls/how-to-use-spell-checking-with-a-context-menu.md)  
 [<span data-ttu-id="e743d-117">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="e743d-117">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)  
 <span data-ttu-id="e743d-118">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="e743d-118">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
