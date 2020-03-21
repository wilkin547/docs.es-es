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
ms.openlocfilehash: c5f315992e8ae37bc79602e6986d90e7af591fb2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186547"
---
# <a name="custom-animations-overview"></a>Información general sobre animaciones personalizadas
En este tema se describe cómo y cuándo extender el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogramas clave personalizados o clases de animación, o utilizando la devolución de llamada por fotograma para omitirlo.  
  
<a name="prerequisites"></a>
## <a name="prerequisites"></a>Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de animación proporcionados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para más información, consulte From/To/By Animations Overview (Información general sobre animaciones From/To/By), [Key-Frame Animations Overview](key-frame-animations-overview.md) (Información general sobre animaciones de fotogramas clave) e [Información general sobre animaciones en trazados](path-animations-overview.md).  
  
 Dado que las clases de animación heredan de la <xref:System.Windows.Freezable> clase, debe estar familiarizado con <xref:System.Windows.Freezable> los objetos y cómo heredar de <xref:System.Windows.Freezable>. Para más información, consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
<a name="extendingtheanimationsystem"></a>
## <a name="extending-the-animation-system"></a>Extender el sistema de animación  
 Hay varias maneras de extender el sistema de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], dependiendo del nivel de funcionalidad integrada que se desee utilizar.  Existen tres puntos principales de extensibilidad en el motor de animación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
- Cree un objeto de marco de clave * \< *personalizado heredando de una de las clases Type>KeyFrame, como <xref:System.Windows.Media.Animation.DoubleKeyFrame>. En este enfoque se utiliza la mayoría de la funcionalidad integrada del motor de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
- Cree su propia clase de <xref:System.Windows.Media.Animation.AnimationTimeline> animación heredando de o una de las * \< *clases Type>AnimationBase.  
  
- Utilizar la devolución de llamada por fotograma para generar animaciones fotograma a fotograma. En este enfoque se omite completamente el sistema de animación y control de tiempo.  
  
 En la tabla siguiente se describen algunos de los escenarios para extender el sistema de animación.  
  
|Si desea...|Utilice este enfoque|  
|-------------------------|-----------------------|  
|Personalizar la interpolación entre los valores de un tipo que tiene un * \<tipo *correspondiente>AnimationUsingKeyFrames|Crear un fotograma clave personalizado. Para más información, consulte la sección [Crear un fotograma clave personalizado](#createacustomkeyframe).|  
|Personalice más que solo la interpolación entre los valores de un tipo que tenga un * \<tipo>* animación correspondiente.|Cree una clase de animación * \< *personalizada que herede de la clase Type>AnimationBase que corresponda al tipo que desea animar. Para más información, consulte la sección [Crear una clase de animación personalizada](#createacustomanimationtype).|  
|Animar un tipo que no tenga una animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondiente|Utilice <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> una clase o cree <xref:System.Windows.Media.Animation.AnimationTimeline>una clase que herede de . Para más información, consulte la sección [Crear una clase de animación personalizada](#createacustomanimationtype).|  
|Animar varios objetos con valores que se calculan para cada fotograma y se basan en el último conjunto de interacciones de objeto|Utilizar la devolución de llamada por fotograma. Para más información, consulte la sección [Crear una devolución de llamada por fotograma](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>
## <a name="create-a-custom-key-frame"></a>Crear un fotograma clave personalizado  
 Crear una clase de fotograma clave personalizado es la manera más simple de extender el sistema de animación. Utilice este enfoque cuando desee utilizar un método de interpolación diferente para una animación de fotograma clave.  Como se describe en [Key-Frame Animations Overview](key-frame-animations-overview.md) (Información general sobre animaciones de fotogramas clave ), una animación de fotograma clave usa objetos de fotograma clave para generar sus valores de salida. Cada objeto de fotograma clave realiza tres funciones:  
  
- Especifica un valor de <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> destino mediante su propiedad.  
  
- Especifica la hora a la que se <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A> debe alcanzar ese valor mediante su propiedad.  
  
- Interpola entre el valor del fotograma clave anterior y su propio valor implementando el método InterpolateValueCore.  
  
 **Instrucciones de implementación**  
  
 Derive de * \< *la Type>KeyFrame clase abstracta e implemente el InterpolateValueCore método. El método InterpolateValueCore devuelve el valor actual del fotograma clave. Acepta dos parámetros: el valor del fotograma clave anterior y un valor de progreso que oscila de 0 a 1. Un progreso de 0 indica que el fotograma clave acaba de iniciarse y un valor de 1 indica <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A> que el fotograma clave se acaba de completar y debe devolver el valor especificado por su propiedad.  
  
 Dado * \< *que el Type><xref:System.Windows.Freezable> KeyFrame clases <xref:System.Windows.Freezable.CreateInstanceCore%2A> heredan de la clase, también debe invalidar core para devolver una nueva instancia de la clase. Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 Después de crear la animación personalizada * \<Type>* KeyFrame, puede usarla con * \<el>De tipo *AnimationUsingKeyFrames para ese tipo.  
  
<a name="createacustomanimationtype"></a>
## <a name="create-a-custom-animation-class"></a>Crear una clase de animación personalizada  
 Crear su propio tipo de animación le ofrece más control sobre cómo se anima un objeto. Hay dos formas recomendadas de crear su propio <xref:System.Windows.Media.Animation.AnimationTimeline> tipo de animación: puede derivar de la clase o * \<el tipo>* clase AnimationBase. Derivado de * \< *la Type>Animation o * \<Type>* AnimationUsingKeyFrames clases no se recomienda.  
  
### <a name="derive-from-typeanimationbase"></a>Derivar de \<Tipo>AnimationBase  
 Derivado de * \< *un Type>AnimationBase clase es la forma más sencilla de crear un nuevo tipo de animación. Utilice este enfoque cuando desee crear una nueva animación para el tipo que ya tiene un * \<tipo *correspondiente>clase AnimationBase.  
  
 **Instrucciones de implementación**  
  
 Derive de * \< *un Type>Animation clase e implemente el GetCurrentValueCore método. El método GetCurrentValueCore devuelve el valor actual de la animación. Toma tres parámetros: un valor inicial sugerido, <xref:System.Windows.Media.Animation.AnimationClock>un valor final sugerido y un , que se utiliza para determinar el progreso de la animación.  
  
 Dado * \< *que el Type><xref:System.Windows.Freezable> AnimationBase clases <xref:System.Windows.Freezable.CreateInstanceCore%2A> heredan de la clase, también debe invalidar core para devolver una nueva instancia de la clase. Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 Para obtener más información, vea la documentación * \< *del método GetCurrentValueCore para la clase Type>AnimationBase para el tipo que desea animar. Para ver un ejemplo, consulte el [ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)  
  
 **Enfoques alternativos**  
  
 Si simplemente desea cambiar la forma en que se interpolan los valores de animación, considere la posibilidad de derivar de una de las * \<clases Type>* KeyFrame. El fotograma clave que cree se puede utilizar con el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]>* \<correspondiente *AnimationUsingKeyFrames proporcionado por .  
  
### <a name="derive-from-animationtimeline"></a>Derivar de AnimationTimeline  
 Derive de <xref:System.Windows.Media.Animation.AnimationTimeline> la clase cuando desee crear una animación para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un tipo que aún no tiene una animación coincidente o si desea crear una animación que no esté fuertemente tipada.  
  
 **Instrucciones de implementación**  
  
 Derive de <xref:System.Windows.Media.Animation.AnimationTimeline> la clase e invalide los siguientes miembros:  
  
- <xref:System.Windows.Freezable.CreateInstanceCore%2A>– Si la nueva clase es <xref:System.Windows.Freezable.CreateInstanceCore%2A> concreta, debe reemplazar para devolver una nueva instancia de la clase.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>– Invalide este método para devolver el valor actual de la animación. Toma tres parámetros: un valor de origen predeterminado, un valor de destino predeterminado y un <xref:System.Windows.Media.Animation.AnimationClock>archivo . Utilice <xref:System.Windows.Media.Animation.AnimationClock> el para obtener la hora actual o el progreso de la animación. Puede elegir si desea usar los valores de origen y destino predeterminados.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>– Invalide esta propiedad para indicar si la animación utiliza el valor de destino predeterminado especificado por el <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> método.  
  
- <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>– Invalide esta <xref:System.Type> propiedad para indicar la salida que produce la animación.  
  
 Si la clase no utiliza propiedades de dependencia para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable).  
  
 El paradigma recomendado (utilizado por las animaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]) es usar dos niveles de herencia:  
  
1. Cree un * \<>* abstracto Clase AnimationBase que derive de <xref:System.Windows.Media.Animation.AnimationTimeline>. Esta clase debe <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A> invalidar el método. También debe introducir un nuevo método abstracto, <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> GetCurrentValueCore, y reemplazar para que valide los tipos del valor de origen predeterminado y los parámetros de valor de destino predeterminados y, a continuación, llama a GetCurrentValueCore.  
  
2. Cree otra clase que herede de la nueva <xref:System.Windows.Freezable.CreateInstanceCore%2A> <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A> * \<clase Type>* AnimationBase e invalide el método, el método GetCurrentValueCore que introdujo y la propiedad.  
  
 **Enfoques alternativos**  
  
 Si desea animar un tipo que no tiene ninguna animación From/To/By <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>correspondiente o animación de fotograma clave, considere la posibilidad de utilizar un archivo . Dado que está débilmente <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> tipado, un puede animar cualquier tipo de valor. El inconveniente de este <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> enfoque es que solo admite la interpolación discreta.  
  
<a name="useperframecallback"></a>
## <a name="use-per-frame-callback"></a>Utilizar la devolución de llamada por fotograma  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Un escenario para este enfoque son las animaciones físicas, en las cuales es preciso volver a calcular una nueva dirección o posición de los objetos animados en cada paso de la animación de acuerdo con el último conjunto de interacciones de objeto.  
  
 **Instrucciones de implementación**  
  
 Al contrario que los demás enfoques descritos en esta información general, para utilizar la devolución de llamada por fotograma no se necesita crear una clase personalizada de animación o de fotograma clave.  
  
 En su lugar, <xref:System.Windows.Media.CompositionTarget.Rendering> se registra para el evento del objeto que contiene los objetos que desea animar. Se llama a este método de control de eventos una vez por cada fotograma. Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] serializa los datos de representación conservados en el árbol visual hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación <xref:System.EventArgs> del fotograma actual, <xref:System.Windows.Media.RenderingEventArgs>el asociado <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> a este evento se puede convertir como , que proporcionan una propiedad que puede usar para obtener el tiempo de representación del fotograma actual.  
  
 Para obtener más <xref:System.Windows.Media.CompositionTarget.Rendering> información, consulte la página.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Animation.AnimationTimeline>
- <xref:System.Windows.Media.Animation.IKeyFrame>
- [Información general sobre técnicas de animación de propiedades](property-animation-techniques-overview.md)
- [Freezable Objects Overview](../advanced/freezable-objects-overview.md) (Información general sobre objetos Freezable)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones en trazados ](path-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre sistemas de control de tiempo y animación](animation-and-timing-system-overview.md)
- [Ejemplo de animación personalizada](https://github.com/Microsoft/WPF-Samples/tree/master/Animation/CustomAnimation)
