---
title: "Optimizar el rendimiento: Otras recomendaciones | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "pinceles, rendimiento"
  - "objetos de pruebas de posicionamiento [WPF]"
  - "opacidad"
  - "ScrollBarVisibility (enumeración)"
  - "representar Terminal Services"
ms.assetid: d028cc65-7e97-4a4f-9859-929734eaf40d
caps.latest.revision: 20
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Optimizar el rendimiento: Otras recomendaciones
<a name="introduction"></a> En este tema se proporcionan recomendaciones de rendimiento además de las que se abordan en los temas de la sección [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md).  
  
 Este tema contiene las siguientes secciones:  
  
-   [Opacidad en los pinceles comparada con opacidad en los elementos](#Opacity)  
  
-   [Navegación hasta un objeto](#Navigation_Objects)  
  
-   [Pruebas de posicionamiento en superficies 3D de gran tamaño](#Hit_Testing)  
  
-   [Evento CompositionTarget.Rendering](#CompositionTarget_Rendering_Event)  
  
-   [Evitar el uso de ScrollBarVisibility\=Auto](#Avoid_Using_ScrollBarVisibility)  
  
-   [Configurar el servicio de almacenamiento en memoria caché de las fuentes para reducir el tiempo de inicio](#FontCache)  
  
<a name="Opacity"></a>   
## Opacidad en los pinceles comparada con opacidad en los elementos  
 Cuando se utiliza un objeto <xref:System.Windows.Media.Brush> para establecer la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> o <xref:System.Windows.Shapes.Shape.Stroke%2A> de un elemento, es mejor establecer el valor de <xref:System.Windows.Media.Brush.Opacity%2A?displayProperty=fullName> en lugar de la propiedad <xref:System.Windows.UIElement.Opacity%2A> del elemento.  Modificar la propiedad <xref:System.Windows.UIElement.Opacity%2A> de un elemento puede hacer que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cree una superficie temporal.  
  
<a name="Navigation_Objects"></a>   
## Navegación hasta un objeto  
 El objeto <xref:System.Windows.Navigation.NavigationWindow> se deriva de la clase <xref:System.Windows.Window> y la extiende aportando compatibilidad de navegación de contenido, gracias, principalmente, a la adición de <xref:System.Windows.Navigation.NavigationService> y del diario.  Puede actualizar el área cliente de <xref:System.Windows.Navigation.NavigationWindow> especificando un [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] o un objeto.  En el ejemplo siguiente se muestran ambos métodos:  
  
 [!code-csharp[Performance#PerformanceSnippet14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/TestNavigation.xaml.cs#performancesnippet14)]
 [!code-vb[Performance#PerformanceSnippet14](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/testnavigation.xaml.vb#performancesnippet14)]  
  
 Cada objeto <xref:System.Windows.Navigation.NavigationWindow> tiene un diario que graba el historial de navegación del usuario en esa ventana.  Uno de los propósitos del diario es permitir a los usuarios desandar sus pasos.  
  
 Cuando se navega mediante [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)], el diario almacena sólo la referencia al [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)].  Esto significa que cada vez que se vuelve a visitar la página, se reconstruye dinámicamente, lo que puede tardar tiempo según complejidad de la página.  En este caso, el costo de almacenamiento en el diario es bajo, pero el tiempo de reconstitución de la página es potencialmente alto.  
  
 Cuando se navega mediante un objeto, el diario almacena el árbol visual completo del objeto.  Esto significa que cada vez que vuelve a visitar la página, se representa inmediatamente sin tener que reconstruirla.  En este caso, el costo de almacenamiento en el diario es alto, pero el tiempo de reconstitución de la página es bajo.  
  
 Cuando se utiliza el objeto <xref:System.Windows.Navigation.NavigationWindow>, es preciso tener presente cómo afecta la compatibilidad con el diario al rendimiento de la aplicación.  Para obtener más información, consulte [Información general sobre navegación](../../../../docs/framework/wpf/app-development/navigation-overview.md).  
  
<a name="Hit_Testing"></a>   
## Pruebas de posicionamiento en superficies 3D de gran tamaño  
 Las pruebas de posicionamiento en superficies 3D de gran tamaño es una operación que afecta intensamente al rendimiento por lo que se refiere al consumo de CPU.  Esto se cumple especialmente cuando la superficie 3D se anima.  Deshabilite las pruebas de posicionamiento en estas superficies si no las necesita.  Los objetos que se derivan de <xref:System.Windows.UIElement> pueden deshabilitar las pruebas de posicionamiento estableciendo la propiedad <xref:System.Windows.UIElement.IsHitTestVisible%2A> en `false`.  
  
<a name="CompositionTarget_Rendering_Event"></a>   
## Evento CompositionTarget.Rendering  
 El evento <xref:System.Windows.Media.CompositionTarget.Rendering?displayProperty=fullName> hace que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se anime de manera continua.  Si utiliza este evento, desasócielo en cada oportunidad que se presente.  
  
<a name="Avoid_Using_ScrollBarVisibility"></a>   
## Evitar el uso de ScrollBarVisibility\=Auto  
 Siempre que sea posible, evite utilizar el valor <xref:System.Windows.Controls.ScrollBarVisibility?displayProperty=fullName> para las propiedades `HorizontalScrollBarVisibility` y `VerticalScrollBarVisibility`.  Estas propiedades se definen para los objetos <xref:System.Windows.Controls.RichTextBox>, <xref:System.Windows.Controls.ScrollViewer> y <xref:System.Windows.Controls.TextBox>, además de cómo propiedad adjunta del objeto <xref:System.Windows.Controls.ListBox>.  En su lugar, establezca <xref:System.Windows.Controls.ScrollBarVisibility> en <xref:System.Windows.Controls.ScrollBarVisibility>, <xref:System.Windows.Controls.ScrollBarVisibility> o <xref:System.Windows.Controls.ScrollBarVisibility>.  
  
 El valor <xref:System.Windows.Controls.ScrollBarVisibility> es para casos de espacio limitado, en que las barras de desplazamiento sólo deben mostrarse cuando se necesiten.  Por ejemplo, puede ser útil utilizar este valor de <xref:System.Windows.Controls.ScrollBarVisibility> con un control <xref:System.Windows.Controls.ListBox> de 30 elementos, en oposición a un control <xref:System.Windows.Controls.TextBox> con centenares de líneas de texto.  
  
<a name="FontCache"></a>   
## Configurar el servicio de almacenamiento en memoria caché de las fuentes para reducir el tiempo de inicio  
 El servicio [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Font Cache comparte los datos de fuentes entre las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  La primera aplicación de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] que se ejecuta inicia este servicio aún no está en ejecución.  Si utiliza [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)], puede establecer el servicio "[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] Font Cache 3.0.0.0" de "Manual" \(el valor predeterminado\) a "Automático \(inicio retrasado\)" para reducir el tiempo de inicio de las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)].  
  
## Vea también  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Sugerencias y trucos para animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-tips-and-tricks.md)