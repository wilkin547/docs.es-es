---
title: Procedimiento Cambiar el color de un elemento mediante eventos de foco
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus events [WPF], changing element color for
- colors of elements [WPF], changing
- elements [WPF], changing color of
ms.assetid: 7e246802-3625-47a7-ae9d-c8a2a40fd040
ms.openlocfilehash: 744963cc543110121a777e1d4c3cdcb3cec40d9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776901"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="2ddfe-102">Procedimiento Cambiar el color de un elemento mediante eventos de foco</span><span class="sxs-lookup"><span data-stu-id="2ddfe-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="2ddfe-103">En este ejemplo se muestra cómo cambiar el color de un elemento cuando recibe y pierde el foco mediante el uso de la <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> eventos.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="2ddfe-104">Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ddfe-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ddfe-105">Example</span></span>  
 <span data-ttu-id="2ddfe-106">La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de dos <xref:System.Windows.Controls.Button> objetos y adjunta los controladores de eventos para el <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> eventos para el <xref:System.Windows.Controls.Button> objetos.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-106">The following [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="2ddfe-107">El código subyacente siguiente crea el <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="2ddfe-108">Cuando el <xref:System.Windows.Controls.Button> ganancias, el foco de teclado del <xref:System.Windows.Controls.Control.Background%2A> de la <xref:System.Windows.Controls.Button> se cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="2ddfe-109">Cuando el <xref:System.Windows.Controls.Button> pierde el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> de la <xref:System.Windows.Controls.Button> se vuelve a cambiar en blanco.</span><span class="sxs-lookup"><span data-stu-id="2ddfe-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="2ddfe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ddfe-110">See also</span></span>

- [<span data-ttu-id="2ddfe-111">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="2ddfe-111">Input Overview</span></span>](input-overview.md)
