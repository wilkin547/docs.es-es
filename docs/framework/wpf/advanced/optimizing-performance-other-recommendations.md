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
ms.openlocfilehash: 3ea776dcb1b8633922aafca31821d367a11260f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-other-recommendations"></a>Optimizar el rendimiento: Otras recomendaciones
<a name="introduction"></a> En este tema se proporcionan recomendaciones de rendimiento, además de las que se incluyen en los temas de la sección [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md).  
  
 Este tema contiene las siguientes secciones:  
  
-   [Opacidad en pinceles frente a opacidad en elementos](#Opacity)  
  
-   [Navegación al objeto](#Navigation_Objects)  
  
-   [Comprobación de visitas en superficies 3D de gran tamaño](#Hit_Testing)  
  
-   [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
-   [Evitar usar ScrollBarVisibility=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Configurar el servicio de caché de fuente para reducir el tiempo de inicio](#FontCache)  
  
<a name="Opacity"></a>   
## <a name="opacity-on-brushes-versus-opacity-on-elements"></a>Opacidad en pinceles frente a opacidad en elementos  
 Cuando se usa un <xref:System.Windows.Media.Brush> para establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> o <xref:System.Windows.Shapes.Shape.Stroke%2A> de un elemento, es mejor establecer el <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=nameWithType> valor en lugar de la configuración del elemento <xref:System.Windows.UIElement.Opacity%2A> propiedad. Modificar un elemento <xref:System.Windows.UIElement.Opacity%2A> propiedad puede provocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] para crear una superficie temporal.  
  
<a name="Navigation_Objects"></a>   
## <a name="navigation-to-object"></a>Navegación al objeto  
 El <xref:System.Windows.Navigation.NavigationWindow> objeto deriva de <xref:System.Windows.Window> y lo extiende con compatibilidad de navegación de contenido, principalmente agregando <xref:System.Windows.Navigation.NavigationService> y el diario. Puede actualizar el área de cliente de <xref:System.Windows.Navigation.NavigationWindow> especificando un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] o un objeto. En el ejemplo siguiente se muestran ambos métodos:  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Cada <xref:System.Windows.Navigation.NavigationWindow> objeto tiene un diario que registra el historial de navegación del usuario en esa ventana. Uno de los propósitos del diario es permitir que los usuarios vuelvan sobre sus pasos.  
  
 Cuando se navega mediante un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], el diario solo almacena la referencia [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]. Esto significa que, cada vez que vuelve a visitar la página, se reconstruye dinámicamente, lo que puede llevar mucho tiempo según la complejidad de la página. En este caso, el costo de almacenamiento del diario es bajo, pero el tiempo para reconstituir la página es potencialmente alto.  
  
 Al navegar con un objeto, el diario almacena todo el árbol visual del objeto. Esto significa que, cada vez que vuelve a la página, se representa inmediatamente sin tener que reconstruirla. En este caso, el costo de almacenamiento del diario es alto, pero el tiempo para reconstituir la página es bajo.  
  
 Cuando se usa el <xref:System.Windows.Navigation.NavigationWindow> de objeto, debe tener en cuenta cómo la compatibilidad de registro en diario afecta al rendimiento de la aplicación. Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## <a name="hit-testing-on-large-3d-surfaces"></a>Comprobación de visitas en superficies 3D de gran tamaño  
 La comprobación de visitas en superficies 3D de gran tamaño es una operación muy intensiva de rendimiento en términos de consumo de CPU. Esto es especialmente cierto cuando se anima la superficie 3D. Si no es necesario comprobar visitas en estas superficies, deshabilite la comprobación de visitas. Objetos que se derivan de <xref:System.Windows.UIElement> puede deshabilitar las pruebas de posicionamiento estableciendo la <xref:System.Windows.UIElement.IsHitTestVisible%2A> propiedad `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## <a name="compositiontargetrendering-event"></a>Evento CompositionTarget.Rendering  
 El <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=nameWithType> provoca eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] anime de manera continua. Si usa este evento, desasócielo en cada oportunidad.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## <a name="avoid-using-scrollbarvisibilityauto"></a>Evitar usar ScrollBarVisibility=Auto  
 Siempre que sea posible, evite utilizar el <xref:System.Windows.Controls.ScrollBarVisibility.Auto?displayProperty=nameWithType> valor para el `HorizontalScrollBarVisibility` y `VerticalScrollBarVisibility` propiedades. Estas propiedades se definen para <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer>, y <xref:System.Windows.Controls.TextBox> objetos y como una propiedad adjunta para la <xref:System.Windows.Controls.ListBox> objeto. En su lugar, establezca <xref:System.Windows.Controls.ScrollBarVisibility> a <xref:System.Windows.Controls.ScrollBarVisibility.Disabled>, <xref:System.Windows.Controls.ScrollBarVisibility.Hidden>, o <xref:System.Windows.Controls.ScrollBarVisibility.Visible>.  
  
 El <xref:System.Windows.Controls.ScrollBarVisibility.Auto> valor está pensado para casos al espacio es limitado y solo se deben mostrar las barras de desplazamiento cuando sea necesario. Por ejemplo, puede ser útil usar esto <xref:System.Windows.Controls.ScrollBarVisibility> valor con un <xref:System.Windows.Controls.ListBox> de 30 elementos en contraposición a un <xref:System.Windows.Controls.TextBox> con cientos de líneas de texto.  
  
<a name="FontCache"></a>   
## <a name="configure-font-cache-service-to-reduce-start-up-time"></a>Configurar el servicio de caché de fuente para reducir el tiempo de inicio  
 El servicio de caché de fuente [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] comparte los datos de fuente entre aplicaciones [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]. La primera aplicación [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que ejecuta inicia este servicio, si este no se está ejecutando. Si utilizas [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], puede establecer el servicio "Windows Presentation Foundation (WPF) Font Cache 3.0.0.0" desde "Manual" (predeterminado) en "Automático (inicio Delayed)" para reducir el tiempo de inicio inicial de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] las aplicaciones.  
  
## <a name="see-also"></a>Vea también  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Sugerencias y trucos para animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)
