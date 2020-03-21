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
ms.openlocfilehash: 67184db7fc1459e83ac7b1e6ff09ef56e43f0ca4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187077"
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
 En general, tener acceso <xref:System.Windows.DependencyObject> a una propiedad de dependencia de a no es más lento que tener acceso a una propiedad CLR. Aunque hay una pequeña sobrecarga de rendimiento para establecer un valor de propiedad, obtener un valor es tan rápido como obtener el valor de una propiedad CLR. El desplazamiento de la pequeña sobrecarga de rendimiento es el hecho de que las propiedades de dependencia admiten características robustas, como el enlace de datos, la animación, la herencia y los estilos. Para obtener más información sobre las propiedades de dependencia, vea [Información general sobre las propiedades de dependencia](dependency-properties-overview.md).  
  
### <a name="dependencyproperty-optimizations"></a>Optimizaciones de DependencyProperty  
 Debe definir las propiedades de dependencia en la aplicación con mucho cuidado. Si <xref:System.Windows.DependencyProperty> solo afecta a las opciones de metadatos <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>de tipo de representación, en lugar de otras opciones de metadatos como , debe marcarlo como tal reemplazando sus metadatos. Para obtener más información sobre cómo invalidar u obtener los metadatos de las propiedades, consulte [Metadatos de las propiedades de dependencia](dependency-property-metadata.md).  
  
 Puede ser más eficaz hacer que un controlador de cambio de propiedad invalide los pases de medición, organización y representación manualmente si todos los cambios de propiedad no afectan realmente a la medición, organización y representación. Por ejemplo, es posible que decida volver a representar un fondo solo cuando un valor sea mayor que un límite establecido. En este caso, el controlador de cambios de propiedades solo invalidará la representación cuando el valor supere el límite establecido.  
  
### <a name="making-a-dependencyproperty-inheritable-is-not-free"></a>Hacer que DependencyProperty sea heredable tiene consecuencias  
 De forma predeterminada, las propiedades de dependencia registradas no son heredables. Sin embargo, puede hacer explícitamente que una propiedad sea heredable. Aunque es una característica útil, convertir una propiedad a heredable afecta al rendimiento, ya que aumenta la cantidad de tiempo para la invalidación de propiedades.  
  
### <a name="use-registerclasshandler-carefully"></a>Usar RegisterClassHandler con cuidado  
 Si <xref:System.Windows.EventManager.RegisterClassHandler%2A> bien la llamada le permite guardar el estado de la instancia, es importante tener en cuenta que se llama al controlador en cada instancia, lo que puede causar problemas de rendimiento. Utilícelo <xref:System.Windows.EventManager.RegisterClassHandler%2A> solo cuando la aplicación requiera que guarde el estado de la instancia.  
  
### <a name="set-the-default-value-for-a-dependencyproperty-during-registration"></a>Establecer el valor predeterminado para DependencyProperty durante el registro  
 Al crear <xref:System.Windows.DependencyProperty> un valor predeterminado que requiere un valor predeterminado, establezca <xref:System.Windows.DependencyProperty.Register%2A> el valor <xref:System.Windows.DependencyProperty>utilizando los metadatos predeterminados pasados como parámetro al método del archivo . Use esta técnica en lugar de establecer el valor de propiedad en un constructor o en cada instancia de un elemento.  
  
### <a name="set-the-propertymetadata-value-using-register"></a>Establecer el valor de PropertyMetadata mediante el Registro  
 Al crear <xref:System.Windows.DependencyProperty>un , tiene la <xref:System.Windows.PropertyMetadata> opción <xref:System.Windows.DependencyProperty.Register%2A> de <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> establecer el uso de los métodos o. Aunque el objeto podría tener <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>un constructor estático para llamar , esta no es la solución óptima y afectará al rendimiento. Para obtener el <xref:System.Windows.PropertyMetadata> mejor rendimiento, <xref:System.Windows.DependencyProperty.Register%2A>establezca durante la llamada en .  
  
<a name="Freezable_Objects"></a>
## <a name="freezable-objects"></a>Objetos Freezable  
 A <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: unfrozen y frozen. Inmovilizar objetos siempre que sea posible mejora el rendimiento de la aplicación y reduce su conjunto de trabajo. Para obtener más información, consulte [Información general sobre objetos Freezable](freezable-objects-overview.md).  
  
 Cada <xref:System.Windows.Freezable> uno <xref:System.Windows.Freezable.Changed> tiene un evento que se genera cada vez que cambia. Sin embargo, las notificaciones de cambio son costosas en términos de rendimiento de la aplicación.  
  
 Considere el siguiente ejemplo <xref:System.Windows.Shapes.Rectangle> en <xref:System.Windows.Media.Brush> el que cada uno utiliza el mismo objeto:  
  
 [!code-csharp[Performance#PerformanceSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 De forma [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] predeterminada, proporciona <xref:System.Windows.Media.SolidColorBrush> un controlador <xref:System.Windows.Freezable.Changed> de eventos para <xref:System.Windows.Shapes.Rectangle> el evento <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto con el fin de invalidar la propiedad del objeto. En este caso, <xref:System.Windows.Media.SolidColorBrush> cada vez <xref:System.Windows.Freezable.Changed> que tiene que desencadenar su evento <xref:System.Windows.Shapes.Rectangle>es necesario invocar la función de devolución de llamada para cada uno: la acumulación de estas invocaciones de función de devolución de llamada imponen una penalización de rendimiento significativa. Además, es muy intensivo para el rendimiento agregar y quitar controladores en este punto, ya que la aplicación deberá recorrer toda la lista para ello. Si el escenario de <xref:System.Windows.Media.SolidColorBrush>la aplicación nunca cambia <xref:System.Windows.Freezable.Changed> el , pagará el costo de mantener los controladores de eventos innecesariamente.  
  
 Congelar un <xref:System.Windows.Freezable> puede mejorar su rendimiento, ya que ya no necesita gastar recursos en el mantenimiento de notificaciones de cambio. La tabla siguiente muestra el <xref:System.Windows.Media.SolidColorBrush> tamaño <xref:System.Windows.Freezable.IsFrozen%2A> de un `true`simple cuando su propiedad se establece en , en comparación con cuando no lo es. Esto supone aplicar un pincel <xref:System.Windows.Shapes.Shape.Fill%2A> a la <xref:System.Windows.Shapes.Rectangle> propiedad de diez objetos.  
  
|**Estado**|**Tamaño**|  
|---------------|--------------|  
|Congelado<xref:System.Windows.Media.SolidColorBrush>|212 bytes|  
|No congelado<xref:System.Windows.Media.SolidColorBrush>|972 bytes|  
  
 En el siguiente ejemplo de código se muestra este concepto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### <a name="changed-handlers-on-unfrozen-freezables-may-keep-objects-alive"></a>Los controladores modificados de objetos Freezable no inmovilizados pueden mantener los objetos activos  
 El delegado que un objeto <xref:System.Windows.Freezable> pasa <xref:System.Windows.Freezable.Changed> al evento de un objeto es efectivamente una referencia a ese objeto. Por <xref:System.Windows.Freezable.Changed> lo tanto, los controladores de eventos pueden mantener los objetos activos más tiempo del esperado. Al realizar la limpieza de un objeto que <xref:System.Windows.Freezable> se <xref:System.Windows.Freezable.Changed> ha registrado para escuchar el evento de un objeto, es esencial quitar ese delegado antes de liberar el objeto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también conecta <xref:System.Windows.Freezable.Changed> eventos internamente. Por ejemplo, todas las <xref:System.Windows.Freezable> propiedades de dependencia <xref:System.Windows.Freezable.Changed> que toman como valor escucharán eventos automáticamente. La <xref:System.Windows.Shapes.Shape.Fill%2A> propiedad, que <xref:System.Windows.Media.Brush>toma un , ilustra este concepto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 En la `myBrush` asignación `myRectangle.Fill`de a , <xref:System.Windows.Shapes.Rectangle> se agregará un <xref:System.Windows.Media.SolidColorBrush> delegado <xref:System.Windows.Freezable.Changed> que apunte hacia el objeto al evento del objeto. Esto significa que el código siguiente realmente no hace que `myRect` sea apto para la recolección de elementos no usados:  
  
 [!code-csharp[Performance#PerformanceSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 En este `myBrush` caso `myRectangle` sigue vivo y le llamará cuando active <xref:System.Windows.Freezable.Changed> su evento. Tenga en `myBrush` cuenta <xref:System.Windows.Shapes.Shape.Fill%2A> que la <xref:System.Windows.Shapes.Rectangle> asignación a la `myBrush`propiedad de un nuevo simplemente agregará otro controlador de eventos a .  
  
 La forma recomendada de limpiar estos tipos <xref:System.Windows.Media.Brush> de <xref:System.Windows.Shapes.Shape.Fill%2A> objetos es quitar el <xref:System.Windows.Freezable.Changed> de la propiedad, que a su vez quitará el controlador de eventos.  
  
 [!code-csharp[Performance#PerformanceSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>
## <a name="user-interface-virtualization"></a>Virtualización de la interfaz de usuario  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]también proporciona una <xref:System.Windows.Controls.StackPanel> variación del elemento que automáticamente "virtualiza" el contenido secundario enlazado a datos. En este contexto, la palabra "virtualizar" hace referencia a una técnica que permite generar un subconjunto de objetos a partir de un número de elementos de datos más grande basados en los elementos que están visibles en pantalla. Es intensiva, tanto en términos de memoria como de procesador, y permite generar un gran número de elementos de interfaz de usuario cuando solo pueden estar en pantalla algunos de ellos en un momento dado. <xref:System.Windows.Controls.VirtualizingStackPanel>(a través <xref:System.Windows.Controls.VirtualizingPanel>de la funcionalidad proporcionada por <xref:System.Windows.Controls.ItemContainerGenerator> ) <xref:System.Windows.Controls.ItemsControl> calcula <xref:System.Windows.Controls.ListBox> los <xref:System.Windows.Controls.ListView>elementos visibles y funciona con el from an (como o ) para crear solo elementos para los elementos visibles.  
  
 Como optimización del rendimiento, los objetos visuales para estos elementos solo se generan o se mantienen activos si están visibles en pantalla. Cuando ya no están en el área visible del control, se pueden quitar los objetos visuales. Esto no se debe confundir con la virtualización de datos, donde los objetos de datos no existen en la colección local, sino que se transmiten según sea necesario.  
  
 La tabla siguiente muestra el tiempo transcurrido agregando y representando 5000 <xref:System.Windows.Controls.TextBlock> elementos a a <xref:System.Windows.Controls.StackPanel> y un <xref:System.Windows.Controls.VirtualizingStackPanel>archivo . En este escenario, las medidas representan el tiempo <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> entre la <xref:System.Windows.Controls.ItemsControl> asociación de una cadena de texto a la propiedad de un objeto a la hora en que los elementos del panel muestran la cadena de texto.  
  
|**Panel de host**|**Tiempo de representación (ms)**|  
|--------------------|----------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## <a name="see-also"></a>Consulte también

- [Optimizar WPF: Rendimiento de aplicaciones](optimizing-wpf-application-performance.md)
- [Planear para mejorar el rendimiento de aplicaciones](planning-for-application-performance.md)
- [Aprovechar el hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Presentación y diseño](optimizing-performance-layout-and-design.md)
- [Imágenes y gráficos 2D](optimizing-performance-2d-graphics-and-imaging.md)
- [Recursos de aplicación](optimizing-performance-application-resources.md)
- [Texto](optimizing-performance-text.md)
- [Enlace de datos](optimizing-performance-data-binding.md)
- [Otras recomendaciones de rendimiento](optimizing-performance-other-recommendations.md)
