---
title: "Cómo: Controlar un evento enrutado"
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
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c491ff4e231d932b3714d2d059b52bad2502368c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-a-routed-event"></a>Cómo: Controlar un evento enrutado
En este ejemplo se muestra cómo funciona la propagación de eventos y cómo se escribe un controlador capaz de procesar los datos de eventos enrutados.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], los elementos se organizan en una estructura de árbol de elementos. El elemento primario puede participar en el control de eventos generados inicialmente por elementos secundarios en el árbol de elementos. Esto es posible gracias al enrutamiento de eventos.  
  
 Normalmente, los eventos enrutados siguen una de las dos estrategias de enrutamiento posibles: propagación o tunelización. En este ejemplo se centra en el evento de propagación y usa el <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> eventos para mostrar cómo funciona el enrutamiento.  
  
 En el ejemplo siguiente se crea dos <xref:System.Windows.Controls.Button> controla y usa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo sintaxis para adjuntar un controlador de eventos a un elemento primario común, que en este ejemplo es <xref:System.Windows.Controls.StackPanel>. En lugar de adjuntar controladores de eventos individuales para cada <xref:System.Windows.Controls.Button> elemento secundario, el ejemplo usa la sintaxis de atributo para asociar el controlador de eventos para el <xref:System.Windows.Controls.StackPanel> elemento primario. Este patrón de control de eventos muestra cómo usar el enrutamiento de eventos como técnica para reducir el número de elementos en los que se adjunta un controlador. Todos los eventos de propagación para cada <xref:System.Windows.Controls.Button> ruta a través del elemento primario.  
  
 Tenga en cuenta que en el registro primario <xref:System.Windows.Controls.StackPanel> elemento, el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> nombre de evento especificado como el atributo se certifica parcialmente nombrando la <xref:System.Windows.Controls.Button> clase. El <xref:System.Windows.Controls.Button> clase es un <xref:System.Windows.Controls.Primitives.ButtonBase> clase derivada que tiene el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento en su lista de miembros. Esta técnica de calificación parcial para adjuntar un controlador de eventos es necesaria si el evento que se controla no existe en la lista de miembros del elemento donde está adjunto el controlador de eventos enrutados.  
  
 [!code-xaml[RoutedEventHandle#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 El siguiente ejemplo se controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  En el ejemplo se notifican el elemento que controla el evento y el elemento que lo genera. El controlador de eventos se ejecuta cuando el usuario hace clic en cualquiera de los botones.  
  
 [!code-csharp[RoutedEventHandle#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.RoutedEvent>  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/events-how-to-topics.md)  
 [Detalles de la sintaxis XAML](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
