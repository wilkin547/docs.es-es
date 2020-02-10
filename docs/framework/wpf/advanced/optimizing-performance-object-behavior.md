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
ms.openlocfilehash: 64e567cd28e9458b483b0963e0dedd924ad23bab
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094493"
---
# <a name="optimizing-performance-object-behavior"></a>Optimizar el rendimiento: Comportamiento de objetos
Entender el comportamiento intrínseco de los objetos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le ayudará a lograr un equilibrio correcto entre funcionalidad y rendimiento.  

<a name="Not_Removing_Event_Handlers"></a>   
## <a name="not-removing-event-handlers-on-objects-may-keep-objects-alive"></a>No quitar los controladores de eventos en objetos puede mantener los objetos activos  
 El delegado que un objeto pasa a su evento es realmente una referencia a ese objeto. Por lo tanto, los controladores de eventos pueden mantener los objetos activos durante más tiempo de lo esperado. Al realizar la limpieza de un objeto registrado para escuchar los eventos de un objeto, es esencial quitar ese delegado antes de liberar el objeto. Mantener activos objetos innecesarios aumenta el uso de memoria de la aplicación. Esto es especialmente cierto cuando el objeto es la raíz de un árbol lógico o un árbol visual.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] presenta un patrón de agente de escucha de evento débil para los eventos que pueden ser útiles en situaciones donde es difícil mantener el seguimiento de las relaciones de vigencia de objeto entre el origen y el agente de escucha. Algunos eventos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes usan este patrón. Si implementa objetos con eventos personalizados, este patrón puede resultarle de utilidad. Para obtener más información, consulte [Modelos de evento débil](weak-event-patterns.md).  
  
 Hay varias herramientas, como CLR Profiler y Visor de espacios de trabajo, que pueden proporcionar información sobre el uso de memoria de un proceso especificado. CLR Profiler incluye varias vistas muy útiles del perfil de asignación, incluido un histograma de tipos asignados, gráficos de asignación y llamadas, una línea de tiempo que muestra recolecciones de elementos no usados de varias generaciones y el estado resultante del montón administrado después de esas colecciones, y un árbol de llamadas que muestra las asignaciones por método y las cargas de ensamblado. Para más información, vea [Rendimiento](https://docs.microsoft.com/previous-versions/aa497289(v=msdn.10)).  
  
<a name="DPs_and_Objects"></a>   
## <a name="dependency-properties-and-objects"></a>Propiedades y objetos de dependencia  
 En general, el acceso a una propiedad de dependencia de un <xref:System.Windows.DependencyObject> no es más lento que el acceso a una propiedad de CLR. Aunque hay una pequeña sobrecarga de rendimiento para establecer un valor de propiedad, obtener un valor es tan rápido como obtener el valor de una propiedad de CLR. El desplazamiento de la pequeña sobrecarga de rendimiento es el hecho de que las propiedades de dependencia admiten características robustas, como el enlace de datos, la animación, la herencia y los estilos. Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Optimizaciones de DependencyProperty  
 Debe definir las propiedades de dependencia en la aplicación con mucho cuidado. Si el <xref:System.Windows.DependencyProperty> afecta solo a las opciones de metadatos de tipo de representación, en lugar de otras opciones de metadatos como <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, debe marcarla como tal invalidando sus metadatos. Para obtener más información sobre cómo invalidar u obtener los metadatos de las propiedades, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
 Puede ser más eficaz hacer que un controlador de cambio de propiedad invalide los pases de medición, organización y representación manualmente si todos los cambios de propiedad no afectan realmente a la medición, organización y representación. Por ejemplo, es posible que decida volver a representar un fondo solo cuando un valor sea mayor que un límite establecido. En este caso, el controlador de cambios de propiedades solo invalidará la representación cuando el valor supere el límite establecido.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Hacer que DependencyProperty sea heredable tiene consecuencias  
 De forma predeterminada, las propiedades de dependencia registradas no son heredables. Sin embargo, puede hacer explícitamente que una propiedad sea heredable. Aunque es una característica útil, convertir una propiedad a heredable afecta al rendimiento, ya que aumenta la cantidad de tiempo para la invalidación de propiedades.  
  
### <a name="use-registerclasshandler-carefully"></a>Usar RegisterClassHandler con cuidado  
 Aunque llamar a <xref:System.Windows.EventManager.RegisterClassHandler%2A> permite guardar el estado de la instancia, es importante tener en cuenta que se llama al controlador en cada instancia, lo que puede causar problemas de rendimiento. Use solo <xref:System.Windows.EventManager.RegisterClassHandler%2A> cuando la aplicación requiera que guarde el estado de la instancia.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Establecer el valor predeterminado para DependencyProperty durante el registro  
 Al crear una <xref:System.Windows.DependencyProperty> que requiera un valor predeterminado, establezca el valor usando los metadatos predeterminados que se pasan como un parámetro al método <xref:System.Windows.DependencyProperty.Register%2A> de la <xref:System.Windows.DependencyProperty>. Use esta técnica en lugar de establecer el valor de propiedad en un constructor o en cada instancia de un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Establecer el valor de PropertyMetadata mediante el Registro  
 Al crear un <xref:System.Windows.DependencyProperty>, tiene la opción de establecer el <xref:System.Windows.PropertyMetadata> mediante los métodos <xref:System.Windows.DependencyProperty.Register%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>. Aunque el objeto puede tener un constructor estático para llamar a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, no es la solución óptima y afectará al rendimiento. Para obtener el mejor rendimiento, establezca la <xref:System.Windows.PropertyMetadata> durante la llamada a <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## <a name="freezable-objects"></a>Objetos Freezable  
 Un <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos Estados: inmovilizado e inmovilizado. Inmovilizar objetos siempre que sea posible mejora el rendimiento de la aplicación y reduce su conjunto de trabajo. Para obtener más información, consulte [Información general sobre objetos Freezable](freezable-objects-overview.md).  
  
 Cada <xref:System.Windows.Freezable> tiene un evento <xref:System.Windows.Freezable.Changed> que se genera cada vez que cambia. Sin embargo, las notificaciones de cambio son costosas en términos de rendimiento de la aplicación.  
  
 Considere el siguiente ejemplo en el que cada <xref:System.Windows.Shapes.Rectangle> usa el mismo objeto <xref:System.Windows.Media.Brush>:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 De forma predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un controlador de eventos para el evento <xref:System.Windows.Freezable.Changed> del objeto <xref:System.Windows.Media.SolidColorBrush> con el fin de invalidar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto <xref:System.Windows.Shapes.Rectangle>. En este caso, cada vez que el <xref:System.Windows.Media.SolidColorBrush> tiene que activar su evento <xref:System.Windows.Freezable.Changed> se requiere invocar la función de devolución de llamada para cada <xref:System.Windows.Shapes.Rectangle>; la acumulación de estas invocaciones de función de devolución de llamada impone una penalización significativa en el rendimiento. Además, es muy intensivo para el rendimiento agregar y quitar controladores en este punto, ya que la aplicación deberá recorrer toda la lista para ello. Si el escenario de la aplicación nunca cambia el <xref:System.Windows.Media.SolidColorBrush>, se le cobrará el costo de mantener <xref:System.Windows.Freezable.Changed> controladores de eventos innecesariamente.  
  
 La inmovilización de un <xref:System.Windows.Freezable> puede mejorar su rendimiento, ya que ya no es necesario dedicar recursos al mantenimiento de las notificaciones de cambios. En la tabla siguiente se muestra el tamaño de un <xref:System.Windows.Media.SolidColorBrush> simple cuando su propiedad <xref:System.Windows.Freezable.IsFrozen%2A> está establecida en `true`, en comparación con cuando no lo está. Se supone que se aplica un pincel a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de diez objetos <xref:System.Windows.Shapes.Rectangle>.  
  
|**State**|**Tamaño**|  
|---------------|--------------|  
|<xref:System.Windows.Media.SolidColorBrush> inmovilizado|212 bytes|  
|<xref:System.Windows.Media.SolidColorBrush> no inmovilizado|972 bytes|  
  
 En el siguiente ejemplo de código se muestra este concepto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Los controladores modificados de objetos Freezable no inmovilizados pueden mantener los objetos activos  
 El delegado que un objeto pasa al evento <xref:System.Windows.Freezable.Changed> de un objeto <xref:System.Windows.Freezable> es realmente una referencia a ese objeto. Por lo tanto, los controladores de eventos <xref:System.Windows.Freezable.Changed> pueden mantener los objetos activos más tiempo del esperado. Al realizar la limpieza de un objeto registrado para escuchar el evento de <xref:System.Windows.Freezable.Changed> de un objeto <xref:System.Windows.Freezable>, es esencial quitar ese delegado antes de liberar el objeto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también enlaza <xref:System.Windows.Freezable.Changed> eventos internamente. Por ejemplo, todas las propiedades de dependencia que toman <xref:System.Windows.Freezable> como valor escucharán automáticamente <xref:System.Windows.Freezable.Changed> eventos. La propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, que toma un <xref:System.Windows.Media.Brush>, ilustra este concepto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 En la asignación de `myBrush` a `myRectangle.Fill`, se agregará al evento <xref:System.Windows.Freezable.Changed> del objeto <xref:System.Windows.Media.SolidColorBrush> un delegado que apunte de nuevo al objeto <xref:System.Windows.Shapes.Rectangle>. Esto significa que el código siguiente realmente no hace que `myRect` sea apto para la recolección de elementos no usados:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 En este caso `myBrush` sigue manteniendo `myRectangle` activo y volverá a llamar a él cuando desencadene su evento <xref:System.Windows.Freezable.Changed>. Tenga en cuenta que la asignación de `myBrush` a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de una nueva <xref:System.Windows.Shapes.Rectangle> simplemente agregará otro controlador de eventos a `myBrush`.  
  
 La manera recomendada de limpiar estos tipos de objetos es quitar el <xref:System.Windows.Media.Brush> de la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, que a su vez quitará el controlador de eventos <xref:System.Windows.Freezable.Changed>.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## <a name="user-interface-virtualization"></a>Virtualización de la interfaz de usuario  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona una variación del elemento <xref:System.Windows.Controls.StackPanel> que "virtualiza" automáticamente el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica que permite generar un subconjunto de objetos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel> (a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel>) calcula los elementos visibles y funciona con la <xref:System.Windows.Controls.ItemContainerGenerator> de un <xref:System.Windows.Controls.ItemsControl> (como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>) para crear solo elementos para elementos visibles.  
  
 Como optimización del rendimiento, los objetos visuales para estos elementos solo se generan o se mantienen activos si están visibles en pantalla. Cuando ya no están en el área visible del control, se pueden quitar los objetos visuales. Esto no se debe confundir con la virtualización de datos, donde los objetos de datos no existen en la colección local, sino que se transmiten según sea necesario.  
  
 En la tabla siguiente se muestra el tiempo transcurrido para agregar y representar 5000 elementos <xref:System.Windows.Controls.TextBlock> en una <xref:System.Windows.Controls.StackPanel> y una <xref:System.Windows.Controls.VirtualizingStackPanel>. En este escenario, las medidas representan el tiempo que transviene entre adjuntar una cadena de texto a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de un objeto <xref:System.Windows.Controls.ItemsControl> hasta el momento en que los elementos del panel muestran la cadena de texto.  
  
|**Panel de host**|**Tiempo de representación (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Consulte también

- [Optimizar el rendimiento de la aplicación WPF](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Recursos de aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
