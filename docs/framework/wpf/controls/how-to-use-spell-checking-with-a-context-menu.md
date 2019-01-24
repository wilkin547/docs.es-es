---
title: Procedimiento Usar el corrector ortográfico con un menú contextual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling spell checking in a text box [WPF]
- reenabling spell checking in a text box [WPF]
- spell checking with a context menu [WPF]
ms.assetid: 61f69a20-2ff3-4056-9060-e32f4483ec5e
ms.openlocfilehash: 2b6790fd4d5d2e322a46bd98ed19e7b88c4923c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713121"
---
# <a name="how-to-use-spell-checking-with-a-context-menu"></a><span data-ttu-id="defc2-102">Procedimiento Usar el corrector ortográfico con un menú contextual</span><span class="sxs-lookup"><span data-stu-id="defc2-102">How to: Use Spell Checking with a Context Menu</span></span>
<span data-ttu-id="defc2-103">De forma predeterminada, cuando se habilita el corrector ortográfico en un control de edición como <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.RichTextBox>, obtendrá las opciones de corrector ortográfico en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="defc2-103">By default, when you enable spell checking in an editing control like <xref:System.Windows.Controls.TextBox> or <xref:System.Windows.Controls.RichTextBox>, you get spell-checking choices in the context menu.</span></span> <span data-ttu-id="defc2-104">Por ejemplo, cuando los usuarios, haga clic en una palabra mal escrita, obtener un conjunto de sugerencias de ortografía o la opción de **omitir todas**.</span><span class="sxs-lookup"><span data-stu-id="defc2-104">For example, when users right-click a misspelled word, they get a set of spelling suggestions or the option to **Ignore All**.</span></span> <span data-ttu-id="defc2-105">Sin embargo, cuando se reemplaza el menú contextual de forma predeterminada con su propio menú contextual personalizado, esta funcionalidad se pierde y necesita escribir código para volver a habilitar la característica de corrector ortográfico en el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="defc2-105">However, when you override the default context menu with your own custom context menu, this functionality is lost, and you need to write code to reenable the spell-checking feature in the context menu.</span></span> <span data-ttu-id="defc2-106">En el ejemplo siguiente se muestra cómo habilitar esto en un <xref:System.Windows.Controls.TextBox>.</span><span class="sxs-lookup"><span data-stu-id="defc2-106">The following example shows how to enable this on a <xref:System.Windows.Controls.TextBox>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="defc2-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="defc2-107">Example</span></span>  
 <span data-ttu-id="defc2-108">El ejemplo siguiente se muestra el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] que crea un <xref:System.Windows.Controls.TextBox> con algunos eventos que se usan para implementar el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="defc2-108">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] that creates a <xref:System.Windows.Controls.TextBox> with some events that are used to implement the context menu.</span></span>  
  
 [!code-xaml[TextBoxMiscSnippets_snip#SpellerCustomContextMenuExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml#spellercustomcontextmenuexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="defc2-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="defc2-109">Example</span></span>  
 <span data-ttu-id="defc2-110">El ejemplo siguiente muestra el código que implementa el menú contextual.</span><span class="sxs-lookup"><span data-stu-id="defc2-110">The following example shows the code that implements the context menu.</span></span>  
  
 [!code-csharp[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/speller_custom_context_menu.xaml.cs#spellercustomcontextmenucodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#SpellerCustomContextMenuCodeExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/speller_custom_context_menu.xaml.vb#spellercustomcontextmenucodeexamplewholepage)]  
  
 <span data-ttu-id="defc2-111">El código que se usa para hacer esto con un <xref:System.Windows.Controls.RichTextBox> es similar.</span><span class="sxs-lookup"><span data-stu-id="defc2-111">The code used for doing this with a <xref:System.Windows.Controls.RichTextBox> is similar.</span></span> <span data-ttu-id="defc2-112">La diferencia principal radica en el parámetro pasado a la `GetSpellingError` método.</span><span class="sxs-lookup"><span data-stu-id="defc2-112">The main difference is in the parameter passed to the `GetSpellingError` method.</span></span> <span data-ttu-id="defc2-113">Para un <xref:System.Windows.Controls.TextBox>, pase el índice de entero de la posición del símbolo de intercalación:</span><span class="sxs-lookup"><span data-stu-id="defc2-113">For a <xref:System.Windows.Controls.TextBox>, pass the integer index of the caret position:</span></span>  
  
 `spellingError = myTextBox.GetSpellingError(caretIndex);`  
  
 <span data-ttu-id="defc2-114">Para un <xref:System.Windows.Controls.RichTextBox>, pase el <xref:System.Windows.Documents.TextPointer> que especifica la posición del símbolo de intercalación:</span><span class="sxs-lookup"><span data-stu-id="defc2-114">For a <xref:System.Windows.Controls.RichTextBox>, pass the <xref:System.Windows.Documents.TextPointer> that specifies the caret position:</span></span>  
  
 `spellingError = myRichTextBox.GetSpellingError(myRichTextBox.CaretPosition);`  
  
## <a name="see-also"></a><span data-ttu-id="defc2-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="defc2-115">See also</span></span>
- [<span data-ttu-id="defc2-116">Información general sobre TextBox</span><span class="sxs-lookup"><span data-stu-id="defc2-116">TextBox Overview</span></span>](../../../../docs/framework/wpf/controls/textbox-overview.md)
- <span data-ttu-id="defc2-117">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md) (Introducción a RichTextBox)</span><span class="sxs-lookup"><span data-stu-id="defc2-117">[RichTextBox Overview](../../../../docs/framework/wpf/controls/richtextbox-overview.md)</span></span>
- [<span data-ttu-id="defc2-118">Habilitar el corrector ortográfico en un control de edición de texto</span><span class="sxs-lookup"><span data-stu-id="defc2-118">Enable Spell Checking in a Text Editing Control</span></span>](../../../../docs/framework/wpf/controls/how-to-enable-spell-checking-in-a-text-editing-control.md)
- [<span data-ttu-id="defc2-119">Usar un menú contextual personalizado con un control TextBox</span><span class="sxs-lookup"><span data-stu-id="defc2-119">Use a Custom Context Menu with a TextBox</span></span>](../../../../docs/framework/wpf/controls/how-to-use-a-custom-context-menu-with-a-textbox.md)
