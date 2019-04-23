---
title: Aplicar estilo a los controles al recibir el foco y FocusVisualStyle
ms.date: 03/30/2017
helpviewer_keywords:
- keyboard focus [WPF]
- focus [WPF], visual styling
- styles [WPF], focus visual style
ms.assetid: 786ac576-011b-4d72-913b-558deccb9b35
ms.openlocfilehash: 745c2174c54ed072f91a6d5eb3b43d5385e96b90
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59172060"
---
# <a name="styling-for-focus-in-controls-and-focusvisualstyle"></a>Aplicar estilo a los controles al recibir el foco y FocusVisualStyle
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona dos mecanismos paralelos para cambiar el aspecto visual de un control cuando recibe el foco de teclado. El primer mecanismo consiste en usar establecedores de propiedad para propiedades como <xref:System.Windows.UIElement.IsKeyboardFocused%2A> dentro del estilo o plantilla que se aplica al control. El segundo mecanismo consiste en proporcionar un estilo independiente como el valor de la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad; el "estilo visual de foco" crea un árbol visual independiente para un adorno que dibuja encima del control, en lugar de cambiar el árbol visual del control u otras interfaces de usuario elemento reemplazándola. En este tema se describen los escenarios en los que es apropiado cada uno de estos mecanismos.  

<a name="Purpose"></a>   
## <a name="the-purpose-of-focus-visual-style"></a>La finalidad del estilo visual de foco  
 La característica de estilo visual de foco proporciona un "modelo de objetos" común para especificar información visual al usuario basándose en la navegación mediante el teclado a cualquier elemento de la interfaz de usuario. Esto es posible sin aplicar una nueva plantilla al control ni conocer la composición de la plantilla concreta.  
  
 Pero, y precisamente porque la característica de estilo visual de foco funciona sin conocer las plantillas de control, la información visual que se puede mostrar para un control usando un estilo visual de foco es necesariamente limitada. Lo que la característica hace en realidad es superponer un árbol visual diferente (un adorno) sobre el árbol visual creado por la representación de un control a través de su plantilla. Definir este árbol visual independiente con un estilo que rellena la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> propiedad.  
  
<a name="Default"></a>   
## <a name="default-focus-visual-style-behavior"></a>Comportamiento predeterminado del estilo visual de foco  
 Los estilos visuales de foco solo actúan cuando la acción de foco se inicia desde el teclado. Los cambios de foco provocados por acciones del mouse o mediante programación deshabilitan el modo de estilos visuales de foco. Para más información sobre las distinciones entre los modos de foco, vea [Información general sobre el foco](focus-overview.md).  
  
 Los temas para los controles incluyen un comportamiento de estilo visual de foco predeterminado que pasa a ser el estilo visual de foco para todos los controles del tema. Este estilo de tema se identifica mediante el valor de la clave estática <xref:System.Windows.SystemParameters.FocusVisualStyleKey%2A>. Al declarar su propio estilo visual de foco en el nivel de aplicación, se reemplaza este comportamiento de estilo predeterminado de los temas. Como alternativa, si define el tema completo, entonces deberá usar esta misma clave para definir el estilo correspondiente al comportamiento predeterminado para todo el tema.  
  
 En los temas, el estilo visual de foco predeterminado suele ser muy simple. A continuación se muestra una aproximación sin detallar:  
  
```xaml  
<Style x:Key="{x:Static SystemParameters.FocusVisualStyleKey}">  
  <Setter Property="Control.Template">  
    <Setter.Value>  
      <ControlTemplate>  
        <Rectangle StrokeThickness="1"  
          Stroke="Black"  
          StrokeDashArray="1 2"  
          SnapsToDevicePixels="true"/>  
      </ControlTemplate>  
    </Setter.Value>  
  </Setter>  
</Style>  
```  
  
<a name="When"></a>   
## <a name="when-to-use-focus-visual-styles"></a>Cuándo usar estilos visuales de foco  
 Conceptualmente, el aspecto de los estilos visuales de foco aplicados a los controles debe ser coherente para todos los controles. Una manera de asegurar la coherencia es cambiar el estilo visual de foco únicamente si se está creando un tema completo, donde cada control que se defina obtendrá exactamente el mismo estilo visual de foco, o bien una variación de un estilo que guarde una relación visual en todos los controles. Como alternativa, se puede usar el mismo estilo (o estilos similares) para aplicárselos a todos los elementos que pueden recibir el foco del teclado de una página o una interfaz de usuario.  
  
 Establecer <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> en estilos de controles individuales que no forman parte de un tema es no, el uso previsto del enfoque de estilos visuales. Esto se debe a que un comportamiento visual incoherente en los distintos controles puede dar lugar a una experiencia del usuario confusa con respecto al foco de teclado. Si tiene previsto comportamientos específicos de control para el foco de teclado que deliberadamente no son coherentes en todo el tema, un enfoque mucho mejor es usar desencadenadores en estilos para las propiedades de estado de entrada individuales, como <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocused%2A>.  
  
 Los estilos visuales de foco actúan exclusivamente para el foco de teclado. Como tales, los estilos visuales de foco son un tipo de característica de accesibilidad. Si quiere efectuar cambios en la interfaz de usuario para cualquier tipo de foco, ya sea mediante el mouse, el teclado o programación, no debe usar los estilos visuales de foco sino establecedores y desencadenadores de estilos o plantillas que funcionen partiendo del valor de las propiedades de foco generales, <xref:System.Windows.UIElement.IsFocused%2A> o <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>.  
  
<a name="How"></a>   
## <a name="how-to-create-a-focus-visual-style"></a>Cómo crear un estilo visual de foco  
 El estilo de creación de un estilo visual de foco siempre debe tener la <xref:System.Windows.Style.TargetType%2A> de <xref:System.Windows.Controls.Control>. El estilo debe consistir principalmente un <xref:System.Windows.Controls.ControlTemplate>. No se especifica el tipo de destino para que sea el tipo que se asigna el estilo visual de foco a la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>.  
  
 Dado que el tipo de destino es siempre <xref:System.Windows.Controls.Control>, deben aplicar los estilos mediante las propiedades que son comunes a todos los controles (mediante las propiedades de la <xref:System.Windows.Controls.Control> clase y sus clases bases). Debe crear una plantilla que funcione correctamente como una superposición a un elemento de la interfaz de usuario y que no oculte áreas funcionales del control. En general, esto significa que la información visual debe aparecer fuera de los márgenes del control, o en forma de efectos temporales o discretos que no bloqueen las pruebas de posicionamiento del control al que se aplica el estilo visual de foco. Las propiedades que puede usar en el enlace de plantilla que son útiles para determinar el tamaño y la posición de la plantilla de superposición incluyen <xref:System.Windows.FrameworkElement.ActualHeight%2A>, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, <xref:System.Windows.FrameworkElement.Margin%2A>, y <xref:System.Windows.Controls.Control.Padding%2A>.  
  
<a name="Alternatives"></a>   
## <a name="alternatives-to-using-a-focus-visual-style"></a>Alternativas al uso de un estilo visual de foco  
 En aquellas situaciones en que no sea apropiado usar un estilo visual de foco, ya sea porque el estilo se aplica a controles individuales o porque se quiere un mayor control sobre la plantilla de control, existen muchas otras propiedades y técnicas accesibles capaces de crear comportamiento visual en respuesta a los cambios de foco.  
  
 Los desencadenadores, establecedores y establecedores de eventos se describen con detalle en [Aplicar estilos y plantillas](../controls/styling-and-templating.md). El control de eventos enrutados se describe en [Información general sobre eventos enrutados](routed-events-overview.md).  
  
### <a name="iskeyboardfocused"></a>IsKeyboardFocused  
 Si está interesado en concreto en el foco de teclado, el <xref:System.Windows.UIElement.IsKeyboardFocused%2A> propiedad de dependencia puede utilizarse para una propiedad <xref:System.Windows.Trigger>. Un desencadenador de propiedad de un estilo o plantilla constituye una técnica más adecuada para definir el comportamiento de foco de teclado más específico para un único control y que no coincida visualmente con el comportamiento de foco de teclado de los demás controles.  
  
 Otra propiedad de dependencia similar es <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A>, que podría ser adecuada si desea indicar visualmente que el foco de teclado está en algún lugar dentro de la composición o dentro del área funcional del control. Por ejemplo, podría colocar un <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> desencadenador tal que un panel que agrupe varios controles aparezca de forma diferente, incluso aunque el foco de teclado con mayor precisión puede ser un elemento individual dentro de ese panel.  
  
 También puede usar los eventos <xref:System.Windows.UIElement.GotKeyboardFocus> y <xref:System.Windows.UIElement.LostKeyboardFocus> (así como sus equivalentes de vista previa). Puede usar estos eventos como base para un <xref:System.Windows.EventSetter>, o bien puede escribir controladores para los eventos en el código subyacente.  
  
### <a name="other-focus-properties"></a>Otras propiedades de foco  
 Si desea que todas las posibles causas del cambio de foco para producir un comportamiento visual, debe basar un establecedor o desencadenador en el <xref:System.Windows.UIElement.IsFocused%2A> propiedad de dependencia, o bien en el <xref:System.Windows.UIElement.GotFocus> o <xref:System.Windows.UIElement.LostFocus> los eventos se usa para un <xref:System.Windows.EventSetter>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Aplicar estilos y plantillas](../controls/styling-and-templating.md)
- [Información general sobre el foco](focus-overview.md)
- [Información general sobre acciones del usuario](input-overview.md)
