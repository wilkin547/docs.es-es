---
title: "Cómo: Buscar el elemento de origen en un controlador de eventos"
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
- source element in event handlers [WPF]
- event handlers [WPF], finding source element in
ms.assetid: 85f71c5a-b714-4c65-9711-7d905c2bbe98
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e9746683ec5b7ad142591c2b419f9af21be8d69c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-the-source-element-in-an-event-handler"></a>Cómo: Buscar el elemento de origen en un controlador de eventos
Este ejemplo muestra cómo buscar el elemento de origen en un controlador de eventos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos que se declara en un archivo de código subyacente. Cuando un usuario hace clic en el botón que está asociado el controlador a, el controlador cambia un valor de propiedad. Utiliza el código del controlador de la <xref:System.Windows.RoutedEventArgs.Source%2A> propiedad de los datos del evento enrutado que se notifican en los argumentos de evento para cambiar la <xref:System.Windows.FrameworkElement.Width%2A> valor de propiedad en el <xref:System.Windows.RoutedEventArgs.Source%2A> elemento.  
  
 [!code-xaml[RoutedEventSource#XAMLHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml#xamlhandler)]  
  
 [!code-csharp[RoutedEventSource#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventSource/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventSource#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventSource/VisualBasic/default.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.RoutedEventArgs>  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)
