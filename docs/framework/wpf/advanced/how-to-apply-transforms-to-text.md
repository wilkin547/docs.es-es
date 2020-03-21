---
title: 'Cómo: Aplicar transformaciones a texto'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], rotated text
- typography [WPF], scaled text
- skewed text [WPF]
- typography [WPF], translated text
- typography [WPF], shadowed text
- rotated text [WPF]
- translated text [WPF]
- shadowed text [WPF]
- transforms in text [WPF]
- typography [WPF], transforms
- scaled text [WPF]
- typography [WPF], skewed text
ms.assetid: 0d61678a-4185-4f2a-85c6-c1d020f96fa0
ms.openlocfilehash: 867f39e3df8493014d8601530e91310c3bbbeeb5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141619"
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="bf4d4-102">Cómo: Aplicar transformaciones a texto</span><span class="sxs-lookup"><span data-stu-id="bf4d4-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="bf4d4-103">Las transformaciones pueden modificar la presentación del texto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="bf4d4-104">En los ejemplos siguientes se utilizan diferentes tipos de <xref:System.Windows.Controls.TextBlock> transformaciones de representación para afectar a la visualización de texto en un control.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf4d4-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bf4d4-105">Example</span></span>  
 <span data-ttu-id="bf4d4-106">En el ejemplo siguiente se muestra el texto girado sobre un punto especificado en el plano x-y bidimensional.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 ![Texto girado usando RotateTransform](./media/how-to-apply-transforms-to-text/text-rotated-ninety-degrees.jpg)  
  
 <span data-ttu-id="bf4d4-108">En el ejemplo <xref:System.Windows.Media.RotateTransform> de código siguiente se usa a para rotar texto.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-108">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="bf4d4-109">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valor de 90 gira el elemento 90 grados en el sentido de las agujas del reloj.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-109">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="bf4d4-110">En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-110">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 ![Texto con escala ajustada usando ScaleTransform](./media/how-to-apply-transforms-to-text/scaled-text-scaletransform.jpg)
  
 <span data-ttu-id="bf4d4-112">En el ejemplo <xref:System.Windows.Media.ScaleTransform> de código siguiente se usa a para escalar texto de su tamaño original.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-112">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
> <span data-ttu-id="bf4d4-113">Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-113">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="bf4d4-114">Los tamaños de fuente se calculan de forma independiente para proporcionar la mejor resolución en diferentes tamaños.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-114">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="bf4d4-115">El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-115">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="bf4d4-116">En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-116">The following example shows text skewed along the x-axis.</span></span>  
  
 ![Texto sesgado usando SkewTransform](./media/how-to-apply-transforms-to-text/skewed-transformed-text.jpg)

 <span data-ttu-id="bf4d4-118">En el ejemplo <xref:System.Windows.Media.SkewTransform> de código siguiente se usa a para sesgar texto.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-118">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="bf4d4-119">Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-119">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="bf4d4-120">En este ejemplo, las dos cadenas de texto están sesgadas -30° y 30° a lo largo de la coordenada x.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-120">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="bf4d4-121">En el ejemplo siguiente se muestra texto trasladado, o movido, a lo largo del eje x y el eje y.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-121">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 ![Texto desplazado usando TranslateTransform](./media/how-to-apply-transforms-to-text/transformed-text-x-y-axis.jpg)
  
 <span data-ttu-id="bf4d4-123">En el ejemplo <xref:System.Windows.Media.TranslateTransform> de código siguiente se utiliza a para desfasar texto.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-123">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="bf4d4-124">En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-124">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
> <span data-ttu-id="bf4d4-125">Proporciona <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> un amplio conjunto de entidades para proporcionar efectos de sombra.</span><span class="sxs-lookup"><span data-stu-id="bf4d4-125">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="bf4d4-126">Para obtener más información, consulte [Crear texto con una sombra](how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="bf4d4-126">For more information, see [Create Text with a Shadow](how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf4d4-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf4d4-127">See also</span></span>

- [<span data-ttu-id="bf4d4-128">Aplicar animaciones a texto</span><span class="sxs-lookup"><span data-stu-id="bf4d4-128">Apply Animations to Text</span></span>](how-to-apply-animations-to-text.md)
