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
# <a name="how-to-change-the-color-of-an-element-using-focus-events"></a>Procedimiento Cambiar el color de un elemento mediante eventos de foco
En este ejemplo se muestra cómo cambiar el color de un elemento cuando gana y pierde el foco mediante los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  
  
 Este ejemplo consta de un archivo [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y un archivo de código subyacente.  
  
## <a name="example"></a>Ejemplo  
 El código XAML siguiente crea la interfaz de usuario, que consta de dos objetos <xref:System.Windows.Controls.Button>, y asocia los controladores de eventos para los eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> a los objetos <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml#gotlostfocussamplexaml)]  
  
 El siguiente código subyacente crea los controladores de eventos <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  Cuando el <xref:System.Windows.Controls.Button> obtiene el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> cambia a rojo.  Cuando el <xref:System.Windows.Controls.Button> pierde el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> del <xref:System.Windows.Controls.Button> se vuelve a cambiar a blanco.  
  
 [!code-csharp[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/csharp/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/CSharp/Window1.xaml.cs#gotlostfocussampleeventhandlers)]
 [!code-vb[gotfocusLostfocusEffectUsingEvent#GotLostFocusSampleEventHandlers](~/samples/snippets/visualbasic/VS_Snippets_Wpf/gotfocusLostfocusEffectUsingEvent/VisualBasic/Window1.xaml.vb#gotlostfocussampleeventhandlers)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre acciones del usuario](input-overview.md)
