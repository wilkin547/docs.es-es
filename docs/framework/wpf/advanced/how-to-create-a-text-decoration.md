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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185925"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="5949b-102">Cómo: Crear una decoración de texto</span><span class="sxs-lookup"><span data-stu-id="5949b-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="5949b-103">Un <xref:System.Windows.TextDecoration> objeto es una ornamentación visual que se puede agregar al texto.</span><span class="sxs-lookup"><span data-stu-id="5949b-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="5949b-104">Hay cuatro tipos de decoraciones de texto: subrayado, línea de base, tachado y exceso.</span><span class="sxs-lookup"><span data-stu-id="5949b-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="5949b-105">En el ejemplo siguiente se muestran las ubicaciones de las decoraciones de texto relativas al texto.</span><span class="sxs-lookup"><span data-stu-id="5949b-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![Diagrama de los tipos de decoración de texto](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="5949b-107">Para agregar una decoración de <xref:System.Windows.TextDecoration> texto al texto, cree un objeto y modifique sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="5949b-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="5949b-108">Utilice <xref:System.Windows.TextDecoration.Location%2A> la propiedad para especificar dónde aparece la decoración del texto, como subrayado.</span><span class="sxs-lookup"><span data-stu-id="5949b-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="5949b-109">Utilice <xref:System.Windows.TextDecoration.Pen%2A> la propiedad para especificar la apariencia de la decoración del texto, como un color de relleno sólido o degradado.</span><span class="sxs-lookup"><span data-stu-id="5949b-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="5949b-110">Si no especifica un valor <xref:System.Windows.TextDecoration.Pen%2A> para la propiedad, el valor predeterminado de las decoraciones tiene el mismo color que el texto.</span><span class="sxs-lookup"><span data-stu-id="5949b-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="5949b-111">Una vez que <xref:System.Windows.TextDecoration> haya definido un <xref:System.Windows.TextDecorations> objeto, agréguelo a la colección del objeto de texto deseado.</span><span class="sxs-lookup"><span data-stu-id="5949b-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="5949b-112">En el ejemplo siguiente se muestra una decoración de texto que se ha diseñado con un pincel de degradado lineal y un lápiz discontinuo.</span><span class="sxs-lookup"><span data-stu-id="5949b-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![Decoración de texto con subrayado degradado lineal](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="5949b-114">El <xref:System.Windows.Documents.Hyperlink> objeto es un elemento de contenido de flujo de nivel en línea que le permite hospedar hipervínculos dentro del contenido de flujo.</span><span class="sxs-lookup"><span data-stu-id="5949b-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="5949b-115">De forma <xref:System.Windows.Documents.Hyperlink> predeterminada, utiliza un <xref:System.Windows.TextDecoration> objeto para mostrar un subrayado.</span><span class="sxs-lookup"><span data-stu-id="5949b-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="5949b-116"><xref:System.Windows.TextDecoration>los objetos pueden tener un rendimiento <xref:System.Windows.Documents.Hyperlink> intensivo para crear instancias, especialmente si tiene muchos objetos.</span><span class="sxs-lookup"><span data-stu-id="5949b-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="5949b-117">Si hace un <xref:System.Windows.Documents.Hyperlink> uso extensivo de los elementos, es posible que <xref:System.Windows.ContentElement.MouseEnter> desee considerar mostrar un subrayado solo al desencadenar un evento, como el evento.</span><span class="sxs-lookup"><span data-stu-id="5949b-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="5949b-118">En el ejemplo siguiente, el subrayado del vínculo "Mi MSN" <xref:System.Windows.ContentElement.MouseEnter> es dinámico: solo aparece cuando se desencadena el evento.</span><span class="sxs-lookup"><span data-stu-id="5949b-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![Hipervínculos que muestran TextDecorations](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="5949b-120">Para obtener más información, consulte [Especificar el subrayado de un hipervínculo](how-to-specify-whether-a-hyperlink-is-underlined.md).</span><span class="sxs-lookup"><span data-stu-id="5949b-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5949b-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5949b-121">Example</span></span>  
 <span data-ttu-id="5949b-122">En el ejemplo de código siguiente, una decoración de texto subrayado utiliza el valor de fuente predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5949b-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="5949b-123">En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de color sólido para el lápiz.</span><span class="sxs-lookup"><span data-stu-id="5949b-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="5949b-124">En el ejemplo de código siguiente, se crea una decoración de texto subrayado con un pincel de degradado lineal para el lápiz discontinuo.</span><span class="sxs-lookup"><span data-stu-id="5949b-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="5949b-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5949b-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="5949b-126">Especificar el subrayado de un hipervínculo</span><span class="sxs-lookup"><span data-stu-id="5949b-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
