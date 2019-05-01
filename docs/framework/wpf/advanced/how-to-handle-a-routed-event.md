---
title: Procedimiento Controlar un evento enrutado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], handling
- bubbling events [WPF]
ms.assetid: 157787b4-f469-4047-8777-5b034145f32e
ms.openlocfilehash: edb3d6724af89b7e85986c50b579084e3c4e5070
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001512"
---
# <a name="how-to-handle-a-routed-event"></a>Procedimiento Controlar un evento enrutado
En este ejemplo se muestra cómo funciona la propagación de eventos y cómo se escribe un controlador capaz de procesar los datos de eventos enrutados.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], los elementos se organizan en una estructura de árbol de elementos. El elemento primario puede participar en el control de eventos generados inicialmente por elementos secundarios en el árbol de elementos. Esto es posible gracias al enrutamiento de eventos.  
  
 Normalmente, los eventos enrutados siguen una de las dos estrategias de enrutamiento posibles: propagación o tunelización. En este ejemplo se centra en el evento de propagación y usa el <xref:System.Windows.Controls.Primitives.ButtonBase.Click?displayProperty=nameWithType> evento para mostrar cómo funciona el enrutamiento.  
  
 En el ejemplo siguiente se crean dos <xref:System.Windows.Controls.Button> controla y usa [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sintaxis para adjuntar un controlador de eventos a un elemento primario común, que en este ejemplo es de atributo <xref:System.Windows.Controls.StackPanel>. En lugar de asociar controladores de eventos individuales para cada <xref:System.Windows.Controls.Button> elemento secundario, el ejemplo usa la sintaxis de atributo para asociar el controlador de eventos el <xref:System.Windows.Controls.StackPanel> elemento primario. Este patrón de control de eventos muestra cómo usar el enrutamiento de eventos como técnica para reducir el número de elementos en los que se adjunta un controlador. Todos los eventos de propagación para cada <xref:System.Windows.Controls.Button> enrutar a través del elemento primario.  
  
 Tenga en cuenta que en el elemento primario <xref:System.Windows.Controls.StackPanel> elemento, el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> nombre de evento especificado como el atributo se califica parcialmente mediante nomenclatura el <xref:System.Windows.Controls.Button> clase. El <xref:System.Windows.Controls.Button> clase es un <xref:System.Windows.Controls.Primitives.ButtonBase> clase derivada que tiene el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos en su lista de miembros. Esta técnica de calificación parcial para adjuntar un controlador de eventos es necesaria si el evento que se controla no existe en la lista de miembros del elemento donde está adjunto el controlador de eventos enrutados.  
  
 [!code-xaml[RoutedEventHandle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml#xaml)]  
  
 El ejemplo siguiente se controla el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> eventos.  En el ejemplo se notifican el elemento que controla el evento y el elemento que lo genera. El controlador de eventos se ejecuta cuando el usuario hace clic en cualquiera de los botones.  
  
 [!code-csharp[RoutedEventHandle#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/RoutedEventHandle/CSharp/default.xaml.cs#handler)]
 [!code-vb[RoutedEventHandle#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RoutedEventHandle/VisualBasic/MainWindow.xaml.vb#handler)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.RoutedEvent>
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Temas "Cómo..."](events-how-to-topics.md)
- [Detalles de la sintaxis XAML](xaml-syntax-in-detail.md)
