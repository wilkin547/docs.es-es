---
title: Filtrar Crear texto con sombreado
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: 4d200aa980e8f2e6d22291669dfb07db54a5f0c0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370688"
---
# <a name="how-to-create-text-with-a-shadow"></a><span data-ttu-id="04b7b-102">Filtrar Crear texto con sombreado</span><span class="sxs-lookup"><span data-stu-id="04b7b-102">How to: Create Text with a Shadow</span></span>
<span data-ttu-id="04b7b-103">En los ejemplos de esta sección se muestra cómo crear un efecto de sombreado para el texto mostrado.</span><span class="sxs-lookup"><span data-stu-id="04b7b-103">The examples in this section show how to create a shadow effect for displayed text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04b7b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="04b7b-104">Example</span></span>  
 <span data-ttu-id="04b7b-105">El <xref:System.Windows.Media.Effects.DropShadowEffect> objeto le permite crear una variedad de colocar los efectos de sombra para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objetos.</span><span class="sxs-lookup"><span data-stu-id="04b7b-105">The <xref:System.Windows.Media.Effects.DropShadowEffect> object allows you to create a variety of drop shadow effects for [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] objects.</span></span> <span data-ttu-id="04b7b-106">En el ejemplo siguiente se muestra un efecto de sombra paralela aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-106">The following example shows a drop shadow effect applied to text.</span></span> <span data-ttu-id="04b7b-107">En este caso, la sombra es suave, lo que significa que su color se desenfoca.</span><span class="sxs-lookup"><span data-stu-id="04b7b-107">In this case, the shadow is a soft shadow, which means the shadow color blurs.</span></span>  
  
 <span data-ttu-id="04b7b-108">![Sombra de texto con suavidad &#61; 0,25](./media/shadowtext01.jpg "ShadowText01")</span><span class="sxs-lookup"><span data-stu-id="04b7b-108">![Text shadow with Softness &#61; 0.25](./media/shadowtext01.jpg "ShadowText01")</span></span>  
<span data-ttu-id="04b7b-109">Ejemplo de texto con una sombra suave</span><span class="sxs-lookup"><span data-stu-id="04b7b-109">Example of text with a soft shadow</span></span>  
  
 <span data-ttu-id="04b7b-110">Puede controlar el ancho de una sombra estableciendo el <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b7b-110">You can control the width of a shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A> property.</span></span> <span data-ttu-id="04b7b-111">Un valor de `4.0` indica un ancho de la sombra de 4 píxeles.</span><span class="sxs-lookup"><span data-stu-id="04b7b-111">A value of `4.0` indicates a shadow width of 4 pixels.</span></span> <span data-ttu-id="04b7b-112">Puede controlar la suavidad o el desenfoque de una sombra modificando el <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b7b-112">You can control the softness, or blur, of a shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property.</span></span> <span data-ttu-id="04b7b-113">Un valor de `0.0` no indica que existe desenfoque.</span><span class="sxs-lookup"><span data-stu-id="04b7b-113">A value of `0.0` indicates no blurring.</span></span> <span data-ttu-id="04b7b-114">El ejemplo de código siguiente muestra cómo crear una sombra suave.</span><span class="sxs-lookup"><span data-stu-id="04b7b-114">The following code example shows how to create a soft shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
>  <span data-ttu-id="04b7b-115">Estos efectos de sombra no pasan por la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] canalización de representación de texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-115">These shadow effects do not go through the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] text rendering pipeline.</span></span> <span data-ttu-id="04b7b-116">Como resultado, ClearType está deshabilitado cuando se usan estos efectos.</span><span class="sxs-lookup"><span data-stu-id="04b7b-116">As a result, ClearType is disabled when using these effects.</span></span>  
  
 <span data-ttu-id="04b7b-117">En el ejemplo siguiente se muestra un efecto de sombra paralela intensa aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-117">The following example shows a hard drop shadow effect applied to text.</span></span> <span data-ttu-id="04b7b-118">En este caso, la sombra no está desenfocada.</span><span class="sxs-lookup"><span data-stu-id="04b7b-118">In this case, the shadow is not blurred.</span></span>  
  
 <span data-ttu-id="04b7b-119">![Sombra de texto con suavidad &#61; 0](./media/shadowtext02.jpg "ShadowText02")</span><span class="sxs-lookup"><span data-stu-id="04b7b-119">![Text shadow with Softness &#61; 0](./media/shadowtext02.jpg "ShadowText02")</span></span>  
<span data-ttu-id="04b7b-120">Ejemplo de texto con una sombra intensa</span><span class="sxs-lookup"><span data-stu-id="04b7b-120">Example of text with a hard shadow</span></span>  
  
 <span data-ttu-id="04b7b-121">Puede crear una sombra intensa estableciendo el <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> propiedad `0.0`, lo que indica que no se usa desenfoque.</span><span class="sxs-lookup"><span data-stu-id="04b7b-121">You can create a hard shadow by setting the <xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A> property to `0.0`, which indicates that no blurring is used.</span></span> <span data-ttu-id="04b7b-122">Puede controlar la dirección de la sombra modificando el <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b7b-122">You can control the direction of the shadow by modifying the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property.</span></span> <span data-ttu-id="04b7b-123">Establezca el valor direccional de esta propiedad en un grado entre `0` y `360`.</span><span class="sxs-lookup"><span data-stu-id="04b7b-123">Set the directional value of this property to a degree between `0` and `360`.</span></span> <span data-ttu-id="04b7b-124">La ilustración siguiente muestra los valores de dirección la <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> configuración de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="04b7b-124">The following illustration shows the directional values of the <xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A> property setting.</span></span>  
  
 <span data-ttu-id="04b7b-125">![Configuración de un objeto DropShadow grado de sombra](./media/shadowtext08.png "ShadowText08")</span><span class="sxs-lookup"><span data-stu-id="04b7b-125">![DropShadow degree setting of shadow](./media/shadowtext08.png "ShadowText08")</span></span>  
<span data-ttu-id="04b7b-126">Diagrama de dirección de un objeto DropShadow</span><span class="sxs-lookup"><span data-stu-id="04b7b-126">DropShadow Direction diagram</span></span>  
  
 <span data-ttu-id="04b7b-127">En el ejemplo de código siguiente se muestra cómo crear una sombra intensa.</span><span class="sxs-lookup"><span data-stu-id="04b7b-127">The following code example shows how to create a hard shadow.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a><span data-ttu-id="04b7b-128">Uso de un efecto de desenfoque</span><span class="sxs-lookup"><span data-stu-id="04b7b-128">Using a Blur Effect</span></span>  
 <span data-ttu-id="04b7b-129">Un <xref:System.Windows.Media.Effects.BlurBitmapEffect> puede usarse para crear un efecto de sombra que se pueda ubicar detrás de un objeto de texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-129">A <xref:System.Windows.Media.Effects.BlurBitmapEffect> can be used to create a shadow-like effect that can be placed behind a text object.</span></span> <span data-ttu-id="04b7b-130">Un efecto de mapa de bits de desenfoque aplicado al texto desenfoca el texto de manera uniforme en todas las direcciones.</span><span class="sxs-lookup"><span data-stu-id="04b7b-130">A blur bitmap effect applied to text blurs the text evenly in all directions.</span></span>  
  
 <span data-ttu-id="04b7b-131">En el ejemplo siguiente se muestra un efecto de desenfoque aplicado al texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-131">The following example shows a blur effect applied to text.</span></span>  
  
 <span data-ttu-id="04b7b-132">![Sombra de texto usando BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")</span><span class="sxs-lookup"><span data-stu-id="04b7b-132">![Text shadow using a BlurBitmapEffect](./media/shadowtext06.jpg "ShadowText06")</span></span>  
<span data-ttu-id="04b7b-133">Ejemplo de texto con efecto de desenfoque</span><span class="sxs-lookup"><span data-stu-id="04b7b-133">Example of text with a blur effect</span></span>  
  
 <span data-ttu-id="04b7b-134">En el ejemplo de código siguiente se muestra cómo crear un efecto de desenfoque.</span><span class="sxs-lookup"><span data-stu-id="04b7b-134">The following code example shows how to create a blur effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a><span data-ttu-id="04b7b-135">Uso de una transformación de traslación</span><span class="sxs-lookup"><span data-stu-id="04b7b-135">Using a Translate Transform</span></span>  
 <span data-ttu-id="04b7b-136">Un <xref:System.Windows.Media.TranslateTransform> puede usarse para crear un efecto de sombra que se pueda ubicar detrás de un objeto de texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-136">A <xref:System.Windows.Media.TranslateTransform> can be used to create a shadow-like effect that can be placed behind a text object.</span></span>  
  
 <span data-ttu-id="04b7b-137">El siguiente ejemplo de código utiliza un <xref:System.Windows.Media.TranslateTransform> para desplazar el texto.</span><span class="sxs-lookup"><span data-stu-id="04b7b-137">The following code example uses a <xref:System.Windows.Media.TranslateTransform> to offset text.</span></span> <span data-ttu-id="04b7b-138">En este ejemplo, una copia ligeramente desplazada del texto bajo el texto primario crea un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="04b7b-138">In this example, a slightly offset copy of text below the primary text creates a shadow effect.</span></span>  
  
 <span data-ttu-id="04b7b-139">![Sombra de texto usando TranslateTransform](./media/shadowtext07.jpg "ShadowText07")</span><span class="sxs-lookup"><span data-stu-id="04b7b-139">![Text shadow using a TranslateTransform](./media/shadowtext07.jpg "ShadowText07")</span></span>  
<span data-ttu-id="04b7b-140">Ejemplo de texto que usa una transformación para un efecto de sombra</span><span class="sxs-lookup"><span data-stu-id="04b7b-140">Example of text using a transform for a shadow effect</span></span>  
  
 <span data-ttu-id="04b7b-141">En el ejemplo de código siguiente se muestra cómo crear una transformación para un efecto de sombra.</span><span class="sxs-lookup"><span data-stu-id="04b7b-141">The following code example shows how to create a transform for a shadow effect.</span></span>  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
