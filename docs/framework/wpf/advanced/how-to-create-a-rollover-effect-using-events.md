---
title: Procedimiento Crear un efecto de sustitución mediante eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
ms.openlocfilehash: 3996a3b9bb976dd5f2e5b675de3894bbaba7d9d3
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960385"
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="b6087-102">Procedimiento Crear un efecto de sustitución mediante eventos</span><span class="sxs-lookup"><span data-stu-id="b6087-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="b6087-103">En este ejemplo se muestra cómo cambiar el color de un elemento a medida que el puntero del Mouse entra y sale del área ocupada por el elemento.</span><span class="sxs-lookup"><span data-stu-id="b6087-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="b6087-104">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="b6087-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6087-105">En este ejemplo se muestra cómo utilizar los eventos, pero la manera recomendada de lograr este mismo efecto es usar <xref:System.Windows.Trigger> un en un estilo.</span><span class="sxs-lookup"><span data-stu-id="b6087-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="b6087-106">Para obtener más información, consulte [Aplicar estilos y plantillas](../controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="b6087-106">For more information, see [Styling and Templating](../controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6087-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b6087-107">Example</span></span>  
 <span data-ttu-id="b6087-108">Lo siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que se <xref:System.Windows.Controls.Border> compone de <xref:System.Windows.Controls.TextBlock>un, y asocia los <xref:System.Windows.Input.Mouse.MouseEnter> controladores <xref:System.Windows.UIElement.MouseLeave> de eventos y a <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="b6087-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="b6087-109">El siguiente código subyacente crea los <xref:System.Windows.UIElement.MouseEnter> controladores <xref:System.Windows.UIElement.MouseLeave> de eventos y.</span><span class="sxs-lookup"><span data-stu-id="b6087-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="b6087-110">Cuando el puntero del Mouse entra <xref:System.Windows.Controls.Border>en, el fondo <xref:System.Windows.Controls.Border> de se cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="b6087-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="b6087-111">Cuando el puntero del mouse sale <xref:System.Windows.Controls.Border>de, el fondo <xref:System.Windows.Controls.Border> de se vuelve a cambiar a blanco.</span><span class="sxs-lookup"><span data-stu-id="b6087-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
