---
title: "Cómo: Crear un efecto de activación mediante eventos"
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
- colors of elements [WPF], changing
- rollover effect [WPF]
- element colors [WPF], changing
ms.assetid: 3b20d028-6f1c-4b25-95d2-fa68cefbdb4c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7fc65c9342cc86d4ceebd65e91c05cc1bea464e6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-rollover-effect-using-events"></a><span data-ttu-id="a2ff1-102">Cómo: Crear un efecto de activación mediante eventos</span><span class="sxs-lookup"><span data-stu-id="a2ff1-102">How to: Create a Rollover Effect Using Events</span></span>
<span data-ttu-id="a2ff1-103">Este ejemplo muestra cómo cambiar el color de un elemento cuando el puntero del mouse entra y sale del área ocupada por el elemento.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-103">This example shows how to change the color of an element as the mouse pointer enters and leaves the area occupied by the element.</span></span>  
  
 <span data-ttu-id="a2ff1-104">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2ff1-105">En este ejemplo se muestra cómo usar los eventos, pero la manera recomendada para lograr este mismo efecto es utilizar un <xref:System.Windows.Trigger> en un estilo.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-105">This example demonstrates how to use events, but the recommended way to achieve this same effect is to use a <xref:System.Windows.Trigger> in a style.</span></span> <span data-ttu-id="a2ff1-106">Para obtener más información, consulte [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span><span class="sxs-lookup"><span data-stu-id="a2ff1-106">For more information, see [Styling and Templating](../../../../docs/framework/wpf/controls/styling-and-templating.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ff1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2ff1-107">Example</span></span>  
 <span data-ttu-id="a2ff1-108">El siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de <xref:System.Windows.Controls.Border> alrededor de una <xref:System.Windows.Controls.TextBlock>y asocia el <xref:System.Windows.Input.Mouse.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos para el <xref:System.Windows.Controls.Border>.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-108">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of <xref:System.Windows.Controls.Border> around a <xref:System.Windows.Controls.TextBlock>, and attaches the <xref:System.Windows.Input.Mouse.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers to the <xref:System.Windows.Controls.Border>.</span></span>  
  
 [!code-xaml[mouseenterMouseleave#MouseEnterLeaveSampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml#mouseenterleavesamplexaml)]  
  
 <span data-ttu-id="a2ff1-109">Crea el código siguiente detrás de la <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-109">The following code behind creates the <xref:System.Windows.UIElement.MouseEnter> and <xref:System.Windows.UIElement.MouseLeave> event handlers.</span></span>  <span data-ttu-id="a2ff1-110">Cuando el puntero del mouse entra en el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> se cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-110">When the mouse pointer enters the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed to red.</span></span>  <span data-ttu-id="a2ff1-111">Cuando el puntero del mouse deja el <xref:System.Windows.Controls.Border>, el fondo de la <xref:System.Windows.Controls.Border> vuelve a establecerse en blanco.</span><span class="sxs-lookup"><span data-stu-id="a2ff1-111">When the mouse pointer leaves the <xref:System.Windows.Controls.Border>, the background of the <xref:System.Windows.Controls.Border> is changed back to white.</span></span>  
  
 [!code-csharp[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/csharp/VS_Snippets_Wpf/mouseenterMouseleave/CSharp/Window1.xaml.cs#mouseenterleavesampleeventhandlers)]
 [!code-vb[mouseenterMouseleave#MouseEnterLeaveSampleEventHandlers](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/mouseenterMouseleave/VisualBasic/Window1.xaml.vb#mouseenterleavesampleeventhandlers)]
