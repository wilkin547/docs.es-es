---
title: 'Optimizar el rendimiento: Recursos de aplicación'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 59b124c28ade0a6c5119b651ff935d460bf4516d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458560"
---
# <a name="optimizing-performance-application-resources"></a>Optimizar el rendimiento: Recursos de aplicación
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite compartir recursos de la aplicación para que pueda admitir una apariencia o un comportamiento coherentes en elementos de tipo similar. En este tema se proporcionan algunas recomendaciones en esta área que pueden ayudarle a mejorar el rendimiento de las aplicaciones.  
  
 Para más información sobre los recursos, vea [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
## <a name="sharing-resources"></a>Compartir recursos  
 Si la aplicación usa controles personalizados y define recursos en un <xref:System.Windows.ResourceDictionary> (o en un nodo de recursos XAML), se recomienda que defina los recursos en el nivel de objeto <xref:System.Windows.Application> o <xref:System.Windows.Window>, o bien que los defina en el tema predeterminado para los controles personalizados. La definición de recursos en la <xref:System.Windows.ResourceDictionary> de un control personalizado impone un impacto en el rendimiento para cada instancia de ese control. Por ejemplo, si tiene operaciones de pincel con un uso intensivo de rendimiento definidas como parte de la definición de recursos de un control personalizado y muchas instancias del control personalizado, el espacio de trabajo de la aplicación aumentará significativamente.  
  
 Para ilustrar este punto, tenga en cuenta lo siguiente. Supongamos que está desarrollando un juego de cartas mediante [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para la mayoría de los juegos de cartas, necesita tarjetas 52 con 52 caras diferentes. Decide implementar un control personalizado de tarjeta y se definen los pinceles 52 (cada uno representa una esfera de tarjeta) en los recursos del control personalizado de la tarjeta. En la aplicación principal, cree inicialmente 52 instancias de este control personalizado de tarjeta. Cada instancia del control personalizado de tarjeta genera 52 instancias de objetos de <xref:System.Windows.Media.Brush>, lo que proporciona un total de 52 * 52 <xref:System.Windows.Media.Brush> objetos en la aplicación. Al mover los pinceles fuera de los recursos de control personalizados de la tarjeta al nivel de objeto <xref:System.Windows.Application> o <xref:System.Windows.Window>, o al definirlos en el tema predeterminado para el control personalizado, se reduce el espacio de trabajo de la aplicación, ya que ahora está compartiendo los pinceles 52 entre 52 instancias del control de tarjeta.  
  
## <a name="sharing-a-brush-without-copying"></a>Compartir un pincel sin copiarlo  
 Si tiene varios elementos con el mismo <xref:System.Windows.Media.Brush> objeto, defina el pincel como un recurso y haga referencia a él, en lugar de definir el pincel insertado en XAML. Este método creará una instancia y la reutilizará, mientras que al definir los pinceles insertados en XAML se crea una nueva instancia para cada elemento.  
  
 En el ejemplo de marcado siguiente se muestra este punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Usar recursos estáticos siempre que sea posible  
 Un recurso estático proporciona un valor para cualquier atributo de propiedad XAML mediante la búsqueda de una referencia a un recurso ya definido. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de compilación.  
  
 Un recurso dinámico, por otro lado, creará una expresión temporal durante la compilación inicial y, por tanto, aplazará la búsqueda de recursos hasta que el valor de recurso solicitado sea realmente necesario para construir un objeto. El comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de ejecución, lo que impone un impacto en el rendimiento. Use recursos estáticos siempre que sea posible en la aplicación, usando recursos dinámicos solo cuando sea necesario.  
  
 En el ejemplo de marcado siguiente se muestra el uso de ambos tipos de recursos:  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vea también

- [Optimizar el rendimiento de la aplicación WPF](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamiento de objetos](optimizing-performance-object-behavior.md)
- [Text](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
