---
title: 'Cómo: Crear texto con sombreado'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186845"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="944cf-102">Cómo: Crear texto con sombreado</span><span class="sxs-lookup"><span data-stu-id="944cf-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="944cf-103">En los ejemplos de esta sección se muestra cómo crear un efecto de sombreado para el texto mostrado.</span><span class="sxs-lookup"><span data-stu-id="944cf-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="944cf-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="944cf-104">Example</span></span>  
 <span data-ttu-id="944cf-105">El <xref:System.Windows.Media.Effects.DropShadowEffect> objeto permite crear una variedad de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] efectos de sombra paralela para objetos.</span><span class="sxs-lookup"><span data-stu-id="944cf-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="944cf-106">En el ejemplo siguiente se muestra un efecto de sombra paralela aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="944cf-107">En este caso, la sombra es suave, lo que significa que su color se desenfoca.</span><span class="sxs-lookup"><span data-stu-id="944cf-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 ![Sombra de texto con suavidad &#61; 0.25](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 <span data-ttu-id="944cf-109">Puede controlar el ancho de una <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> sombra estableciendo la propiedad.</span><span class="sxs-lookup"><span data-stu-id="944cf-109">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="944cf-110">Un valor `4.0` de indica un ancho de sombra de 4 píxeles.</span><span class="sxs-lookup"><span data-stu-id="944cf-110">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="944cf-111">Puede controlar la suavidad o el desenfoque de una sombra modificando la <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="944cf-111">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="944cf-112">Un valor `0.0` de indica que no hay desenfoque.</span><span class="sxs-lookup"><span data-stu-id="944cf-112">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="944cf-113">El ejemplo de código siguiente muestra cómo crear una sombra suave.</span><span class="sxs-lookup"><span data-stu-id="944cf-113">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> <span data-ttu-id="944cf-114">Estos efectos de sombra [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] no pasan por la canalización de representación de texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-114">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="944cf-115">Como resultado, ClearType está deshabilitado cuando se usan estos efectos.</span><span class="sxs-lookup"><span data-stu-id="944cf-115">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="944cf-116">En el ejemplo siguiente se muestra un efecto de sombra paralela intensa aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-116">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="944cf-117">En este caso, la sombra no está desenfocada.</span><span class="sxs-lookup"><span data-stu-id="944cf-117">In this case, the shadow is not blurred.</span></span>  
  
 ![Sombra de texto con suavidad &#61; 0](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 <span data-ttu-id="944cf-119">Puede crear una sombra dura <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> estableciendo la propiedad en `0.0`, lo que indica que no se utiliza ningún desenfoque.</span><span class="sxs-lookup"><span data-stu-id="944cf-119">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="944cf-120">Puede controlar la dirección de la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> sombra modificando la propiedad.</span><span class="sxs-lookup"><span data-stu-id="944cf-120">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="944cf-121">Establezca el valor direccional de `0` esta `360`propiedad en un grado entre y .</span><span class="sxs-lookup"><span data-stu-id="944cf-121">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="944cf-122">En la ilustración siguiente <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> se muestran los valores direccionales de la configuración de propiedad.</span><span class="sxs-lookup"><span data-stu-id="944cf-122">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 ![Valor de grado de sombra paralela de una sombra](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 <span data-ttu-id="944cf-124">En el ejemplo de código siguiente se muestra cómo crear una sombra intensa.</span><span class="sxs-lookup"><span data-stu-id="944cf-124">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="944cf-125">Uso de un efecto de desenfoque</span><span class="sxs-lookup"><span data-stu-id="944cf-125">Using a Blur Effect</span></span>  
 <span data-ttu-id="944cf-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> se puede utilizar para crear un efecto similar a una sombra que se puede colocar detrás de un objeto de texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-126">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="944cf-127">Un efecto de mapa de bits de desenfoque aplicado al texto desenfoca el texto de manera uniforme en todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="944cf-127">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="944cf-128">En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-128">The following example shows a blur effect applied to text.</span></span>  
  
 ![Sombra de texto usando BlurBitmapEffect](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 <span data-ttu-id="944cf-130">En el ejemplo de código siguiente se muestra cómo crear un efecto de desenfoque.</span><span class="sxs-lookup"><span data-stu-id="944cf-130">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="944cf-131">Uso de una transformación de traslación</span><span class="sxs-lookup"><span data-stu-id="944cf-131">Using a Translate Transform</span></span>  
 <span data-ttu-id="944cf-132">A <xref:System.Windows.Media.TranslateTransform> se puede utilizar para crear un efecto similar a una sombra que se puede colocar detrás de un objeto de texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-132">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="944cf-133">En el ejemplo <xref:System.Windows.Media.TranslateTransform> de código siguiente se utiliza a para desfasar texto.</span><span class="sxs-lookup"><span data-stu-id="944cf-133">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="944cf-134">En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="944cf-134">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 ![Sombra de texto usando TranslateTransform](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 <span data-ttu-id="944cf-136">En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="944cf-136">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
