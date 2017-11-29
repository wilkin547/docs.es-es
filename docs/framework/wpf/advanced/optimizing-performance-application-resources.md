---
title: "Optimizar el rendimiento: Recursos de aplicación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ac462f3b49788fd909f9d9f4fc785db74704ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-application-resources"></a>Optimizar el rendimiento: Recursos de aplicación
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le permite compartir recursos de la aplicación para que pueda admitir una apariencia coherente o comportamiento a través de los elementos escritos de manera similar. Este tema proporciona algunas recomendaciones que aparecen en esta área que puede ayudar a mejora el rendimiento de las aplicaciones.  
  
 Para más información sobre los recursos, vea [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## <a name="sharing-resources"></a>Uso compartido de recursos  
 Si la aplicación utiliza controles personalizados y define recursos en un <xref:System.Windows.ResourceDictionary> (o nodo de recursos XAML), se recomienda que se puede definir los recursos en el <xref:System.Windows.Application> o <xref:System.Windows.Window> nivel de objeto o definirlas en el tema predeterminado para el controles personalizados. Definición de recursos en un control personalizado <xref:System.Windows.ResourceDictionary> afecta negativamente al rendimiento para cada instancia de ese control. Por ejemplo, si hay operaciones de pincel de rendimiento intensivo que se define como parte de la definición de recursos de un control personalizado y muchas instancias del control personalizado, espacio de trabajo de la aplicación aumentará significativamente.  
  
 Para ilustrar este punto, tenga en cuenta lo siguiente. Supongamos que está desarrollando un juego de tarjeta utilizando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para la mayoría de los juegos de cartas, necesita 52 cartas con 52 caras diferentes. Se decide implementar un control personalizado de tarjeta y definen 52 pinceles (cada uno representa una cara de carta) en los recursos de su control personalizado de la tarjeta. En la aplicación principal, crea inicialmente 52 instancias de este control personalizado de la tarjeta. Cada instancia del control personalizado de tarjeta genera 52 instancias de <xref:System.Windows.Media.Brush> objetos, que le da un total de 52 * 52 <xref:System.Windows.Media.Brush> objetos de la aplicación. Moviendo los pinceles de los recursos de control personalizado de la tarjeta a la <xref:System.Windows.Application> o <xref:System.Windows.Window> nivel de objeto o definiéndolos en el tema predeterminado del control personalizado, reducir el espacio de trabajo de la aplicación, ya que ahora se compartirá los 52 pinceles entre las 52 instancias del control de ficha.  
  
## <a name="sharing-a-brush-without-copying"></a>Compartir un pincel sin copiar  
 Si tiene varios elementos con el mismo <xref:System.Windows.Media.Brush> objeto, defina el pincel como un recurso y hacer referencia a él, en lugar de definir el pincel insertado en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Este método creará una instancia y volver a usarla, mientras que definir los pinceles insertados en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] crea una nueva instancia para cada elemento.  
  
 El ejemplo de marcado siguiente ilustra este punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Utilizar recursos estáticos siempre que sea posible  
 Un recurso estático proporciona un valor para cualquier atributo de propiedad XAML buscando una referencia a un recurso ya definido. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de compilación.  
  
 Un recurso dinámico, por otro lado, creará una expresión temporal durante la compilación inicial y, por tanto, aplazar la consulta de recursos hasta que el valor de recurso solicitado se necesite realmente para construir un objeto. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de ejecución, lo que afecta negativamente al rendimiento. Utilice recursos estáticos siempre que sea posible en su aplicación, utilice los recursos dinámicos solo cuando sea necesario.  
  
 El ejemplo de marcado siguiente muestra el uso de ambos tipos de recursos:  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamiento de objetos](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
