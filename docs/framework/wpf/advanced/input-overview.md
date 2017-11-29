---
title: "Información general sobre acciones del usuario"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- commands [WPF]
- input [WPF], overview
- keyboard focus [WPF]
- keyboard input [WPF]
- touch events [WPF]
- event routing [WPF]
- touch input [WPF]
- manipulation [WPF]
- logical focus [WPF]
- stylus input [WPF]
- text input [WPF]
- input events [WPF], handling
- WPF [WPF], input overview
- manipulation events [WPF]
- mouse input [WPF]
- mouse capture [WPF]
- focus [WPF]
- mouse position [WPF]
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: "50"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c12d8655babeb45800f4a5c068cb2ab74faac3d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="input-overview"></a>Información general sobre acciones del usuario
<a name="introduction"></a> El subsistema de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona una [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] eficaz para obtener datos desde una variedad de dispositivos, como el mouse, el teclado, las funciones táctiles y el lápiz. En este tema se describen los servicios que proporciona [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y se explica la arquitectura de los sistemas de entrada.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>API de entrada  
 La entrada principal [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] exposición se encuentra en las clases de elementos base: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.FrameworkContentElement>.  Para obtener más información sobre los elementos base, consulte [Información general sobre los elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Estas clases proporcionan funcionalidad para los eventos de entrada relacionados con las pulsaciones de teclas, los botones del mouse, la rueda del mouse, el movimiento del mouse, la administración del foco, la captura del mouse, etc. Al situar la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de entrada en los elementos base, en lugar de tratar todos los eventos de entrada como un servicio, la arquitectura de entrada permite que los eventos de entrada tengan su origen en un objeto determinado en la interfaz de usuario y que admitan un esquema de enrutamiento de eventos en que más de un elemento tiene la oportunidad de controlar un evento de entrada. Muchos eventos de entrada tienen un par de eventos asociados.  Por ejemplo, el evento de tecla presionada está asociado con el <xref:System.Windows.Input.Keyboard.KeyDown> y <xref:System.Windows.Input.Keyboard.PreviewKeyDown> eventos.  La diferencia entre estos eventos radica en cómo se redirigen al elemento de destino.  Los eventos de vista previa tunelizan el árbol de elementos desde el elemento raíz al de destino.  Los eventos de propagación se propagan del elemento de destino al elemento raíz.  El enrutamiento de eventos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se describe con más detalle más adelante, dentro de esta información general, y en [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
### <a name="keyboard-and-mouse-classes"></a>Clases Keyboard y Mouse  
 Además de la entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en las clases de elementos base, el <xref:System.Windows.Input.Keyboard> clase y <xref:System.Windows.Input.Mouse> clases proporcionan adicionales [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] para trabajar con el teclado y mouse de entrada.  
  
 Ejemplos de entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en el <xref:System.Windows.Input.Keyboard> clase la <xref:System.Windows.Input.Keyboard.Modifiers%2A> propiedad, que devuelve el <xref:System.Windows.Input.ModifierKeys> presionados actualmente y el <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> método, que determina si se presiona una tecla especificada.  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> método para determinar si un <xref:System.Windows.Input.Key> está en estado presionado.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Ejemplos de entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en el <xref:System.Windows.Input.Mouse> clase <xref:System.Windows.Input.Mouse.MiddleButton%2A>, que obtiene el estado del botón central del mouse, y <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, que obtiene el elemento en el puntero del mouse está sobre.  
  
 En el ejemplo siguiente se determina si el <xref:System.Windows.Input.Mouse.LeftButton%2A> del mouse se encuentra en la <xref:System.Windows.Input.MouseButtonState.Pressed> estado.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 El <xref:System.Windows.Input.Mouse> y <xref:System.Windows.Input.Keyboard> clases se tratan con más detalle a lo largo de esta información general.  
  
### <a name="stylus-input"></a>Entrada del lápiz  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]tiene compatibilidad integrada para la <xref:System.Windows.Input.Stylus>.  El <xref:System.Windows.Input.Stylus> es una entrada de lápiz popularizó por la [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  Las aplicaciones de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pueden tratar el lápiz como un mouse mediante la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de mouse, pero [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también cuenta con una abstracción del dispositivo de lápiz que usa un modelo similar al del teclado y el mouse.  Todas las [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] relacionadas con el lápiz contienen la palabra "Stylus".  
  
 Dado que el lápiz puede actuar como un mouse, las aplicaciones que solo admiten la entrada de mouse pueden tener cierto nivel de compatibilidad con el lápiz automáticamente. Cuando se usa el lápiz de esta forma, la aplicación tiene la oportunidad de controlar el evento de lápiz adecuado y, a continuación, el evento de mouse correspondiente. Además, los servicios de nivel superior, como las entradas manuscritas, también están disponibles a través de la abstracción del dispositivo de lápiz.  Para obtener más información sobre la escritura con lápiz como entrada, consulte [Introducción a las entradas manuscritas](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Enrutamiento de eventos  
 Un <xref:System.Windows.FrameworkElement> puede contener otros elementos como elementos secundarios en su modelo de contenido, que forman un árbol de elementos.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento primario puede participar en la entrada dirigida a sus elementos secundarios o a otros descendientes al controlar los eventos. Esto es especialmente útil para crear controles a partir de los controles más pequeños, un proceso conocido como "composición de controles" o "composición". Para obtener más información acerca de los árboles de elementos y cómo se relacionan con las rutas de eventos, consulte [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 El enrutamiento de eventos es el proceso de reenviar eventos a varios elementos para que un objeto o elemento determinado de la ruta pueda elegir ofrecer una respuesta significativa (a través del control) a un evento que podría tener su origen en otro elemento.  Los eventos enrutados usan uno de los tres mecanismos de enrutamiento: directo, propagación y tunelización.  En el enrutamiento directo, el elemento de origen es el único elemento notificado y el evento no se redirige a ningún otro elemento. Sin embargo, el evento enrutado directo todavía ofrece algunas funcionalidades adicionales que solo están presentes para eventos enrutados, en lugar de para eventos de [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] estándares. La propagación prepara el árbol de elementos: en primer lugar, notifica al elemento que dio origen al evento; a continuación, al elemento primario, etc.  La tunelización comienza en la raíz del árbol de elementos y desciende para acabar con el elemento de origen original.  Para obtener más información sobre los eventos enrutados, consulte [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 Los eventos de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] suelen encontrarse en parejas formadas por un evento de tunelización y otro de propagación.  Los eventos de tunelización se distinguen de los eventos de propagación con el prefijo "Preview".  Por ejemplo, <xref:System.Windows.Input.Mouse.PreviewMouseMove> es la versión de túnel de un evento de movimiento del mouse y <xref:System.Windows.Input.Mouse.MouseMove> es la versión de propagación de este evento. Este emparejamiento de eventos es una convención que se implementa en el nivel de elemento y no es una funcionalidad propia del sistema de eventos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Para obtener más información, consulte la sección Eventos de entrada de WPF en [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Control de eventos de entrada  
 Para recibir una entrada en un elemento, se debe asociar un controlador de eventos con el evento concreto.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] es sencillo: se debe hacer referencia al nombre del evento como atributo del elemento que se escuchará para este evento.  A continuación, se establece el valor del atributo con el nombre del controlador de eventos que se define, en función de un delegado.  El controlador de eventos debe escribirse en código, como [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)], y puede incluirse en un archivo de código subyacente.  
  
 Los eventos de teclado tienen lugar cuando el sistema operativo notifica acciones de teclas que se producen mientras el foco del teclado está en un elemento. Los eventos de mouse y lápiz se dividen en dos categorías: eventos que informan de cambios en la posición del puntero en relación con el elemento y eventos que informan de cambios en el estado de los botones del dispositivo.  
  
### <a name="keyboard-input-event-example"></a>Ejemplo de evento de entrada de teclado  
 En el ejemplo siguiente se escucha una pulsación de tecla de flecha izquierda.  A <xref:System.Windows.Controls.StackPanel> se crea que tiene un <xref:System.Windows.Controls.Button>.  Un controlador de eventos para escuchar para presionar la tecla de flecha izquierda se adjunta a la <xref:System.Windows.Controls.Button> instancia.  
  
 La primera sección del ejemplo se crea el <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.Button> y asocia el controlador de eventos para el <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xaml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 La segunda sección está escrita en código y define el controlador de eventos.  Cuando se presiona la tecla de flecha izquierda y la <xref:System.Windows.Controls.Button> tiene el foco de teclado, se ejecuta el controlador y el <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> se cambia.  Si se presiona la tecla, pero no es la tecla de flecha izquierda, el <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> se vuelve a cambiar su color inicial.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Ejemplo de evento de entrada de mouse  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.Control.Background%2A> color de un <xref:System.Windows.Controls.Button> se cambia cuando el puntero del mouse entra en el <xref:System.Windows.Controls.Button>.  El <xref:System.Windows.Controls.Control.Background%2A> color se restaura cuando el mouse deja el <xref:System.Windows.Controls.Button>.  
  
 La primera sección del ejemplo se crea el <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.Button> controlar y adjunta los controladores de eventos para el <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> eventos para el <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 La segunda sección del ejemplo está escrita en código y define los controladores de eventos.  Cuando el mouse entra en el <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> se cambia a <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Cuando el mouse deja el <xref:System.Windows.Controls.Button>, el <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> vuelve a establecerse en <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Entrada de texto  
 El <xref:System.Windows.ContentElement.TextInput> evento le permite realizar escuchas de entrada de texto de una manera independiente del dispositivo. El teclado es el medio principal de entrada de texto, pero la voz, la escritura a mano y otros dispositivos de entrada también pueden generar entradas de texto.  
  
 Para la entrada de teclado, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] primero envía la correspondiente <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> eventos. Si no se controlan los eventos y la clave es texto en lugar de (una clave de control, como las flechas de dirección) o las teclas de función, un <xref:System.Windows.ContentElement.TextInput> evento se desencadena.  No siempre hay una asignación unívoca simple entre <xref:System.Windows.ContentElement.KeyDown> / <xref:System.Windows.ContentElement.KeyUp> y <xref:System.Windows.ContentElement.TextInput> eventos porque varias pulsaciones de tecla pueden generar un único carácter de entrada de texto y las pulsaciones de teclas solo pueden generar varios caracteres cadenas.  Esto es especialmente cierto en el caso de idiomas como el chino, japonés y coreano, que usan [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] para generar los miles de caracteres posibles de sus alfabetos correspondientes.  
  
 Cuando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] envía una <xref:System.Windows.ContentElement.KeyUp> / <xref:System.Windows.ContentElement.KeyDown> eventos, <xref:System.Windows.Input.KeyEventArgs.Key%2A> está establecido en <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> si las pulsaciones de teclas se pasan a formar parte de un <xref:System.Windows.ContentElement.TextInput> evento (si se presiona ALT + S, por ejemplo). Esto permite que el código en un <xref:System.Windows.ContentElement.KeyDown> controlador de eventos para comprobar si <xref:System.Windows.Input.Key.System?displayProperty=nameWithType> y, si lo encuentra, dejar el procesamiento para el controlador de posteriormente presionado <xref:System.Windows.ContentElement.TextInput> eventos. En estos casos, las diversas propiedades de la <xref:System.Windows.Input.TextCompositionEventArgs> argumento se puede utilizar para determinar las pulsaciones de teclas originales. De forma similar, si un [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] está activo, <xref:System.Windows.Input.Key> tiene el valor de <xref:System.Windows.Input.Key.ImeProcessed?displayProperty=nameWithType>, y <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> ofrece la pulsación de tecla o pulsaciones de teclas original.  
  
 En el ejemplo siguiente se define un controlador para el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento y un controlador para el <xref:System.Windows.UIElement.KeyDown> eventos.  
  
 El primer segmento de código o marcado crea la interfaz de usuario.  
  
 [!code-xaml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 El segundo segmento de código contiene los controladores de eventos.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Dado que los eventos de entrada propagan de la ruta del evento, el <xref:System.Windows.Controls.StackPanel> recibe la entrada independientemente del elemento que tiene el foco de teclado. El <xref:System.Windows.Controls.TextBox> se notifica al control primero y el `OnTextInputKeyDown` se llama controlador sólo si la <xref:System.Windows.Controls.TextBox> no controló la entrada. Si el <xref:System.Windows.UIElement.PreviewKeyDown> de eventos se usan en lugar de la <xref:System.Windows.UIElement.KeyDown> eventos, el `OnTextInputKeyDown` en primer lugar, se llamará al controlador.  
  
 En este ejemplo, la lógica de control se escribe dos veces: una vez para CTRL+O y otra para el evento de clic del botón. Esto se puede simplificar mediante el uso de comandos, en lugar de controlar los eventos de entrada directamente.  Los comandos se describen en esta información general y en [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Funciones táctiles y manipulación  
 El nuevo hardware y la API en el sistema operativo Windows 7 proporcionan a las aplicaciones la capacidad de recibir entradas de varios toques simultáneamente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] permite que las aplicaciones detecten las funciones táctiles y respondan a ellas del mismo modo que con otras entradas, como el mouse o el teclado, y que generen eventos cuando se detecta un toque.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] expone dos tipos de eventos cuando se usa una función táctil: eventos de función táctil y eventos de manipulación. Los eventos de función táctil proporcionan datos sin procesar sobre cada dedo en una pantalla táctil y su movimiento. Los eventos de manipulación interpretan la entrada como determinadas acciones. Ambos tipos de eventos se describen en esta sección.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Para desarrollar una aplicación que responda a las funciones táctiles, necesitará los componentes siguientes.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Un dispositivo, como una pantalla táctil, compatible con Windows Touch.  
  
### <a name="terminology"></a>Terminología  
 Para referirse a la función táctil, se usan los términos siguientes.  
  
-   **La función táctil** es un tipo de entrada de usuario que reconoce Windows 7. Normalmente, se inicia colocando los dedos en una pantalla táctil. Tenga en cuenta que algunos dispositivos, como el panel táctil habitual en portátiles, no admiten la función táctil cuando se limitan a convertir la posición y el movimiento del dedo a entradas de mouse.  
  
-   **La función multitáctil** es una función táctil que tiene lugar desde más de un punto de forma simultánea. Windows 7 y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admiten la función multitáctil. Cada vez que se menciona la función táctil en la documentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los conceptos se aplican a la función multitáctil.  
  
-   Una **manipulación** se produce cuando la función táctil se interpreta como una acción física que se aplica a un objeto. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los eventos de manipulación interpretan las entradas como una manipulación de traducción, expansión o rotación.  
  
-   `touch device` representa un dispositivo que genera entradas táctiles, como un solo dedo en una pantalla táctil.  
  
### <a name="controls-that-respond-to-touch"></a>Controles que responden a la función táctil  
 Los siguientes controles se pueden desplazar al arrastrar un dedo por el control si tiene contenido que se desplaza fuera de la vista.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 El <xref:System.Windows.Controls.ScrollViewer> define la <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=nameWithType> adjunta la propiedad que le permite especificar si el modo panorámico táctil está habilitado horizontalmente, verticalmente, ambos o ninguno. El <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=nameWithType> propiedad especifica qué rapidez el desplazamiento se ralentiza cuando el usuario levanta el dedo desde la pantalla táctil. El <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=nameWithType> propiedad adjunta especifica la proporción de desplazamiento para traducir el desplazamiento de manipulación.  
  
### <a name="touch-events"></a>Eventos de funciones táctiles  
 Las clases base, <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, y <xref:System.Windows.ContentElement>, definen eventos que se pueden suscribir a por lo que la aplicación responda a la entrada táctil. Los eventos de funciones táctiles resultan útiles cuando la aplicación interpreta la función táctil como algo distinto a la manipulación de un objeto. Por ejemplo, una aplicación que permite a un usuario dibujar con uno o más dedos podría suscribirse a los eventos de función táctil.  
  
 Las tres clases definen los siguientes eventos, que se comportan de forma similar, independientemente de la clase de definición.  
  
-   <xref:System.Windows.UIElement.TouchDown>  
  
-   <xref:System.Windows.UIElement.TouchMove>  
  
-   <xref:System.Windows.UIElement.TouchUp>  
  
-   <xref:System.Windows.UIElement.TouchEnter>  
  
-   <xref:System.Windows.UIElement.TouchLeave>  
  
-   <xref:System.Windows.UIElement.PreviewTouchDown>  
  
-   <xref:System.Windows.UIElement.PreviewTouchMove>  
  
-   <xref:System.Windows.UIElement.PreviewTouchUp>  
  
-   <xref:System.Windows.UIElement.GotTouchCapture>  
  
-   <xref:System.Windows.UIElement.LostTouchCapture>  
  
 Del mismo modo que los eventos de teclado y mouse, los eventos de función táctil son eventos enrutados. Los eventos que empiezan por `Preview` son eventos de tunelización, mientras que los que empiezan por `Touch` son eventos de propagación. Para obtener más información sobre los eventos enrutados, consulte [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md). Al controlar estos eventos, puede obtener la posición de la entrada, con respecto a todos los elementos, mediante una llamada a la <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> o <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> método.  
  
 Para entender la interacción entre los eventos de función táctil, considere un escenario en que un usuario coloca un dedo en un elemento, lo mueve en el elemento y, a continuación, lo levanta. En la ilustración siguiente se muestra la ejecución de los eventos de propagación (los eventos de tunelización se omiten por motivos de simplicidad).  
  
 ![La secuencia de eventos de toque. ] (../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
Eventos de función táctil  
  
 En la lista siguiente se describe la secuencia de los eventos de la ilustración anterior.  
  
1.  El <xref:System.Windows.UIElement.TouchEnter> evento se produce una vez cuando el usuario coloca un dedo en el elemento.  
  
2.  El <xref:System.Windows.UIElement.TouchDown> evento tiene lugar una vez.  
  
3.  El <xref:System.Windows.UIElement.TouchMove> evento aparece varias veces cuando el usuario mueve el dedo dentro del elemento.  
  
4.  El <xref:System.Windows.UIElement.TouchUp> evento tiene lugar cuando el usuario levanta el dedo desde el elemento de una vez.  
  
5.  El <xref:System.Windows.UIElement.TouchLeave> evento tiene lugar una vez.  
  
 Cuando se usan más de dos dedos, se producen eventos para cada dedo.  
  
### <a name="manipulation-events"></a>Eventos de manipulación  
 Para los casos donde una aplicación permite a los usuarios manipular un objeto, el <xref:System.Windows.UIElement> clase define los eventos de manipulación. A diferencia de los eventos de función táctil que, simplemente, notifican la posición de la función táctil, los eventos de manipulación indican cómo se puede interpretar la entrada. Hay tres tipos de manipulación: traducción, expansión y rotación. En la lista siguiente se describe cómo invocar los tres tipos de manipulaciones.  
  
-   Coloque un dedo en un objeto y mueva el dedo por la pantalla táctil para invocar una manipulación de traducción. Normalmente, esto mueve el objeto.  
  
-   Coloque dos dedos en un objeto y acérquelos o aléjelos para invocar una manipulación de expansión. Normalmente, esto cambia el tamaño del objeto.  
  
-   Coloque dos dedos en un objeto y gírelos entre sí para invocar una manipulación de rotación. Normalmente, esto gira el objeto.  
  
 Se puede producir más de un tipo de manipulación al mismo tiempo.  
  
 Cuando hace que los objetos respondan a manipulaciones, puede hacer que parezca que el objeto tenga inercia. Esto puede hacer que los objetos simulen el mundo físico. Por ejemplo, si empuja un libro encima de una mesa con suficiente fuerza, el libro seguirá moviéndose cuando lo suelte. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] le permite simular este comportamiento, ya que puede generar eventos de manipulación cuando los dedos del usuario liberan el objeto.  
  
 Para obtener información sobre cómo crear una aplicación que permita al usuario mover y girar un objeto, o cambiar su tamaño, consulte [Tutorial: Crear su primera aplicación táctil](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 El <xref:System.Windows.UIElement> define los siguientes eventos de manipulación.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 De forma predeterminada, un <xref:System.Windows.UIElement> no recibe estos eventos de manipulación. Para recibir eventos de manipulación en una <xref:System.Windows.UIElement>, establezca <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=nameWithType> a `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>Ruta de acceso de ejecución de eventos de manipulación  
 Considere un escenario en que un usuario "lanza" un objeto. El usuario coloca un dedo en el objeto, mueve el dedo por la pantalla táctil una distancia corta y, a continuación, lo levanta mientras se mueve. El resultado es que el objeto se moverá bajo el dedo del usuario y lo seguirá haciendo cuando el usuario lo levante.  
  
 En la ilustración siguiente se muestra la ruta de acceso de ejecución de los eventos de manipulación e información importante sobre cada evento.  
  
 ![La secuencia de eventos de manipulación. ] (../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
Eventos de manipulación  
  
 En la lista siguiente se describe la secuencia de los eventos de la ilustración anterior.  
  
1.  El <xref:System.Windows.UIElement.ManipulationStarting> evento tiene lugar cuando el usuario coloca un dedo en el objeto. Entre otras cosas, este evento le permite establecer el <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> propiedad. En los eventos posteriores, la posición de la manipulación será relativa a la <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. En eventos distintos de <xref:System.Windows.UIElement.ManipulationStarting>, esta propiedad es de solo lectura, por lo que el <xref:System.Windows.UIElement.ManipulationStarting> evento es la única vez que se puede establecer esta propiedad.  
  
2.  El <xref:System.Windows.UIElement.ManipulationStarted> a continuación se produce el evento. Este evento indica el origen de la manipulación.  
  
3.  El <xref:System.Windows.UIElement.ManipulationDelta> evento aparece varias veces como movimiento de dedos de un usuario en una pantalla táctil. El <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> propiedad de la <xref:System.Windows.Input.ManipulationDeltaEventArgs> clase notifica si la manipulación se interpreta como el movimiento, expansión o traducción. En este punto se realiza la mayoría del trabajo de manipulación de un objeto.  
  
4.  El <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento tiene lugar cuando los dedos del usuario pierden el contacto con el objeto. Este evento permite especificar la desaceleración de las manipulaciones durante la inercia. Esto sirve para que el objeto pueda emular espacios físicos o atributos diferentes, si así lo elige. Por ejemplo, suponga que la aplicación tiene dos objetos que representan elementos del mundo físico y que uno es más pesado que el otro. Puede hacer que el objeto más pesado disminuya su velocidad más rápidamente que el objeto ligero.  
  
5.  El <xref:System.Windows.UIElement.ManipulationDelta> evento aparece varias veces cuando se realiza la inercia. Tenga en cuenta que este evento se produce cuando los dedos del usuario se mueven por la pantalla táctil y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] simula la inercia. En otras palabras, <xref:System.Windows.UIElement.ManipulationDelta> se produce antes y después de la <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos. El <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=nameWithType> propiedad informes si el <xref:System.Windows.UIElement.ManipulationDelta> evento tiene lugar durante la inercia, para que pueda comprobar esa propiedad y realizar acciones diferentes, dependiendo de su valor.  
  
6.  El <xref:System.Windows.UIElement.ManipulationCompleted> evento se produce cuando finaliza la manipulación y la inercia. Es decir, todos los después la <xref:System.Windows.UIElement.ManipulationDelta> eventos se producen, el <xref:System.Windows.UIElement.ManipulationCompleted> se produce un evento para indicar que la manipulación está completa.  
  
 El <xref:System.Windows.UIElement> también define la <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos. Este evento se produce cuando el <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> método se llama en el <xref:System.Windows.UIElement.ManipulationDelta> eventos. El <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos permite a las aplicaciones o componentes proporcionan información visual cuando un objeto alcanza un límite. Por ejemplo, el <xref:System.Windows.Window> clase controla la <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> evento hace que la ventana se mueva ligeramente cuando se encuentra el borde.  
  
 Puede cancelar la manipulación mediante una llamada a la <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> método en los argumentos de evento de cualquier evento de manipulación excepto <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos. Cuando se llama a <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, ya no se generan los eventos de manipulación y los eventos del mouse se producen para entrada táctil. En la tabla siguiente se describe la relación entre el momento en que se cancela la manipulación y los eventos del mouse que se producen.  
  
|Evento con el que se llama al método Cancel|Eventos del mouse que se generan para entradas que ya se han producido|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> y <xref:System.Windows.UIElement.ManipulationStarted>|Eventos de presión del mouse.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|Eventos de presión y movimiento del mouse.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> y <xref:System.Windows.UIElement.ManipulationCompleted>|Eventos de presión, movimiento y liberación del mouse.|  
  
 Tenga en cuenta que si se llama a <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> cuando la manipulación está en inercia, el método devuelve `false` y la entrada no genera eventos del mouse.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>Relación entre eventos de función táctil y manipulación  
 Un <xref:System.Windows.UIElement> siempre puede recibir eventos de toque. Cuando el <xref:System.Windows.UIElement.IsManipulationEnabled%2A> propiedad está establecida en `true`, un <xref:System.Windows.UIElement> pueden recibir eventos de manipulación y toque.  Si el <xref:System.Windows.UIElement.TouchDown> no se controló el evento (es decir, el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad es `false`), la lógica de manipulación captura la entrada táctil en el elemento y genera los eventos de manipulación. Si el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad está establecida en `true` en el <xref:System.Windows.UIElement.TouchDown> eventos, la lógica de manipulación no generan eventos de manipulación. En la siguiente ilustración se muestra la relación entre los eventos de función táctil y los de manipulación.  
  
 ![Relación entre los eventos de manipulación y toque](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
Eventos de función táctil y de manipulación  
  
 En la lista siguiente se describe la relación entre los eventos de función táctil y de manipulación que se muestra en la ilustración anterior.  
  
-   Cuando el primer dispositivo de toque genera un <xref:System.Windows.UIElement.TouchDown> eventos en un <xref:System.Windows.UIElement>, las llamadas de la lógica de manipulación la <xref:System.Windows.UIElement.CaptureTouch%2A> método, que genera el <xref:System.Windows.UIElement.GotTouchCapture> eventos.  
  
-   Cuando el <xref:System.Windows.UIElement.GotTouchCapture> se produce, las llamadas de la lógica de manipulación la <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=nameWithType> método, que genera el <xref:System.Windows.UIElement.ManipulationStarting> eventos.  
  
-   Cuando el <xref:System.Windows.UIElement.TouchMove> los eventos se producen, la lógica de manipulación genera el <xref:System.Windows.UIElement.ManipulationDelta> eventos que se producen antes de la <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos.  
  
-   Cuando el último dispositivo táctil el elemento provoca la <xref:System.Windows.UIElement.TouchUp> la lógica de manipulación genera el evento, el <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos.  
  
<a name="focus"></a>   
## <a name="focus"></a>Foco  
 Hay dos conceptos principales relacionados con el foco en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: el foco de teclado y el foco lógico.  
  
### <a name="keyboard-focus"></a>Foco de teclado  
 El foco de teclado hace referencia al elemento que recibe la entrada del teclado.  Puede haber un único elemento en todo el escritorio que tenga el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tendrá el elemento que tiene el foco de teclado <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> establecido en `true`.  El método estático <xref:System.Windows.Input.Keyboard> método <xref:System.Windows.Input.Keyboard.FocusedElement%2A> devuelve el elemento que tiene actualmente el foco del teclado.  
  
 El foco de teclado puede obtenerse de tabulación a un elemento o haga clic en el mouse en determinados elementos, como un <xref:System.Windows.Controls.TextBox>.  El foco de teclado también se puede obtener mediante programación utilizando la <xref:System.Windows.Input.Keyboard.Focus%2A> método en la <xref:System.Windows.Input.Keyboard> clase.  <xref:System.Windows.Input.Keyboard.Focus%2A>intenta dar el foco de teclado del elemento especificado.  El elemento devuelto por <xref:System.Windows.Input.Keyboard.Focus%2A> es el elemento que tiene actualmente el foco del teclado.  
  
 En orden para un elemento que se va a obtener el foco del teclado el <xref:System.Windows.UIElement.Focusable%2A> propiedad y el <xref:System.Windows.UIElement.IsVisible%2A> propiedades deben establecerse en **true**.  Algunas clases, como <xref:System.Windows.Controls.Panel>, tienen <xref:System.Windows.UIElement.Focusable%2A> establecido en `false` de forma predeterminada; por lo tanto, puede que tenga que establecer esta propiedad en `true` si desea que ese elemento para poder obtener el foco.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Input.Keyboard.Focus%2A> para establecer el foco de teclado en un <xref:System.Windows.Controls.Button>.  Es el lugar recomendado para establecer el foco inicial en una aplicación en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Para obtener más información acerca del foco de teclado, consulte [Foco de teclado](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Foco lógico  
 El foco lógico hace referencia a la <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> en un ámbito de foco.  Puede haber varios elementos que tengan el foco lógico en una aplicación, pero solo puede haber uno con el foco lógico en un ámbito de foco concreto.  
  
 Un ámbito de foco es un elemento contenedor que realiza un seguimiento de los <xref:System.Windows.Input.FocusManager.FocusedElement%2A> dentro de su ámbito.  Cuando el foco sale de un ámbito de foco, el elemento enfocado pierde el foco de teclado, pero conserva el foco lógico.  Cuando el foco vuelve al ámbito de foco, el elemento enfocado recibe el foco de teclado.  Esto permite cambiar el foco de teclado entre varios ámbitos de foco, pero garantiza que el elemento enfocado dentro del ámbito siga siendo el elemento enfocado cuando vuelva el foco.  
  
 Un elemento se puede convertir en un ámbito de foco en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] estableciendo la <xref:System.Windows.Input.FocusManager> propiedad adjunta <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> a `true`, o en el código estableciendo la propiedad adjunta mediante el <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> método.  
  
 En el ejemplo siguiente se realiza una <xref:System.Windows.Controls.StackPanel> en un ámbito de foco estableciendo la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> propiedad adjunta.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que son ámbitos de foco de forma predeterminada son <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, y <xref:System.Windows.Controls.ContextMenu>.  
  
 Un elemento que tiene el foco de teclado también tendrá el foco lógico para el ámbito de foco pertenece a; Por consiguiente, establecer el foco en un elemento con la <xref:System.Windows.Input.Keyboard.Focus%2A> método en la <xref:System.Windows.Input.Keyboard> clase o las clases de elementos base intentará dar el foco de teclado del elemento y el foco lógico.  
  
 Para determinar el elemento tiene el foco en un ámbito de foco, utilice <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Para cambiar el elemento tiene el foco de un ámbito de foco, utilice <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Para obtener más información acerca del foco lógico, consulte [Foco lógico](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Posición del mouse  
 La [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona información útil respecto a los espacios de coordenadas.  Por ejemplo, la coordenada `(0,0)` es la coordenada superior izquierda, pero ¿de qué elemento del árbol? ¿El elemento de destino de la entrada? ¿El elemento adjunto al controlador de eventos? ¿O alguna otra cosa? Para evitar confusiones, la [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] de entrada de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] requiere que especifique el marco de referencia cuando trabaje con coordenadas obtenidas a través del mouse. El <xref:System.Windows.Input.Mouse.GetPosition%2A> método devuelve la coordenada del puntero del mouse en relación con el elemento especificado.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Captura del mouse  
 Los dispositivos de mouse tienen una característica modal concreta que se denomina captura del mouse. La captura del mouse se usa para mantener un estado de entrada transitorio cuando se inicia una operación de arrastrar y colocar, para que otras operaciones relacionadas con la posición en pantalla nominal del puntero del mouse no se produzcan necesariamente. Al arrastrar, el usuario no puede hacer clic sin anular la acción de arrastrar y colocar, lo que hace que la mayoría de las indicaciones que se producen al pasar el mouse sean inadecuadas mientras se conserva la captura del mouse desde el origen de la acción de arrastrar. El sistema de entrada expone [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que pueden determinar el estado de captura del mouse, además de [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que pueden forzar la captura del mouse en un elemento concreto o borrar el estado de la captura del mouse. Para obtener más información sobre las operaciones de arrastrar y colocar, consulte [Información general sobre la función de arrastrar y colocar](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Comandos  
 Los comandos habilitan el control de entrada en un nivel más semántico que la entrada de dispositivos.  Los comandos son directivas sencillas, como `Cut`, `Copy`, `Paste` o `Open`.  Los comandos son útiles para centralizar la lógica de comando.  El mismo comando puede tener acceso desde una <xref:System.Windows.Controls.Menu>, en un <xref:System.Windows.Controls.ToolBar>, o a través de un método abreviado de teclado. Los comandos también proporcionan un mecanismo para deshabilitar controles cuando el comando deja de estar disponible.  
  
 <xref:System.Windows.Input.RoutedCommand>es el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación de <xref:System.Windows.Input.ICommand>.  Cuando un <xref:System.Windows.Input.RoutedCommand> se ejecuta, un <xref:System.Windows.Input.CommandManager.PreviewExecuted> y un <xref:System.Windows.Input.CommandManager.Executed> evento se desencadena en el destino del comando, qué túnel y burbujas a través del árbol de elementos como otra entrada.  Si no se define ningún destino de comando, el elemento con el foco de teclado será el destino del comando.  La lógica que ejecuta el comando se adjunta a un <xref:System.Windows.Input.CommandBinding>.  Cuando un <xref:System.Windows.Input.CommandManager.Executed> evento alcanza un <xref:System.Windows.Input.CommandBinding> para ese comando concreto, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> en el <xref:System.Windows.Input.CommandBinding> se llama.  Este controlador realiza la acción del comando.  
  
 Para obtener más información sobre los comandos, consulte [Información general sobre los comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona una biblioteca de comandos comunes que consta de <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, y <xref:System.Windows.Documents.EditingCommands>, o puede definir las suyas propias.  
  
 En el ejemplo siguiente se muestra cómo configurar un <xref:System.Windows.Controls.MenuItem> para que cuando se hace clic en invocará la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando el <xref:System.Windows.Controls.TextBox>, suponiendo que el <xref:System.Windows.Controls.TextBox> tiene el foco de teclado.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Para obtener más información sobre los comandos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>Sistema de entrada y elementos base  
 Eventos de entrada como los eventos adjuntos definidos por el <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, y <xref:System.Windows.Input.Stylus> clases se generados por el sistema de entrada y se insertan en una posición concreta en el modelo de objetos basado en el árbol visual en tiempo de ejecución de la prueba de posicionamiento.  
  
 Cada uno de los eventos que <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, y <xref:System.Windows.Input.Stylus> definir como un evento adjunto también se puede volver a exponer mediante las clases de elementos base <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> como un nuevo evento enrutado. Los eventos enrutados de elementos base se generan desde clases que controlan el evento adjunto original y reutilizan los datos del evento.  
  
 Cuando el evento de entrada se asocia con un elemento de origen determinado a través de la implementación del evento de entrada de elemento base, se puede redirigir a través del resto de una ruta de evento que se basa en una combinación de objetos del árbol lógico y visual, y se puede controlar desde el código de la aplicación.  Por lo general, resulta más conveniente controlar estos eventos de entrada relacionados con los dispositivos utilizando los eventos enrutados en <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>, ya que puede utilizar eventos controlador una sintaxis más intuitiva ambos en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en el código. También puede elegir controlar el evento adjunto que inició el proceso, pero tendría que enfrentarse a varios problemas: el evento adjunto puede estar marcado como controlado por el control de la clase de elemento base, y debe utilizar métodos de descriptor de acceso, en lugar de la sintaxis de eventos true a fin de adjuntar controladores para eventos adjuntos.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Pasos adicionales  
 Ahora dispone de varias técnicas para controlar la entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  También debe tener una mejor comprensión de los distintos tipos de eventos de entrada y los mecanismos de eventos enrutados que usa [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Existen recursos adicionales que explican los elementos del marco de trabajo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y el enrutamiento de eventos con más detalle. Consulte los temas siguientes para obtener más información: [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md), [Información general sobre el foco](../../../../docs/framework/wpf/advanced/focus-overview.md), [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md) e [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el foco](../../../../docs/framework/wpf/advanced/focus-overview.md)  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)  
 [Propiedades](../../../../docs/framework/wpf/advanced/properties-wpf.md)
