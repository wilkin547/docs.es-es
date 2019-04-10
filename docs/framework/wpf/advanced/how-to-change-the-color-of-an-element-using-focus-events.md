---
title: Filtrar Cambiar el color de un elemento mediante eventos de foco
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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217645"
---
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Filtrar Cambiar el color de un elemento mediante eventos de foco
En este ejemplo se muestra cómo cambiar el color de un elemento cuando recibe y pierde el foco mediante el uso de la <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> eventos.  
  
 Este ejemplo consta de un [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] archivo y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 La siguiente [!INCLUDE[TLA2#tla_titlexaml](../../../../includes/tla2sharptla-titlexaml-md.md)] crea la interfaz de usuario, que consta de dos <xref:System.Windows.Controls.Button> objetos y adjunta los controladores de eventos para el <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> eventos para el <xref:System.Windows.Controls.Button> objetos.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 El código subyacente siguiente crea el <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> controladores de eventos.  Cuando el <xref:System.Windows.Controls.Button> ganancias, el foco de teclado del <xref:System.Windows.Controls.Control.Background%2A> de la <xref:System.Windows.Controls.Button> se cambia a rojo.  Cuando el <xref:System.Windows.Controls.Button> pierde el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> de la <xref:System.Windows.Controls.Button> se vuelve a cambiar en blanco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
