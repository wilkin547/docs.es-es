---
title: Filtrar Buscar el elemento de origen en un controlador de eventos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
ms.openlocfilehash: 9a49878c9ad8313903df4506796998fd43e2e749
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104564"
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Filtrar Buscar el elemento de origen en un controlador de eventos
En este ejemplo se muestra cómo buscar el elemento de origen en un controlador de eventos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se muestra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos que se declara en un archivo de código subyacente. Cuando un usuario hace clic en el botón que está conectado al controlador, el controlador cambia un valor de propiedad. Usa el código del controlador del <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad de los datos de evento enrutado que se notifican en los argumentos de evento para cambiar la <xref:System.Windows.FrameworkElement.Width%2A> valor de propiedad en el <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.RoutedEventArgs>
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
