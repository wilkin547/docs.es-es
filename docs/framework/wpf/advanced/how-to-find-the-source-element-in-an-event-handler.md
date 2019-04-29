---
title: Procedimiento Buscar el elemento de origen en un controlador de eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61757513"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="a7bdb-102">Procedimiento Buscar el elemento de origen en un controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="a7bdb-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="a7bdb-103">En este ejemplo se muestra cómo buscar el elemento de origen en un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="a7bdb-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7bdb-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7bdb-104">Example</span></span>  
 <span data-ttu-id="a7bdb-105">El ejemplo siguiente se muestra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos que se declara en un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="a7bdb-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="a7bdb-106">Cuando un usuario hace clic en el botón que está conectado al controlador, el controlador cambia un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="a7bdb-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="a7bdb-107">Usa el código del controlador del <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad de los datos de evento enrutado que se notifican en los argumentos de evento para cambiar la <xref:System.Windows.FrameworkElement.Width%2A> valor de propiedad en el <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.</span><span class="sxs-lookup"><span data-stu-id="a7bdb-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="a7bdb-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7bdb-108">See also</span></span>

- <xref:System.Windows.RoutedEventArgs>
- [<span data-ttu-id="a7bdb-109">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="a7bdb-109">Routed Events Overview</span></span>](routed-events-overview.md)
- [<span data-ttu-id="a7bdb-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="a7bdb-110">How-to Topics</span></span>](events-how-to-topics.md)
