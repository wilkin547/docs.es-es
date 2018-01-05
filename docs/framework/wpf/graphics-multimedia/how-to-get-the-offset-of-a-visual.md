---
title: "Cómo: Obtener el desplazamiento de un objeto Visual"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- getting offset values from visual objects [WPF]
- offset values [WPF], retrieving from visual objects [WPF]
- visual objects [WPF], retrieving offset values from
- retrieving offset values from visual objects [WPF]
ms.assetid: 889a1dd6-1b11-445a-b351-fbb04c53ee34
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ee18503bdd6100cbe7a62ac70d7ea0848fb124eb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-get-the-offset-of-a-visual"></a><span data-ttu-id="797eb-102">Cómo: Obtener el desplazamiento de un objeto Visual</span><span class="sxs-lookup"><span data-stu-id="797eb-102">How to: Get the Offset of a Visual</span></span>
<span data-ttu-id="797eb-103">Estos ejemplos muestran cómo recuperar el valor de desplazamiento de un objeto visual que es relativa a su elemento primario, o cualquier antecesor o descendiente.</span><span class="sxs-lookup"><span data-stu-id="797eb-103">These examples show how to retrieve the offset value of a visual object that is relative to its parent, or any ancestor or descendant.</span></span>  
  
## <a name="example"></a><span data-ttu-id="797eb-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="797eb-104">Example</span></span>  
 <span data-ttu-id="797eb-105">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que se define con <xref:System.Windows.FrameworkElement.Margin%2A> valor 4.</span><span class="sxs-lookup"><span data-stu-id="797eb-105">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is defined with <xref:System.Windows.FrameworkElement.Margin%2A> value of 4.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet1)]  
  
 <span data-ttu-id="797eb-106">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="797eb-106">The following code example shows how to use the <xref:System.Windows.Media.VisualTreeHelper.GetOffset%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="797eb-107">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Vector> valor.</span><span class="sxs-lookup"><span data-stu-id="797eb-107">The offset values are contained within the returned <xref:System.Windows.Vector> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet2)]
 [!code-vb[VisualSnippets#VisualSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet2)]  
  
 <span data-ttu-id="797eb-108">El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valor.</span><span class="sxs-lookup"><span data-stu-id="797eb-108">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> value.</span></span> <span data-ttu-id="797eb-109">En este caso, <xref:System.Windows.Vector.X%2A> es 4, y <xref:System.Windows.Vector.Y%2A> es 4.</span><span class="sxs-lookup"><span data-stu-id="797eb-109">In this case, <xref:System.Windows.Vector.X%2A> is 4, and <xref:System.Windows.Vector.Y%2A> is 4.</span></span>  
  
 <span data-ttu-id="797eb-110">El valor de desplazamiento devuelto es relativo al elemento primario de la <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="797eb-110">The returned offset value is relative to the parent of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="797eb-111">Si desea devolver un valor de desplazamiento que no es relativo al elemento primario de un <xref:System.Windows.Media.Visual>, use el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método.</span><span class="sxs-lookup"><span data-stu-id="797eb-111">If you want to return an offset value that is not relative to the parent of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-an-ancestor"></a><span data-ttu-id="797eb-112">Obtener el desplazamiento relativo a un antecesor</span><span class="sxs-lookup"><span data-stu-id="797eb-112">Getting the Offset Relative to an Ancestor</span></span>  
 <span data-ttu-id="797eb-113">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está anidada dentro de dos <xref:System.Windows.Controls.StackPanel> objetos.</span><span class="sxs-lookup"><span data-stu-id="797eb-113">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is nested within two <xref:System.Windows.Controls.StackPanel> objects.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window2.xaml#visualsnippet7)]  
  
 <span data-ttu-id="797eb-114">En la siguiente ilustración muestra el resultado del marcado.</span><span class="sxs-lookup"><span data-stu-id="797eb-114">The following illustration shows the results of the markup.</span></span>  
  
 <span data-ttu-id="797eb-115">![Valores de desplazamiento de objetos](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span><span class="sxs-lookup"><span data-stu-id="797eb-115">![Offset values of objects](../../../../docs/framework/wpf/graphics-multimedia/media/visualoffset-01.png "VisualOffset_01")</span></span>  
<span data-ttu-id="797eb-116">Objeto TextBlock anidado dentro de dos objetos StackPanel</span><span class="sxs-lookup"><span data-stu-id="797eb-116">TextBlock nested within two StackPanels</span></span>  
  
 <span data-ttu-id="797eb-117">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToAncestor%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.TextBlock> con respecto a la que contiene <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="797eb-117">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToAncestor%2A> method to retrieve the offset of the <xref:System.Windows.Controls.TextBlock> relative to the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="797eb-118">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.</span><span class="sxs-lookup"><span data-stu-id="797eb-118">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet5)]
 [!code-vb[VisualSnippets#VisualSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet5)]  
  
 <span data-ttu-id="797eb-119">El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valores para todos los objetos dentro de la que contiene <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="797eb-119">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects within the containing <xref:System.Windows.Window>.</span></span> <span data-ttu-id="797eb-120">En este caso, <xref:System.Windows.Vector.X%2A> es 28 (16 + 8 + 4), y <xref:System.Windows.Vector.Y%2A> es 28.</span><span class="sxs-lookup"><span data-stu-id="797eb-120">In this case, <xref:System.Windows.Vector.X%2A> is 28 (16 + 8 + 4), and <xref:System.Windows.Vector.Y%2A> is 28.</span></span>  
  
 <span data-ttu-id="797eb-121">El valor de desplazamiento devuelto es relativo al antecesor de la <xref:System.Windows.Media.Visual>.</span><span class="sxs-lookup"><span data-stu-id="797eb-121">The returned offset value is relative to the ancestor of the <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="797eb-122">Si desea devolver un valor de desplazamiento que sea relativo a los descendientes de un <xref:System.Windows.Media.Visual>, use el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método.</span><span class="sxs-lookup"><span data-stu-id="797eb-122">If you want to return an offset value that is relative to the descendant of a <xref:System.Windows.Media.Visual>, use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method.</span></span>  
  
## <a name="getting-the-offset-relative-to-a-descendant"></a><span data-ttu-id="797eb-123">Obtener el desplazamiento relativo a un descendiente</span><span class="sxs-lookup"><span data-stu-id="797eb-123">Getting the Offset Relative to a Descendant</span></span>  
 <span data-ttu-id="797eb-124">El ejemplo de marcado siguiente se muestra un <xref:System.Windows.Controls.TextBlock> que está dentro de un <xref:System.Windows.Controls.StackPanel> objeto.</span><span class="sxs-lookup"><span data-stu-id="797eb-124">The following markup example shows a <xref:System.Windows.Controls.TextBlock> that is contained within a <xref:System.Windows.Controls.StackPanel> object.</span></span>  
  
 [!code-xaml[VisualSnippets#VisualSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml#visualsnippet4)]  
  
 <span data-ttu-id="797eb-125">En el ejemplo de código siguiente se muestra cómo utilizar el <xref:System.Windows.Media.Visual.TransformToDescendant%2A> método para recuperar el desplazamiento de la <xref:System.Windows.Controls.StackPanel> en relación con su elemento secundario <xref:System.Windows.Controls.TextBlock>.</span><span class="sxs-lookup"><span data-stu-id="797eb-125">The following code example shows how to use the <xref:System.Windows.Media.Visual.TransformToDescendant%2A> method to retrieve the offset of the <xref:System.Windows.Controls.StackPanel> relative to its child <xref:System.Windows.Controls.TextBlock>.</span></span> <span data-ttu-id="797eb-126">Los valores de desplazamiento se encuentran en el valor devuelto <xref:System.Windows.Media.GeneralTransform> valor.</span><span class="sxs-lookup"><span data-stu-id="797eb-126">The offset values are contained within the returned <xref:System.Windows.Media.GeneralTransform> value.</span></span>  
  
 [!code-csharp[VisualSnippets#VisualSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualSnippets/CSharp/Window1.xaml.cs#visualsnippet9)]
 [!code-vb[VisualSnippets#VisualSnippet9](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualSnippets/visualbasic/window1.xaml.vb#visualsnippet9)]  
  
 <span data-ttu-id="797eb-127">El desplazamiento tiene en cuenta el <xref:System.Windows.FrameworkElement.Margin%2A> valores para todos los objetos.</span><span class="sxs-lookup"><span data-stu-id="797eb-127">The offset takes into account the <xref:System.Windows.FrameworkElement.Margin%2A> values for all objects.</span></span> <span data-ttu-id="797eb-128">En este caso, <xref:System.Windows.Vector.X%2A> es -4, y <xref:System.Windows.Vector.Y%2A> es -4.</span><span class="sxs-lookup"><span data-stu-id="797eb-128">In this case, <xref:System.Windows.Vector.X%2A> is -4, and <xref:System.Windows.Vector.Y%2A> is -4.</span></span> <span data-ttu-id="797eb-129">Los valores de desplazamiento son valores negativos, puesto que el objeto primario tiene un desplazamiento negativo respecto a su objeto secundario.</span><span class="sxs-lookup"><span data-stu-id="797eb-129">The offset values are negative values, since the parent object is negatively offset relative to its child object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="797eb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="797eb-130">See Also</span></span>  
 <xref:System.Windows.Media.Visual>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="797eb-131">Información general sobre la representación de gráficos en WPF</span><span class="sxs-lookup"><span data-stu-id="797eb-131">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
