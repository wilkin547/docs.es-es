---
title: "Prioridad de los valores de propiedades de dependencia | Microsoft Docs"
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
  - "clases, propietarias de propiedades de dependencia"
  - "propiedades de dependencia, clases propietarias"
  - "propiedades de dependencia, metadatos"
  - "metadatos, propiedades de dependencia"
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
caps.latest.revision: 27
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Prioridad de los valores de propiedades de dependencia
<a name="introduction"></a> En este tema se explica el modo en que los mecanismos del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] pueden afectar al valor de una [propiedad de dependencia](GTMT), y se describe la prioridad por la que ciertos aspectos del sistema de propiedades se aplican al valor efectivo de una propiedad.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Requisitos previos  
 En este tema se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], y que ha leído el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para seguir los ejemplos de este tema, también debería entender [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y saber escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## El sistema de animación de propiedades de WPF  
 El sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona una manera eficaz de determinar el valor de las propiedades de dependencia mediante diversos factores, lo que posibilita características como la validación de propiedades en tiempo real, el enlace en tiempo de ejecución y la notificación a las propiedades relacionadas de los cambios en los valores de otras propiedades.  El orden y la lógica exactos que se utilizan para determinar los valores de propiedad de dependencia son relativamente complejos.  Conocer este orden le ayudará a evitar establecer propiedades sin necesidad y también podrá eliminar la confusión sobre el motivo exacto por el cual algún intento de influir o prever el valor de una propiedad de dependencia no produjo el valor esperado.  
  
<a name="multiple_sets"></a>   
## Las propiedades de dependencia se pueden "establecer" en varios lugares  
 A continuación se muestra [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de ejemplo en el que la misma propiedad \(<xref:System.Windows.Controls.Control.Background%2A>\) tiene tres operaciones "set" que podrían influir en su valor.  
  
 [!code-xml[PropertiesOvwSupport#DPPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 ¿Aquí, qué color espera que se aplique, rojo, verde o azul?  
  
 Con la excepción de los valores animados y la conversión, los conjuntos de propiedades locales se establecen con la mayor prioridad.  Si establece un valor localmente, puede esperar que dicho valor tendrá prioridad, incluso sobre cualquier estilo o sobre las plantillas de los controles.  En nuestro ejemplo, <xref:System.Windows.Controls.Control.Background%2A> se establece en el color rojo \(Red\) de forma local.  Por consiguiente el estilo definido en este ámbito, aunque se trata de un estilo implícito que en otro caso se aplicaría a todos los elementos de ese tipo en ese ámbito, no tiene la máxima prioridad para dar su valor a la propiedad <xref:System.Windows.Controls.Control.Background%2A>.  Si quitara el valor local Red de esa instancia de Button, el estilo tendría prioridad y el botón obtendría el valor Background del estilo.  Dentro del estilo, los desencadenadores tienen prioridad, por lo que el botón será azul si el mouse está encima, y verde en caso contrario.  
  
<a name="listing"></a>   
## Lista de prioridad para el establecimiento de propiedades de dependencia  
 A continuación se muestra el orden definitivo que utiliza el sistema de propiedades al asignar los valores de las propiedades de dependencia en tiempo de ejecución.  En primer lugar se indican los que tienen mayor prioridad.  Esta lista desarrolla algunas de las generalizaciones realizadas en el tema [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
1.  **Conversión del sistema de propiedades.** Para obtener detalles sobre la conversión, vea [Conversión, animaciones y valor base](#animations) más adelante en este tema.  
  
2.  **Animaciones activas o animaciones con un comportamiento de bloqueo.** Para tener cualquier efecto práctico, una animación de una propiedad debe poder tener prioridad sobre el valor base \(inanimado\), incluso si dicho valor se estableció localmente.  Para obtener información detallada, vea [Conversión, animaciones y valor base](#animations) más adelante en este tema.  
  
3.  **Valor local.** Un valor local se podría establecer a través de la comodidad de la propiedad de "contenedor", que también equivale a establecer como un atributo o elemento de propiedad en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], o mediante una llamada al método <xref:System.Windows.DependencyObject.SetValue%2A>[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] utilizando una propiedad de una instancia concreta.  Si establece un valor local utilizando un enlace o un recurso, cada uno de ellos actúa con la misma prioridad que si se estableciera un valor directo.  
  
4.  **Propiedades de plantilla TemplatedParent.** Un elemento tiene la propiedad <xref:System.Windows.FrameworkElement.TemplatedParent%2A> si se creó como parte de una plantilla \(<xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>\).  Para obtener información detallada sobre cuándo se aplica esto, vea [TemplatedParent](#templatedparent) más adelante en este tema.  Dentro de la plantilla, se aplica la prioridad siguiente:  
  
    1.  Desencadenadores de la plantilla <xref:System.Windows.FrameworkElement.TemplatedParent%2A>.  
  
    2.  Conjuntos de propiedades \(normalmente a través de atributos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] \) de la plantilla <xref:System.Windows.FrameworkElement.TemplatedParent%2A>.  
  
5.  **Estilo implícito.** Sólo se aplica a la propiedad `Style`.  La propiedad `Style` se llena con cualquier recurso de estilo cuya clave coincida con el tipo de ese elemento.  Ese recurso de estilo debe existir o en la página o en la aplicación; la búsqueda de un recurso de estilo implícito no continúa en los temas.  
  
6.  **Desencadenadores de los estilos.** Los desencadenadores incluidos en los estilos de la página o la aplicación \(estos estilos podrían ser explícitos o implícitos, pero no proceder de los estilos predeterminados, que tienen una prioridad más baja\).  
  
7.  **Desencadenadores de la plantilla.** Cualquier desencadenador de una plantilla incluida en un estilo o de una plantilla aplicada directamente.  
  
8.  **Establecedores de estilo.** Valores procedentes de un elemento <xref:System.Windows.Setter> procedente de la página o la aplicación.  
  
9. **Estilo predeterminado \(tema\).** Para obtener información más detallada sobre cuándo se aplica y cómo se relacionan los estilos del tema con las plantillas incluidas en los estilos del tema, vea [Estilos predeterminados \(tema\)](#themestyles) más adelante en este tema.  Dentro de un estilo predeterminado se aplica el orden de prioridad siguiente:  
  
    1.  Desencadenadores activos del estilo del tema.  
  
    2.  Establecedores del estilo del tema.  
  
10. **Herencia.** Algunas propiedades de dependencia heredan sus valores del elemento primario a los elementos secundarios, de forma que es necesario establecerlas específicamente en cada elemento de la aplicación.  Para obtener información detallada, vea [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
11. **Valor predeterminado de los metadatos de la propiedad de dependencia.** Cualquier propiedad de dependencia determinada puede tener un valor predeterminado establecido por el registro del sistema de propiedades de esa propiedad concreta.  Asimismo, las clases derivadas que heredan una propiedad de dependencia tienen la opción de invalidar esos metadatos \(incluso el valor predeterminado\) para cada tipo.  Vea [Metadatos de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md) para obtener más información.  Dado que la herencia se comprueba antes que el valor predeterminado, para una propiedad heredada un valor predeterminado del elemento primario tiene prioridad sobre un elemento secundario.  Por consiguiente, si no se establece una propiedad heredable en ninguna parte, se utiliza el valor predeterminado tal como se ha especificado en la raíz o en el elemento primario en lugar del valor predeterminado del elemento secundario.  
  
<a name="templatedparent"></a>   
## TemplatedParent  
 TemplatedParent no se aplica como un elemento de prioridad a cualquier propiedad de un elemento que se declara directamente en el marcado de la aplicación estándar.  El concepto de TemplatedParent sólo existe para los elementos secundarios dentro de un árbol visual que se generan al aplicar la plantilla.  Cuando el sistema de propiedades busca un valor en la plantilla <xref:System.Windows.FrameworkElement.TemplatedParent%2A>, está buscando en la plantilla que creó ese elemento.  Los valores de propiedades procedentes de la plantilla <xref:System.Windows.FrameworkElement.TemplatedParent%2A> generalmente se comportan como si se hubieran establecido como un valor local en el elemento secundario, pero esta prioridad menor frente a la del valor local existe porque es posible que las plantillas se compartan.  Para obtener información detallada, vea <xref:System.Windows.FrameworkElement.TemplatedParent%2A>.  
  
<a name="style_property"></a>   
## La propiedad Style.  
 El orden de búsqueda descrito anteriormente se aplica a todas las propiedades de dependencia posibles excepto una: la propiedad <xref:System.Windows.FrameworkElement.Style%2A>.  La propiedad <xref:System.Windows.FrameworkElement.Style%2A> es única porque no se le pueden aplicar estilos, por lo que no le aplican los elementos de prioridad del 5 al 8.  Asimismo, no se recomienda animar o convertir <xref:System.Windows.FrameworkElement.Style%2A> \(animar <xref:System.Windows.FrameworkElement.Style%2A> requeriría una clase de animación personalizada\).  De este modo, quedan tres formas en las que se podría establecer la propiedad <xref:System.Windows.FrameworkElement.Style%2A>:  
  
-   **Estilo explícito.** El valor de la propiedad <xref:System.Windows.FrameworkElement.Style%2A> se establece directamente.  En la mayoría de los escenarios, el estilo no se define en el propio código, sino que se hace referencia a él como un recurso, por clave explícita.  En este caso, la propia propiedad Style se comporta como si fuera un valor local, es decir, un elemento de prioridad 3.  
  
-   **Estilo implícito.** El valor de la propiedad <xref:System.Windows.FrameworkElement.Style%2A> no se establece directamente.  Sin embargo, <xref:System.Windows.FrameworkElement.Style%2A> existe en algún nivel en la secuencia de búsqueda de recursos \(página, aplicación\) y se le asigna una clave utilizando una clave de recurso que coincide con el tipo al que debe aplicarse el estilo.  En este caso, la propia propiedad <xref:System.Windows.FrameworkElement.Style%2A> adquiere una prioridad identificada en la secuencia como elemento de nivel 5.  Esta condición se puede detectar utilizando <xref:System.Windows.DependencyPropertyHelper> con la propiedad <xref:System.Windows.FrameworkElement.Style%2A> y buscando <xref:System.Windows.BaseValueSource> en los resultados.  
  
-   **Estilo predeterminado**, también conocido como **el estilo del tema**. La propiedad <xref:System.Windows.FrameworkElement.Style%2A> no se establece directamente y de hecho se leerá como `null` hasta el tiempo de ejecución.  En este caso, el estilo procede de la evaluación del tema en tiempo de ejecución que forma parte del motor de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para los estilos implícitos que no pertenecen a los temas, el tipo debe coincidir exactamente: una clase derivada de `MyButton` `Button` no utilizará implícitamente un estilo para `Button`.  
  
<a name="themestyles"></a>   
## Estilos predeterminados \(tema\)  
 Cada control que se distribuye con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tiene un estilo predeterminado.  Ese estilo predeterminado puede variar para cada tema, motivo por el que a veces se le conoce como estilo del tema.  
  
 La información más importante que se incluye en un estilo predeterminado para un control es su plantilla de control, que existe en el estilo del tema como un establecedor para su propiedad <xref:System.Windows.Controls.Control.Template%2A>.  Si no hubiera ninguna plantilla en los estilos predeterminados, un control sin una plantilla personalizada como parte de un estilo personalizado no tendría ninguna apariencia visual.  La plantilla del estilo predeterminado da una estructura básica a la apariencia visual de cada control y también define las conexiones entre las propiedades definidas en el árbol visual de la plantilla y la clase de control correspondiente.  Cada control expone un conjunto de propiedades que pueden influir en la apariencia visual del control sin reemplazar la plantilla por completo.  Por ejemplo, considere la apariencia visual predeterminada de un control <xref:System.Windows.Controls.Primitives.Thumb>, que es un componente de <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 Un control <xref:System.Windows.Controls.Primitives.Thumb> tiene ciertas propiedades personalizables.  La plantilla predeterminada de un control <xref:System.Windows.Controls.Primitives.Thumb> crea una estructura básica o árbol visual con varios componentes <xref:System.Windows.Controls.Border> anidados para crear una apariencia de tipo bisel.  Si se va a exponer una propiedad que forma parte de la plantilla para que la personalice la clase <xref:System.Windows.Controls.Primitives.Thumb>, dicha propiedad debe ser expuesta mediante [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) dentro de la plantilla.  En el caso de <xref:System.Windows.Controls.Primitives.Thumb>, varias propiedades de estos bordes comparten un enlace de plantilla a propiedades como <xref:System.Windows.Controls.Border.Background%2A> o <xref:System.Windows.Controls.Border.BorderThickness%2A>.  Pero algunas otras propiedades u organizaciones visuales están incluidas en el código de la plantilla de control o se enlazan a valores que proceden directamente del tema y no se pueden cambiar salvo reemplazando la plantilla completa.  Generalmente, si una propiedad procede de un elemento primario con plantilla y no se expone mediante un enlace de plantilla, no puede ajustarse mediante los estilos, porque no hay ninguna manera sencilla de especificarla como destino.  Pero la herencia de valores de propiedades de la plantilla aplicada todavía podría influir en esa propiedad, igual que podría hacerlo el valor predeterminado.  
  
 Los estilos del tema utilizan un tipo como clave en sus definiciones.  Sin embargo, cuando se aplican temas a una instancia determinada de un elemento, la búsqueda de los temas para este tipo se realiza comprobando la propiedad <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> en un control.  Esto contrasta con el uso del tipo literal, tal como hacen los estilos implícitos.  El valor de <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> se heredaría a las clases derivadas incluso si el implementador no lo cambiara \(la forma prevista de cambiar la propiedad no es invalidarla en el nivel de propiedad, sino cambiar su valor predeterminado en los metadatos de la propiedad\).  Este direccionamiento indirecto permite a las clases base definir los estilos del tema para los elementos derivados que, de otra forma, no tendrían ningún estilo \(o, lo que es más importante, no tienen una plantilla dentro de ese estilo y, por ello, no tendrían ningún tipo de apariencia visual predeterminada\).  Así, puede derivar `MyButton` de <xref:System.Windows.Controls.Button> y aun así obtener la plantilla predeterminada de <xref:System.Windows.Controls.Button>.  Si fuera el autor del control `MyButton` y deseara un comportamiento diferente, podría invalidar los metadatos de la propiedad de dependencia para <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> en `MyButton` con objeto de devolver una clave diferente y, a continuación, definiría los estilos del tema pertinentes, incluyendo la plantilla para `MyButton` que debe empaquetar con su control `MyButton`.  Para obtener más detalles sobre los temas, los estilos y la creación de controles, vea [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="resources"></a>   
## Referencias de recursos dinámicos y los enlaces  
 Las referencias de recursos dinámicos y las operaciones de enlace respetan la prioridad de la ubicación en la que se establecen.  Por ejemplo, un recurso dinámico aplicado a un valor local adquiere una prioridad como elemento 3, un enlace para un establecedor de propiedades dentro de un estilo del tema adquiere una prioridad como elemento 9, etc.  Dado que tanto las referencias de recursos dinámicos como los enlaces deben poder obtener valores del estado de tiempo de ejecución de la aplicación, esto implica que el proceso real de determinar la prioridad del valor de propiedad para cualquier propiedad determinada también se extiende al tiempo de ejecución.  
  
 En sentido estricto, las referencias de recursos dinámicos no forman parte del sistema de propiedades, pero tienen un orden de búsqueda propio que interactúa con la secuencia citada anteriormente.  Esa prioridad se documenta con más detalles en el tema [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  Dicha prioridad puede resumirse básicamente en: elemento a raíz de la página, aplicación, tema, sistema.  
  
 Los recursos dinámicos y los enlaces tienen la prioridad de la ubicación en la que se establecieron, pero el valor se aplaza.  Una consecuencia de esto es que si establece un recurso dinámico o un enlace en un valor local, cualquier cambio del valor local reemplazará el recurso dinámico o el enlace completamente.  Incluso si llama al método <xref:System.Windows.DependencyObject.ClearValue%2A> para borrar el valor establecido localmente, no se restaurará el recurso dinámico o el enlace.  De hecho, si llama a <xref:System.Windows.DependencyObject.ClearValue%2A> para una propiedad que tiene un recurso dinámico o un enlace \(sin ningún valor local literal\), la llamada a <xref:System.Windows.DependencyObject.ClearValue%2A> también los borra.  
  
<a name="setcurrentvalue"></a>   
## SetCurrentValue  
 El método <xref:System.Windows.DependencyObject.SetCurrentValue%2A> es otra manera de establecer una propiedad, pero no está en el orden de prioridad.  En su lugar, <xref:System.Windows.DependencyObject.SetCurrentValue%2A> permite cambiar el valor de una propiedad sin sobrescribir el origen de un valor anterior.  Puede utilizar <xref:System.Windows.DependencyObject.SetCurrentValue%2A> en cualquier momento que desee establecer un valor sin conceder a ese valor la prioridad de un valor local.  Por ejemplo, si un desencadenador establece una propiedad y, a continuación, le asigna otro valor mediante <xref:System.Windows.DependencyObject.SetCurrentValue%2A>, el sistema de propiedades aún respetará el desencadenador y la propiedad cambiará si ocurre la acción del desencadenador.  <xref:System.Windows.DependencyObject.SetCurrentValue%2A> permite cambiar el valor de la propiedad sin asignarle un origen con una prioridad mayor.  Igualmente, puede utilizar <xref:System.Windows.DependencyObject.SetCurrentValue%2A> para cambiar el valor de una propiedad sin sobrescribir un enlace.  
  
<a name="animations"></a>   
## Conversión, animaciones y valor base  
 La conversión y las animaciones se aplican a un valor que se denomina "valor base" en este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)].  Por tanto, el valor base es cualquier valor que se determina evaluando hacia arriba en los elementos hasta que se alcanza el elemento 2.  
  
 Para una animación, el valor base puede tener efecto en el valor animado, si esa animación no especifica tanto "From" como "To" para ciertos comportamientos o si la animación recupera deliberadamente el valor base cuando se completa.  Para obtener un ejemplo práctico de ello, ejecute [From, To, and By Animation Target Values Sample](http://go.microsoft.com/fwlink/?LinkID=159988).  Pruebe a establecer los valores locales del alto del rectángulo en el ejemplo, de forma que el valor local inicial difiera de cualquier "From" en la animación.  Observará que las animaciones se inician inmediatamente utilizando los valores "From" y que reemplazan el valor base tras iniciarse.  La animación podría especificar que se vuelva al valor hallado antes de la animación una vez completada especificando el <xref:System.Windows.Media.Animation.FillBehavior> final.  Después se utiliza la prioridad normal para la determinación del valor base.  
  
 Es posible que se apliquen varias animaciones a una sola propiedad y que cada una de ellas se haya definido desde puntos distintos en la prioridad de valores.  Sin embargo, puede que estas animaciones compongan sus valores, en lugar de aplicar simplemente la animación que tenga la prioridad más alta.  Esto depende de cómo se definen exactamente las animaciones y del tipo del valor que se anima.  Para obtener más información sobre la animación de propiedades, vea [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 La conversión se aplica en el nivel más alto.  Incluso una animación que ya está ejecutándose está sujeta a la conversión de valores.  Ciertas propiedades de dependencia existentes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen integrada la conversión.  Para una propiedad de dependencia personalizada, el comportamiento de la conversión se define escribiendo una devolución de llamada <xref:System.Windows.CoerceValueCallback> y pasando la devolución de llamada como parte de los metadatos al crear la propiedad.  También puede invalidar el comportamiento de la conversión de las propiedades existentes invalidando los metadatos de esa propiedad en una clase derivada.  La conversión interactúa con el valor base de forma que se aplican restricciones en cuanto a la conversión siempre y cuando existan en ese momento, pero el valor base se sigue conservando.  Por consiguiente, si posteriormente se levantan las restricciones en cuanto a conversión, ésta devolverá el valor más cercano posible a ese valor base y puede que la influencia de la conversión en una propiedad cese en cuanto se levanten todas las restricciones.  Para obtener más información acerca del comportamiento de la conversión, vea [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
<a name="triggers"></a>   
## Comportamientos desencadenantes  
 Los controles suelen definir comportamientos desencadenantes como parte de su estilo predeterminado en los temas.  El establecimiento de propiedades locales en los controles podría evitar que los desencadenadores fueran capaces de responder a los eventos controlados por el usuario, bien de forma visual o mediante su comportamiento.  El uso más común de un desencadenador de propiedades es para propiedades de control o de estado como <xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A>.  Por ejemplo, de forma predeterminada, cuando un control <xref:System.Windows.Controls.Button> está deshabilitado \(el desencadenador d <xref:System.Windows.UIElement.IsEnabled%2A> es `false`\), el valor de <xref:System.Windows.Controls.Control.Foreground%2A> en el estilo del tema es lo que hace que el control aparezca "deshabilitado".  Pero si ha establecido un valor local para <xref:System.Windows.Controls.Control.Foreground%2A>, la prioridad de ese color normal para el botón deshabilitado será reemplazada por el conjunto de propiedades locales, incluso en este escenario desencadenado por propiedades.  Tenga cuidado al establecer valores para las propiedades que tienen comportamientos de desencadenador en el nivel del tema y asegúrese de que no está interfiriendo excesivamente con la experiencia del usuario pensada por ese control.  
  
<a name="clearvalue"></a>   
## ClearValue y la prioridad de los valores  
 El método <xref:System.Windows.DependencyObject.ClearValue%2A> proporciona un medio conveniente para borrar cualquier valor aplicado localmente de una [propiedad de dependencia](GTMT) establecida en un elemento.  Sin embargo, llamar a <xref:System.Windows.DependencyObject.ClearValue%2A> no garantiza que el valor predeterminado establecido en los metadatos durante el registro de la propiedad sea el nuevo valor efectivo.  Todos los demás participantes en la prioridad de valores siguen estando activos.  Sólo se ha quitado de la secuencia de prioridad el valor establecido localmente.  Por ejemplo, si llama a <xref:System.Windows.DependencyObject.ClearValue%2A> para una propiedad que también se establece mediante un estilo del tema, se aplicará el valor del tema como el nuevo valor en lugar del valor predeterminado basado en los metadatos.  Si desea sacar del proceso a todos los participantes del valor de propiedad y establecer el valor en el valor predeterminado de los metadatos registrados, puede obtener ese valor predeterminado definitivamente consultando los metadatos de la propiedad de dependencia y, a continuación, utilizar el valor predeterminado para establecer localmente la propiedad con una llamada a <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
## Vea también  
 <xref:System.Windows.DependencyObject>   
 <xref:System.Windows.DependencyProperty>   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)