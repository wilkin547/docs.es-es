---
title: Información general sobre elementos base
ms.date: 03/30/2017
helpviewer_keywords:
- base elements [WPF]
ms.assetid: 2c997092-72c6-4767-bc84-74267f4eee72
ms.openlocfilehash: 7d52d951d4fa4df83bbcca6b4cb479e18e532d2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141633"
---
# <a name="base-elements-overview"></a>Información general sobre elementos base
Un alto porcentaje [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] de clases en se derivan de cuatro clases que se conocen comúnmente en la documentación del SDK como las clases de elemento base. Estas clases <xref:System.Windows.FrameworkElement> <xref:System.Windows.ContentElement>son <xref:System.Windows.UIElement> <xref:System.Windows.FrameworkContentElement>, , , y . La <xref:System.Windows.DependencyObject> clase también está relacionada, porque es <xref:System.Windows.UIElement> una clase base común de ambos y<xref:System.Windows.ContentElement>  

<a name="base_apis"></a>
## <a name="base-element-apis-in-wpf-classes"></a>API de elementos base en clases de WPF  
 Ambos <xref:System.Windows.UIElement> <xref:System.Windows.ContentElement> y se <xref:System.Windows.DependencyObject>derivan de, a través de caminos algo diferentes. La división en este <xref:System.Windows.UIElement> nivel <xref:System.Windows.ContentElement> se ocupa de cómo se utiliza o se utilizan en una interfaz de usuario y qué propósito sirven en una aplicación. <xref:System.Windows.UIElement>también <xref:System.Windows.Media.Visual> tiene en su jerarquía de clases, que es una clase [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]que expone la compatibilidad con gráficos de nivel inferior subyacente a la . <xref:System.Windows.Media.Visual>proporciona un marco de representación mediante la definición de regiones de pantalla rectangulares independientes. En la <xref:System.Windows.UIElement> práctica, es para los elementos que admitirán un modelo de objetos más grande, están diseñados para representar y diseñar en regiones que se pueden describir como regiones de pantalla rectangulares, y donde el modelo de contenido es deliberadamente más abierto, para permitir diferentes combinaciones de elementos. <xref:System.Windows.ContentElement>no deriva <xref:System.Windows.Media.Visual>de ; su modelo es <xref:System.Windows.ContentElement> que a sería consumido por otra cosa, como un lector o visor <xref:System.Windows.Media.Visual> [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que luego interpretaría los elementos y produciría el completo para consumir. Ciertas <xref:System.Windows.UIElement> clases están diseñadas para ser hosts de <xref:System.Windows.ContentElement> contenido:<xref:System.Windows.Controls.DocumentViewer> proporcionan el hospedaje y la representación para una o más clases (es un ejemplo de dicha clase). <xref:System.Windows.ContentElement>se utiliza como clase base para elementos con modelos de objetos algo más pequeños <xref:System.Windows.UIElement>y que más abordan el texto, la información o el contenido del documento que podría hospedarse en un archivo .  
  
### <a name="framework-level-and-core-level"></a>Nivel de marco y nivel básico  
 <xref:System.Windows.UIElement>sirve como la <xref:System.Windows.FrameworkElement>clase <xref:System.Windows.ContentElement> base para , <xref:System.Windows.FrameworkContentElement>y sirve como la clase base para . La razón de este siguiente nivel de clases es admitir un nivel de núcleo wpfwpf que es independiente de un nivel de marco de WPFWPF, con esta división también existe en cómo las API se dividen entre el PresentationCore y PresentationFramework ensamblados. El nivel de marco de WPF presenta una solución más completa para las necesidades básicas de las aplicaciones, incluida la implementación del administrador de diseño para la presentación. El nivel básico de WPF proporciona una manera de usar gran parte de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sin la sobrecarga del ensamblado adicional. La distinción entre estos niveles muy rara vez importa para la mayoría [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de los escenarios de desarrollo de aplicaciones típicos y, en general, debe pensar en las API en su conjunto y no preocuparse por la diferencia entre el nivel de marco de WPFwpf y el nivel de núcleo de WPFWPF. Es posible que deba conocer las diferencias de nivel si el diseño de su aplicación opta por reemplazar una cantidad importante de funciones de nivel de marco de WPF, como, por ejemplo, si toda la solución ya tiene sus propias implementaciones de composición y diseño de [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].  
  
<a name="subclassing_elements"></a>
## <a name="choosing-which-element-to-derive-from"></a>Elección del elemento del que va a derivar  
 La manera más práctica para crear una clase personalizada que amplíe [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es que derive de una de las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], donde se obtiene la máxima cantidad de funcionalidad deseada a través de la jerarquía de clases existente. En esta sección se muestra la funcionalidad que se incluye con tres de las clases de elementos más importantes para ayudarle a decidir de qué clase se debe heredar.  
  
 Si va a implementar un control, que es realmente una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de las razones más comunes para derivar de una clase, probablemente desee <xref:System.Windows.Controls.Control> derivar de una clase que es un control práctico, una clase base de familia de control o al menos de la clase base. Para obtener orientación y ejemplos prácticos, consulte [Información general sobre la creación de controles](../controls/control-authoring-overview.md).  
  
 Si no está creando un control y necesita derivar de una clase superior en la jerarquía, las siguientes secciones son una guía de las características que se definen en cada clase de elemento base.  
  
 Si crea una clase que <xref:System.Windows.DependencyObject>deriva de , heredará la siguiente funcionalidad:  
  
- <xref:System.Windows.DependencyObject.GetValue%2A>y <xref:System.Windows.DependencyObject.SetValue%2A> el apoyo, y el apoyo general del sistema de propiedad.  
  
- Capacidad de usar las propiedades de dependencia y las propiedades adjuntas que están implementadas como propiedades de dependencia.  
  
 Si crea una clase que <xref:System.Windows.UIElement>deriva de , heredará la siguiente <xref:System.Windows.DependencyObject>funcionalidad además de la proporcionada por:  
  
- Compatibilidad básica para valores de propiedades animadas. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
- Los métodos virtuales se pueden invalidar para proporcionar información a un sistema de diseño.  
  
 Si crea una clase que <xref:System.Windows.FrameworkElement>deriva de , heredará la siguiente <xref:System.Windows.UIElement>funcionalidad además de la proporcionada por:  
  
- Compatibilidad con estilos y guiones gráficos. Para obtener más <xref:System.Windows.Style> información, vea información general sobre [guiones gráficos](../graphics-multimedia/storyboards-overview.md).  
  
- Compatibilidad con el enlace de datos. Para obtener más información, vea [Información general sobre el enlace](../data/data-binding-overview.md)de datos .  
  
- Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos, que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
- Concepto del árbol lógico. Para obtener más información, consulte [Árboles en WPF](trees-in-wpf.md).  
  
- Compatibilidad con la implementación práctica de nivel de <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> marco de WPFWPF del sistema de diseño, incluida una invalidación que puede detectar cambios en las propiedades que influyen en el diseño.  
  
 Si crea una clase que <xref:System.Windows.ContentElement>deriva de , heredará la siguiente <xref:System.Windows.DependencyObject>funcionalidad además de la proporcionada por:  
  
- Compatibilidad con las animaciones. Para obtener más información, consulte [Información general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con eventos de entrada básicos y compatibilidad con comandos. Para obtener más información, consulte [Información general sobre acciones del usuario](input-overview.md) e [Información general sobre comandos](commanding-overview.md).  
  
 Si crea una clase que <xref:System.Windows.FrameworkContentElement>deriva de , obtendrá la siguiente <xref:System.Windows.ContentElement>funcionalidad además de la proporcionada por :  
  
- Compatibilidad con estilos y guiones gráficos. Para obtener más <xref:System.Windows.Style> información, consulte Información [general sobre animaciones](../graphics-multimedia/animation-overview.md).  
  
- Compatibilidad con el enlace de datos. Para obtener más información, vea [Información general sobre el enlace](../data/data-binding-overview.md)de datos .  
  
- Compatibilidad con las referencias de recursos dinámicos. Para obtener más información, consulte [Recursos XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md).  
  
- Compatibilidad con la herencia de valores de propiedad y otras marcas en los metadatos que ayudan a comunicar condiciones sobre las propiedades a los servicios de marco, como el enlace de datos, los estilos o la implementación del marco del diseño. Para obtener más información, consulte [Metadatos de las propiedades de marco de trabajo](framework-property-metadata.md).  
  
- No se hereda el acceso a <xref:System.Windows.FrameworkElement.ArrangeOverride%2A>las modificaciones del sistema de diseño (como ). Las implementaciones del sistema <xref:System.Windows.FrameworkElement>de diseño solo están disponibles en . Sin embargo, <xref:System.Windows.FrameworkElement.OnPropertyChanged%2A> hereda una invalidación que puede detectar cambios en las propiedades que influyen en el diseño y notificarlos a cualquier host de contenido.  
  
 Los modelos de contenido se documentan para distintas clases. El modelo de contenido de una clase es uno de los factores posibles que debe considerar si quiere buscar una clase adecuada de la que derivar. Para obtener más información, consulte [Modelo de contenido de WPF](../controls/wpf-content-model.md).  
  
<a name="other_base_classes"></a>
## <a name="other-base-classes"></a>Otras clases base  
  
### <a name="dispatcherobject"></a>DispatcherObject  
 <xref:System.Windows.Threading.DispatcherObject>proporciona compatibilidad [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] con el modelo de subprocesos y permite que todos los objetos creados para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las aplicaciones se asocien a un <xref:System.Windows.Threading.Dispatcher>archivo . Incluso si no deriva <xref:System.Windows.UIElement> <xref:System.Windows.DependencyObject>de <xref:System.Windows.Media.Visual>, , o , <xref:System.Windows.Threading.DispatcherObject> debe considerar derivar de con el fin de obtener esta compatibilidad con el modelo de subprocesos. Para obtener más información, consulte [Modelo de subprocesos](threading-model.md).  
  
### <a name="visual"></a>Elemento visual  
 <xref:System.Windows.Media.Visual>implementa el concepto de un objeto 2D que generalmente requiere una presentación visual en una región aproximadamente rectangular. La representación <xref:System.Windows.Media.Visual> real de a ocurre en otras clases <xref:System.Windows.Media.Visual> (no es independiente), pero la clase proporciona un tipo conocido que se utiliza en los procesos de representación en varios niveles. <xref:System.Windows.Media.Visual>implementa pruebas de posicionación, pero no expone eventos que informan <xref:System.Windows.UIElement>de positivos de pruebas de posicionación (estos están en ). Para obtener más información, consulte [Programación de capas visuales](../graphics-multimedia/visual-layer-programming.md).  
  
### <a name="freezable"></a>Inmovilizable  
 <xref:System.Windows.Freezable>simula la inmutabilidad en un objeto mutable proporcionando los medios para generar copias del objeto cuando se requiere o se desea un objeto inmutable por motivos de rendimiento. El <xref:System.Windows.Freezable> tipo proporciona una base común para ciertos elementos gráficos como geometrías y pinceles, así como animaciones. En particular, <xref:System.Windows.Freezable> a <xref:System.Windows.Media.Visual>no es un ; puede contener propiedades que se <xref:System.Windows.Freezable> convierten en subpropiedades cuando se aplica para rellenar un valor de propiedad de otro objeto, y esas subpropiedades pueden afectar a la representación. Para obtener más información, consulte [Información general sobre objetos Freezable](freezable-objects-overview.md).  
  
 <xref:System.Windows.Media.Animation.Animatable>  
  
 <xref:System.Windows.Media.Animation.Animatable>es <xref:System.Windows.Freezable> una clase derivada que agrega específicamente la capa de control de animación y algunos miembros de la utilidad para que las propiedades animadas actualmente se puedan distinguir de las propiedades no animadas.  
  
### <a name="control"></a>Control  
 <xref:System.Windows.Controls.Control>es la clase base prevista para el tipo de objeto que se denomina de manera diversa un control o componente, dependiendo de la tecnología. En general, las clases de control [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son clases que representan directamente un control de interfaz de usuario o que participan estrechamente en la composición del control. La funcionalidad principal <xref:System.Windows.Controls.Control> que habilita es la plantillas de control.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.Control>
- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Información general sobre la creación de controles](../controls/control-authoring-overview.md)
- [Arquitectura de WPF](wpf-architecture.md)
