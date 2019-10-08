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
ms.openlocfilehash: 5c59dc5f2f8f26fac69933f9ef641a3a51306619
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004839"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a><span data-ttu-id="be2f8-102">Procedimiento Cambiar el color de un elemento mediante eventos de foco</span><span class="sxs-lookup"><span data-stu-id="be2f8-102">How to: Change the Color of an Element Using Focus Events</span></span>
<span data-ttu-id="be2f8-103">En este ejemplo se muestra cómo cambiar el color de un elemento cuando gana y pierde el foco mediante los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="be2f8-103">This example shows how to change the color of an element when it gains and loses focus by using the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events.</span></span>  
  
 <span data-ttu-id="be2f8-104">Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="be2f8-104">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] file and a code-behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be2f8-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="be2f8-105">Example</span></span>  
 <span data-ttu-id="be2f8-106">El código XAML siguiente crea la interfaz de usuario, que consta de dos objetos <xref:System.Windows.Controls.Button>, y asocia los controladores de eventos para los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> a los objetos <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="be2f8-106">The following XAML creates the user interface, which consists of two <xref:System.Windows.Controls.Button> objects, and attaches event handlers for the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> events to the <xref:System.Windows.Controls.Button> objects.</span></span>  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 <span data-ttu-id="be2f8-107">El siguiente código subyacente crea los controladores de eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.</span><span class="sxs-lookup"><span data-stu-id="be2f8-107">The following code behind creates the <xref:System.Windows.UIElement.GotFocus> and <xref:System.Windows.UIElement.LostFocus> event handlers.</span></span>  <span data-ttu-id="be2f8-108">Cuando el <xref:System.Windows.Controls.Button> obtiene el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> cambia a rojo.</span><span class="sxs-lookup"><span data-stu-id="be2f8-108">When the <xref:System.Windows.Controls.Button> gains keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed to red.</span></span>  <span data-ttu-id="be2f8-109">Cuando el <xref:System.Windows.Controls.Button> pierde el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> se vuelve a cambiar a blanco.</span><span class="sxs-lookup"><span data-stu-id="be2f8-109">When the <xref:System.Windows.Controls.Button> loses keyboard focus, the <xref:System.Windows.Controls.Control.Background%2A> of the <xref:System.Windows.Controls.Button> is changed back to white.</span></span>  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a><span data-ttu-id="be2f8-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="be2f8-110">See also</span></span>

- [<span data-ttu-id="be2f8-111">Información general sobre acciones del usuario</span><span class="sxs-lookup"><span data-stu-id="be2f8-111">Input Overview</span></span>](input-overview.md)
