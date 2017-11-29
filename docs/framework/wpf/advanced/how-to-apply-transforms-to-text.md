---
title: "Cómo: Aplicar transformaciones a texto"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ed10a00d3d62f7eae91e5932a917be692de868b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-apply-transforms-to-text"></a><span data-ttu-id="fc260-102">Cómo: Aplicar transformaciones a texto</span><span class="sxs-lookup"><span data-stu-id="fc260-102">How to: Apply Transforms to Text</span></span>
<span data-ttu-id="fc260-103">Las transformaciones pueden modificar la presentación del texto en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc260-103">Transforms can alter the display of text in your application.</span></span> <span data-ttu-id="fc260-104">Los ejemplos siguientes usan diferentes tipos de representación de las transformaciones que afectan a la presentación del texto de un <xref:System.Windows.Controls.TextBlock> control.</span><span class="sxs-lookup"><span data-stu-id="fc260-104">The following examples use different types of rendering transforms to affect the display of text in a <xref:System.Windows.Controls.TextBlock> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc260-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc260-105">Example</span></span>  
 <span data-ttu-id="fc260-106">En el ejemplo siguiente se muestra el texto girado sobre un punto especificado en el plano x-y bidimensional.</span><span class="sxs-lookup"><span data-stu-id="fc260-106">The following example shows text rotated about a specified point in the two-dimensional x-y plane.</span></span>  
  
 <span data-ttu-id="fc260-107">![Texto girado usando RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span><span class="sxs-lookup"><span data-stu-id="fc260-107">![Text rotated using a RotateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext01.jpg "TransformedText01")</span></span>  
<span data-ttu-id="fc260-108">Ejemplo de texto girado 90 grados</span><span class="sxs-lookup"><span data-stu-id="fc260-108">Example of text rotated 90 degrees</span></span>  
  
 <span data-ttu-id="fc260-109">El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.RotateTransform> para girar el texto.</span><span class="sxs-lookup"><span data-stu-id="fc260-109">The following code example uses a <xref:System.Windows.Media.RotateTransform> to rotate text.</span></span> <span data-ttu-id="fc260-110">Un <xref:System.Windows.Media.RotateTransform.Angle%2A> valor de 90 gira el elemento 90 grados a la derecha.</span><span class="sxs-lookup"><span data-stu-id="fc260-110">An <xref:System.Windows.Media.RotateTransform.Angle%2A> value of 90 rotates the element 90 degrees clockwise.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample1)]  
  
 <span data-ttu-id="fc260-111">En el ejemplo siguiente se muestra la segunda línea de texto escalada al 150 % a lo largo del eje X y la tercera línea de texto escalada al 150 % a lo largo del eje Y.</span><span class="sxs-lookup"><span data-stu-id="fc260-111">The following example shows the second line of text scaled by 150% along the x-axis, and the third line of text scaled by 150% along the y-axis.</span></span>  
  
 <span data-ttu-id="fc260-112">![Texto con escala ajustada usando ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span><span class="sxs-lookup"><span data-stu-id="fc260-112">![Text scaled using a ScaleTransform](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")</span></span>  
<span data-ttu-id="fc260-113">Ejemplo de texto escalado</span><span class="sxs-lookup"><span data-stu-id="fc260-113">Example of scaled text</span></span>  
  
 <span data-ttu-id="fc260-114">El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.ScaleTransform> al texto de la escala de su tamaño original.</span><span class="sxs-lookup"><span data-stu-id="fc260-114">The following code example uses a <xref:System.Windows.Media.ScaleTransform> to scale text from its original size.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample2)]  
  
> [!NOTE]
>  <span data-ttu-id="fc260-115">Escalar texto no es lo mismo que aumentar el tamaño de la fuente de texto.</span><span class="sxs-lookup"><span data-stu-id="fc260-115">Scaling text is not the same as increasing the font size of text.</span></span> <span data-ttu-id="fc260-116">Los tamaños de fuente se calculan de forma independiente para proporcionar la mejor resolución en diferentes tamaños.</span><span class="sxs-lookup"><span data-stu-id="fc260-116">Font sizes are calculated independently of each other in order to provide the best resolution at different sizes.</span></span> <span data-ttu-id="fc260-117">El texto escalado, por otro lado, conserva las proporciones del texto de tamaño original.</span><span class="sxs-lookup"><span data-stu-id="fc260-117">Scaled text, on the other hand, preserves the proportions of the original-sized text.</span></span>  
  
 <span data-ttu-id="fc260-118">En el ejemplo siguiente se muestra el texto sesgado a lo largo del eje X.</span><span class="sxs-lookup"><span data-stu-id="fc260-118">The following example shows text skewed along the x-axis.</span></span>  
  
 <span data-ttu-id="fc260-119">![Texto sesgado usando SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span><span class="sxs-lookup"><span data-stu-id="fc260-119">![Text skewed using a SkewTransform](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")</span></span>  
<span data-ttu-id="fc260-120">Ejemplo de texto sesgado</span><span class="sxs-lookup"><span data-stu-id="fc260-120">Example of skewed text</span></span>  
  
 <span data-ttu-id="fc260-121">El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.SkewTransform> para sesgar el texto.</span><span class="sxs-lookup"><span data-stu-id="fc260-121">The following code example uses a <xref:System.Windows.Media.SkewTransform> to skew text.</span></span> <span data-ttu-id="fc260-122">Un sesgo, también conocido como distorsión, es una transformación que expande el espacio de coordenadas de una manera no uniforme.</span><span class="sxs-lookup"><span data-stu-id="fc260-122">A skew, also known as a shear, is a transformation that stretches the coordinate space in a non-uniform manner.</span></span> <span data-ttu-id="fc260-123">En este ejemplo, las dos cadenas de texto están sesgadas -30° y 30° a lo largo de la coordenada x.</span><span class="sxs-lookup"><span data-stu-id="fc260-123">In this example, the two text strings are skewed -30° and 30° along the x-coordinate.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample3)]  
  
 <span data-ttu-id="fc260-124">En el ejemplo siguiente se muestra texto trasladado, o movido, a lo largo del eje x y el eje y.</span><span class="sxs-lookup"><span data-stu-id="fc260-124">The following example shows text translated, or moved, along the x- and y-axis.</span></span>  
  
 <span data-ttu-id="fc260-125">![Texto desplazado usando TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span><span class="sxs-lookup"><span data-stu-id="fc260-125">![Text offset using a TranslateTransform](../../../../docs/framework/wpf/advanced/media/transformedtext04.jpg "TransformedText04")</span></span>  
<span data-ttu-id="fc260-126">Ejemplo de texto trasladado</span><span class="sxs-lookup"><span data-stu-id="fc260-126">Example of translated text</span></span>  
  
 <span data-ttu-id="fc260-127">El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto.</span><span class="sxs-lookup"><span data-stu-id="fc260-127">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="fc260-128">En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="fc260-128">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 [!code-xaml[TextTransformSample#TextTransformSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextTransformSample/CS/Window1.xaml#texttransformsample4)]  
  
> [!NOTE]
>  <span data-ttu-id="fc260-129">El <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> proporciona un amplio conjunto de características para ofrecer efectos de sombra.</span><span class="sxs-lookup"><span data-stu-id="fc260-129">The <xref:System.Windows.Media.Effects.DropShadowBitmapEffect> provides a rich set of features for providing shadow effects.</span></span> <span data-ttu-id="fc260-130">Para obtener más información, consulte [crear texto con una sombra](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).</span><span class="sxs-lookup"><span data-stu-id="fc260-130">For more information, see [Create Text with a Shadow](../../../../docs/framework/wpf/advanced/how-to-create-text-with-a-shadow.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc260-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc260-131">See Also</span></span>  
 [<span data-ttu-id="fc260-132">Aplicar animaciones a texto</span><span class="sxs-lookup"><span data-stu-id="fc260-132">Apply Animations to Text</span></span>](../../../../docs/framework/wpf/advanced/how-to-apply-animations-to-text.md)
