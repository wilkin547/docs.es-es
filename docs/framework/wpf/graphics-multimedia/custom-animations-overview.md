---
title: Información general sobre animaciones personalizadas
ms.date: 03/30/2017
helpviewer_keywords:
- custom classes [WPF], animation
- key frames [WPF], custom
- custom key frames [WPF]
- animation [WPF], custom classes
- custom animation classes [WPF]
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
ms.openlocfilehash: 5a9ca51b87f73a24b90d0bd843ee306f8a1b970a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453096"
---
# <a name="custom-animations-overview"></a>Información general sobre animaciones personalizadas
En este tema se describe cómo y cuándo extender el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogramas clave personalizados o clases de animación, o utilizando la devolución de llamada por fotograma para omitirlo.  
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 Para entender este tema, debe estar familiarizado con los distintos tipos de animación proporcionados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para más información, consulte From/To/By Animations Overview (Información general sobre animaciones From/To/By), [Key-Frame Animations Overview](key-frame-animations-overview.md) (Información general sobre animaciones de fotogramas clave) e [Información general sobre animaciones en trazados](path-animations-overview.md).  
  
 Dado que las clases de animación heredan de la clase <xref:System.Windows.Freezable>, debería estar familiarizado con <xref:System.Windows.Freezable> objetos y con la herencia de <xref:System.Windows.Freezable>. Para más información, consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
<a name="extendingtheanimationsystem"></a>   
## <a name="extending-the-animation-system"></a>Extender el sistema de animación  
 Hay varias maneras de extender el sistema de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], dependiendo del nivel de funcionalidad integrada que se desee utilizar.  Existen tres puntos principales de extensibilidad en el motor de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Cree un objeto de fotograma clave personalizado heredando de uno de los *\<tipo >* clases de fotogramas clave, como <xref:System.Windows.Media.Animation.DoubleKeyFrame>. En este enfoque se utiliza la mayoría de la funcionalidad integrada del motor de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Cree su propia clase de animación heredando de <xref:System.Windows.Media.Animation.AnimationTimeline> o de una de las clases de *\<tipo >* AnimationBase.  
  
- Utilizar la devolución de llamada por fotograma para generar animaciones fotograma a fotograma. En este enfoque se omite completamente el sistema de animación y control de tiempo.  
  
 En la tabla siguiente se describen algunos de los escenarios para extender el sistema de animación.  
  
|Si desea...|Utilice este enfoque|  
|-------------------------|-----------------------|  
|Personalizar la interpolación entre valores de un tipo que tiene un *\<Tipo >* AnimationUsingKeyFrames correspondiente|Crear un fotograma clave personalizado. Para más información, consulte la sección [Crear un fotograma clave personalizado](#createacustomkeyframe).|  
|Personalizar algo más que la interpolación entre valores de un tipo que tiene una clase *\<Tipo>* Animation correspondiente.|Crear una clase de animación personalizada que herede de la clase *\<Tipo >* AnimationBase correspondiente al tipo que desee animar. Para más información, consulte la sección [Crear una clase de animación personalizada](#createacustomanimationtype).|  
|Animar un tipo que no tenga una animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondiente|Use una <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> o cree una clase que herede de <xref:System.Windows.Media.Animation.AnimationTimeline>. Para más información, consulte la sección [Crear una clase de animación personalizada](#createacustomanimationtype).|  
|Animar varios objetos con valores que se calculan para cada fotograma y se basan en el último conjunto de interacciones de objeto|Utilizar la devolución de llamada por fotograma. Para más información, consulte la sección [Crear una devolución de llamada por fotograma](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## <a name="create-a-custom-key-frame"></a>Crear un fotograma clave personalizado  
 Crear una clase de fotograma clave personalizado es la manera más simple de extender el sistema de animación. Utilice este enfoque cuando desee utilizar un método de interpolación diferente para una animación de fotograma clave.  Como se describe en [Key-Frame Animations Overview](key-frame-animations-overview.md) (Información general sobre animaciones de fotogramas clave ), una animación de fotograma clave usa objetos de fotograma clave para generar sus valores de salida. Cada objeto de fotograma clave realiza tres funciones:  
  
- Especifica un valor de destino mediante su propiedad <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
- Especifica la hora a la que se debe alcanzar ese valor mediante su <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> propiedad.  
  
- Interpola entre el valor del fotograma clave anterior y su propio valor implementando el método InterpolateValueCore.  
  
 **Instrucciones de implementación**  
  
 Derive de la clase abstracta *\<Tipo>* Keyframe e implemente el método InterpolateValueCore. El método InterpolateValueCore devuelve el valor actual del fotograma clave. Acepta dos parámetros: el valor del fotograma clave anterior y un valor de progreso que oscila de 0 a 1. Un progreso de 0 indica que el fotograma clave se acaba de iniciar y un valor de 1 indica que el fotograma clave se acaba de completar y debe devolver el valor especificado por su propiedad <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Dado que las clases de *\<tipo >* fotogramas clave heredan de la clase <xref:System.Windows.Freezable>, también debe invalidar <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core para devolver una nueva instancia de la clase. Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 Después de haber creado la animación personalizada *\<Tipo>* Keyframe, puede usarla con la clase *\<Tipo>* AnimationUsingKeyFrames correspondiente a ese tipo.  
  
<a name="createacustomanimationtype"></a>   
## <a name="create-a-custom-animation-class"></a>Crear una clase de animación personalizada  
 Crear su propio tipo de animación le ofrece más control sobre cómo se anima un objeto. Hay dos maneras recomendadas de crear su propio tipo de animación: puede derivar de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> o del *tipo de\<>* clase AnimationBase. No se recomienda derivar de las clases *\<Tipo>* Animation o *\<Tipo>* AnimationUsingKeyFrames.  
  
### <a name="derive-from-typeanimationbase"></a>Derivar de \<Tipo>AnimationBase  
 Derivar de una clase *\<Tipo>* AnimationBase es la manera más sencilla de crear un nuevo tipo de animación. Utilice este enfoque cuando desee crear una nueva animación para un tipo que ya tiene una clase *\<Tipo>* AnimationBase correspondiente.  
  
 **Instrucciones de implementación**  
  
 Derive de una clase *\<Tipo>* Animación e implemente el método GetCurrentValueCore. El método GetCurrentValueCore devuelve el valor actual de la animación. Toma tres parámetros: un valor de inicio sugerido, un valor final sugerido y un <xref:System.Windows.Media.Animation.AnimationClock>, que se usa para determinar el progreso de la animación.  
  
 Dado que el *tipo de\<>* clases AnimationBase heredan de la clase <xref:System.Windows.Freezable>, también debe invalidar <xref:System.Windows.Freezable.CreateInstanceCore%2A> Core para devolver una nueva instancia de la clase. Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 Para más información, consulte la documentación del método GetCurrentValueCore para la clase *\<Tipo>* AnimationBase para el tipo que desee animar. Para ver un ejemplo, consulte el [ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Enfoques alternativos**  
  
 Si simplemente desea cambiar la forma en que se interpolan los valores de animación, puede que sea conveniente derivar de una de las clases *\<Tipo>* KeyFrame. El fotograma clave que se cree puede usarse con las clases *\<Tipo>* AnimationUsingKeyFrames correspondientes proporcionadas por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### <a name="derive-from-animationtimeline"></a>Derivar de AnimationTimeline  
 Derive de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> cuando desee crear una animación para un tipo que no tenga ya una animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] o que desee crear una animación que no esté fuertemente tipada.  
  
 **Instrucciones de implementación**  
  
 Derive de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> e invalide los miembros siguientes:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>: Si la nueva clase es concreta, debe invalidar <xref:System.Windows.Freezable.CreateInstanceCore%2A> para devolver una nueva instancia de la clase.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>: Invalide este método para devolver el valor actual de la animación. Toma tres parámetros: un valor de origen predeterminado, un valor de destino predeterminado y un <xref:System.Windows.Media.Animation.AnimationClock>. Utilice la <xref:System.Windows.Media.Animation.AnimationClock> para obtener la hora actual o el progreso de la animación. Puede elegir si desea usar los valores de origen y destino predeterminados.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>: invalide esta propiedad para indicar si la animación utiliza el valor de destino predeterminado especificado por el método <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>: invalide esta propiedad para indicar el <xref:System.Type> de salida que produce la animación.  
  
 Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 El paradigma recomendado (utilizado por las animaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) es usar dos niveles de herencia:  
  
1. Cree un *tipo de\<* abstracto > clase AnimationBase que derive de <xref:System.Windows.Media.Animation.AnimationTimeline>. Esta clase debe invalidar el método <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>. También debe introducir un nuevo método abstracto, GetCurrentValueCore e invalidar <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> para que valide los tipos del valor de origen predeterminado y los parámetros de valor de destino predeterminados, y, a continuación, llame a GetCurrentValueCore.  
  
2. Cree otra clase que herede de su nuevo *tipo de\<>* clase AnimationBase e invalide el método <xref:System.Windows.Freezable.CreateInstanceCore%2A>, el método GetCurrentValueCore que ha introducido y la propiedad <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>.  
  
 **Enfoques alternativos**  
  
 Si desea animar un tipo que no tiene ninguna animación from/to/by o animación de fotogramas clave correspondiente, considere la posibilidad de usar un <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>. Dado que está débilmente tipado, una <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> puede animar cualquier tipo de valor. El inconveniente de este enfoque es que <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> solo admite la interpolación discreta.  
  
<a name="useperframecallback"></a>   
## <a name="use-per-frame-callback"></a>Utilizar la devolución de llamada por fotograma  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Un escenario para este enfoque son las animaciones físicas, en las cuales es preciso volver a calcular una nueva dirección o posición de los objetos animados en cada paso de la animación de acuerdo con el último conjunto de interacciones de objeto.  
  
 **Instrucciones de implementación**  
  
 Al contrario que los demás enfoques descritos en esta información general, para utilizar la devolución de llamada por fotograma no se necesita crear una clase personalizada de animación o de fotograma clave.  
  
 En su lugar, se registra para el evento <xref:System.Windows.Media.CompositionTarget.Rendering> del objeto que contiene los objetos que desea animar. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación del fotograma actual, el <xref:System.EventArgs> asociado a este evento se puede convertir en <xref:System.Windows.Media.RenderingEventArgs>, que proporcionan una propiedad <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> que se puede usar para obtener el tiempo de representación del fotograma actual.  
  
 Para obtener más información, vea la página <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
- [Información general sobre objetos Freezable](../advanced/freezable-objects-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones en trazados ](path-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre sistemas de control de tiempo y animación ](animation-and-timing-system-overview.md)
- [Ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
