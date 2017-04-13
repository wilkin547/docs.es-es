---
title: "Optimizar el rendimiento: Comportamiento de objetos | Microsoft Docs"
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
  - "propiedades de dependencia, rendimiento"
  - "controladores de eventos [WPF]"
  - "Freezable (objetos), rendimiento"
  - "consideraciones sobre el rendimiento de los objetos"
  - "virtualización de la interfaz de usuario"
ms.assetid: 73aa2f47-1d73-439a-be1f-78dc4ba2b5bd
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Optimizar el rendimiento: Comportamiento de objetos
Entender el comportamiento intrínseco de los objetos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le ayudará a alcanzar el equilibrio adecuado entre funcionalidad y rendimiento.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Not_Removing_Event_Handlers"></a>   
## No quitar los controladores de eventos de los objetos puede hacer que los objetos se mantengan activos  
 El delegado que un objeto pasa a su evento es, en realidad, una referencia a ese objeto.  Por consiguiente, los controladores de eventos pueden mantener los objetos activos durante más tiempo de lo esperado.  Al realizar la limpieza de un objeto que se ha registrado para escuchar a fin de detectar el evento de un objeto, es esencial quitar ese delegado antes de liberar el objeto.  Mantener activos objetos innecesarios aumenta el uso de memoria por parte de la aplicación.  Esto se cumple especialmente cuando el objeto es la raíz de un [árbol lógico](GTMT) o de un [árbol visual](GTMT).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] introduce un modelo de agentes de escucha de evento débil para los eventos que puede resultar de utilidad en aquellos casos en que resulta difícil seguir la traza de las relaciones de duración del objeto entre el origen y el agente de escucha.  Algunos eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] existentes utilizan este modelo.  Si implementa objetos con eventos personalizados, este modelo puede resultarle de utilidad.  Para obtener información detallada, vea [Modelos de evento débil](../../../../docs/framework/wpf/advanced/weak-event-patterns.md).  
  
 Hay varias herramientas, tales como el generador de perfiles de CLR y el visor de espacio de trabajo, que pueden proporcionar información sobre el uso de memoria por parte de un proceso especificado.  El generador de perfiles de CLR incluye varias vistas muy útiles del perfil de asignación, entre las que se incluye un histograma de tipos asignados, gráficos de asignación y llamadas, una escala temporal que muestra recolecciones de elementos no utilizados de varias generaciones y el estado resultante del montón administrado después de esas recolecciones, así como un árbol de llamadas que muestra las asignaciones por método y las cargas de ensamblado.  Para obtener más información, visite [.NET Framework Developer Center](http://go.microsoft.com/fwlink/?LinkId=117435).  
  
<a name="DPs_and_Objects"></a>   
## Objetos y propiedades de dependencia  
 En general, tener acceso a una [propiedad de dependencia](GTMT) de un objeto <xref:System.Windows.DependencyObject> no es más lento que tener acceso a una propiedad de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Aunque al establecer un valor de propiedad se produce una pequeña sobrecarga de rendimiento, la obtención de un valor es tan rápida como en una propiedad de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)].  Esta pequeña sobrecarga de rendimiento se compensa con el hecho de que las [propiedades de dependencia](GTMT) admiten características robustas, tales como enlace de datos, animación, herencia y estilos.  Para obtener más información, consulte [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
### Optimización de las propiedades de dependencia  
 Deben extremarse las precauciones al definir [propiedades de dependencia](GTMT) en la aplicación.  Si <xref:System.Windows.DependencyProperty> sólo afecta a las opciones de metadatos de tipo de representación, y no a otras opciones de metadatos como <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, debe marcarla como a tal invalidando sus metadatos.  Para obtener más información sobre cómo invalidar u obtener metadatos de propiedades, vea [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md).  
  
 Puede ser más eficaz hacer que un controlador de cambio de propiedad invalide manualmente los pases de medida, organización y representación si no todos los cambios afectan realmente a la medición, organización y representación.  Por ejemplo, podría optar por representar de nuevo un fondo únicamente cuando un valor sea superior a un límite establecido.  En este caso, el controlador de cambio de propiedad únicamente invalidaría la representación cuando el valor superase ese límite establecido.  
  
### Hacer que una propiedad de dependencia se pueda heredar consume recursos  
 De manera predeterminada, las [propiedades de dependencia](GTMT) registradas no se pueden heredar.  Sin embargo, puede hacer explícitamente que cualquier propiedad sea heredable.  Aunque se trata de una característica útil, convertir una propiedad en heredable afecta negativamente al rendimiento, porque aumenta el tiempo que se tarda en invalidar las propiedades.  
  
### RegisterClassHandler debe utilizarse con prudencia  
 Aunque llamar a <xref:System.Windows.EventManager.RegisterClassHandler%2A> permite guardar el estado de instancia, es importante ser consciente de que se llama al controlador en cada instancia, lo que puede dar lugar a problemas de rendimiento.  Únicamente debe utilizar <xref:System.Windows.EventManager.RegisterClassHandler%2A> cuando la aplicación necesite que se guarde el estado de instancia.  
  
### Establecer el valor predeterminado de una propiedad de dependencia durante el registro  
 Al crear una <xref:System.Windows.DependencyProperty> que requiere un valor predeterminado, establezca el valor mediante los metadatos predeterminados que se pasan como parámetro al método <xref:System.Windows.DependencyProperty.Register%2A> de <xref:System.Windows.DependencyProperty>.  Utilice esta técnica en lugar de establecer el valor de propiedad en un constructor o en cada instancia de un elemento.  
  
### Establecer el valor de PropertyMetadata mediante el Registro  
 Al crear una <xref:System.Windows.DependencyProperty>, si lo desea puede establecer <xref:System.Windows.PropertyMetadata> mediante los métodos <xref:System.Windows.DependencyProperty.Register%2A> o <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>.  Aunque el objeto podría tener un constructor estático para llamar a <xref:System.Windows.DependencyProperty.OverrideMetadata%2A>, no es la solución óptima y afecta negativamente al rendimiento.  Para obtener el máximo rendimiento, establezca <xref:System.Windows.PropertyMetadata> durante la llamada a <xref:System.Windows.DependencyProperty.Register%2A>.  
  
<a name="Freezable_Objects"></a>   
## Objetos Freezable  
 Un objeto <xref:System.Windows.Freezable> es un tipo especial de objeto que tiene dos estados: no inmovilizado e inmovilizado.  Inmovilizar los objetos siempre que es posible mejora el rendimiento de la aplicación y reduce su espacio de trabajo.  Para obtener más información, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 Cada objeto <xref:System.Windows.Freezable> tiene un evento <xref:System.Windows.Freezable.Changed> que se provoca cada vez que cambia.  Sin embargo, las notificaciones de cambio son costosas por lo que se refiere al rendimiento de la aplicación.  
  
 Estudie el ejemplo siguiente, en el que cada <xref:System.Windows.Shapes.Rectangle> utiliza el mismo objeto <xref:System.Windows.Media.Brush>:  
  
 [!code-csharp[Performance#PerformanceSnippet2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet2)]
 [!code-vb[Performance#PerformanceSnippet2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet2)]  
  
 De manera predeterminada, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un controlador para el evento <xref:System.Windows.Freezable.Changed> del objeto <xref:System.Windows.Media.SolidColorBrush> a fin de invalidar la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> del objeto <xref:System.Windows.Shapes.Rectangle>.  En este caso, cada vez que <xref:System.Windows.Media.SolidColorBrush> tiene que iniciar su evento <xref:System.Windows.Freezable.Changed>, es preciso invocar la función de devolución de llamada para cada <xref:System.Windows.Shapes.Rectangle>: la acumulación de estas invocaciones de la función de devolución de llamada conlleva importante reducción del rendimiento.  Además, agregar y quitar controladores en este punto también supone una intensa carga para el rendimiento, puesto que para hacerlo la aplicación tiene que recorrer la lista completa.  Si en el escenario de aplicación <xref:System.Windows.Media.SolidColorBrush> nunca cambia, estará pagando el costo de mantener innecesariamente los controladores de eventos <xref:System.Windows.Freezable.Changed>.  
  
 Inmovilizar un objeto <xref:System.Windows.Freezable> puede mejorar su rendimiento, porque ya no es preciso dedicar recursos a mantener notificaciones de cambio.  En la tabla siguiente se muestra el tamaño de un <xref:System.Windows.Media.SolidColorBrush> simple cuando su propiedad <xref:System.Windows.Freezable.IsFrozen%2A> está establecida en `true`, en comparación con cuando no lo está.  Se basa en el supuesto de que se aplica un pincel a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de diez objetos <xref:System.Windows.Shapes.Rectangle>.  
  
|**Estado**|**Size**|  
|----------------|--------------|  
|<xref:System.Windows.Media.SolidColorBrush> inmovilizado|212 bytes|  
|<xref:System.Windows.Media.SolidColorBrush> no inmovilizado|972 bytes|  
  
 En el ejemplo de código siguiente se muestra este concepto:  
  
 [!code-csharp[Performance#PerformanceSnippet3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet3)]
 [!code-vb[Performance#PerformanceSnippet3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet3)]  
  
### Los controladores modificados de objetos Freezable no inmovilizados pueden mantener los objetos activos  
 El delegado que un objeto pasa al evento <xref:System.Windows.Freezable.Changed> de un objeto <xref:System.Windows.Freezable> es, en realidad, una referencia a ese objeto.  Por consiguiente, los controladores de eventos <xref:System.Windows.Freezable.Changed> pueden mantener los objetos activos durante más tiempo de lo esperado.  Al realizar la limpieza de un objeto que se ha registrado para escuchar a fin de detectar el evento <xref:System.Windows.Freezable.Changed> de un objeto <xref:System.Windows.Freezable>, es esencial quitar ese delegado antes de liberar el objeto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también enlaza internamente los eventos <xref:System.Windows.Freezable.Changed>.  Por ejemplo, todas las [propiedades de dependencia](GTMT) que aceptan <xref:System.Windows.Freezable> como valor escucharán automáticamente para detectar los eventos <xref:System.Windows.Freezable.Changed>.  La propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, que acepta un <xref:System.Windows.Media.Brush>, muestra este concepto.  
  
 [!code-csharp[Performance#PerformanceSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet4)]
 [!code-vb[Performance#PerformanceSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet4)]  
  
 Al asignar `myBrush` a `myRectangle.Fill`, un delegado que señala hacia atrás al objeto <xref:System.Windows.Shapes.Rectangle> se agregará al evento <xref:System.Windows.Freezable.Changed> del objeto <xref:System.Windows.Media.SolidColorBrush>.  Esto significa que el código siguiente realmente no hace que `myRect` sea apto para la recolección de elementos no utilizados:  
  
 [!code-csharp[Performance#PerformanceSnippet5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet5)]
 [!code-vb[Performance#PerformanceSnippet5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet5)]  
  
 En este caso, `myBrush` mantiene `myRectangle` activo y le devolverá la llamada cuando provoque su evento <xref:System.Windows.Freezable.Changed>.  Observe que al asignar `myBrush` a la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> de un nuevo <xref:System.Windows.Shapes.Rectangle>, simplemente se agrega otro controlador de eventos a `myBrush`.  
  
 La manera recomendada de limpiar estos tipos de objetos es quitar <xref:System.Windows.Media.Brush> de la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>, lo que, a su vez, quitará el controlador de eventos de <xref:System.Windows.Freezable.Changed>.  
  
 [!code-csharp[Performance#PerformanceSnippet6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml.cs#performancesnippet6)]
 [!code-vb[Performance#PerformanceSnippet6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/window1.xaml.vb#performancesnippet6)]  
  
<a name="User_Interface_Virtualization"></a>   
## Virtualización de la interfaz de usuario  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también proporciona una variación del elemento <xref:System.Windows.Controls.StackPanel> que "virtualiza" automáticamente el contenido secundario enlazado a datos.  En este contexto, el término "virtualizar" se refiere a una técnica por la que se genera un subconjunto de objetos a partir de un número mayor de elementos de datos en función de los elementos que están visibles en pantalla.  Generar un gran número de elementos de interfaz de usuario cuando sólo pueden estar en pantalla algunos de ellos en un momento dado, requiere un uso intensivo, tanto de la memoria como del procesador.  <xref:System.Windows.Controls.VirtualizingStackPanel> \(a través de la funcionalidad proporcionada por <xref:System.Windows.Controls.VirtualizingPanel>\) calcula los elementos visibles y trabaja con <xref:System.Windows.Controls.ItemContainerGenerator> desde un control <xref:System.Windows.Controls.ItemsControl> \(como <xref:System.Windows.Controls.ListBox> o <xref:System.Windows.Controls.ListView>\) para crear elementos únicamente para los elementos visibles.  
  
 Para optimizar el rendimiento, los objetos visuales correspondientes a estos elementos se generan o mantienen activos únicamente si están visibles en la pantalla.  Cuando ya no se encuentran en el área visible del control, los objetos visuales se pueden quitar.  Esto no debe confundirse con la virtualización de datos, donde los objetos de datos no están presentes en absoluto en la colección local, sino que se transmiten a medida que se necesitan.  
  
 En la tabla siguiente se muestra el tiempo transcurrido para agregar y representar 5000 elementos <xref:System.Windows.Controls.TextBlock> en un <xref:System.Windows.Controls.StackPanel> y en un <xref:System.Windows.Controls.VirtualizingStackPanel>.  En este escenario, las mediciones representan el tiempo transcurrido entre el momento de asociar una cadena de texto a la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> de un objeto <xref:System.Windows.Controls.ItemsControl> hasta el momento en que los elementos de panel muestran la cadena de texto.  
  
|**Panel host**|**Tiempo de representación \(ms\)**|  
|--------------------|-----------------------------------------|  
|<xref:System.Windows.Controls.StackPanel>|3210|  
|<xref:System.Windows.Controls.VirtualizingStackPanel>|46|  
  
## Vea también  
 [Optimizar WPF: Rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [Planear para mejorar el rendimiento de aplicaciones](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [Aprovechar el hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [Presentación y diseño](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [Imágenes y gráficos GDI\+](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [Recursos de aplicación](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [Text](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)   
 [Enlace de datos](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [Otras recomendaciones de rendimiento](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)