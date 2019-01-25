---
title: Procedimiento Obtener el desplazamiento de un objeto Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
ms.openlocfilehash: ad45dee5b72594f30b141e3affbb26706af645aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54645397"
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="8e41b-102">Procedimiento Obtener el desplazamiento de un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="8e41b-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="8e41b-103">Estos ejemplos muestran cómo recuperar el valor de desplazamiento de un objeto visual que es relativo a su elemento primario, o cualquier antecesor o descendiente.</span><span class="sxs-lookup"><span data-stu-id="8e41b-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e41b-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8e41b-104">Example</span></span>  
 <span data-ttu-id="8e41b-105">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que se define con <xref:System.Windows.FrameworkElement.Margin%2A> valor 4.</span><span class="sxs-lookup"><span data-stu-id="8e41b-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="8e41b-106">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="8e41b-107">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Vector> valor.</span><span class="sxs-lookup"><span data-stu-id="8e41b-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="8e41b-108">El desplazamiento tiene en cuenta la <xref:System.Windows.FrameworkElement.Margin%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="8e41b-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="8e41b-109">En este caso, <xref:System.Windows.Vector.X%2A> es 4, y <xref:System.Windows.Vector.Y%2A> es 4.</span><span class="sxs-lookup"><span data-stu-id="8e41b-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="8e41b-110">El valor de desplazamiento devuelto es relativo al elemento primario de la <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="8e41b-111">Si desea devolver un valor de desplazamiento no es relativo al elemento primario de un <xref:System.Windows.Media.Visual>, utilice el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8e41b-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="8e41b-112">Obtener el desplazamiento relativo a un antecesor</span><span class="sxs-lookup"><span data-stu-id="8e41b-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="8e41b-113">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está anidada dentro de dos <xref:System.Windows.Controls.StackPanel> objetos.</span><span class="sxs-lookup"><span data-stu-id="8e41b-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="8e41b-114">La siguiente ilustración muestra los resultados del marcado.</span><span class="sxs-lookup"><span data-stu-id="8e41b-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="8e41b-115">![Valores de objetos de desplazamiento](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="8e41b-115">![Offset values of objects](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="8e41b-116">TextBlock anidado dentro de dos objetos StackPanel</span><span class="sxs-lookup"><span data-stu-id="8e41b-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="8e41b-117">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock> en relación con la que contiene <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="8e41b-118">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.</span><span class="sxs-lookup"><span data-stu-id="8e41b-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="8e41b-119">El desplazamiento tiene en cuenta la <xref:System.Windows.FrameworkElement.Margin%2A> valores para todos los objetos dentro de la que contiene <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="8e41b-120">En este caso, <xref:System.Windows.Vector.X%2A> es 28 (16 + 8 + 4), y <xref:System.Windows.Vector.Y%2A> es 28.</span><span class="sxs-lookup"><span data-stu-id="8e41b-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="8e41b-121">El valor de desplazamiento devuelto es relativo al antecesor de la <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="8e41b-122">Si desea devolver un valor de desplazamiento es relativo a los descendientes de un <xref:System.Windows.Media.Visual>, utilice el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método.</span><span class="sxs-lookup"><span data-stu-id="8e41b-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="8e41b-123">Obtener el desplazamiento relativo a un descendiente</span><span class="sxs-lookup"><span data-stu-id="8e41b-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="8e41b-124">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está dentro de un <xref:System.Windows.Controls.StackPanel> objeto.</span><span class="sxs-lookup"><span data-stu-id="8e41b-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="8e41b-125">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.StackPanel> en relación con su elemento secundario <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="8e41b-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="8e41b-126">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.</span><span class="sxs-lookup"><span data-stu-id="8e41b-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="8e41b-127">El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> para todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="8e41b-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="8e41b-128">En este caso, <xref:System.Windows.Vector.X%2A> es -4, y <xref:System.Windows.Vector.Y%2A> es -4.</span><span class="sxs-lookup"><span data-stu-id="8e41b-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="8e41b-129">Los valores de desplazamiento son valores negativos, puesto que el objeto primario es un desplazamiento negativo respecto a su objeto secundario.</span><span class="sxs-lookup"><span data-stu-id="8e41b-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e41b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e41b-130">See also</span></span>
- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- [<span data-ttu-id="8e41b-131">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="8e41b-131">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
