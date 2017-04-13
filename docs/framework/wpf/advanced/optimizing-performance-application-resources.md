---
title: "Optimizar el rendimiento: Recursos de aplicaci&#243;n | Microsoft Docs"
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
  - "recursos de la aplicación, rendimiento"
  - "pinceles, rendimiento"
  - "recursos, rendimiento"
  - "compartir pinceles sin copiar"
  - "compartir recursos"
  - "recursos estáticos"
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Optimizar el rendimiento: Recursos de aplicaci&#243;n
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite compartir los recursos de aplicación, a fin de permitirle utilizar una apariencia o un comportamiento coherentes en elementos de tipos parecidos.  En este tema se proporcionan algunas recomendaciones en este sentido que pueden ayudarle a mejorar el rendimiento de sus aplicaciones.  
  
 Para obtener más información sobre recursos, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## Compartir recursos  
 Si la aplicación utiliza controles personalizados y define recursos en un diccionario de recursos \(<xref:System.Windows.ResourceDictionary>\) \(o nodo de recursos XAML\), se recomienda que defina los recursos en el nivel del objeto <xref:System.Windows.Application> o <xref:System.Windows.Window>, o bien que los defina en el tema predeterminado para los controles personalizados.  Definir los recursos en un control <xref:System.Windows.ResourceDictionary> personalizado afecta negativamente al rendimiento para cada instancia de ese control.  Por ejemplo, si ha realizado operaciones de pincel que deterioran el rendimiento definidas como parte de la definición de recurso de un control personalizado y muchas instancias del control personalizado, el espacio de trabajo de la aplicación aumentará significativamente.  
  
 Para ilustrar este punto, estudie lo siguiente.  Supongamos que está programando un juego de cartas mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para la mayoría de los juegos de cartas, necesita 52 cartas con 52 caras diferentes.  Decide implementar un control de carta personalizado y definen 52 pinceles \(cada uno de ellos representa una cara de carta\) en los recursos del control de carta personalizado.  En la aplicación principal, crea inicialmente 52 instancias del control de carta personalizado.  Cada instancia del control de carta personalizado genera 52 instancias de objetos <xref:System.Windows.Media.Brush>, con lo que tenemos un total de 52 \* 52 objetos <xref:System.Windows.Media.Brush> en la aplicación.  Si saca los pinceles de los recursos del control personalizado y los coloca en el nivel del objeto <xref:System.Windows.Application> o <xref:System.Windows.Window>, o los define en el tema predeterminado del control personalizado, reducirá el espacio de trabajo de la aplicación, puesto que ahora compartirá los 52 pinceles entre las 52 instancias del control de carta.  
  
## Compartir un pincel sin copiar  
 Si tiene varios elementos que utilizan el mismo objeto <xref:System.Windows.Media.Brush>, defina el pincel como un recurso y haga referencia a él, en lugar de definir el pincel insertado en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)].  Este método creará una instancia y la reutilizará, mientras que al definir los pinceles insertados en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)], se crea una nueva instancia para cada elemento.  
  
 En el ejemplo de marcado siguiente se ilustra este punto:  
  
 [!code-xml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## Utilizar recursos estáticos siempre que sea posible  
 Un recurso estático proporciona un valor para cualquier atributo de propiedad XAML buscando una referencia a un recurso ya definido.  El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de compilación.  
  
 Un recurso dinámico, por otro lado, creará una expresión temporal durante la compilación inicial y, de este modo, diferirá la consulta de recursos hasta que el valor de recurso solicitado se necesite realmente para construir un objeto.  El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de ejecución, que afecta negativamente al rendimiento.  Siempre que sea posible, utilice recursos estáticos en la aplicación, y utilice los recursos dinámicos únicamente cuando sea necesario.  
  
 En el ejemplo de marcado siguiente se muestra el uso de ambos tipos de recursos:  
  
 [!code-xml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)