---
title: 'Cómo: Aplicar FocusVisualStyle a un control'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: b44330ee7554f953389556bd62ff49db120b5db9
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459809"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="a3a03-102">Cómo: Aplicar FocusVisualStyle a un control</span><span class="sxs-lookup"><span data-stu-id="a3a03-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="a3a03-103">En este ejemplo se muestra cómo crear un estilo visual de foco en los recursos y cómo aplicar el estilo a un control mediante la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3a03-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3a03-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3a03-104">Example</span></span>  
 <span data-ttu-id="a3a03-105">En el ejemplo siguiente se define un estilo que crea una composición de control adicional que solo se aplica cuando ese control tiene el foco de teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a3a03-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="a3a03-106">Esto se logra definiendo un estilo con un <xref:System.Windows.Controls.ControlTemplate>y haciendo referencia a ese estilo como un recurso al establecer la propiedad <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3a03-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="a3a03-107">Un rectángulo externo similar a un borde se coloca fuera del área rectangular.</span><span class="sxs-lookup"><span data-stu-id="a3a03-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="a3a03-108">A menos que se modifique de otro modo, el tamaño del estilo utiliza el <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular donde se aplica el estilo visual de foco.</span><span class="sxs-lookup"><span data-stu-id="a3a03-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="a3a03-109">Este ejemplo establece los valores negativos del <xref:System.Windows.FrameworkElement.Margin%2A> para que el borde aparezca ligeramente fuera del control con foco.</span><span class="sxs-lookup"><span data-stu-id="a3a03-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="a3a03-110">Un <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es aditivo para cualquier estilo de plantilla de control que proceda de un estilo explícito o de un estilo de tema. el estilo principal de un control todavía se puede crear con una <xref:System.Windows.Controls.ControlTemplate> y establecer ese estilo en la propiedad <xref:System.Windows.FrameworkElement.Style%2A>.</span><span class="sxs-lookup"><span data-stu-id="a3a03-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="a3a03-111">Los estilos visuales de foco deben usarse de forma coherente en un tema o una interfaz de usuario, en lugar de usar uno diferente para cada elemento que pueda recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="a3a03-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="a3a03-112">Para obtener más información, vea [aplicar estilo a los controles y FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="a3a03-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a03-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3a03-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="a3a03-114">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="a3a03-114">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="a3a03-115">Aplicar estilo a los controles al recibir el foco y FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="a3a03-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
