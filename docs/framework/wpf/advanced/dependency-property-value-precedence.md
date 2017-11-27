---
title: Prioridad de los valores de propiedades de dependencia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency properties [WPF], classes as owners
- dependency properties [WPF], metadata
- classes [WPF], owners of dependency properties
- metadata [WPF], dependency properties
ms.assetid: 1fbada8e-4867-4ed1-8d97-62c07dad7ebc
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0b52b809b732f3859a7ce02a4433b2387e797932
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="dependency-property-value-precedence"></a>Prioridad de los valores de propiedades de dependencia
<a name="introduction"></a> En este tema se explica cómo puede afectar el trabajo del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] al valor de una propiedad de dependencia y se describe la precedencia de aplicación de los aspectos del sistema de propiedades al valor efectivo de una propiedad.  
    
  
<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Requisitos previos  
 En este tema, se supone que entiende las propiedades de dependencia desde la perspectiva de un consumidor de propiedades de dependencia existentes en las clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y que ha leído [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md). Para seguir los ejemplos de este tema, también debe comprender el lenguaje [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] y saber cómo escribir aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
<a name="intro"></a>   
## <a name="the-wpf-property-system"></a>Sistema de propiedades de WPF  
 El sistema de propiedades de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite que el valor de las propiedades de dependencia se determine de forma eficaz mediante una serie de factores, que habilita características como la validación de propiedades en tiempo real, el enlace en tiempo de ejecución y la notificación de propiedades relacionadas de cambios a valores de otras propiedades. El orden y la lógica exactos que se usan para determinar los valores de las propiedades de dependencia son bastante complejos. Conocer este orden le evitará establecer propiedades innecesarias y puede eliminar la confusión sobre el motivo por el que un intento de influir en el valor de una propiedad de dependencia o de anticiparlo no dio como resultado el valor esperado.  
  
<a name="multiple_sets"></a>   
## <a name="dependency-properties-might-be-set-in-multiple-places"></a>Las propiedades de dependencia podrían ser "set" en varios lugares  
 El siguiente es ejemplo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] donde la misma propiedad (<xref:System.Windows.Controls.Control.Background%2A>) con tres diferentes "set" operaciones que podrían influir en el valor.  
  
 [!code-xaml[PropertiesOvwSupport#DPPrecedence](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml#dpprecedence)]  
  
 ¿Qué color espera que se aplique aquí: rojo, verde o azul?  
  
 A excepción de los valores animados y la coerción, los conjuntos de propiedades locales se establecen con la precedencia más alta. Si establece un valor localmente, puede esperar que este se respete, incluso por encima de cualquier estilo o plantilla de control. Aquí, en el ejemplo, <xref:System.Windows.Controls.Control.Background%2A> se establece en rojo localmente. Por lo tanto, el estilo definido en este ámbito, aunque se encuentre un estilo implícito que normalmente se aplicaría a todos los elementos de ese tipo en ese ámbito, no es la prioridad más alta de ofrecer el <xref:System.Windows.Controls.Control.Background%2A> propiedad su valor.  En el caso de quitar el valor local de Red desde esa instancia de Button, el estilo tendría precedencia y el botón obtendría el valor de Background del estilo.  Dentro del estilo, los desencadenadores tienen precedencia, por lo que el botón será azul si el mouse está encima de él y verde en caso contrario.  
  
<a name="listing"></a>   
## <a name="dependency-property-setting-precedence-list"></a>Lista de precedencia de configuración de propiedades de dependencia  
 El siguiente es el orden definitivo que usa el sistema de propiedades al asignar los valores de tiempo de ejecución de las propiedades de dependencia. La precedencia más alta aparece primero. Esta lista desarrolla algunas de las generalizaciones realizadas en la [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  
  
1.  **Coerción del sistema de propiedades.** Para obtener más información sobre la coerción, consulte [Coerción, animación y valor base](#animations) más adelante en este tema.  
  
2.  **Animaciones activas o animaciones con un comportamiento Hold.** Para tener cualquier efecto práctico, una animación de una propiedad debe poder tener precedencia sobre el valor base (inanimado), aunque dicho valor se estableciera localmente. Para obtener más información, consulte [Coerción, animación y valor base](#animations) más adelante en este tema.  
  
3.  **Valor local.** Un valor local puede establecerse a través de la comodidad de la propiedad "contenedor", que también equivale a establecer como un atributo o elemento de propiedad en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], o mediante una llamada a la <xref:System.Windows.DependencyObject.SetValue%2A> [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] utilizando una propiedad de una instancia específica. Si establece un valor local mediante un enlace o un recurso, cada uno de estos actuará con la precedencia como si se hubiese establecido un valor directo.  
  
4.  **Propiedades de la plantilla TemplatedParent.** Un elemento tiene un <xref:System.Windows.FrameworkElement.TemplatedParent%2A> si se ha creado como parte de una plantilla (un <xref:System.Windows.Controls.ControlTemplate> o <xref:System.Windows.DataTemplate>). Para obtener más información sobre cuándo se aplica el caso anterior, consulte [TemplatedParent](#templatedparent) más adelante en este tema. En la plantilla, se aplica la siguiente precedencia:  
  
    1.  Desencadenadores de la <xref:System.Windows.FrameworkElement.TemplatedParent%2A> plantilla.  
  
    2.  Conjuntos de propiedades (normalmente a través [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributos) en el <xref:System.Windows.FrameworkElement.TemplatedParent%2A> plantilla.  
  
5.  **Estilo implícito.** Solo se aplica a la propiedad `Style`. La propiedad `Style` se rellena con cualquier recurso de estilo que tenga una clave que coincida con el tipo de ese elemento. Ese recurso de estilo debe existir en la página o la aplicación; la búsqueda de un recurso de estilo implícito no continúa en los temas.  
  
6.  **Desencadenadores de estilo.** Desencadenadores dentro de los estilos de una página o aplicación (estos estilos pueden ser explícitos o implícitos, pero no pueden ser predeterminados, con una precedencia más baja).  
  
7.  **Desencadenadores de plantilla.** Cualquier desencadenador de una plantilla dentro de un estilo o una plantilla aplicada directamente.  
  
8.  **Establecedores de estilo.** Los valores de un <xref:System.Windows.Setter> dentro de estilos de página o la aplicación.  
  
9. **Estilo (tema) predeterminado.** Para obtener más información sobre cuándo se aplica y cómo se relacionan los estilos de tema con las plantillas dentro de los estilos de tema, consulte [Estilos (temas) predeterminados](#themestyles) más adelante en este tema. Dentro de un estilo predeterminado, se aplica el orden de precedencia siguiente:  
  
    1.  Desencadenadores activos del estilo de tema.  
  
    2.  Establecedores del estilo de tema.  
  
10. **Herencia.** Algunas propiedades de dependencia heredan sus valores del elemento primario a los elementos secundarios, de manera que no se tienen que establecer específicamente en cada elemento de una aplicación. Para obtener información detallada, consulte [Herencia de valores de propiedad](../../../../docs/framework/wpf/advanced/property-value-inheritance.md).  
  
11. **Valor predeterminado de los metadatos de las propiedades de dependencia.** Cualquier propiedad de dependencia puede tener un valor predeterminado establecido en el registro del sistema de propiedades de esa propiedad concreta. Además, las clases derivadas que heredan una propiedad de dependencia tienen la opción de invalidar esos metadatos (incluido el valor predeterminado) por tipo. Para obtener más información, consulte [Metadados de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md). Puesto que la herencia se comprueba antes que el valor predeterminado, para una propiedad heredada, un valor predeterminado de un elemento primario tiene precedencia sobre un elemento secundario.  Por consiguiente, si una propiedad heredable no está establecida en ningún lugar, se usa el valor predeterminado tal como se especifica en la raíz o el elemento primario, en lugar del valor predeterminado del elemento secundario.  
  
<a name="templatedparent"></a>   
## <a name="templatedparent"></a>TemplatedParent  
 TemplatedParent, como un elemento de precedencia, no se aplica a ninguna propiedad de un elemento que se declara directamente en la marcación de aplicación estándar. El concepto de TemplatedParent existe solo para los elementos secundarios dentro de un árbol visual que se genera a través de la aplicación de la plantilla. Cuando el sistema de propiedades busca el <xref:System.Windows.FrameworkElement.TemplatedParent%2A> plantilla para un valor, busca en la plantilla que creó ese elemento. Los valores de propiedad de la <xref:System.Windows.FrameworkElement.TemplatedParent%2A> plantilla generalmente actúan como si estuvieran establecidos como un valor local en el elemento secundario, pero esta prioridad menor en comparación con el valor local existe porque potencialmente se comparten las plantillas. Para obtener información detallada, vea <xref:System.Windows.FrameworkElement.TemplatedParent%2A>.  
  
<a name="style_property"></a>   
## <a name="the-style-property"></a>Propiedad Style  
 El orden de búsqueda descrito anteriormente se aplica a todas las propiedades de dependencia posibles excepto uno: el <xref:System.Windows.FrameworkElement.Style%2A> propiedad. El <xref:System.Windows.FrameworkElement.Style%2A> propiedad es única en que se no se propio le pueden aplicar estilos, por lo que no se aplican los elementos de prioridad 5 a 8. Además, animar o convertir <xref:System.Windows.FrameworkElement.Style%2A> no se recomienda (y animación <xref:System.Windows.FrameworkElement.Style%2A> requeriría una clase de animación personalizada). Esto deja tres formas de que el <xref:System.Windows.FrameworkElement.Style%2A> propiedad esté establecida en:  
  
-   **Estilo explícito.** El <xref:System.Windows.FrameworkElement.Style%2A> propiedad se establece directamente. En la mayoría de los escenarios, el estilo no se define en línea, sino que se hace referencia a este como un recurso, por la clave explícita. En este caso, la propia propiedad Style actúa como si fuera un valor local, el elemento de precedencia 3.  
  
-   **Estilo implícito.** El <xref:System.Windows.FrameworkElement.Style%2A> no se establece directamente la propiedad. Sin embargo, la <xref:System.Windows.FrameworkElement.Style%2A> existe en algún nivel en la secuencia de búsqueda de recursos (página, aplicación) y tiene una clave con una clave de recurso que coincide con el tipo es el estilo que se aplicará a. En este caso, el <xref:System.Windows.FrameworkElement.Style%2A> actúa de propiedad en sí una prioridad identificada en la secuencia como elemento 5. Esta condición se puede detectar con <xref:System.Windows.DependencyPropertyHelper> contra la <xref:System.Windows.FrameworkElement.Style%2A> propiedad y buscando <xref:System.Windows.BaseValueSource.ImplicitStyleReference> en los resultados.  
  
-   **Estilo predeterminado**, también conocido como **estilo del tema.** El <xref:System.Windows.FrameworkElement.Style%2A> propiedad no se establece directamente y de hecho se leerá como `null` hasta el tiempo de ejecución. En este caso, el estilo procede de la evaluación del tema en tiempo de ejecución que forma parte del motor de presentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Para los estilos implícitos que no procedan de temas, el tipo debe coincidir exactamente (una clase derivada de `MyButton``Button` no usará de manera implícita un estilo para `Button`).  
  
<a name="themestyles"></a>   
## <a name="default-theme-styles"></a>Estilos (temas) predeterminados  
 Todos los controles que se suministran con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen un estilo predeterminado. Ese estilo predeterminado puede variar según el tema, motivo por el cual se denomina a veces "estilo de tema".  
  
 La información más importante que se encuentra dentro de un estilo predeterminado para un control es su plantilla de control, que existe en el estilo del tema como un establecedor para su <xref:System.Windows.Controls.Control.Template%2A> propiedad. Si no hubiera ninguna plantilla en los estilos predeterminados, un control sin una plantilla personalizada como parte de un estilo personalizado no tendría ninguna apariencia visual. La plantilla del estilo predeterminado proporciona a la apariencia visual de cada control una estructura básica, además de definir las conexiones entre las propiedades definidas en el árbol visual de la plantilla y la clase de control correspondiente. Cada control expone un conjunto de propiedades que puede influir en la apariencia visual del control sin reemplazar completamente la plantilla. Por ejemplo, considere la apariencia visual predeterminada de un <xref:System.Windows.Controls.Primitives.Thumb> control, que es un componente de un <xref:System.Windows.Controls.Primitives.ScrollBar>.  
  
 Un <xref:System.Windows.Controls.Primitives.Thumb> tiene ciertas propiedades personalizables. La plantilla predeterminada de un <xref:System.Windows.Controls.Primitives.Thumb> crea una estructura básica / anidados del árbol visual con varios <xref:System.Windows.Controls.Border> componentes para crear un aspecto del bisel. Si una propiedad que forma parte de la plantilla se va a exponer para la personalización mediante la <xref:System.Windows.Controls.Primitives.Thumb> de la clase, a continuación, esa propiedad debe exponerse mediante un [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md), dentro de la plantilla. En el caso de <xref:System.Windows.Controls.Primitives.Thumb>, varias propiedades de estos bordes comparten un enlace de plantilla a las propiedades como <xref:System.Windows.Controls.Border.Background%2A> o <xref:System.Windows.Controls.Border.BorderThickness%2A>. No obstante, otras propiedades u organizaciones visuales están codificadas de forma rígida en la plantilla de control o enlazadas a valores que proceden directamente del tema, y no se pueden cambiar a poco de reemplazar la plantilla completa. Por lo general, si una propiedad procede de un elemento primario con plantilla y no se expone mediante un enlace a plantilla, no puede ajustarse mediante estilos porque no hay ninguna forma sencilla de establecerla como destino. No obstante, aún se podría influir en esa propiedad mediante la herencia de valores de propiedad de la plantilla aplicada o el valor predeterminado.  
  
 Los estilos de tema usan un tipo como clave en sus definiciones. Sin embargo, cuando los temas se aplican a una instancia de un elemento determinado, búsqueda de los temas de este tipo se realiza comprobando la <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> propiedad en un control. Esto es lo contrario a usar el literal Type, como hacen los estilos implícitos. El valor de <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> heredaría a las clases derivadas incluso si el implementador no lo cambiara (la forma prevista de cambiar la propiedad es no invalidarlo en el nivel de propiedad, pero que en su lugar, cambiar su valor predeterminado en los metadatos). Este direccionamiento indirecto permite que las clases base definan los estilos de tema de elementos derivados que, de lo contrario, no tendrían ningún estilo (o más importante aún, no tendrían ninguna plantilla dentro de ese estilo y no tendrían, por tanto, ninguna apariencia visual predeterminada en absoluto). Por lo tanto, puede derivar `MyButton` de <xref:System.Windows.Controls.Button> y seguirán enviando el <xref:System.Windows.Controls.Button> plantilla predeterminada. Si fuera el autor del control de `MyButton` y desea que un comportamiento diferente, podría invalidar los metadatos de propiedad de dependencia de <xref:System.Windows.FrameworkElement.DefaultStyleKey%2A> en `MyButton` para devolver una clave diferente y, a continuación, defina los estilos del tema relevante incluida plantilla para `MyButton` que se debe empaquetar con su `MyButton` control. Para obtener más detalles sobre los temas, los estilos y la creación de controles, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
<a name="resources"></a>   
## <a name="dynamic-resource-references-and-binding"></a>Enlace y referencias de recursos dinámicos  
 Las operaciones de enlace y referencias de recursos dinámicos respetan la precedencia de la ubicación en la que están establecidas. Por ejemplo, un recurso dinámico aplicado a un valor local actúa por elemento de precedencia 3, un enlace para un establecedor de propiedad dentro de un estilo de tema se aplica al elemento de precedencia 9 y así sucesivamente. Dado que el enlace y las referencias de recursos dinámicos deben ser capaces de obtener los valores del estado de tiempo de ejecución de la aplicación, esto implica que el proceso real de determinar la precedencia de los valores de propiedad para cualquier propiedad determinada se extiende también al tiempo de ejecución.  
  
 Las referencias de recursos dinámicos no forman parte del sistema de propiedades en sentido estricto, pero tienen un orden de búsqueda propio que interactúa con la secuencia citada anteriormente. Esa precedencia se documenta con más detalle en [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md). El resumen básico de esa precedencia es: elemento a raíz de la página, aplicación, tema y sistema.  
  
 Los enlaces y los recursos dinámicos tienen la precedencia de donde se establecieron, pero el valor se aplaza. Una consecuencia de esto es que, si establece un recurso dinámico o un enlace en un valor local, cualquier cambio en el valor local reemplazará el recurso dinámico o el enlace completamente. Incluso si se llama a la <xref:System.Windows.DependencyObject.ClearValue%2A> método para borrar establecida localmente no se restaurará el valor, el recurso dinámico o un enlace. De hecho, si se llama a <xref:System.Windows.DependencyObject.ClearValue%2A> en una propiedad que tiene un recurso dinámico o un enlace en su lugar (sin ningún valor local literal), se borran por la <xref:System.Windows.DependencyObject.ClearValue%2A> llamar demasiado.  
  
<a name="setcurrentvalue"></a>   
## <a name="setcurrentvalue"></a>SetCurrentValue  
 El <xref:System.Windows.DependencyObject.SetCurrentValue%2A> método es otra manera de establecer una propiedad, pero no está en el orden de prioridad. En su lugar, <xref:System.Windows.DependencyObject.SetCurrentValue%2A> le permite cambiar el valor de una propiedad sin sobrescribir el origen de un valor anterior. Puede usar <xref:System.Windows.DependencyObject.SetCurrentValue%2A> cada vez que se desea establecer un valor sin proporcionar ese valor de la prioridad de un valor local. Por ejemplo, si una propiedad se establece mediante un desencadenador y, a continuación, asignar otro valor mediante <xref:System.Windows.DependencyObject.SetCurrentValue%2A>, el sistema de propiedades todavía respeta el desencadenador y la propiedad cambiará si se produce la acción del desencadenador. <xref:System.Windows.DependencyObject.SetCurrentValue%2A>permite cambiar el valor de la propiedad sin darle un origen con una prioridad más alta. Del mismo modo, puede usar <xref:System.Windows.DependencyObject.SetCurrentValue%2A> para cambiar el valor de una propiedad sin sobrescribir un enlace.  
  
<a name="animations"></a>   
## <a name="coercion-animations-and-base-value"></a>Coerción, animaciones y valor base  
 Tanto la coerción como la animación actúan sobre un valor al que nos referimos como "valor base" en este [!INCLUDE[TLA2#tla_sdk](../../../../includes/tla2sharptla-sdk-md.md)]. El valor base es, por tanto, cualquier valor que se determine mediante la evaluación ascendente de los elementos hasta alcanzar el elemento 2.  
  
 Para una animación, el valor base puede tener un efecto en el valor animado si la animación no especifica los valores "From" y "To" para ciertos comportamientos o si se revierte deliberadamente al valor base al completarse. Para verlo en la práctica, ejecute el [Ejemplo de valores de destino de animación From, To y By](http://go.microsoft.com/fwlink/?LinkID=159988). Intente establecer los valores locales del alto del rectángulo del ejemplo, de modo que el valor local inicial difiera de cualquier valor "From" de la animación. Observará que las animaciones se inician inmediatamente mediante los valores "From" y reemplazan el valor base una vez iniciadas. Puede especificar la animación para recuperar el valor encontrado antes de animación cuando se completa mediante la especificación de la detención <xref:System.Windows.Media.Animation.FillBehavior>. Después, se usa la precedencia normal para la determinación del valor base.  
  
 Varias animaciones podrían aplicarse a una propiedad única y cada una de estas animaciones se podría haber definido desde diferentes puntos de la precedencia de valores. Sin embargo, estas animaciones compondrán potencialmente sus valores, en lugar de aplicar la animación de mayor precedencia simplemente. Esto depende de la exactitud con la que estén definidas las animaciones y del tipo de valor que se esté animando. Para obtener más información sobre la animación de propiedades, consulte [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 La coerción se aplica en el nivel más alto de todos. Incluso una animación que ya se está ejecutando está sujeta a la coerción de valores. Ciertas propiedades de dependencia existentes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen la coerción integrada. Para una propiedad de dependencia personalizada, definir el comportamiento de conversión de una propiedad de dependencia personalizada escribiendo una <xref:System.Windows.CoerceValueCallback> y pasar la devolución de llamada como parte de los metadatos cuando se crea la propiedad. También puede invalidar el comportamiento de la coerción de las propiedades existentes mediante la invalidación de los metadatos de esa propiedad en una clase derivada. La coerción interactúa con el valor base de forma que se aplican las restricciones en la coerción, ya que esas restricciones existen en el momento, pero el valor base se sigue conservando. Por lo tanto, si las restricciones en la coerción se levantan posteriormente, la coerción devolverá el valor más próximo posible a ese valor base y la influencia de la coerción sobre una propiedad cesará potencialmente en cuanto se levanten todas las restricciones. Para obtener más información sobre el comportamiento de la coerción, consulte [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
<a name="triggers"></a>   
## <a name="trigger-behaviors"></a>Comportamientos de los desencadenadores  
 Los controles suelen definir los comportamientos de los desencadenadores como parte de su estilo predeterminado en los temas. Establecer las propiedades locales en los controles puede impedir que los desencadenadores sean capaces de responder a eventos controlados por el usuario, ya sea de manera visual o conductual. El uso más común de un desencadenador de propiedad es para las propiedades de control o estado como <xref:System.Windows.Controls.Primitives.Selector.IsSelected%2A>. Por ejemplo, de forma predeterminada cuando un <xref:System.Windows.Controls.Button> está deshabilitado (desencadenar <xref:System.Windows.UIElement.IsEnabled%2A> es `false`), a continuación, el <xref:System.Windows.Controls.Control.Foreground%2A> valor en el estilo del tema es lo que hace que el control aparezca "atenuado". Sin embargo, si ha establecido una variable local <xref:System.Windows.Controls.Control.Foreground%2A> valor, que el conjunto de propiedades local, incluso en este escenario desencadenada propiedad quedará anulado color gris horizontal normal en prioridad. Tenga precaución al establecer valores de propiedades con comportamientos de desencadenador de nivel de tema y asegúrese de no interferir excesivamente en la experiencia de usuario prevista para este control.  
  
<a name="clearvalue"></a>   
## <a name="clearvalue-and-value-precedence"></a>Precedencia de los valores y ClearValue  
 El <xref:System.Windows.DependencyObject.ClearValue%2A> método proporciona un medio conveniente para borrar cualquier valor aplicado localmente de una propiedad de dependencia que se establece en un elemento. Sin embargo, al llamar a <xref:System.Windows.DependencyObject.ClearValue%2A> no es una garantía de que el valor predeterminado establecido en los metadatos durante el registro de la propiedad es el nuevo valor efectivo. Todos los demás participantes en la precedencia de valores siguen estando activos. Solo el valor establecido localmente se quitó de la secuencia de precedencia. Por ejemplo, si se llama a <xref:System.Windows.DependencyObject.ClearValue%2A> en una propiedad donde esa propiedad también se establece mediante un estilo de tema, a continuación, el valor del tema se aplica como el nuevo valor en lugar de con el valor predeterminado basado en metadatos. Si desea realizar a todos los participantes del valor de propiedad fuera del proceso y establezca el valor en el valor predeterminado de metadatos registrados, puede obtener que valor predeterminado definitivamente consultando los metadatos de propiedad de dependencia y, a continuación, puede usar el valor predeterminado para localmente Establezca la propiedad con una llamada a <xref:System.Windows.DependencyObject.SetValue%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.DependencyObject>  
 <xref:System.Windows.DependencyProperty>  
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)  
 [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md)
