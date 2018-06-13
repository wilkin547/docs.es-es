---
title: 'Cómo: Crear una decoración de texto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545414"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="9e07a-102">Cómo: Crear una decoración de texto</span><span class="sxs-lookup"><span data-stu-id="9e07a-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="9e07a-103">Un <xref:System.Windows.TextDecoration> objeto es un adorno visual que se puede agregar al texto.</span><span class="sxs-lookup"><span data-stu-id="9e07a-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="9e07a-104">Hay cuatro tipos de decoraciones de texto: subrayado, línea base, tachado y línea alta.</span><span class="sxs-lookup"><span data-stu-id="9e07a-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="9e07a-105">El ejemplo siguiente muestra las ubicaciones de las decoraciones de texto en relación con el texto.</span><span class="sxs-lookup"><span data-stu-id="9e07a-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="9e07a-106">![Diagrama de ubicaciones de decoraciones de texto](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="9e07a-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="9e07a-107">Ejemplo de tipos de decoración de texto</span><span class="sxs-lookup"><span data-stu-id="9e07a-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="9e07a-108">Para agregar una decoración de texto al texto, cree un <xref:System.Windows.TextDecoration> de objetos y modificar sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="9e07a-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="9e07a-109">Use la <xref:System.Windows.TextDecoration.Location%2A> propiedad para especificar dónde aparece la decoración de texto, como subrayado.</span><span class="sxs-lookup"><span data-stu-id="9e07a-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="9e07a-110">Use la <xref:System.Windows.TextDecoration.Pen%2A> propiedad para especificar la apariencia de la decoración de texto, por ejemplo, un relleno sólido o degradado de color.</span><span class="sxs-lookup"><span data-stu-id="9e07a-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="9e07a-111">Si no especifica un valor para el <xref:System.Windows.TextDecoration.Pen%2A> propiedad, los valores predeterminados de decoraciones en el mismo color que el texto.</span><span class="sxs-lookup"><span data-stu-id="9e07a-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="9e07a-112">Una vez que haya definido una <xref:System.Windows.TextDecoration> objeto, agréguela a la <xref:System.Windows.TextDecorations> colección del objeto de texto que desee.</span><span class="sxs-lookup"><span data-stu-id="9e07a-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="9e07a-113">En el ejemplo siguiente se muestra una decoración de texto que se ha aplicado el estilo con un pincel de degradado lineal y un lápiz discontinuo.</span><span class="sxs-lookup"><span data-stu-id="9e07a-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="9e07a-114">![Decoración de texto con subrayado degradado lineal](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="9e07a-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="9e07a-115">Ejemplo de un subrayado con estilo con un degradado lineal discontinua lápiz y pincel</span><span class="sxs-lookup"><span data-stu-id="9e07a-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="9e07a-116">La <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido dinámico insertado que permite hospedar hipervínculos dentro del contenido dinámico.</span><span class="sxs-lookup"><span data-stu-id="9e07a-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="9e07a-117">De forma predeterminada, <xref:System.Windows.Documents.Hyperlink> utiliza un <xref:System.Windows.TextDecoration> objeto para mostrar un subrayado.</span><span class="sxs-lookup"><span data-stu-id="9e07a-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="9e07a-118"><xref:System.Windows.TextDecoration> los objetos pueden ser mejorar el rendimiento al crear instancias, especialmente si tiene muchos <xref:System.Windows.Documents.Hyperlink> objetos.</span><span class="sxs-lookup"><span data-stu-id="9e07a-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="9e07a-119">Si realiza uso extenso de <xref:System.Windows.Documents.Hyperlink> elementos, puede que desee tener en cuenta que muestra un subrayado únicamente al desencadenar un evento, como el <xref:System.Windows.ContentElement.MouseEnter> eventos.</span><span class="sxs-lookup"><span data-stu-id="9e07a-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="9e07a-120">En el ejemplo siguiente, el subrayado para el vínculo "My MSN" es dinámico, solo aparece cuando la <xref:System.Windows.ContentElement.MouseEnter> evento se desencadena.</span><span class="sxs-lookup"><span data-stu-id="9e07a-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="9e07a-121">![Hipervínculos que muestran TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="9e07a-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="9e07a-122">Hipervínculos definidos con TextDecorations</span><span class="sxs-lookup"><span data-stu-id="9e07a-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="9e07a-123">Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="9e07a-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e07a-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e07a-124">Example</span></span>  
 <span data-ttu-id="9e07a-125">En el ejemplo de código siguiente, una decoración de texto subrayado utiliza el valor de fuente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="9e07a-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="9e07a-126">En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de color sólido para el lápiz.</span><span class="sxs-lookup"><span data-stu-id="9e07a-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="9e07a-127">En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de degradado lineal para el lápiz discontinuo.</span><span class="sxs-lookup"><span data-stu-id="9e07a-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="9e07a-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9e07a-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="9e07a-129">Especificar el subrayado de un hipervínculo</span><span class="sxs-lookup"><span data-stu-id="9e07a-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
