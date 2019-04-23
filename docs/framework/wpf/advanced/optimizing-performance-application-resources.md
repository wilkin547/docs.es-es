---
title: 'Optimizar el rendimiento: Recursos de la aplicación'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 362d0f0fd3282365e5e05dcd43c49a9fd2ddc9a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139430"
---
# <a name="optimizing-performance-application-resources"></a>Optimizar el rendimiento: Recursos de la aplicación
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le permite compartir recursos de la aplicación para que pueda admitir un comportamiento o aspecto coherente entre los elementos de tipo similar. Este tema se proporcionan algunas recomendaciones de esta área que puede ayudarle a mejoran el rendimiento de las aplicaciones.  
  
 Para más información sobre los recursos, vea [Recursos XAML](xaml-resources.md).  
  
## <a name="sharing-resources"></a>Uso compartido de recursos  
 Si la aplicación utiliza controles personalizados y define los recursos en un <xref:System.Windows.ResourceDictionary> (o nodo de recursos XAML), se recomienda que se puede definir los recursos en el <xref:System.Windows.Application> o <xref:System.Windows.Window> objeto de nivel, o bien definirlos en el tema predeterminado para el controles personalizados. Definición de recursos en un control personalizado <xref:System.Windows.ResourceDictionary> afecta negativamente al rendimiento de cada instancia de ese control. Por ejemplo, si tiene operaciones de rendimiento intensivo pincel definidas como parte de la definición de recursos de un control personalizado y el número de instancias del control personalizado, espacio de trabajo de la aplicación aumentará significativamente.  
  
 Para ilustrar este punto, considere lo siguiente. Supongamos que está desarrollando un juego de tarjeta con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para la mayoría de los juegos de cartas, necesita 52 cartas con 52 caras diferentes. Decide implementar un control personalizado de la tarjeta y definir 52 pinceles (cada uno representa una carta cara) en los recursos de su control personalizado de la tarjeta. En la aplicación principal, crear inicialmente 52 instancias de este control personalizado de la tarjeta. Cada instancia del control personalizado tarjeta genera 52 instancias de <xref:System.Windows.Media.Brush> objetos, que le da un total de 52 * 52 <xref:System.Windows.Media.Brush> objetos en la aplicación. Moviendo los pinceles de los recursos del control personalizado a la <xref:System.Windows.Application> o <xref:System.Windows.Window> nivel de objeto o que definirlas en el tema predeterminado para el control personalizado, reducir el espacio de trabajo de la aplicación, ya que ahora están compartiendo el 52 pinceles entre las 52 instancias del control de tarjeta.  
  
## <a name="sharing-a-brush-without-copying"></a>Compartir un pincel sin copiar  
 Si tiene varios elementos con el mismo <xref:System.Windows.Media.Brush> objeto, definir el pincel como un recurso y hacer referencia a él, en lugar de definir el pincel insertado en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Este método creará una instancia y volver a usarla, mientras que definir pinceles alineado en [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] crea una nueva instancia para cada elemento.  
  
 Ejemplo de marcado siguiente ilustra este punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Usar recursos estáticos siempre que sea posible  
 Un recurso estático proporciona un valor para cualquier atributo de propiedad XAML buscando una referencia a un recurso ya definido. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de compilación.  
  
 Un recurso dinámico, por otro lado, creará una expresión temporal durante la compilación inicial y, por tanto, aplazar la consulta de recursos hasta que el valor del recurso solicitado sea realmente necesario para construir un objeto. Comportamiento de búsqueda de ese recurso es análogo a la búsqueda de tiempo de ejecución, que afecta negativamente al rendimiento. Usar recursos estáticos siempre que sea posible en la aplicación con los recursos dinámicos solo cuando sea necesario.  
  
 Ejemplo de marcado siguiente muestra el uso de ambos tipos de recursos:  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vea también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
