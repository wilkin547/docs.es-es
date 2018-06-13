---
title: 'Cómo: Buscar el elemento de origen en un controlador de eventos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: c3ae893cd7fd7780854d6eb6ffd682feadb5c5a0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544009"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a><span data-ttu-id="1b0f1-102">Cómo: Buscar el elemento de origen en un controlador de eventos</span><span class="sxs-lookup"><span data-stu-id="1b0f1-102">How to: Find the Source Element in an Event Handler</span></span>
<span data-ttu-id="1b0f1-103">Este ejemplo muestra cómo buscar el elemento de origen en un controlador de eventos.</span><span class="sxs-lookup"><span data-stu-id="1b0f1-103">This example shows how to find the source element in an event handler.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b0f1-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1b0f1-104">Example</span></span>  
 <span data-ttu-id="1b0f1-105">El ejemplo siguiente muestra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos que se declara en un archivo de código subyacente.</span><span class="sxs-lookup"><span data-stu-id="1b0f1-105">The following example shows a <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handler that is declared in a code-behind file.</span></span> <span data-ttu-id="1b0f1-106">Cuando un usuario hace clic en el botón que está asociado el controlador a, el controlador cambia un valor de propiedad.</span><span class="sxs-lookup"><span data-stu-id="1b0f1-106">When a user clicks the button that the handler is attached to, the handler changes a property value.</span></span> <span data-ttu-id="1b0f1-107">Utiliza el código del controlador de la <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad de los datos del evento enrutado que se notifican en los argumentos de evento para cambiar la <xref:System.Windows.FrameworkElement.Width%2A> valor de propiedad en el <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.</span><span class="sxs-lookup"><span data-stu-id="1b0f1-107">The handler code uses the <xref:System.Windows.RoutedEventArgs.Source%2A> property of the routed event data that is reported in the event arguments to change the <xref:System.Windows.FrameworkElement.Width%2A> property value on the <xref:System.Windows.RoutedEventArgs.Source%2A> element.</span></span>  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a><span data-ttu-id="1b0f1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b0f1-108">See Also</span></span>  
 <xref:System.Windows.RoutedEventArgs>  
 [<span data-ttu-id="1b0f1-109">Información general sobre eventos enrutados</span><span class="sxs-lookup"><span data-stu-id="1b0f1-109">Routed Events Overview</span></span>](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [<span data-ttu-id="1b0f1-110">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="1b0f1-110">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
