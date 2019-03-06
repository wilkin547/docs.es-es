---
title: Información general sobre elementos base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: a7ed16690172f2720424807325150ea3db5d5caa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372835"
---
# <a name="base-elements-overview"></a>Información general sobre elementos base
Un porcentaje elevado de clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] deriva de cuatro clases a las que se hace referencia normalmente en la documentación de [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] como clases de elementos base. Estas clases son <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, y <xref:System.Windows.FrameworkContentElement>. El <xref:System.Windows.DependencyObject> clase también está relacionada, porque es una clase base común de ambos <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API de elementos base en clases de WPF  
 Ambos <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> se derivan de <xref:System.Windows.DependencyObject>, a través de rutas ligeramente distintas. La división en este nivel se ocupa de cómo un <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> se usan en una interfaz de usuario y su finalidad en una aplicación. <xref:System.Windows.UIElement> También tiene <xref:System.Windows.Media.Visual> en su jerarquía de clases, que es una clase que expone la compatibilidad con gráficos de nivel inferior subyacente el [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual> Proporciona un marco de trabajo de representación mediante la definición de regiones de pantalla rectangulares independientes. En la práctica, <xref:System.Windows.UIElement> es para los elementos que admitirán un modelo de objetos más grande son está previsto para representar y disponerse en regiones que pueden describirse como regiones de pantalla rectangulares, y donde el modelo de contenido es deliberadamente más abierto, para permitir diferentes combinaciones de elementos. <xref:System.Windows.ContentElement> no se deriva de <xref:System.Windows.Media.Visual>; su modelo consiste en que un <xref:System.Windows.ContentElement> sería consumido por otro valor, como un lector o visor que, a continuación, se podría interpretar los elementos y producir completo <xref:System.Windows.Media.Visual> para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para consumir. Ciertos <xref:System.Windows.UIElement> están diseñadas para ser hosts de contenido: proporcionan hospedaje y representación para uno o varios <xref:System.Windows.ContentElement> clases (<xref:System.Windows.Controls.DocumentViewer> es un ejemplo de este tipo de clase). <xref:System.Windows.ContentElement> se usa como clase base para elementos con modelos de objetos un poco más pequeños y que, más el texto, la información de direcciones o contenido de los documentos que podrían hospedarse en un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Nivel de marco y nivel básico  
 <xref:System.Windows.UIElement> actúa como clase base para <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.ContentElement> actúa como clase base para <xref:System.Windows.FrameworkContentElement>. El motivo de este nivel superior de clases es admitir un nivel básico de WPF independiente de un nivel de marco de WPF, con esta división también presente en la manera de dividir las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] entre los ensamblados PresentationCore y PresentationFramework. El nivel de marco de WPF presenta una solución más completa para las necesidades básicas de las aplicaciones, incluida la implementación del administrador de diseño para la presentación. El nivel básico de WPF proporciona una manera de usar gran parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin la sobrecarga del ensamblado adicional. La distinción entre estos niveles muy rara vez es importante para los escenarios de desarrollo de aplicaciones más habituales y, en general, podría considerar las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como un todo, sin preocuparse por la diferencia entre el nivel de marco de WPF y el nivel básico de WPF. Es posible que deba conocer las diferencias de nivel si el diseño de su aplicación opta por reemplazar una cantidad importante de funciones de nivel de marco de WPF, como, por ejemplo, si toda la solución ya tiene sus propias implementaciones de composición y diseño de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Elección del elemento del que va a derivar  
 La manera más práctica para crear una clase personalizada que amplíe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es que derive de una de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], donde se obtiene la máxima cantidad de funcionalidad deseada a través de la jerarquía de clases existente. En esta sección se muestra la funcionalidad que se incluye con tres de las clases de elementos más importantes para ayudarle a decidir de qué clase se debe heredar.  
  
 Si está implementando un control, que es una de las razones más comunes para derivar de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (clase), probablemente desee derivar de una clase que es un control práctico, una clase base familia de control, o, al menos, de la <xref:System.Windows.Controls.Control> clase base. Para obtener orientación y ejemplos prácticos, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Si no está creando un control y necesita derivar de una clase superior en la jerarquía, las siguientes secciones son una guía de las características que se definen en cada clase de elemento base.  
  
 Si crea una clase que derive de <xref:System.Windows.DependencyObject>, hereda la funcionalidad siguiente:  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A> y <xref:System.Windows.DependencyObject.SetValue%2A> soporte técnico y soporte técnico de propiedades general del sistema.  
  
-   Capacidad de usar las propiedades de dependencia y las propiedades adjuntas que están implementadas como propiedades de dependencia.  
  
 Si crea una clase que derive de <xref:System.Windows.UIElement>, hereda la funcionalidad siguiente a la que se proporciona por <xref:System.Windows.DependencyObject>:  
  
-   Compatibilidad básica para valores de propiedades animadas. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
-   Los métodos virtuales se pueden invalidar para proporcionar información a un sistema de diseño.  
  
 Si crea una clase que derive de <xref:System.Windows.FrameworkElement>, hereda la funcionalidad siguiente a la que se proporciona por <xref:System.Windows.UIElement>:  
  
-   Compatibilidad con estilos y guiones gráficos. Para obtener más información, consulte <xref:System.Windows.Style> y [Storyboards Overview](../graphics-multimedia/storyboards-overview.md).  
  
-   Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
-   Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos, que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
-   Concepto del árbol lógico. Para obtener más información, consulte [Árboles en WPF](trees-in-wpf.md).  
  
-   Compatibilidad con la implementación de nivel de marco WPF práctica del sistema de diseño, incluyendo un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> invalidación que puede detectar cambios en las propiedades que influyen en el diseño.  
  
 Si crea una clase que derive de <xref:System.Windows.ContentElement>, hereda la funcionalidad siguiente a la que se proporciona por <xref:System.Windows.DependencyObject>:  
  
-   Compatibilidad con las animaciones. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
 Si crea una clase que derive de <xref:System.Windows.FrameworkContentElement>, obtendrá la siguiente funcionalidad a la que proporciona <xref:System.Windows.ContentElement>:  
  
-   Compatibilidad con estilos y guiones gráficos. Para obtener más información, consulte <xref:System.Windows.Style> y [información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../data/data-binding-overview.md).  
  
-   Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
-   No se hereda el acceso a las modificaciones del sistema de diseño (como <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Solo están disponibles en las implementaciones de sistema de diseño <xref:System.Windows.FrameworkElement>. Sin embargo, hereda un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> invalidación que puede detectar cambios en las propiedades que influyen en el diseño y comunicárselas a cualquier host de contenido.  
  
 Los modelos de contenido se documentan para distintas clases. El modelo de contenido de una clase es uno de los factores posibles que debe considerar si quiere buscar una clase adecuada de la que derivar. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Otras clases base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject> proporciona compatibilidad para la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subprocesamiento de modelo y habilita todos los objetos creados para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones se asocie a un <xref:System.Windows.Threading.Dispatcher>. Incluso si no se derivan de <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, o <xref:System.Windows.Media.Visual>, deberían considerar derivarlos del <xref:System.Windows.Threading.DispatcherObject> con el fin de obtener compatibilidad con este modelo de subprocesamiento. Para obtener más información, consulte [Modelo de subprocesos](threading-model.md).  
  
### <a name="visual"></a>Elemento visual  
 <xref:System.Windows.Media.Visual> implementa el concepto de un objeto 2D que normalmente requiere la presentación visual en una región más o menos rectangular. La representación real de un <xref:System.Windows.Media.Visual> ocurre en otras clases (no es autocontenida), pero la <xref:System.Windows.Media.Visual> clase proporciona un tipo conocido que se usa en los procesos de representación en varios niveles. <xref:System.Windows.Media.Visual> implementa la prueba de posicionamiento, pero no expone eventos que informan de la prueba de posicionamiento positivos (están en <xref:System.Windows.UIElement>). Para obtener más información, consulte [Programación de capas visuales](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Inmovilizable  
 <xref:System.Windows.Freezable> simula la inmutabilidad en un objeto mutable, ya que proporciona los medios para generar copias del objeto cuando un objeto inmutable es requerido o deseado por motivos de rendimiento. El <xref:System.Windows.Freezable> tipo proporciona una base común para determinados elementos gráficos, como geometrías y pinceles, así como las animaciones. En concreto, un <xref:System.Windows.Freezable> no es un <xref:System.Windows.Media.Visual>; puede contener propiedades que se convierten en subpropiedades cuando la <xref:System.Windows.Freezable> se aplica para rellenar un valor de propiedad de otro objeto, y esas subpropiedades podrían afectar a la representación. Para obtener más información, consulte [Información general sobre objetos Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable> es un <xref:System.Windows.Freezable> clase derivada que agrega específicamente la capa de control de animación y algunos miembros de utilidad para que las propiedades animadas actualmente se pueden distinguir de las no animadas.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control> es la clase base deseada para el tipo de objeto que se denomina un control o componente, dependiendo de la tecnología. En general, las clases de control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son clases que representan directamente un control de interfaz de usuario o que participan estrechamente en la composición del control. La funcionalidad principal que <xref:System.Windows.Controls.Control> habilita es la creación de plantillas de control.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.Control>
- [Información general sobre las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Arquitectura de WPF](wpf-architecture.md)
