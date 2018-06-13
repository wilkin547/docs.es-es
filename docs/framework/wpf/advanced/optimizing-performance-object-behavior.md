---
title: 'Optimizar el rendimiento: Comportamiento de objetos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- user interface virtualization [WPF]
- dependency properties [WPF], performance
- event handlers [WPF]
- object performance considerations [WPF]
- Freezable objects [WPF], performance
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
ms.openlocfilehash: 2e1f56dec87de7a22aa8a0bfefe84222d74ba085
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549222"
---
# <a name="optimizing-performance-object-behavior"></a>Optimizar el rendimiento: Comportamiento de objetos
Entender el comportamiento intrínseco de los objetos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le ayudará a lograr un equilibrio correcto entre funcionalidad y rendimiento.  
  

  
<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>No quitar los controladores de eventos en objetos puede mantener los objetos activos  
 El delegado que un objeto pasa a su evento es realmente una referencia a ese objeto. Por lo tanto, los controladores de eventos pueden mantener los objetos activos durante más tiempo de lo esperado. Al realizar la limpieza de un objeto registrado para escuchar los eventos de un objeto, es esencial quitar ese delegado antes de liberar el objeto. Mantener activos objetos innecesarios aumenta el uso de memoria de la aplicación. Esto es especialmente cierto cuando el objeto es la raíz de un árbol lógico o un árbol visual.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta un patrón de agente de escucha de evento débil para los eventos que pueden ser útiles en situaciones donde es difícil mantener el seguimiento de las relaciones de vigencia de objeto entre el origen y el agente de escucha. Algunos eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes usan este patrón. Si implementa objetos con eventos personalizados, este patrón puede resultarle de utilidad. Para obtener más información, consulte [Modelos de evento débil](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
 Hay varias herramientas, como CLR Profiler y Visor de espacios de trabajo, que pueden proporcionar información sobre el uso de memoria de un proceso especificado. CLR Profiler incluye varias vistas muy útiles del perfil de asignación, incluido un histograma de tipos asignados, gráficos de asignación y llamadas, una línea de tiempo que muestra recolecciones de elementos no usados de varias generaciones y el estado resultante del montón administrado después de esas colecciones, y un árbol de llamadas que muestra las asignaciones por método y las cargas de ensamblado. Para obtener más información, consulte [Centro para desarrolladores de .NET Framework](http://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Propiedades y objetos de dependencia  
 En general, obtener acceso a una propiedad de dependencia de un <xref:System.Windows.DependencyObject> no es más lento que el acceso a un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] propiedad. Aunque hay una pequeña sobrecarga de rendimiento para establecer un valor de propiedad, obtener un valor es tan rápido como obtener el valor de una propiedad [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]. El desplazamiento de la pequeña sobrecarga de rendimiento es el hecho de que las propiedades de dependencia admiten características robustas, como el enlace de datos, la animación, la herencia y los estilos. Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Optimizaciones de DependencyProperty  
 Debe definir las propiedades de dependencia en la aplicación con mucho cuidado. Si su <xref:System.Windows.DependencyProperty> afecta solo representan las opciones de metadatos de tipo, en lugar de otras opciones de metadatos como <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, debe marcar como tal invalidando sus metadatos. Para obtener más información sobre cómo invalidar u obtener los metadatos de las propiedades, consulte [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Puede ser más eficaz hacer que un controlador de cambio de propiedad invalide los pases de medición, organización y representación manualmente si todos los cambios de propiedad no afectan realmente a la medición, organización y representación. Por ejemplo, es posible que decida volver a representar un fondo solo cuando un valor sea mayor que un límite establecido. En este caso, el controlador de cambios de propiedades solo invalidará la representación cuando el valor supere el límite establecido.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Hacer que DependencyProperty sea heredable tiene consecuencias  
 De forma predeterminada, las propiedades de dependencia registradas no son heredables. Sin embargo, puede hacer explícitamente que una propiedad sea heredable. Aunque es una característica útil, convertir una propiedad a heredable afecta al rendimiento, ya que aumenta la cantidad de tiempo para la invalidación de propiedades.  
  
### <a name="use-registerclasshandler-carefully"></a>Usar RegisterClassHandler con cuidado  
 Mientras se llama <xref:System.Windows.EventManager.RegisterClassHandler%2A> le permite guardar el estado de la instancia, es importante tener en cuenta que se llama al controlador en cada instancia, lo que puede provocar problemas de rendimiento. Usar solo <xref:System.Windows.EventManager.RegisterClassHandler%2A> cuando la aplicación requiere que guarde el estado de la instancia.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Establecer el valor predeterminado para DependencyProperty durante el registro  
 Al crear un <xref:System.Windows.DependencyProperty> que requiere un valor predeterminado, establezca el valor mediante los metadatos predeterminados que se pasa como un parámetro a la <xref:System.Windows.DependencyProperty.Register%2A> método de la <xref:System.Windows.DependencyProperty>. Use esta técnica en lugar de establecer el valor de propiedad en un constructor o en cada instancia de un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Establecer el valor de PropertyMetadata mediante el Registro  
 Al crear un <xref:System.Windows.DependencyProperty>, tiene la opción de configuración de la <xref:System.Windows.PropertyMetadata> utilizando la <xref:System.Windows.DependencyProperty.Register%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> métodos. Aunque el objeto podría tener un constructor estático para llamar a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, esto no es la solución óptima y afectará al rendimiento. Para obtener el mejor rendimiento, establezca la <xref:System.Windows.PropertyMetadata> durante la llamada a <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Objetos Freezable  
 A <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: no inmovilizado e inmovilizado. Inmovilizar objetos siempre que sea posible mejora el rendimiento de la aplicación y reduce su conjunto de trabajo. Para obtener más información, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Cada <xref:System.Windows.Freezable> tiene un <xref:System.Windows.Freezable.Changed> evento que se desencadena cuando cambia. Sin embargo, las notificaciones de cambio son costosas en términos de rendimiento de la aplicación.  
  
 Considere el ejemplo siguiente, donde cada <xref:System.Windows.Shapes.Rectangle> utiliza la misma <xref:System.Windows.Media.Brush> objeto:  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un controlador de eventos para el <xref:System.Windows.Media.SolidColorBrush> del objeto <xref:System.Windows.Freezable.Changed> eventos con el fin de invalidar la <xref:System.Windows.Shapes.Rectangle> del objeto <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad. En este caso, cada vez que la <xref:System.Windows.Media.SolidColorBrush> tiene que activar su <xref:System.Windows.Freezable.Changed> evento es necesario para invocar la función de devolución de llamada para cada <xref:System.Windows.Shapes.Rectangle>, la acumulación de estas llamadas de función de devolución de llamada imponer una penalización de rendimiento significativas. Además, es muy intensivo para el rendimiento agregar y quitar controladores en este punto, ya que la aplicación deberá recorrer toda la lista para ello. Si su escenario de aplicación nunca cambia el <xref:System.Windows.Media.SolidColorBrush>, estará pagando el costo de mantenimiento <xref:System.Windows.Freezable.Changed> controladores de eventos innecesariamente.  
  
 Inmovilizar un <xref:System.Windows.Freezable> puede mejorar su rendimiento, porque ya no es necesario dedicar recursos a mantener las notificaciones de cambio. La siguiente tabla muestra el tamaño de un sencillo <xref:System.Windows.Media.SolidColorBrush> cuando su <xref:System.Windows.Freezable.IsFrozen%2A> propiedad está establecida en `true`en comparación con cuando no es. Esto supone aplicar un pincel para el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de diez <xref:System.Windows.Shapes.Rectangle> objetos.  
  
|**Estado**|**Size**|  
|---------------|--------------|  
|Inmovilizado <xref:System.Windows.Media.SolidColorBrush>|212 bytes|  
|Inmovilizado no <xref:System.Windows.Media.SolidColorBrush>|972 bytes|  
  
 En el siguiente ejemplo de código se muestra este concepto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Los controladores modificados de objetos Freezable no inmovilizados pueden mantener los objetos activos  
 El delegado que pasa un objeto a un <xref:System.Windows.Freezable> del objeto <xref:System.Windows.Freezable.Changed> eventos es una referencia a ese objeto. Por lo tanto, <xref:System.Windows.Freezable.Changed> controladores de eventos pueden mantener los objetos activos durante más tiempo de espera. Al realizar una limpieza de un objeto que se ha registrado para que escuche un <xref:System.Windows.Freezable> del objeto <xref:System.Windows.Freezable.Changed> eventos, es fundamental para quitar ese delegado antes de liberar el objeto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también enlaza <xref:System.Windows.Freezable.Changed> eventos internamente. Por ejemplo, todas las propiedades de dependencia que toman <xref:System.Windows.Freezable> como un valor escucharán <xref:System.Windows.Freezable.Changed> eventos automáticamente. El <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad, que toma un <xref:System.Windows.Media.Brush>, se muestra este concepto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 En la asignación de `myBrush` a `myRectangle.Fill`, un delegado que apunta hacia la <xref:System.Windows.Shapes.Rectangle> objeto se agregará a la <xref:System.Windows.Media.SolidColorBrush> del objeto <xref:System.Windows.Freezable.Changed> eventos. Esto significa que el código siguiente realmente no hace que `myRect` sea apto para la recolección de elementos no usados:  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 En este caso `myBrush` se mantiene `myRectangle` activo y volverá a llamar a ella cuando se desencadena su <xref:System.Windows.Freezable.Changed> eventos. Tenga en cuenta que asignar `myBrush` a la <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad de un nuevo <xref:System.Windows.Shapes.Rectangle> simplemente agregará otro controlador de eventos para `myBrush`.  
  
 La manera recomendada para limpiar estos tipos de objetos es quitar el <xref:System.Windows.Media.Brush> desde el <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad, lo que a su vez se quitará el <xref:System.Windows.Freezable.Changed> controlador de eventos.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Virtualización de la interfaz de usuario  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] También proporciona una variación de la <xref:System.Windows.Controls.StackPanel> elemento que "virtualiza" automáticamente el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica que permite generar un subconjunto de objetos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel> (a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel>) calcula los elementos visibles y funciona con la <xref:System.Windows.Controls.ItemContainerGenerator> desde una <xref:System.Windows.Controls.ItemsControl> (como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) sólo crear elementos para elementos visibles.  
  
 Como optimización del rendimiento, los objetos visuales para estos elementos solo se generan o se mantienen activos si están visibles en pantalla. Cuando ya no están en el área visible del control, se pueden quitar los objetos visuales. Esto no se debe confundir con la virtualización de datos, donde los objetos de datos no existen en la colección local, sino que se transmiten según sea necesario.  
  
 La siguiente tabla muestra el tiempo transcurrido, agregar y representar 5000 <xref:System.Windows.Controls.TextBlock> elementos a un <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.VirtualizingStackPanel>. En este escenario, las mediciones representan el tiempo transcurrido entre adjuntar una cadena de texto a la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad de un <xref:System.Windows.Controls.ItemsControl> objeto a la hora cuando los elementos de panel muestran la cadena de texto.  
  
|**Panel de host**|**Tiempo de representación (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Imágenes y gráficos 2D](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Recursos de la aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [Texto](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
