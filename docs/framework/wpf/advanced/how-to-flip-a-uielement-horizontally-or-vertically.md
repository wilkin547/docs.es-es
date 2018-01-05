---
title: "Cómo: Voltear un control UIElement horizontal o verticalmente"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- flipping UIElements [WPF]
- UIElements [WPF], flipping
ms.assetid: 02c6730f-65c0-40d5-a553-4cb663721882
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d34aea4ea99bc03b328fb08582cac3e18a98df66
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-flip-a-uielement-horizontally-or-vertically"></a><span data-ttu-id="553aa-102">Cómo: Voltear un control UIElement horizontal o verticalmente</span><span class="sxs-lookup"><span data-stu-id="553aa-102">How to: Flip a UIElement Horizontally or Vertically</span></span>
<span data-ttu-id="553aa-103">Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.ScaleTransform> debe voltear un <xref:System.Windows.UIElement> horizontal o verticalmente.</span><span class="sxs-lookup"><span data-stu-id="553aa-103">This example shows how to use a <xref:System.Windows.Media.ScaleTransform> to flip a <xref:System.Windows.UIElement> horizontally or vertically.</span></span> <span data-ttu-id="553aa-104">En este ejemplo, un <xref:System.Windows.Controls.Button> control (un tipo de <xref:System.Windows.UIElement>) se voltea aplicando un <xref:System.Windows.Media.ScaleTransform> a su <xref:System.Windows.UIElement.RenderTransform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="553aa-104">In this example, a <xref:System.Windows.Controls.Button> control (a type of <xref:System.Windows.UIElement>) is flipped by applying a <xref:System.Windows.Media.ScaleTransform> to its <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="553aa-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="553aa-105">Example</span></span>  
 <span data-ttu-id="553aa-106">En la siguiente ilustración muestra el botón Examinar.</span><span class="sxs-lookup"><span data-stu-id="553aa-106">The following illustration shows the button to flip.</span></span>  
  
 <span data-ttu-id="553aa-107">![Un botón sin transformación](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span><span class="sxs-lookup"><span data-stu-id="553aa-107">![A button with no transform](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipbeforeflip.gif "graphicsmm_buttonflipbeforeflip")</span></span>  
<span data-ttu-id="553aa-108">El elemento de IU para voltear</span><span class="sxs-lookup"><span data-stu-id="553aa-108">The UIElement to flip</span></span>  
  
 <span data-ttu-id="553aa-109">A continuación muestra el código que crea el botón.</span><span class="sxs-lookup"><span data-stu-id="553aa-109">The following shows the code that creates the button.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMButtonWithoutFlip](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmbuttonwithoutflip)]  
  
## <a name="example"></a><span data-ttu-id="553aa-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="553aa-110">Example</span></span>  
 <span data-ttu-id="553aa-111">Para voltear horizontalmente el botón, cree una <xref:System.Windows.Media.ScaleTransform> y establecer su <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> propiedad en -1.</span><span class="sxs-lookup"><span data-stu-id="553aa-111">To flip the button horizontally, create a <xref:System.Windows.Media.ScaleTransform> and set its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property to -1.</span></span> <span data-ttu-id="553aa-112">Aplicar el <xref:System.Windows.Media.ScaleTransform> en el botón <xref:System.Windows.UIElement.RenderTransform%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="553aa-112">Apply the <xref:System.Windows.Media.ScaleTransform> to the button's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample1)]  
  
 <span data-ttu-id="553aa-113">![Un botón volteado horizontalmente alrededor de &#40; 0,0 &#41; ] (../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span><span class="sxs-lookup"><span data-stu-id="553aa-113">![A button flipped horizontally about &#40;0,0&#41;](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-displaced.gif "graphicsmm_buttonfliphorizontalflip_displaced")</span></span>  
<span data-ttu-id="553aa-114">El botón después de aplicar ScaleTransform</span><span class="sxs-lookup"><span data-stu-id="553aa-114">The button after applying the ScaleTransform</span></span>  
  
## <a name="example"></a><span data-ttu-id="553aa-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="553aa-115">Example</span></span>  
 <span data-ttu-id="553aa-116">Como puede ver en la ilustración anterior, el botón se ha volteado, pero también se ha movido.</span><span class="sxs-lookup"><span data-stu-id="553aa-116">As you can see from the previous illustration, the button was flipped, but it was also moved.</span></span> <span data-ttu-id="553aa-117">Eso es porque se voltea el botón de la esquina superior izquierda.</span><span class="sxs-lookup"><span data-stu-id="553aa-117">That's because the button was flipped from its top left corner.</span></span> <span data-ttu-id="553aa-118">Para voltear el botón en su lugar, desea aplicar el <xref:System.Windows.Media.ScaleTransform> a su centro, no a su esquina.</span><span class="sxs-lookup"><span data-stu-id="553aa-118">To flip the button in place, you want to apply the <xref:System.Windows.Media.ScaleTransform> to its center, not its corner.</span></span> <span data-ttu-id="553aa-119">Una forma sencilla de aplicar el <xref:System.Windows.Media.ScaleTransform> a los botones es establecer el botón Centro <xref:System.Windows.UIElement.RenderTransformOrigin%2A> propiedad en 0,5, 0,5.</span><span class="sxs-lookup"><span data-stu-id="553aa-119">An easy way to apply the <xref:System.Windows.Media.ScaleTransform> to the buttons center is to set the button's <xref:System.Windows.UIElement.RenderTransformOrigin%2A> property to 0.5, 0.5.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmflipbuttonexample2)]  
  
 <span data-ttu-id="553aa-120">![Botón volteado horizontalmente alrededor de su centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="553aa-120">![A button flipped horizontally about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonfliphorizontalflip-inplace.gif "graphicsmm_buttonfliphorizontalflip_inplace")</span></span>  
<span data-ttu-id="553aa-121">El botón con un valor de RenderTransformOrigin de 0,5, 0,5</span><span class="sxs-lookup"><span data-stu-id="553aa-121">The button with a RenderTransformOrigin of 0.5, 0.5</span></span>  
  
## <a name="example"></a><span data-ttu-id="553aa-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="553aa-122">Example</span></span>  
 <span data-ttu-id="553aa-123">Para voltear verticalmente el botón, establezca la <xref:System.Windows.Media.ScaleTransform> del objeto <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> propiedad en lugar de su <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="553aa-123">To flip the button vertically, set the <xref:System.Windows.Media.ScaleTransform> object's <xref:System.Windows.Media.ScaleTransform.ScaleY%2A> property instead of its <xref:System.Windows.Media.ScaleTransform.ScaleX%2A> property.</span></span>  
  
 [!code-xaml[Transforms_snip#GraphicsMMVerticalFlipButtonExample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/FlipExample.xaml#graphicsmmverticalflipbuttonexample2)]  
  
 <span data-ttu-id="553aa-124">![Botón volteado verticalmente alrededor de su centro](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span><span class="sxs-lookup"><span data-stu-id="553aa-124">![A button flipped vertically about its center](../../../../docs/framework/wpf/advanced/media/graphicsmm-buttonflipverticalflip-inplace.gif "graphicsmm_buttonflipverticalflip_inplace")</span></span>  
<span data-ttu-id="553aa-125">El botón volteado verticalmente</span><span class="sxs-lookup"><span data-stu-id="553aa-125">The vertically flipped button</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="553aa-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="553aa-126">See Also</span></span>  
 [<span data-ttu-id="553aa-127">Información general sobre transformaciones</span><span class="sxs-lookup"><span data-stu-id="553aa-127">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
