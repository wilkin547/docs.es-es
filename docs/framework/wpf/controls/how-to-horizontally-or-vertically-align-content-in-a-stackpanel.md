---
title: Procedimiento Alinear horizontal o verticalmente el contenido de un elemento StackPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StackPanel control [WPF], content alignment [WPF]
- content alignment [WPF]
- aligning [WPF], content
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
ms.openlocfilehash: 80a0c6534e15a7a9f30976c739bade2043e96734
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733108"
---
# <a name="how-to-horizontally-or-vertically-align-content-in-a-stackpanel"></a><span data-ttu-id="35897-102">Procedimiento Alinear horizontal o verticalmente el contenido de un elemento StackPanel</span><span class="sxs-lookup"><span data-stu-id="35897-102">How to: Horizontally or Vertically Align Content in a StackPanel</span></span>
<span data-ttu-id="35897-103">En este ejemplo se muestra cómo ajustar el <xref:System.Windows.Controls.StackPanel.Orientation%2A> de contenido dentro de un <xref:System.Windows.Controls.StackPanel> elemento y también cómo ajustar el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> del contenido secundario.</span><span class="sxs-lookup"><span data-stu-id="35897-103">This example shows how to adjust the <xref:System.Windows.Controls.StackPanel.Orientation%2A> of content within a <xref:System.Windows.Controls.StackPanel> element, and also how to adjust the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> of child content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35897-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35897-104">Example</span></span>  
 <span data-ttu-id="35897-105">En el siguiente ejemplo crea tres <xref:System.Windows.Controls.ListBox> elementos en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="35897-105">The following example creates three <xref:System.Windows.Controls.ListBox> elements in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].</span></span> <span data-ttu-id="35897-106">Cada <xref:System.Windows.Controls.ListBox> representa los valores posibles de la <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> las propiedades de un <xref:System.Windows.Controls.StackPanel>.</span><span class="sxs-lookup"><span data-stu-id="35897-106">Each <xref:System.Windows.Controls.ListBox> represents the possible values of the <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>, and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> properties of a <xref:System.Windows.Controls.StackPanel>.</span></span> <span data-ttu-id="35897-107">Cuando un usuario selecciona un valor en cualquiera de los <xref:System.Windows.Controls.ListBox> elementos, la propiedad asociada de la <xref:System.Windows.Controls.StackPanel> y su elemento secundario <xref:System.Windows.Controls.Button> cambiar elementos.</span><span class="sxs-lookup"><span data-stu-id="35897-107">When a user selects a value in any of the <xref:System.Windows.Controls.ListBox> elements, the associated property of the <xref:System.Windows.Controls.StackPanel> and its child <xref:System.Windows.Controls.Button> elements change.</span></span>  
  
 [!code-xaml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="35897-108">El archivo de código subyacente siguiente define los cambios a los eventos que están asociados con el <xref:System.Windows.Controls.ListBox> cambios de selección.</span><span class="sxs-lookup"><span data-stu-id="35897-108">The following code-behind file defines the changes to the events that are associated with the <xref:System.Windows.Controls.ListBox> selection changes.</span></span> <span data-ttu-id="35897-109"><xref:System.Windows.Controls.StackPanel> se identifica mediante el <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span><span class="sxs-lookup"><span data-stu-id="35897-109"><xref:System.Windows.Controls.StackPanel> is identified by the <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.</span></span>  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="35897-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="35897-110">See also</span></span>
- <xref:System.Windows.Controls.StackPanel>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>
- <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>
- [<span data-ttu-id="35897-111">Información general sobre elementos Panel</span><span class="sxs-lookup"><span data-stu-id="35897-111">Panels Overview</span></span>](../../../../docs/framework/wpf/controls/panels-overview.md)
