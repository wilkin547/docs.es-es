---
title: "Cómo: Aplicar FocusVisualStyle a un control"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f614e244293d08cd836edaf82496ca9e7b51423e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="c4ae5-102">Cómo: Aplicar FocusVisualStyle a un control</span><span class="sxs-lookup"><span data-stu-id="c4ae5-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="c4ae5-103">Este ejemplo muestra cómo crear un estilo visual del foco en recursos y aplique el estilo a un control utilizando la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4ae5-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c4ae5-104">Example</span></span>  
 <span data-ttu-id="c4ae5-105">En el ejemplo siguiente se define un estilo que crea la composición del control adicional que solo se aplica cuando ese control recibe el foco del teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c4ae5-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="c4ae5-106">Esto se logra mediante la definición de un estilo con un <xref:System.Windows.Controls.ControlTemplate>, a continuación, hacer referencia a ese estilo como un recurso al establecer el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="c4ae5-107">Un rectángulo externo que parece un borde se coloca fuera del área rectangular.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="c4ae5-108">A menos que modifique en caso contrario, el tamaño del estilo utiliza el <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular que se aplica el estilo visual del foco.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="c4ae5-109">Este ejemplo establece los valores negativos para la <xref:System.Windows.FrameworkElement.Margin%2A> para hacer que el borde parezca ligeramente fuera del control tiene el foco.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="c4ae5-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es suma para cualquier estilo de plantilla de control que se incluye desde un estilo explícito o un estilo de tema; el estilo de un control principal todavía se puede crear mediante el uso de un <xref:System.Windows.Controls.ControlTemplate> y establecer ese estilo en el <xref:System.Windows.FrameworkElement.Style%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="c4ae5-111">Foco estilos visuales deben utilizarse de manera coherente a través de un tema o una interfaz de usuario, en lugar de utilizar uno diferente para cada elemento puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="c4ae5-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="c4ae5-112">Para obtener más información, consulte [aplicación de estilos para se centran en los controles y FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="c4ae5-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4ae5-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4ae5-113">See Also</span></span>  
 <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>  
 [<span data-ttu-id="c4ae5-114">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="c4ae5-114">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="c4ae5-115">Aplicar estilo a los controles al recibir el foco y FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="c4ae5-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](../../../../docs/framework/wpf/advanced/styling-for-focus-in-controls-and-focusvisualstyle.md)
