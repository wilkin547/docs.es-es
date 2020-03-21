---
title: 'Optimizar el rendimiento: Otras recomendaciones'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Terminal Services rendering [WPF]
- opacity [WPF]
- hit-test objects [WPF]
- ScrollBarVisibility enumeration [WPF]
- brushes [WPF], performance
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
ms.openlocfilehash: 727331adb41251460209f157d1804ff455bcf473
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186301"
---
# <a name="optimizing-performance-other-recommendations"></a>Optimizar el rendimiento: Otras recomendaciones
<a name="introduction"></a> En este tema se proporcionan recomendaciones de rendimiento, además de las que se incluyen en los temas de la sección [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md).  
  
 Este tema contiene las siguientes secciones:  
  
- [Opacidad en pinceles frente a opacidad en elementos](#Opacity)  
  
- [Navegación al objeto](#Navigation_Objects)  
  
- [Comprobación de visitas en superficies 3D de gran tamaño](#Hit_Testing)  
  
- [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
- [Evitar usar ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
- [Configurar el servicio de caché de fuente para reducir el tiempo de inicio](#FontCache)  
  
<a name="Opacity"></a>
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Opacidad en pinceles frente a opacidad en elementos  
 Cuando se <xref:System.Windows.Media.Brush> usa a <xref:System.Windows.Shapes.Shape.Fill%2A> <xref:System.Windows.Shapes.Shape.Stroke%2A> para establecer el o de <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> un elemento, es mejor <xref:System.Windows.UIElement.Opacity%2A> establecer el valor en lugar de establecer la propiedad del elemento. Modificar la propiedad <xref:System.Windows.UIElement.Opacity%2A> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un elemento puede hacer crear una superficie temporal.  
  
<a name="Navigation_Objects"></a>
## <a name="navigation-to-object"></a>Navegación al objeto  
 El <xref:System.Windows.Navigation.NavigationWindow> objeto deriva <xref:System.Windows.Window> y lo extiende con compatibilidad con la navegación <xref:System.Windows.Navigation.NavigationService> de contenido, principalmente agregando y el diario. Puede actualizar el área <xref:System.Windows.Navigation.NavigationWindow> de cliente especificando un identificador uniforme de recursos (URI) o un objeto. En el ejemplo siguiente se muestran ambos métodos:  
  
 [!code-csharp[Performance#PerformanceSnippet14](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Cada <xref:System.Windows.Navigation.NavigationWindow> objeto tiene un diario que registra el historial de navegación del usuario en esa ventana. Uno de los propósitos del diario es permitir que los usuarios vuelvan sobre sus pasos.  
  
 Cuando se navega mediante un identificador uniforme de recursos (URI), el diario almacena solo la referencia de identificador uniforme de recursos (URI). Esto significa que, cada vez que vuelve a visitar la página, se reconstruye dinámicamente, lo que puede llevar mucho tiempo según la complejidad de la página. En este caso, el costo de almacenamiento del diario es bajo, pero el tiempo para reconstituir la página es potencialmente alto.  
  
 Al navegar con un objeto, el diario almacena todo el árbol visual del objeto. Esto significa que, cada vez que vuelve a la página, se representa inmediatamente sin tener que reconstruirla. En este caso, el costo de almacenamiento del diario es alto, pero el tiempo para reconstituir la página es bajo.  
  
 Cuando utilice <xref:System.Windows.Navigation.NavigationWindow> el objeto, deberá tener en cuenta cómo la compatibilidad con el registro en diario afecta al rendimiento de la aplicación. Para obtener más información, consulte [Información general sobre navegación](../app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>
## <a name="hit-testing-on-large-3d-surfaces"></a>Comprobación de visitas en superficies 3D de gran tamaño  
 La comprobación de visitas en superficies 3D de gran tamaño es una operación muy intensiva de rendimiento en términos de consumo de CPU. Esto es especialmente cierto cuando se anima la superficie 3D. Si no es necesario comprobar visitas en estas superficies, deshabilite la comprobación de visitas. Los objetos derivados pueden <xref:System.Windows.UIElement> deshabilitar las <xref:System.Windows.UIElement.IsHitTestVisible%2A> pruebas `false`de posicionación estableciendo la propiedad en .  
  
<a name="CompositionTarget_Rendering_Event"></a>
## <a name="compositiontargetrendering-event"></a>Evento CompositionTarget.Rendering  
 El <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> evento [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] provoca que se anime continuamente. Si usa este evento, desasócielo en cada oportunidad.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>
## <a name="avoid-using-scrollbarvisibilityauto"></a>Evitar usar ScrollBarVisibility=Auto  
 Siempre que sea <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> posible, `HorizontalScrollBarVisibility` evite `VerticalScrollBarVisibility` usar el valor de las propiedades y. Estas propiedades se <xref:System.Windows.Controls.RichTextBox> <xref:System.Windows.Controls.ScrollViewer>definen <xref:System.Windows.Controls.TextBox> para , , y <xref:System.Windows.Controls.ListBox> objetos, y como una propiedad adjunta para el objeto. En su <xref:System.Windows.Controls.ScrollBarVisibility> <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>lugar, establezca en , <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, o <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 El <xref:System.Windows.Controls.ScrollBarVisibility.Auto> valor está pensado para casos en los que el espacio es limitado y las barras de desplazamiento solo se deben mostrar cuando sea necesario. Por ejemplo, puede ser útil <xref:System.Windows.Controls.ScrollBarVisibility> usar <xref:System.Windows.Controls.ListBox> este valor con un de <xref:System.Windows.Controls.TextBox> 30 elementos en lugar de a con cientos de líneas de texto.  
  
<a name="FontCache"></a>
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Configurar el servicio de caché de fuente para reducir el tiempo de inicio  
 El servicio de caché de fuentes de WPFWPF comparte datos de fuente entre aplicaciones WPFWPF. La primera aplicación WPFWPF que ejecute inicia este servicio si el servicio aún no se está ejecutando. Si usa Windows Vista, puede establecer el servicio "Caché de fuentes 3.0.0.0" de Windows Presentation Foundation (WPF) de "Manual" (valor predeterminado) en "Automático (Inicio retrasado)" para reducir el tiempo de inicio inicial de las aplicaciones WPF.  
  
## <a name="see-also"></a>Consulte también

- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Recursos de aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Sugerencias y trucos para animaciones](../graphics-multimedia/animation-tips-and-tricks.md)
