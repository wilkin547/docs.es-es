---
title: "Informaci&#243;n general sobre elementos base | Microsoft Docs"
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
  - "elementos base"
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Informaci&#243;n general sobre elementos base
Un porcentaje elevado de clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se derivan de cuatro clases a las que se suele hacer referencia en la documentación del [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] como clases de elementos base.  Estas clases son <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement> y <xref:System.Windows.FrameworkContentElement>.  La clase <xref:System.Windows.DependencyObject> también está relacionada, porque es una clase base común de <xref:System.Windows.UIElement> y de <xref:System.Windows.ContentElement>  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="base_apis"></a>   
## API de elementos base en las clases de WPF  
 Tanto <xref:System.Windows.UIElement> como <xref:System.Windows.ContentElement> se derivan de <xref:System.Windows.DependencyObject>, aunque mediante rutas ligeramente distintas.  La diferencia en este nivel reside en el modo de utilizar los elementos <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> en una interfaz de usuario y en su finalidad dentro de una aplicación.  Además, <xref:System.Windows.UIElement> tiene <xref:System.Windows.Media.Visual> en su jerarquía de clases, que es una clase que expone la compatibilidad con los gráficos de bajo nivel que subyacen en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  <xref:System.Windows.Media.Visual> proporciona un marco de trabajo de presentación para definir zonas de la pantalla rectangulares independientes.  En la práctica, <xref:System.Windows.UIElement> es para elementos que admitan un modelo de objetos mayor, se han diseñado para presentar y diseñar en zonas que pueden describirse como zonas de la pantalla rectangulares y donde el modelo de contenido es deliberadamente más abierto, a fin de permitir diferentes combinaciones de elementos.  <xref:System.Windows.ContentElement> no se deriva de <xref:System.Windows.Media.Visual>; su modelo consiste en que un elemento <xref:System.Windows.ContentElement> sea consumido por otro elemento, como un lector o un visor, que a su vez interpretarán los elementos y producirán el objeto <xref:System.Windows.Media.Visual> completo utilizado por [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  Algunas clases <xref:System.Windows.UIElement> están diseñadas para ser hosts de contenido: proporcionan hospedaje y presentación para una o más clases <xref:System.Windows.ContentElement> \(<xref:System.Windows.Controls.DocumentViewer> es un ejemplo de una clase de este tipo\).  <xref:System.Windows.ContentElement> se utiliza como clase base para elementos con modelos de objetos algo más reducidos, más dirigidos a contenido de texto, información o documentos que puedan hospedarse en un elemento <xref:System.Windows.UIElement>.  
  
### Nivel del marco de trabajo y nivel básico  
 <xref:System.Windows.UIElement> actúa como clase base para <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.ContentElement> actúa como clase base para <xref:System.Windows.FrameworkContentElement>.  La razón de ser de este siguiente nivel de clases es la compatibilidad con el [nivel básico de WPF](GTMT), independiente del [nivel de marco de trabajo de WPF](GTMT); esta división también está presente en cómo se dividen las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] entre los ensamblados PresentationCore y PresentationFramework.  El [nivel de marco de trabajo de WPF](GTMT) presenta una solución más completa para las necesidades de aplicaciones básicas, que incluye la implementación del administrador de diseño para presentación.  El [nivel básico de WPF](GTMT) proporciona una manera de utilizar gran parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin la sobrecarga del ensamblado adicional.  La distinción entre estos niveles casi nunca es relevante en la mayoría de los escenarios típicos de programación de aplicaciones y, en general, es preferible pensar en las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en conjunto sin preocuparse por la diferencia entre el [nivel de marco de trabajo de WPF](GTMT) y el [nivel básico de WPF](GTMT).  Puede que necesite conocer estas distinciones de nivel si en el diseño de una aplicación se opta por reemplazar cantidades importantes de funcionalidades del [nivel de marco de trabajo de WPF](GTMT); por ejemplo, si la solución global ya tiene sus propias implementaciones de composición y diseño de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## Elegir el elemento del que derivar una clase  
 La manera más práctica de crear una clase personalizada que extienda [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste en derivar de una de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que permita obtener la máxima cantidad posible de la funcionalidad deseada a través de la jerarquía de clases existente.  En esta sección, se muestra una lista de funcionalidades suministradas con las principales clases de elementos, a fin de ayudarle a decidir de qué clase se debe heredar.  
  
 Si está implementando un control, que es una de las razones más comunes para derivar de una clase de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es probable que sea conveniente derivar de una clase que sea un control práctico, una clase base de una familia de controles o, como mínimo, de la clase base <xref:System.Windows.Controls.Control>.  Para obtener orientación y ejemplos prácticos, vea [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Si no está creando un control y necesita derivar de una clase situada en un punto más alto de la jerarquía, las secciones siguientes le ofrecen información sobre las características definidas en cada clase de elementos base.  
  
 Si crea una clase que se deriva de <xref:System.Windows.DependencyObject>, se hereda la funcionalidad siguiente:  
  
-   Compatibilidad con <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A>, así como con el sistema de propiedades general.  
  
-   Capacidad para utilizar [propiedades de dependencia](GTMT) y [propiedades adjuntas](GTMT), que se implementan como [propiedades de dependencia](GTMT).  
  
 Si crea una clase que se deriva de <xref:System.Windows.UIElement>, además de la funcionalidad proporcionada por <xref:System.Windows.DependencyObject> heredará la siguiente:  
  
-   Compatibilidad básica para valores de propiedades animadas.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos.  Para obtener más información, vea [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md) y [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Métodos virtuales que se pueden invalidar para proporcionar información a un sistema de diseño.  
  
 Si crea una clase que se deriva de <xref:System.Windows.FrameworkElement>, además de la funcionalidad proporcionada por <xref:System.Windows.UIElement> heredará la siguiente:  
  
-   Compatibilidad con la aplicación de estilos y los guiones gráficos.  Para obtener más información, vea <xref:System.Windows.Style> y [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Compatibilidad con enlaces de datos.  Para obtener más información, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Compatibilidad con referencias de recurso dinámicas.  Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedades y otros marcadores de los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios del marco de trabajo, tales como el enlace de datos, los estilos o la implementación del diseño en el marco de trabajo.  Para obtener más información, vea [Metadatos de las propiedades de marco de trabajo](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   El concepto de [árbol lógico](GTMT).  Para obtener más información, vea [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Compatibilidad con la implementación práctica del [nivel de marco de trabajo de WPF](GTMT) del sistema del diseño, incluida una invalidación del método <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> capaz de detectar cambios en las propiedades que influyen en el diseño.  
  
 Si crea una clase que se deriva de <xref:System.Windows.ContentElement>, además de la funcionalidad proporcionada por <xref:System.Windows.DependencyObject> heredará la siguiente:  
  
-   Compatibilidad con las animaciones.  Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos.  Para obtener más información, vea [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md) y [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Si crea una clase que se deriva de <xref:System.Windows.FrameworkContentElement>, además de la funcionalidad proporcionada por <xref:System.Windows.ContentElement> obtendrá la siguiente:  
  
-   Compatibilidad con la aplicación de estilos y los guiones gráficos.  Para obtener más información, vea <xref:System.Windows.Style> y [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con enlaces de datos.  Para obtener más información, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Compatibilidad con referencias de recurso dinámicas.  Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedades y otros marcadores de los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios del marco de trabajo, tales como el enlace de datos, los estilos o la implementación del diseño en el marco de trabajo.  Para obtener más información, vea [Metadatos de las propiedades de marco de trabajo](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   No se hereda el acceso a las modificaciones del sistema de diseño \(como <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>\).  Las implementaciones del sistema de diseño únicamente están disponibles en <xref:System.Windows.FrameworkElement>.  Sin embargo, sí heredará una invalidación de <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> capaz de detectar los cambios de propiedades que influyen en el diseño y comunicárselas a cualquier host de contenido.  
  
 Se documentan modelos de contenido para gran variedad de clases.  El modelo de contenido de una clase es uno de los factores posibles que deben tenerse en cuenta al buscar la clase adecuada para derivarla.  Para obtener más información, vea [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## Otras clases base  
  
### DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> proporciona compatibilidad con el modelo de subprocesos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y permite asociar todos los objetos creados para aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a <xref:System.Windows.Threading.Dispatcher>.  Aunque no se derive de <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject> o de <xref:System.Windows.Media.Visual>, puede ser conveniente derivar de <xref:System.Windows.Threading.DispatcherObject> para obtener esta compatibilidad con el modelo de subprocesos.  Para obtener más información, vea [Modelo de subprocesos](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### Visual  
 <xref:System.Windows.Media.Visual> implementa el concepto de objeto 2D que, en general, requiere la presentación visual en una zona con una forma más o menos rectangular.  La representación real de <xref:System.Windows.Media.Visual> tiene lugar en otras clases \(no es autónoma\), pero la clase <xref:System.Windows.Media.Visual> proporciona un tipo conocido que los procesos de presentación utilizan en varios niveles.  <xref:System.Windows.Media.Visual> implementa las pruebas de posicionamiento, pero no expone eventos que comunican los casos positivos de ello \(éstos se encuentran en <xref:System.Windows.UIElement>\).  Para obtener más información, vea [Programación de capas visuales](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### Freezable  
 <xref:System.Windows.Freezable> simula la inmutabilidad en un objeto mutable; para ello, proporciona un medio de generar copias del mismo cuando se necesita o desea un objeto inmutable por motivos de rendimiento.  El tipo <xref:System.Windows.Freezable> proporciona una base común para algunos elementos de gráficos, como geometrías y pinceles, así como animaciones.  Cabe destacar que un objeto <xref:System.Windows.Freezable> no es un objeto <xref:System.Windows.Media.Visual>; puede contener propiedades que se convierten en subpropiedades al aplicar el objeto <xref:System.Windows.Freezable> para rellenar el valor de una propiedad de otro objeto, subpropiedades que pueden afectar a la representación.  Para obtener más información, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> es una clase derivada de <xref:System.Windows.Freezable> que agrega de manera específica la capa de control de animación y algunos miembros de utilidad, a fin de permitir que las propiedades actualmente animadas se distingan de las propiedades no animadas.  
  
### Control  
 <xref:System.Windows.Controls.Control> es la clase base dirigida al tipo de objeto que se denomina o bien control o bien componente, dependiendo de la tecnología.  En general, las clases de controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son aquéllas que representan directamente un control de interfaz de usuario o que participan estrechamente en la composición de controles.  La funcionalidad primaria habilitada por <xref:System.Windows.Controls.Control> es la creación de plantillas de controles.  
  
## Vea también  
 <xref:System.Windows.Controls.Control>   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)