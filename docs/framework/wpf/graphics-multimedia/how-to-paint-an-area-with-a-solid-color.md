---
title: 'Cómo: Pintar un área con un color sólido'
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849527"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a><span data-ttu-id="91eeb-102">Cómo: Pintar un área con un color sólido</span><span class="sxs-lookup"><span data-stu-id="91eeb-102">How to: Paint an Area with a Solid Color</span></span>
<span data-ttu-id="91eeb-103">Para pintar un área con un color sólido, puede utilizar <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>un pincel del sistema <xref:System.Windows.Media.SolidColorBrush> predefinido, <xref:System.Windows.Media.SolidColorBrush.Color%2A> como o , o puede crear un nuevo y describir su uso de valores alfa, rojo, verde y azul.</span><span class="sxs-lookup"><span data-stu-id="91eeb-103">To paint an area with a solid color, you can use a predefined system brush, such as <xref:System.Windows.Media.Brushes.Red%2A> or <xref:System.Windows.Media.Brushes.Blue%2A>, or you can create a new <xref:System.Windows.Media.SolidColorBrush> and describe its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using alpha, red, green, and blue values.</span></span> <span data-ttu-id="91eeb-104">En XAML, también puede pintar un área con un color sólido utilizando la notación hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="91eeb-104">In XAML, you may also paint an area with a solid color by using hexidecimal notation.</span></span>  
  
 <span data-ttu-id="91eeb-105">En los ejemplos siguientes se utiliza <xref:System.Windows.Shapes.Rectangle> cada una de estas técnicas para pintar un azul.</span><span class="sxs-lookup"><span data-stu-id="91eeb-105">The following examples uses each of these techniques to paint a <xref:System.Windows.Shapes.Rectangle> blue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91eeb-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="91eeb-106">Example</span></span>  
 <span data-ttu-id="91eeb-107">**Utilizar un pincel predefinido**</span><span class="sxs-lookup"><span data-stu-id="91eeb-107">**Using a Predefined Brush**</span></span>  
  
 <span data-ttu-id="91eeb-108">En el ejemplo siguiente se <xref:System.Windows.Media.Brushes.Blue%2A> utiliza el pincel predefinido para pintar un rectángulo azul.</span><span class="sxs-lookup"><span data-stu-id="91eeb-108">In the following example uses the predefined brush <xref:System.Windows.Media.Brushes.Blue%2A> to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 <span data-ttu-id="91eeb-109">**Utilizar la notación hexadecimal**</span><span class="sxs-lookup"><span data-stu-id="91eeb-109">**Using Hexadecimal Notation**</span></span>  
  
 <span data-ttu-id="91eeb-110">En el ejemplo siguiente se utiliza la notación hexadecimal de 8 dígitos para pintar un rectángulo azul.</span><span class="sxs-lookup"><span data-stu-id="91eeb-110">The next example uses 8-digit hexadecimal notation to paint a rectangle blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 <span data-ttu-id="91eeb-111">**Utilizar los valores ARGB**</span><span class="sxs-lookup"><span data-stu-id="91eeb-111">**Using ARGB Values**</span></span>  
  
 <span data-ttu-id="91eeb-112">En el ejemplo <xref:System.Windows.Media.SolidColorBrush> siguiente se <xref:System.Windows.Media.SolidColorBrush.Color%2A> crea a y se describe su uso de los valores ARGB para el color azul.</span><span class="sxs-lookup"><span data-stu-id="91eeb-112">The next example creates a <xref:System.Windows.Media.SolidColorBrush> and describes its <xref:System.Windows.Media.SolidColorBrush.Color%2A> using the ARGB values for the color blue.</span></span>  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 <span data-ttu-id="91eeb-113">Para otras formas de describir <xref:System.Windows.Media.Color> el color, consulte la estructura.</span><span class="sxs-lookup"><span data-stu-id="91eeb-113">For other ways of describing color, see the <xref:System.Windows.Media.Color> structure.</span></span>  
  
 <span data-ttu-id="91eeb-114">**Temas relacionados**</span><span class="sxs-lookup"><span data-stu-id="91eeb-114">**Related Topics**</span></span>  
  
 <span data-ttu-id="91eeb-115">Para obtener <xref:System.Windows.Media.SolidColorBrush> más información y ejemplos adicionales, consulte La [información general sobre la pintura con colores sólidos y degradados.](painting-with-solid-colors-and-gradients-overview.md)</span><span class="sxs-lookup"><span data-stu-id="91eeb-115">For more information about <xref:System.Windows.Media.SolidColorBrush> and additional examples, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md) overview.</span></span>  
  
 <span data-ttu-id="91eeb-116">Este ejemplo de código forma parte <xref:System.Windows.Media.SolidColorBrush> de un ejemplo más amplio proporcionado para la clase.</span><span class="sxs-lookup"><span data-stu-id="91eeb-116">This code example is part of a larger example provided for the <xref:System.Windows.Media.SolidColorBrush> class.</span></span> <span data-ttu-id="91eeb-117">Para ver el ejemplo completo, consulte la [muestra Pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span><span class="sxs-lookup"><span data-stu-id="91eeb-117">For the complete sample, see the [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91eeb-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="91eeb-118">See also</span></span>

- <xref:System.Windows.Media.Brushes>
