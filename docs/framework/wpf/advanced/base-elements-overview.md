---
title: "Información general sobre elementos base"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 270388b8e3dda0342ba74187d8dc45616d0e769d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="base-elements-overview"></a>Información general sobre elementos base
Un porcentaje elevado de clases de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] deriva de cuatro clases a las que se hace referencia normalmente en la documentación de [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)] como clases de elementos base. Estas clases son <xref:System.Windows.UIElement>, <xref:System.Windows.FrameworkElement>, <xref:System.Windows.ContentElement>, y <xref:System.Windows.FrameworkContentElement>. El <xref:System.Windows.DependencyObject> clase también está relacionada, porque es una clase base común de ambos <xref:System.Windows.UIElement> y<xref:System.Windows.ContentElement>  
 
  
<a name="base_apis"></a>   
## <a name="base-element-apis-in-wpf-classes"></a>API de elementos base en clases de WPF  
 Ambos <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> derivadas de <xref:System.Windows.DependencyObject>, mediante rutas ligeramente distintas. La división en este nivel se ocupa de cómo un <xref:System.Windows.UIElement> o <xref:System.Windows.ContentElement> se usan en una interfaz de usuario y la finalidad de una aplicación. <xref:System.Windows.UIElement>También tiene <xref:System.Windows.Media.Visual> en su jerarquía de clases, que es una clase que expone la compatibilidad con gráficos de bajo nivel subyacente la [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]. <xref:System.Windows.Media.Visual>Proporciona un marco de representación mediante la definición de las regiones de pantalla rectangulares independientes. En la práctica, <xref:System.Windows.UIElement> es para elementos que admiten un modelo de objetos mayor, son está pensado para representar y el diseño en las regiones de que se puede describir como regiones de pantalla rectangular y donde el modelo de contenido es deliberadamente más abierto, para permitir diferentes combinaciones de elementos. <xref:System.Windows.ContentElement>no se deriva de <xref:System.Windows.Media.Visual>; su modelo es que un <xref:System.Windows.ContentElement> sea consumido por otro elemento, como un lector o un visor que, a continuación, se podría interpretar los elementos y generar completo <xref:System.Windows.Media.Visual> para [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] para consumir. Ciertos <xref:System.Windows.UIElement> clases están pensadas para ser hosts de contenido: proporcionan hospedaje y presentación para uno o varios <xref:System.Windows.ContentElement> clases (<xref:System.Windows.Controls.DocumentViewer> es un ejemplo de esta clase). <xref:System.Windows.ContentElement>se usa como clase base para los elementos con los modelos de objetos algo más pequeños y que más el texto, la información de direcciones o documento de contenido que se pueden hospedar dentro de un <xref:System.Windows.UIElement>.  
  
### <a name="framework-level-and-core-level"></a>Nivel de marco y nivel básico  
 <xref:System.Windows.UIElement>actúa como clase base para <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.ContentElement> actúa como la clase base para <xref:System.Windows.FrameworkContentElement>. El motivo de este nivel superior de clases es admitir un nivel básico de WPF independiente de un nivel de marco de WPF, con esta división también presente en la manera de dividir las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] entre los ensamblados PresentationCore y PresentationFramework. El nivel de marco de WPF presenta una solución más completa para las necesidades básicas de las aplicaciones, incluida la implementación del administrador de diseño para la presentación. El nivel básico de WPF proporciona una manera de usar gran parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin la sobrecarga del ensamblado adicional. La distinción entre estos niveles muy rara vez es importante para los escenarios de desarrollo de aplicaciones más habituales y, en general, podría considerar las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] como un todo, sin preocuparse por la diferencia entre el nivel de marco de WPF y el nivel básico de WPF. Es posible que deba conocer las diferencias de nivel si el diseño de su aplicación opta por reemplazar una cantidad importante de funciones de nivel de marco de WPF, como, por ejemplo, si toda la solución ya tiene sus propias implementaciones de composición y diseño de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>   
## <a name="choosing-which-element-to-derive-from"></a>Elección del elemento del que va a derivar  
 La manera más práctica para crear una clase personalizada que amplíe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es que derive de una de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], donde se obtiene la máxima cantidad de funcionalidad deseada a través de la jerarquía de clases existente. En esta sección se muestra la funcionalidad que se incluye con tres de las clases de elementos más importantes para ayudarle a decidir de qué clase se debe heredar.  
  
 Si está implementando un control, que es una de las razones más comunes para derivar de un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (clase), probablemente desee derivar de una clase que sea un control práctico, una clase base familia de control, o en menos de la <xref:System.Windows.Controls.Control> clase base. Para obtener orientación y ejemplos prácticos, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Si no está creando un control y necesita derivar de una clase superior en la jerarquía, las siguientes secciones son una guía de las características que se definen en cada clase de elemento base.  
  
 Si crea una clase que deriva de <xref:System.Windows.DependencyObject>, hereda la funcionalidad siguiente:  
  
-   <xref:System.Windows.DependencyObject.GetValue%2A>y <xref:System.Windows.DependencyObject.SetValue%2A> compatibilidad y soporte técnico del sistema de propiedades general.  
  
-   Capacidad de usar las propiedades de dependencia y las propiedades adjuntas que están implementadas como propiedades de dependencia.  
  
 Si crea una clase que deriva de <xref:System.Windows.UIElement>, heredan la siguiente funcionalidad a la que proporcionan <xref:System.Windows.DependencyObject>:  
  
-   Compatibilidad básica para valores de propiedades animadas. Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md) e [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
-   Los métodos virtuales se pueden invalidar para proporcionar información a un sistema de diseño.  
  
 Si crea una clase que deriva de <xref:System.Windows.FrameworkElement>, heredan la siguiente funcionalidad a la que proporcionan <xref:System.Windows.UIElement>:  
  
-   Compatibilidad con estilos y guiones gráficos. Para obtener más información, consulte <xref:System.Windows.Style> y [información general de guiones gráficos](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
-   Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos, que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   Concepto del árbol lógico. Para obtener más información, consulte [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
-   Compatibilidad con la implementación de nivel de marco WPF práctica del sistema de diseño, incluido un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> invalidación que puede detectar cambios en las propiedades que influyen en el diseño.  
  
 Si crea una clase que deriva de <xref:System.Windows.ContentElement>, heredan la siguiente funcionalidad a la que proporcionan <xref:System.Windows.DependencyObject>:  
  
-   Compatibilidad con las animaciones. Para obtener más información, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md) e [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 Si crea una clase que deriva de <xref:System.Windows.FrameworkContentElement>, obtendrá la siguiente funcionalidad a la que proporcionan <xref:System.Windows.ContentElement>:  
  
-   Compatibilidad con estilos y guiones gráficos. Para obtener más información, consulte <xref:System.Windows.Style> y [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
-   Compatibilidad con el enlace de datos. Para obtener más información, consulte [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
-   Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](../../../../docs/framework/wpf/advanced/framework-property-metadata.md).  
  
-   No hereda el acceso a las modificaciones del sistema de diseño (como <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>). Las implementaciones del sistema de diseño solo están disponibles en <xref:System.Windows.FrameworkElement>. Sin embargo, heredar un <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> invalidación que puede detectar cambios en las propiedades que influyen en el diseño y notificar a todos los hosts de contenido.  
  
 Los modelos de contenido se documentan para distintas clases. El modelo de contenido de una clase es uno de los factores posibles que debe considerar si quiere buscar una clase adecuada de la que derivar. Para obtener más información, consulte [Modelo de contenido de WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>   
## <a name="other-base-classes"></a>Otras clases base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>proporciona compatibilidad para la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] subprocesamiento de modelo y permite que todos los objetos se crean para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] aplicaciones para asociar a un <xref:System.Windows.Threading.Dispatcher>. Aunque no se derivan de <xref:System.Windows.UIElement>, <xref:System.Windows.DependencyObject>, o <xref:System.Windows.Media.Visual>, deberían considerar derivarlos del <xref:System.Windows.Threading.DispatcherObject> con el fin de obtener esta compatibilidad de modelo de subprocesamiento. Para obtener más información, consulte [Modelo de subprocesos](../../../../docs/framework/wpf/advanced/threading-model.md).  
  
### <a name="visual"></a>Elemento visual  
 <xref:System.Windows.Media.Visual>implementar el concepto de un objeto 2D que normalmente requiere la presentación visual de una región rectangular aproximadamente. La representación real de un <xref:System.Windows.Media.Visual> ocurre en otras clases (que no es autónomo), pero la <xref:System.Windows.Media.Visual> clase proporciona un tipo conocido que se usa en varios niveles de representación procesa. <xref:System.Windows.Media.Visual>implementa la prueba de posicionamiento, pero no expone eventos que informan de la prueba de posicionamiento positivos (se trata en <xref:System.Windows.UIElement>). Para obtener más información, consulte [Programación de capas visuales](../../../../docs/framework/wpf/graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Inmovilizable  
 <xref:System.Windows.Freezable>simula la inmutabilidad en un objeto mutable proporcionando los medios para generar copias del objeto cuando un objeto inmutable es requerido o deseado por motivos de rendimiento. El <xref:System.Windows.Freezable> tipo proporciona una base común para ciertos elementos gráficos, como geometrías y pinceles, así como las animaciones. En concreto, un <xref:System.Windows.Freezable> no es un <xref:System.Windows.Media.Visual>; puede contener propiedades que se convierten en subpropiedades cuando el <xref:System.Windows.Freezable> se aplica para rellenar un valor de propiedad de otro objeto, y esas subpropiedades podrían afectar a la representación. Para obtener más información, consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>es un <xref:System.Windows.Freezable> clase derivada que específicamente agrega el nivel de control de animación y algunos miembros de utilidad para que se pueden distinguir propiedades animadas actualmente desde propiedades selecciónela.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control>es la clase base deseada para el tipo de objeto que se denomina o bien un control o componente, según la tecnología. En general, las clases de control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son clases que representan directamente un control de interfaz de usuario o que participan estrechamente en la composición del control. La funcionalidad principal que <xref:System.Windows.Controls.Control> habilita es plantillas de control.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.Control>  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Arquitectura de WPF](../../../../docs/framework/wpf/advanced/wpf-architecture.md)
