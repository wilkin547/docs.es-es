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
ms.openlocfilehash: 18cb28de04737973876e70cdb7b87e720836bcba
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59332700"
---
# <a name="ui-automation-and-screen-scaling"></a>UI Automation y ajuste de escala de la pantalla
> [!NOTE]
>  Esta documentación está dirigida a los desarrolladores de .NET Framework que quieran usar las clases [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] administradas definidas en el espacio de nombres <xref:System.Windows.Automation>. Para obtener información más reciente sobre [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], consulte [Windows Automation API: Automatización de interfaz de usuario](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] permite a los usuarios cambiar la [!INCLUDE[TLA#tla_dpi](../../../includes/tlasharptla-dpi-md.md)] establecer para que la mayoría [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] elementos en la pantalla parezcan de mayor tamaño. Aunque esta característica ha estado disponible desde hace mucho tiempo en [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)], en las versiones anteriores, el escalado se tenía que implementar por las aplicaciones. En [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)], el Administrador de ventanas de escritorio realiza el ajuste de escala predeterminado para todas las aplicaciones que no controlan su propia escala. Las aplicaciones cliente de automatización de la interfaz de usuario deben tener en cuenta esta característica.  
  
<a name="Scaling_in_Windows_Vista"></a>   
## <a name="scaling-in-windows-vista"></a>Escalado en Windows Vista  
 La configuración de [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] predeterminada es 96, lo que significa que 96 píxeles ocupan el ancho o el alto de una pulgada teórica. La medida exacta de una "pulgada" depende del tamaño y de la resolución física del monitor. Por ejemplo, en un monitor de 12 pulgadas de ancho, con una resolución horizontal de 1280 píxeles, una línea horizontal de 96 píxeles se amplía aproximadamente 9/10 de una pulgada.  
  
 Cambiar la configuración de [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] no es lo mismo que cambiar la resolución de pantalla. Con el ajuste de escala [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] , el número de píxeles físicos de la pantalla sigue siendo el mismo. Sin embargo, se aplica el ajuste de escala al tamaño y a la ubicación de los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] . Este ajuste de escala se puede realizar automáticamente mediante el Administrador de ventanas de escritorio (DWM) para el escritorio y para las aplicaciones que no solicitan explícitamente para cambiar de escala.  
  
 En efecto, cuando el usuario establece el factor de escala en 120 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], una pulgada vertical u horizontal en la pantalla aumenta en un 25 por ciento. Todas las dimensiones se escalan en consecuencia. El desplazamiento de una ventana de aplicación desde los bordes superior e izquierdo de la pantalla aumenta en un 25 por ciento. Si el ajuste de escala de aplicación está habilitado y la aplicación no es para [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], el tamaño de la ventana aumenta en la misma proporción, junto con los desplazamientos y los tamaños de todos los elementos [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] que contiene.  
  
> [!NOTE]
>  De forma predeterminada, el DWM no realiza el ajuste de escala para aplicaciones que no son de[!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]cuando el usuario establece [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] en 120, pero lo realiza cuando [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] se establece en un valor personalizado de 144 o superior. Sin embargo, el usuario puede invalidar el comportamiento predeterminado.  
  
 El escalado de pantalla crea nuevos desafíos para las aplicaciones a las que les preocupa de cualquier manera las coordenadas de pantalla. La pantalla contiene ahora dos sistemas de coordenadas: físico y lógico. Las coordenadas físicas de un punto son el desplazamiento real en píxeles desde la parte superior izquierda del origen. Las coordenadas lógicas son los desplazamientos de la manera que serían si se escalaran los propios píxeles.  
  
 Supongamos que diseña un cuadro de diálogo con un botón en las coordenadas (100, 48). Cuando este cuadro de diálogo se muestre en el [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]96 predeterminado, el botón se encuentra en las coordenadas físicas (100, 48). En [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]120, se encuentra en las coordenadas físicas (125, 60). Pero las coordenadas lógicas son las mismas en cualquier [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] configuración: (100, 48).  
  
 Las coordenadas lógicas son importantes porque hacen que el comportamiento del sistema operativo y las aplicaciones sea coherente independientemente de la configuración de [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] . Por ejemplo, <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType> normalmente devuelve las coordenadas lógicas. Si mueve el cursor sobre un elemento en un cuadro de diálogo, se devuelven las mismas coordenadas con independencia de la configuración [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] . Si dibuja un control en (100, 100), se dibuja con esas coordenadas lógicas y ocupará la misma posición relativa en cualquier configuración [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] .  
  
<a name="Scaling_in_UI_Automation_Clients"></a>   
## <a name="scaling-in-ui-automation-clients"></a>Escalado en los clientes de automatización de la interfaz de usuario  
  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] [!INCLUDE[TLA#tla_api](../../../includes/tlasharptla-api-md.md)] no usa coordenadas lógicas. Los siguientes métodos y propiedades devuelven coordenadas físicas o las toman como parámetros.  
  
-   <xref:System.Windows.Automation.AutomationElement.GetClickablePoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.TryGetClickablePoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.ClickablePointProperty>  
  
-   <xref:System.Windows.Automation.AutomationElement.FromPoint%2A>  
  
-   <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.BoundingRectangle%2A>  
  
 De manera predeterminada, una aplicación de cliente de automatización de la interfaz de usuario que se está ejecutando en un entorno que no sea de 96 [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)] no podrá obtener resultados correctos de estos métodos y propiedades. Por ejemplo, dado que la posición del cursor se encuentra en coordenadas lógicas, el cliente no podrá pasar simplemente estas coordenadas a <xref:System.Windows.Automation.AutomationElement.FromPoint%2A> para obtener el elemento que se encuentra debajo del cursor. Además, la aplicación no podrá colocar correctamente ventanas fuera de su área de cliente.  
  
 La solución consta de dos partes.  
  
1. En primer lugar, haga que la aplicación cliente sea para [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)]. Para ello, llame a la función [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]`SetProcessDPIAware` al inicio. En código administrado, la siguiente declaración hace que esta función esté disponible.  
  
     [!code-csharp[Highlighter#101](../../../samples/snippets/csharp/VS_Snippets_Wpf/Highlighter/CSharp/NativeMethods.cs#101)]
     [!code-vb[Highlighter#101](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Highlighter/VisualBasic/NativeMethods.vb#101)]  
  
     Esta función realiza todo el proceso de reconocimiento de PPP, lo que significa que todas las ventanas que pertenecen al proceso sean sin escala. En el [Highlighter Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter), por ejemplo, las cuatro ventanas que componen el rectángulo resaltado se encuentran en las coordenadas físicas obtenidas de la automatización de interfaz de usuario, no las coordenadas lógicas. Si el ejemplo no era con reconocimiento de PPP, el resaltado se dibujaría en las coordenadas lógicas del escritorio, lo que daría lugar a una ubicación incorrecta en un entorno que no sea de 96 PPP.  
  
2. Para obtener coordenadas de cursor, llame a la función [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `GetPhysicalCursorPos`. En el ejemplo siguiente se muestra cómo declarar y usar esta función.  
  
     [!code-csharp[UIAClient_snip#185](../../../samples/snippets/csharp/VS_Snippets_Wpf/UIAClient_snip/CSharp/ClientForm.cs#185)]
     [!code-vb[UIAClient_snip#185](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UIAClient_snip/VisualBasic/ClientForm.vb#185)]  
  
> [!CAUTION]
>  No use <xref:System.Windows.Forms.Cursor.Position%2A?displayProperty=nameWithType>. El comportamiento de esta propiedad fuera de las ventanas de cliente en un entorno de escala es indefinido.  
  
 Si la aplicación realiza una comunicación directa entre procesos con aplicaciones que no son para [!INCLUDE[TLA2#tla_dpi](../../../includes/tla2sharptla-dpi-md.md)], puede que tenga que convertir entre las coordenadas lógicas y físicas mediante las funciones [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] `PhysicalToLogicalPoint` y `LogicalToPhysicalPoint`.  
  
## <a name="see-also"></a>Vea también

- [Ejemplo de marcador de resaltado](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/Highlighter)
