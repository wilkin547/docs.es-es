---
title: Información general sobre elementos base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 823c81bf6b21b88d719503387a68ce6e7d643d61
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740917"
---
# <a name="base-elements-overview"></a>Información general sobre elementos base
Un porcentaje alto de clases en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] se derivan de cuatro clases a las que se suele hacer referencia en la documentación del SDK como las clases de elementos base. Estas clases son <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>y <xref:System.Windows.FrameworkContentElement>. La clase <xref:System.Windows.DependencyObject> también está relacionada, ya que es una clase base común de <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>  

<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API de elementos base en clases de WPF  
 Tanto <xref:System.Windows.UIElement> como <xref:System.Windows.ContentElement> derivan de <xref:System.Windows.DependencyObject>, a través de rutas ligeramente diferentes. La división en este nivel aborda el modo en que se usa una <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> en una interfaz de usuario y el propósito de la aplicación. <xref:System.Windows.UIElement> también tiene <xref:System.Windows.Media.Visual> en su jerarquía de clases, que es una clase que expone la compatibilidad con gráficos de nivel inferior subyacente a la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> proporciona un marco de representación mediante la definición de regiones de pantalla rectangulares independientes. En la práctica, <xref:System.Windows.UIElement> se aplica a los elementos que admiten un modelo de objetos más grande, están diseñados para representar y diseñar en regiones que se pueden describir como regiones de pantalla rectangular, y donde el modelo de contenido está abierto deliberadamente, para permitir diferentes combinaciones de elementos. <xref:System.Windows.ContentElement> no se deriva de <xref:System.Windows.Media.Visual>; su modelo es que una <xref:System.Windows.ContentElement> sería consumida por otra cosa, como un lector o un visor que, a continuación, interpretaría los elementos y produciría el <xref:System.Windows.Media.Visual> completo para que [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consumirse. Ciertas clases de <xref:System.Windows.UIElement> están diseñadas para ser hosts de contenido: proporcionan el hospedaje y la representación de una o varias clases de <xref:System.Windows.ContentElement> (<xref:System.Windows.Controls.DocumentViewer> es un ejemplo de este tipo de clase). <xref:System.Windows.ContentElement> se utiliza como clase base para los elementos con modelos de objetos algo más pequeños y que más direccionan el texto, la información o el contenido del documento que podría estar hospedado en una <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Nivel de marco y nivel básico  
 <xref:System.Windows.UIElement> actúa como clase base para <xref:System.Windows.FrameworkElement>y <xref:System.Windows.ContentElement> actúa como clase base para <xref:System.Windows.FrameworkContentElement>. La razón de este siguiente nivel de clases es admitir un nivel de núcleo de WPF que es independiente de un nivel de marco de WPF, y esta división también existe en la forma en que se dividen las API entre los ensamblados PresentationCore y PresentationFramework. El nivel de marco de WPF presenta una solución más completa para las necesidades básicas de las aplicaciones, incluida la implementación del administrador de diseño para la presentación. El nivel básico de WPF proporciona una manera de usar gran parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin la sobrecarga del ensamblado adicional. La distinción entre estos niveles rara vez es importante en los escenarios de desarrollo de aplicaciones más habituales y, en general, debería considerar las API de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como un conjunto y no preocuparse por la diferencia entre el nivel de marco de WPF y el nivel básico de WPF. Es posible que deba conocer las diferencias de nivel si el diseño de su aplicación opta por reemplazar una cantidad importante de funciones de nivel de marco de WPF, como, por ejemplo, si toda la solución ya tiene sus propias implementaciones de composición y diseño de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Elección del elemento del que va a derivar  
 La manera más práctica para crear una clase personalizada que amplíe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es que derive de una de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], donde se obtiene la máxima cantidad de funcionalidad deseada a través de la jerarquía de clases existente. En esta sección se muestra la funcionalidad que se incluye con tres de las clases de elementos más importantes para ayudarle a decidir de qué clase se debe heredar.  
  
 Si está implementando un control, que es realmente uno de los motivos más comunes para derivar de una clase [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], es probable que desee derivar de una clase que sea un control práctico, una clase base de la familia de controles o, al menos, de la clase base <xref:System.Windows.Controls.Control>. Para obtener orientación y ejemplos prácticos, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Si no está creando un control y necesita derivar de una clase superior en la jerarquía, las siguientes secciones son una guía de las características que se definen en cada clase de elemento base.  
  
 Si crea una clase que deriva de <xref:System.Windows.DependencyObject>, heredará la funcionalidad siguiente:  
  
- compatibilidad con <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> y compatibilidad con el sistema de propiedades general.  
  
- Capacidad de usar las propiedades de dependencia y las propiedades adjuntas que están implementadas como propiedades de dependencia.  
  
 Si crea una clase que deriva de <xref:System.Windows.UIElement>, heredará la siguiente funcionalidad además de la que proporciona <xref:System.Windows.DependencyObject>:  
  
- Compatibilidad básica para valores de propiedades animadas. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
- Los métodos virtuales se pueden invalidar para proporcionar información a un sistema de diseño.  
  
 Si crea una clase que deriva de <xref:System.Windows.FrameworkElement>, heredará la siguiente funcionalidad además de la que proporciona <xref:System.Windows.UIElement>:  
  
- Compatibilidad con estilos y guiones gráficos. Para obtener más información, vea [información general sobre <xref:System.Windows.Style> y guiones gráficos](../graphics-multimedia/storyboards-overview.md).  
  
- Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
- Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos, que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
- Concepto del árbol lógico. Para obtener más información, consulte [Árboles en WPF](trees-in-wpf.md).  
  
- Compatibilidad con la implementación de nivel de marco de WPF práctica del sistema de diseño, incluida una invalidación <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> que puede detectar cambios en las propiedades que influyen en el diseño.  
  
 Si crea una clase que deriva de <xref:System.Windows.ContentElement>, heredará la siguiente funcionalidad además de la que proporciona <xref:System.Windows.DependencyObject>:  
  
- Compatibilidad con las animaciones. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
 Si crea una clase que deriva de <xref:System.Windows.FrameworkContentElement>, obtendrá la siguiente funcionalidad además de la que proporciona <xref:System.Windows.ContentElement>:  
  
- Compatibilidad con estilos y guiones gráficos. Para obtener más información, vea [información general sobre <xref:System.Windows.Style> y animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
- Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
- No se hereda el acceso a las modificaciones del sistema de diseño (como <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Las implementaciones del sistema de diseño solo están disponibles en <xref:System.Windows.FrameworkElement>. Sin embargo, se hereda una invalidación <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> que puede detectar cambios en las propiedades que influyen en el diseño y se notifican a los hosts de contenido.  
  
 Los modelos de contenido se documentan para distintas clases. El modelo de contenido de una clase es uno de los factores posibles que debe considerar si quiere buscar una clase adecuada de la que derivar. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Otras clases base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> proporciona compatibilidad con el modelo de subprocesos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y permite asociar todos los objetos creados para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones a un <xref:System.Windows.Threading.Dispatcher>. Incluso si no deriva de <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>o <xref:System.Windows.Media.Visual>, debería considerar la posibilidad de derivar de <xref:System.Windows.Threading.DispatcherObject> para obtener compatibilidad con este modelo de subprocesos. Para obtener más información, consulte [Modelo de subprocesos](threading-model.md).  
  
### <a name="visual"></a>Elemento visual  
 <xref:System.Windows.Media.Visual> implementa el concepto de un objeto 2D que generalmente requiere la presentación visual en una región más aproximadamente rectangular. La representación real de una <xref:System.Windows.Media.Visual> ocurre en otras clases (no es independiente), pero la clase <xref:System.Windows.Media.Visual> proporciona un tipo conocido que se usa en los procesos de representación en varios niveles. <xref:System.Windows.Media.Visual> implementa la prueba de posicionamiento, pero no expone los eventos que notifican los positivos de la prueba de aciertos (se encuentran en <xref:System.Windows.UIElement>). Para obtener más información, consulte [Programación de capas visuales](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Inmovilizable  
 <xref:System.Windows.Freezable> simula la inmutabilidad en un objeto mutable proporcionando los medios para generar copias del objeto cuando se requiere o se desea un objeto inmutable por motivos de rendimiento. El tipo de <xref:System.Windows.Freezable> proporciona una base común para determinados elementos gráficos, como geometrías y pinceles, así como animaciones. En particular, una <xref:System.Windows.Freezable> no es un <xref:System.Windows.Media.Visual>; puede contener propiedades que se convierten en subpropiedades cuando se aplica el <xref:System.Windows.Freezable> para rellenar un valor de propiedad de otro objeto, y esas subpropiedades pueden afectar a la representación. Para obtener más información, consulte [Información general sobre objetos Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> es una clase derivada de <xref:System.Windows.Freezable> que agrega específicamente la capa de control de animación y algunos miembros de utilidad para que las propiedades animadas actualmente se puedan distinguir de las propiedades no animadas.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control> es la clase base deseada para el tipo de objeto que se extremos a un control o componente, dependiendo de la tecnología. En general, las clases de control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son clases que representan directamente un control de interfaz de usuario o que participan estrechamente en la composición del control. La funcionalidad principal que <xref:System.Windows.Controls.Control> habilita es el control de la plantilla.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Control>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Arquitectura de WPF](wpf-architecture.md)
