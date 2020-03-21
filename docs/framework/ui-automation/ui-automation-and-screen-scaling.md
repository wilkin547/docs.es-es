---
title: UI Automation y ajuste de escala de la pantalla
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- scaling, screens
- screens, scaling
- UI (user interface), automation
- UI Automation
ms.assetid: 4380cad7-e509-448f-b9a5-6de042605fd4
ms.openlocfilehash: 2a68a74fa6aadcaba21f142d394a1f8a3d8af371
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179975"
---
# <a name="ui-automation-and-screen-scaling"></a>UI Automation y ajuste de escala de la pantalla
> [!NOTE]
> Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para ver la información más reciente acerca de [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: automatización de la interfaz de usuario](/windows/win32/winauto/entry-uiauto-win32).  
  
A partir de Windows Vista, Windows permite a los usuarios cambiar la configuración de puntos por pulgada (dpi) para que la mayoría de los elementos de la interfaz de usuario (UI) de la pantalla parezcan más grandes. Aunque esta característica ha estado disponible durante mucho tiempo en Windows, en versiones anteriores el escalado tenía que ser implementado por las aplicaciones. A partir de Windows Vista, el Administrador de ventanas de escritorio realiza el escalado predeterminado para todas las aplicaciones que no controlan su propio escalado. Las aplicaciones cliente de automatización de la interfaz de usuario deben tener en cuenta esta característica.  
  
<a name="Scaling_in_Windows_Vista"></a>
## <a name="scaling-in-windows-vista"></a>Escalado en Windows Vista  
 El valor predeterminado de ppp es 96, lo que significa que 96 píxeles ocupan un ancho o alto de una pulgada nocional. La medida exacta de una "pulgada" depende del tamaño y de la resolución física del monitor. Por ejemplo, en un monitor de 12 pulgadas de ancho, con una resolución horizontal de 1280 píxeles, una línea horizontal de 96 píxeles se amplía aproximadamente 9/10 de una pulgada.  
  
 Cambiar la configuración de ppp no es lo mismo que cambiar la resolución de la pantalla. Con el escalado de ppp, el número de píxeles físicos en la pantalla sigue siendo el mismo. Sin embargo, se aplica el ajuste de escala al tamaño y a la ubicación de los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Este ajuste de escala se puede realizar automáticamente mediante el Administrador de ventanas de escritorio (DWM) para el escritorio y para las aplicaciones que no solicitan explícitamente para cambiar de escala.  
  
 En efecto, cuando el usuario establece el factor de escala en 120 ppp, una pulgada vertical u horizontal en la pantalla se hace más grande en un 25 por ciento. Todas las dimensiones se escalan en consecuencia. El desplazamiento de una ventana de aplicación desde los bordes superior e izquierdo de la pantalla aumenta en un 25 por ciento. Si el escalado de la aplicación está habilitado y la aplicación no es compatible con ppp, el tamaño [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] de la ventana aumenta en la misma proporción, junto con los desplazamientos y tamaños de todos los elementos que contiene.  
  
> [!NOTE]
> De forma predeterminada, DWM no realiza el escalado para aplicaciones que no son compatibles con ppp cuando el usuario establece el ppp en 120, pero lo realiza cuando el ppp se establece en un valor personalizado de 144 o superior. Sin embargo, el usuario puede invalidar el comportamiento predeterminado.  
  
 El escalado de pantalla crea nuevos desafíos para las aplicaciones a las que les preocupa de cualquier manera las coordenadas de pantalla. La pantalla contiene ahora dos sistemas de coordenadas: físico y lógico. Las coordenadas físicas de un punto son el desplazamiento real en píxeles desde la parte superior izquierda del origen. Las coordenadas lógicas son los desplazamientos de la manera que serían si se escalaran los propios píxeles.  
  
 Supongamos que diseña un cuadro de diálogo con un botón en las coordenadas (100, 48). Cuando este cuadro de diálogo se muestra en el valor predeterminado de 96 ppp, el botón se encuentra en coordenadas físicas de (100, 48). A 120 dpi, se encuentra en coordenadas físicas de (125, 60). Pero las coordenadas lógicas son las mismas en cualquier configuración de ppp: (100, 48).  
  
 Las coordenadas lógicas son importantes, ya que hacen que el comportamiento del sistema operativo y las aplicaciones sea coherente independientemente de la configuración de ppp. Por ejemplo, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> normalmente devuelve las coordenadas lógicas. Si mueve el cursor sobre un elemento de un cuadro de diálogo, se devuelven las mismas coordenadas independientemente de la configuración de ppp. Si dibuja un control en (100, 100), se dibuja a esas coordenadas lógicas y ocupará la misma posición relativa en cualquier configuración de ppp.  
  
<a name="Scaling_in_UI_Automation_Clients"></a>
## <a name="scaling-in-ui-automation-clients"></a>Escalado en los clientes de automatización de la interfaz de usuario  
 La [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] API no utiliza coordenadas lógicas. Los siguientes métodos y propiedades devuelven coordenadas físicas o las toman como parámetros.  
  
- <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
- <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
- <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 De forma predeterminada, una aplicación cliente de Automatización de la interfaz de usuarioUI Automation que se ejecute en un entorno que no sea de 96 ppp no podrá obtener los resultados correctos de estos métodos y propiedades. Por ejemplo, dado que la posición del cursor se encuentra en coordenadas lógicas, el cliente no podrá pasar simplemente estas coordenadas a <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> para obtener el elemento que se encuentra debajo del cursor. Además, la aplicación no podrá colocar correctamente ventanas fuera de su área de cliente.  
  
 La solución consta de dos partes.  
  
1. En primer lugar, haga que la aplicación cliente sea compatible con dpi. Para ello, llame a la `SetProcessDPIAware` función Win32 al inicio. En código administrado, la siguiente declaración hace que esta función esté disponible.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Esta función hace que todo el proceso tenga en cuenta dpi, lo que significa que todas las ventanas que pertenecen al proceso no están en escala. En el ejemplo de [resaltador](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), por ejemplo, las cuatro ventanas que componen el rectángulo de resaltado se encuentran en las coordenadas físicas obtenidas de Automatización de la interfaz de usuarioUI Automation, no en las coordenadas lógicas. Si la muestra no fuera compatible con ppp, el resaltado se dibujaría en las coordenadas lógicas del escritorio, lo que daría lugar a una colocación incorrecta en un entorno que no sea de 96 ppp.  
  
2. Para obtener coordenadas del cursor, `GetPhysicalCursorPos`llame a la función Win32 . En el ejemplo siguiente se muestra cómo declarar y usar esta función.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
> No use <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. El comportamiento de esta propiedad fuera de las ventanas de cliente en un entorno de escala es indefinido.  
  
 Si la aplicación realiza una comunicación directa entre procesos con aplicaciones que no son compatibles con ppp, `PhysicalToLogicalPoint` `LogicalToPhysicalPoint`es posible que tenga que convertir entre coordenadas lógicas y físicas mediante las funciones Win32 y .  
  
## <a name="see-also"></a>Consulte también

- [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
