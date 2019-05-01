---
title: Procedimiento Aplicar un FocusVisualStyle a un control
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: 53d4984946143c15c4a2b71095529fb5ee7de4b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051330"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a><span data-ttu-id="5e3ca-102">Procedimiento Aplicar un FocusVisualStyle a un control</span><span class="sxs-lookup"><span data-stu-id="5e3ca-102">How to: Apply a FocusVisualStyle to a Control</span></span>
<span data-ttu-id="5e3ca-103">En este ejemplo se muestra cómo crear un estilo visual de foco en recursos y aplicar el estilo a un control, mediante el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-103">This example shows you how to create a focus visual style in resources and apply the style to a control, using the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e3ca-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5e3ca-104">Example</span></span>  
 <span data-ttu-id="5e3ca-105">En el ejemplo siguiente se define un estilo que crea la composición del control adicional que solo se aplica cuando ese control recibe el foco del teclado en el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5e3ca-105">The following example defines a style that creates additional control compositing that only applies when that control is keyboard focused in the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].</span></span> <span data-ttu-id="5e3ca-106">Esto se logra definiendo un estilo con un <xref:System.Windows.Controls.ControlTemplate>, a continuación, hacer referencia a ese estilo como un recurso al establecer el <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-106">This is accomplished by defining a style with a <xref:System.Windows.Controls.ControlTemplate>, then referencing that style as a resource when setting the <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> property.</span></span>  
  
 <span data-ttu-id="5e3ca-107">Un rectángulo externo que parece un borde se coloca fuera del área rectangular.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-107">An external rectangle resembling a border is placed outside of the rectangular area.</span></span> <span data-ttu-id="5e3ca-108">A menos que modifique en caso contrario, el tamaño del estilo usa la <xref:System.Windows.FrameworkElement.ActualHeight%2A> y <xref:System.Windows.FrameworkElement.ActualWidth%2A> del control rectangular donde se aplica el estilo visual de foco.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-108">Unless otherwise modified, the sizing of the style uses the <xref:System.Windows.FrameworkElement.ActualHeight%2A> and <xref:System.Windows.FrameworkElement.ActualWidth%2A> of the rectangular control where the focus visual style is applied.</span></span> <span data-ttu-id="5e3ca-109">Este ejemplo establece los valores negativos para la <xref:System.Windows.FrameworkElement.Margin%2A> para que el borde parezca ligeramente fuera del control con el foco.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-109">This example sets negative values for the <xref:System.Windows.FrameworkElement.Margin%2A> to make the border appear slightly outside the focused control.</span></span>  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 <span data-ttu-id="5e3ca-110">Un <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> es aditiva para cualquier estilo de plantilla de control que se incluye desde un estilo explícito o un estilo de tema; el estilo de un control principal todavía se puede crear mediante el uso de un <xref:System.Windows.Controls.ControlTemplate> y si ese estilo se establece en el <xref:System.Windows.FrameworkElement.Style%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-110">A <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> is additive to any control template style that comes either from an explicit style or a theme style; the primary style for a control can still be created by using a <xref:System.Windows.Controls.ControlTemplate> and setting that style to the <xref:System.Windows.FrameworkElement.Style%2A> property.</span></span>  
  
 <span data-ttu-id="5e3ca-111">Los estilos visuales deben usarse de forma coherente en un tema o una interfaz de usuario, el foco en lugar de usar otro diferente para cada elemento puede recibir el foco.</span><span class="sxs-lookup"><span data-stu-id="5e3ca-111">Focus visual styles should be used consistently across a theme or a UI, rather than using a different one for each focusable element.</span></span> <span data-ttu-id="5e3ca-112">Para obtener más información, consulte [aplicar estilo a controles y FocusVisualStyle foco](styling-for-focus-in-controls-and-focusvisualstyle.md).</span><span class="sxs-lookup"><span data-stu-id="5e3ca-112">For details, see [Styling for Focus in Controls, and FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e3ca-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e3ca-113">See also</span></span>

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [<span data-ttu-id="5e3ca-114">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="5e3ca-114">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="5e3ca-115">Aplicar estilo a los controles al recibir el foco y FocusVisualStyle</span><span class="sxs-lookup"><span data-stu-id="5e3ca-115">Styling for Focus in Controls, and FocusVisualStyle</span></span>](styling-for-focus-in-controls-and-focusvisualstyle.md)
