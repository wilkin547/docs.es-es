---
title: "Informaci&#243;n general sobre animaciones personalizadas | Microsoft Docs"
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
  - "animación, clases personalizadas"
  - "clases de animación personalizadas"
  - "clases personalizadas, animación"
  - "fotogramas clave personalizados"
  - "fotogramas clave, personalizadas"
ms.assetid: 9be69d50-3384-4938-886f-08ce00e4a7a6
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre animaciones personalizadas
En este tema se describe cómo y cuándo extender el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] creando fotogramas clave personalizados o clases de animación, o utilizando la devolución de llamada por fotograma para omitirlo.  
  
<a name="autoTopLevelSectionsOUTLINE0"></a>   
<a name="prerequisites"></a>   
## Requisitos previos  
 Para entender este tema, debe estar familiarizado con los distintos tipos de animación proporcionados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Para obtener más información, consulte [Información general sobre animaciones From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md), [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md) y [Información general sobre animaciones en trazados](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md).  
  
 Dado que las clases de animación heredan de la clase <xref:System.Windows.Freezable>, debe estar familiarizado con los objetos <xref:System.Windows.Freezable> y con cómo heredan de <xref:System.Windows.Freezable>.  Para obtener más información, vea [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
<a name="extendingtheanimationsystem"></a>   
## Extender el sistema de animación  
 Hay varias maneras de extender el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], dependiendo del nivel de funcionalidad integrada que se desee utilizar.  Existen tres puntos principales de extensibilidad en el motor de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:  
  
-   Crear un objeto de fotograma clave personalizado heredando de una de las clases *\<Tipo\>*KeyFrame, como <xref:System.Windows.Media.Animation.DoubleKeyFrame>.  En este enfoque se utiliza la mayoría de la funcionalidad integrada del motor de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
-   Crear su propia clase de animación heredando de <xref:System.Windows.Media.Animation.AnimationTimeline> o de una de las clases *\<Tipo\>*AnimationBase.  
  
-   Utilizar la devolución de llamada por fotograma para generar animaciones fotograma a fotograma.  En este enfoque se omite completamente el sistema de animación y control de tiempo.  
  
 En la tabla siguiente se describen algunos de los escenarios para extender el sistema de animación.  
  
|Si desea...|Utilice este enfoque|  
|-----------------|--------------------------|  
|Personalizar la interpolación entre valores de un tipo que tiene una clase *\<Tipo\>*AnimationUsingKeyFrames correspondiente|Crear un fotograma clave personalizado.  Para obtener más información, consulte la sección [Crear un fotograma clave personalizado](#createacustomkeyframe).|  
|Personalizar algo más que simplemente la interpolación entre valores de un tipo que tiene una clase *\<Tipo\>*Animation correspondiente.|Crear una clase de animación personalizada que herede de la clase *\<Tipo\>*AnimationBase correspondiente al tipo que desee animar.  Para obtener más información, consulte la sección [Crear una clase de animación personalizada](#createcustomanimationtype).|  
|Animar un tipo que no tiene ninguna animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondiente|Utilizar <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> o crear una clase que herede de <xref:System.Windows.Media.Animation.AnimationTimeline>.  Para obtener más información, consulte la sección [Crear una clase de animación personalizada](#createcustomanimationtype).|  
|Animar varios objetos con valores que se calculan para cada fotograma y se basan en el último conjunto de interacciones de objeto|Utilizar la devolución de llamada por fotograma.  Para obtener más información, consulte la sección [Utilizar la devolución de llamada por fotograma](#useperframecallback).|  
  
<a name="createacustomkeyframe"></a>   
## Crear un fotograma clave personalizado  
 Crear una clase de fotograma clave personalizado es la manera más simple de extender el sistema de animación.  Utilice este enfoque cuando desee utilizar un método de interpolación diferente para una animación de fotograma clave.  Como se describe en [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md), una animación de fotograma clave objetos de fotograma clave para generar sus valores de salida.  Cada objeto de fotograma clave realiza tres funciones:  
  
-   Especifica un valor de destino mediante su propiedad <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
-   Especifica la hora a la que se alcanzará ese valor mediante la propiedad <xref:System.Windows.Media.Animation.IKeyFrame.KeyTime%2A>.  
  
-   Interpola entre el valor del fotograma clave anterior y su propio valor implementando el método InterpolateValueCore.  
  
 **Instrucciones de implementación**  
  
 Derive de la clase abstracta *\<Tipo\>*KeyFrame e implemente el método InterpolateValueCore.  El método InterpolateValueCore devuelve el valor actual del fotograma clave.  Acepta dos parámetros: el valor del fotograma clave anterior y un valor de progreso que oscila de 0 a 1.  Un progreso de 0 indica que el fotograma clave se acaba de iniciar, y un valor de 1 indica que el fotograma clave se acaba de completar y debe devolver el valor especificado por su propiedad <xref:System.Windows.Media.Animation.IKeyFrame.Value%2A>.  
  
 Dado que las clases *\<Tipo\>*KeyFrame heredan de la clase <xref:System.Windows.Freezable>, también debe invalidar el núcleo del método <xref:System.Windows.Freezable.CreateInstanceCore%2A> para devolver una nueva instancia de la clase.  Si la clase no utiliza [propiedades de dependencia](GTMT) para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md) para obtener más información.  
  
 Después de haber creado la animación personalizada de *\<Tipo\>*KeyFrame, puede utilizarla con la clase *\<Tipo\>*AnimationUsingKeyFrames correspondiente a ese tipo.  
  
<a name="createacustomanimationtype"></a>   
## Crear una clase de animación personalizada  
 Crear su propio tipo de animación le ofrece más control sobre cómo se anima un objeto.  Hay dos maneras recomendadas de crear su propio tipo de animación: puede derivar de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> o de la clase *\<Tipo\>*AnimationBase.  No se recomienda derivar de las clases *\<Tipo\>*Animation o *\<Tipo\>*AnimationUsingKeyFrames.  
  
### Derivar de \<Tipo\>AnimationBase  
 Derivar de una clase *\<Tipo\>*AnimationBase es la manera más sencilla de crear un nuevo tipo de animación.  Utilice este enfoque cuando desee crear una nueva animación para un tipo que ya tiene una clase *\<Tipo\>*AnimationBase correspondiente.  
  
 **Instrucciones de implementación**  
  
 Derive de una clase *\<Tipo\>*Animation e implemente el método GetCurrentValueCore.  El método GetCurrentValueCore devuelve el valor actual de la animación.  Acepta tres parámetros: un valor inicial sugerido, un valor final sugerido y un <xref:System.Windows.Media.Animation.AnimationClock>, que se utiliza para determinar el progreso de la animación.  
  
 Dado que las clases *\<Tipo\>*AnimationBase heredan de la clase <xref:System.Windows.Freezable>, también debe invalidar el núcleo del método <xref:System.Windows.Freezable.CreateInstanceCore%2A> para devolver una nueva instancia de la clase.  Si la clase no utiliza [propiedades de dependencia](GTMT) para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md) para obtener más información.  
  
 Para obtener más información, consulte la documentación del método GetCurrentValueCore correspondiente a la clase *\<Tipo\>*AnimationBase del tipo que desea animar.  Para obtener un ejemplo, vea [Custom Animation Sample](http://go.microsoft.com/fwlink/?LinkID=159981)  
  
 **Enfoques alternativos**  
  
 Si simplemente desea cambiar cómo se interpolan los valores de animación, puede ser conveniente derivar de una de las clases *\<Tipo\>*KeyFrame.  El fotograma clave que se crea se puede utilizar con las clases *\<Tipo\>*AnimationUsingKeyFrames correspondientes proporcionadas por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
### Derivar de AnimationTimeline  
 Derive de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> cuando desee crear una animación para un tipo que aún no tiene una animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] correspondiente, o cuando desee crear una animación que no esté fuertemente tipada.  
  
 **Instrucciones de implementación**  
  
 Derive de la clase <xref:System.Windows.Media.Animation.AnimationTimeline> e invalide los miembros siguientes:  
  
-   <xref:System.Windows.Freezable.CreateInstanceCore%2A>: si la nueva clase es concreta, debe invalidar <xref:System.Windows.Freezable.CreateInstanceCore%2A> para devolver una nueva instancia de la clase.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>: invalide este método para devolver el valor actual de la animación.  Acepta tres parámetros: un valor de origen predeterminado, un valor de destino predeterminado y un objeto <xref:System.Windows.Media.Animation.AnimationClock>.  Utilice <xref:System.Windows.Media.Animation.AnimationClock> para obtener la hora actual o el progreso de la animación.  Puede decidir si usar los valores de origen y destino predeterminados.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>: invalide esta propiedad para indicar si la animación usa el valor de destino predeterminado especificado por el método <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A>.  
  
-   <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>: invalide esta propiedad para indicar el objeto <xref:System.Type> de salida que genera la animación.  
  
 Si la clase no utiliza [propiedades de dependencia](GTMT) para almacenar sus datos o requiere que se inicialice otra vez después de haberse creado, es posible que tenga que invalidar otros métodos; consulte [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md) para obtener más información.  
  
 El paradigma recomendado \(utilizado por las animaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\) es utilizar dos niveles de herencia:  
  
1.  Cree una clase *\<Tipo\>*AnimationBase abstracta que se derive de <xref:System.Windows.Media.Animation.AnimationTimeline>.  Esta clase debe invalidar el método <xref:System.Windows.Media.Animation.AnimationTimeline.TargetPropertyType%2A>.  También debe introducir un nuevo método abstracto, GetCurrentValueCore, e invalidar <xref:System.Windows.Media.Animation.AnimationTimeline.GetCurrentValue%2A> para validar el valor de origen y los parámetros de los valores de destino predeterminados; por último, llama a GetCurrentValueCore.  
  
2.  Cree otra clase que herede de la nueva clase *\<Tipo\>*AnimationBase e invalide el método <xref:System.Windows.Freezable.CreateInstanceCore%2A>, el método GetCurrentValueCore que ha introducido y la propiedad <xref:System.Windows.Media.Animation.AnimationTimeline.IsDestinationDefault%2A>.  
  
 **Enfoques alternativos**  
  
 Si desea animar un tipo que no tiene ninguna animación From\/To\/By ni animación de fotograma clave correspondiente, puede ser interesante utilizar <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames>.  Al no tener establecimiento inflexible de tipos, <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> puede animar cualquier tipo de valor.  La desventaja a este enfoque es que <xref:System.Windows.Media.Animation.ObjectAnimationUsingKeyFrames> admite únicamente la [interpolación discreta](GTMT).  
  
<a name="useperframecallback"></a>   
## Utilizar la devolución de llamada por fotograma  
 Utilice este enfoque cuando necesite omitir completamente el sistema de animación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  Un escenario para este enfoque son las animaciones físicas, en las cuales es preciso volver a calcular una nueva dirección o posición de los objetos animados en cada paso de la animación de acuerdo con el último conjunto de interacciones de objeto.  
  
 **Instrucciones de implementación**  
  
 Al contrario que los demás enfoques descritos en esta información general, para utilizar la devolución de llamada por fotograma no se necesita crear una clase personalizada de animación o de fotograma clave.  
  
 En su lugar, se efectúa el registro para el evento <xref:System.Windows.Media.CompositionTarget.Rendering> del objeto que contiene los objetos que se desea animar.  Se llama a este método de control de eventos una vez por cada fotograma.  Cada vez que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] calcula las referencias de los datos de representación conservados en el [árbol visual](GTMT) hasta el árbol de composición, se llama a este método de control de eventos.  
  
 En el controlador de eventos, realice los cálculos necesarios para el efecto de animación y establezca las propiedades de los objetos que desea animar con estos valores.  
  
 Para obtener el tiempo de presentación del fotograma actual, puede convertir el <xref:System.EventArgs> asociado a este evento como <xref:System.Windows.Media.RenderingEventArgs>, que proporciona una propiedad <xref:System.Windows.Media.RenderingEventArgs.RenderingTime%2A> que puede utilizar para obtener el tiempo de representación del fotograma actual.  
  
 Para obtener más información, vea la página <xref:System.Windows.Media.CompositionTarget.Rendering>.  
  
## Vea también  
 <xref:System.Windows.Media.Animation.AnimationTimeline>   
 <xref:System.Windows.Media.Animation.IKeyFrame>   
 [Información general sobre técnicas de animación de propiedades](../../../../docs/framework/wpf/graphics-multimedia/property-animation-techniques-overview.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Información general sobre animaciones From\/To\/By](../../../../docs/framework/wpf/graphics-multimedia/from-to-by-animations-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Información general sobre animaciones en trazados](../../../../docs/framework/wpf/graphics-multimedia/path-animations-overview.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Información general sobre sistemas de temporización y animación](../../../../docs/framework/wpf/graphics-multimedia/animation-and-timing-system-overview.md)   
 [Ejemplo Custom Animation](http://go.microsoft.com/fwlink/?LinkID=159981)