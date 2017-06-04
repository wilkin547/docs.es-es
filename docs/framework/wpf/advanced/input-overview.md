---
title: "Informaci&#243;n general sobre acciones del usuario | Microsoft Docs"
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
  - "comandos [WPF]"
  - "información general, de entrada [WPF]"
  - "foco de teclado [WPF]"
  - "entrada mediante teclado [WPF]"
  - "touch (eventos) [WPF]"
  - "enrutamiento de eventos [WPF]"
  - "entrada táctil [WPF]"
  - "manipulación [WPF]"
  - "foco lógico [WPF]"
  - "entrada del lápiz [WPF]"
  - "entrada de texto [WPF]"
  - "eventos de entrada [WPF], control"
  - "WPF, información general de entrada"
  - "eventos de manipulación [WPF]"
  - "entrada del mouse [WPF]"
  - "captura del mouse [WPF]"
  - "foco [WPF]"
  - "posición del mouse [WPF]"
ms.assetid: ee5258b7-6567-415a-9b1c-c0cbe46e79ef
caps.latest.revision: 50
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 50
---
# Informaci&#243;n general sobre acciones del usuario
<a name="introduction"></a>El[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] proporciona un eficaz subsistema [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] para obtener los datos desde una variedad de dispositivos, incluidos el mouse, el teclado, el toque y el lápiz. Este tema describen los servicios proporcionados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] y explica la arquitectura de los sistemas de entrada.  
  
  
<a name="input_api"></a>   
## <a name="input-api"></a>API de entrada  
 La entrada principal [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] exposición se encuentra en las clases de elementos base: <xref:System.Windows.UIElement>, <xref:System.Windows.ContentElement>, <xref:System.Windows.FrameworkElement>, y <xref:System.Windows.FrameworkContentElement>.  Para obtener más información sobre los elementos base, vea [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  Estas clases proporcionan funcionalidad para los eventos de entrada relacionados con las presiones de tecla, botones del mouse, rueda del mouse, movimiento del mouse, administración del foco y la captura del mouse, por nombrar algunos. Al colocar la entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en los elementos base, en lugar de tratar todos los eventos de entrada como un servicio, la arquitectura de entrada habilita los eventos de entrada tengan su origen en un objeto determinado en la interfaz de usuario y para admitir un esquema de enrutamiento de eventos donde más de un elemento tiene la oportunidad de controlar un evento de entrada. Muchos eventos de entrada tienen un par de eventos asociados a ellos.  Por ejemplo, el evento soltar tecla está asociado con el <xref:System.Windows.Input.Keyboard.KeyDown> y <xref:System.Windows.Input.Keyboard.PreviewKeyDown> eventos.  La diferencia en estos eventos radica en cómo se enrutan al elemento de destino.  Túnel de eventos de vista previa por el árbol de elementos desde el elemento raíz para el elemento de destino.  Propagar eventos ascienden desde el elemento de destino para el elemento raíz.  Enrutamiento de eventos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se describe con más detalle más adelante en esta información general y, en la [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
### <a name="keyboard-and-mouse-classes"></a>Clases de Mouse y teclado  
 Además de la entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en las clases de elementos base, el <xref:System.Windows.Input.Keyboard> clase y <xref:System.Windows.Input.Mouse> clases proporcionan adicionales [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] para trabajar con el teclado y mouse de entrada.  
  
 Ejemplos de entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en el <xref:System.Windows.Input.Keyboard> clase la <xref:System.Windows.Input.Keyboard.Modifiers%2A> propiedad, que devuelve el <xref:System.Windows.Input.ModifierKeys> está presionada y el <xref:System.Windows.Input.Keyboard.IsKeyDown%2A> método, que determina si se presiona una tecla especificada.  
  
 En el ejemplo siguiente se utiliza la <xref:System.Windows.Input.Keyboard.GetKeyStates%2A> método para determinar si un <xref:System.Windows.Input.Key> está en estado presionado.  
  
 [!code-csharp[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyArgsSnippetSample/CSharp/Window1.xaml.cs#keyeventargskeyboardgetkeystates)]
 [!code-vb[keyargssnippetsample#KeyEventArgsKeyBoardGetKeyStates](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyArgsSnippetSample/visualbasic/window1.xaml.vb#keyeventargskeyboardgetkeystates)]  
  
 Ejemplos de entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] en el <xref:System.Windows.Input.Mouse> clase <xref:System.Windows.Input.Mouse.MiddleButton%2A>, que obtiene el estado del botón central del mouse, y <xref:System.Windows.Input.Mouse.DirectlyOver%2A>, que obtiene el elemento en el puntero del mouse está sobre.  
  
 En el ejemplo siguiente se determina si el <xref:System.Windows.Input.Mouse.LeftButton%2A> del mouse se encuentra en la <xref:System.Windows.Input.MouseButtonState> estado.  
  
 [!code-csharp[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MouseRelatedSnippets/CSharp/Window1.xaml.cs#mouserelatedsnippetsgetleftbuttonmouse)]
 [!code-vb[mouserelatedsnippets#MouseRelatedSnippetsGetLeftButtonMouse](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MouseRelatedSnippets/visualbasic/window1.xaml.vb#mouserelatedsnippetsgetleftbuttonmouse)]  
  
 El <xref:System.Windows.Input.Mouse> y <xref:System.Windows.Input.Keyboard> clases se tratan con más detalle en esta información general.  
  
### <a name="stylus-input"></a>Entrada de lápiz  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]tiene compatibilidad integrada para la <xref:System.Windows.Input.Stylus>.  El <xref:System.Windows.Input.Stylus> es una entrada de lápiz popularizó por la [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]las aplicaciones pueden tratar el lápiz como un mouse con el mouse [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)], pero [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] también expone una abstracción del dispositivo de lápiz que usar un modelo similar para el teclado y el mouse.  Todos los relacionados con el lápiz [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] contienen la palabra "Lápiz".  
  
 Dado que el lápiz puede actuar como un mouse, las aplicaciones que admiten entrada de mouse sólo pueden obtener los cierto nivel de compatibilidad con el lápiz automáticamente. Cuando se utiliza el lápiz de esta forma, la aplicación tiene la oportunidad de controlar el evento de lápiz adecuado y, a continuación, controla el evento de mouse correspondiente. Además, los servicios de nivel superior como entradas manuscritas también están disponibles a través de la abstracción del dispositivo de lápiz.  Para obtener más información acerca de la entrada manuscrita como entrada, consulte [Getting Started with Ink](../../../../docs/framework/wpf/advanced/getting-started-with-ink.md).  
  
<a name="event_routing"></a>   
## <a name="event-routing"></a>Enrutamiento de eventos  
 Un <xref:System.Windows.FrameworkElement> puede contener otros elementos como elementos secundarios en su modelo de contenido, que forman un árbol de elementos.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento primario puede participar en la entrada dirigida a sus elementos secundarios o a otros descendientes controlando los eventos. Esto es especialmente útil para crear controles fuera de los controles más pequeños, un proceso conocido como "composición de controles" o "composición". Para obtener más información acerca de los árboles de elementos y cómo se relacionan con árboles de elementos a las rutas de eventos, vea [árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).  
  
 Enrutamiento de eventos es el proceso de reenvío de eventos a varios elementos, para que pueda elegir un objeto o elemento determinado a lo largo de la ruta ofrecer una respuesta significativa (a través de control) a un evento que podría tener su origen en otro elemento.  Eventos enrutados utilizan uno de los tres mecanismos de enrutamientos: directo, propagación y túnel.  En el enrutamiento directo, el elemento de origen es el único elemento una notificación y el evento no se enruta a los demás elementos. Sin embargo, el evento enrutado directo todavía ofrece algunas capacidades adicionales que sólo están presentes para los eventos enrutados en lugar de estándar [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] eventos. La propagación asciende por el árbol de elementos notificando primero al elemento que originó el evento, a continuación, el elemento primario y así sucesivamente.  Túnel comienza en la raíz del árbol de elementos y desciende termina con el elemento de origen original.  Para obtener más información sobre eventos enrutados, vea [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]eventos de entrada generalmente vienen en parejas que consta de un evento de túnel y un evento de propagación.  Los eventos de tunelización se distinguen de los eventos de propagación con el prefijo "Preview".  Por ejemplo, <xref:System.Windows.Input.Mouse.PreviewMouseMove> es la versión de tunelización de un evento de movimiento del mouse y <xref:System.Windows.Input.Mouse.MouseMove> es la versión de propagación de este evento. Este emparejamiento de eventos es una convención que se implementa en el nivel de elemento y no es una funcionalidad propia de la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sistema de eventos. Para obtener más información, consulte la sección eventos de entrada de WPF en [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
<a name="handling_input_events"></a>   
## <a name="handling-input-events"></a>Entrada de control de eventos  
 Para recibir la entrada en un elemento, un controlador de eventos debe asociarse a ese evento concreto.  En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esto es sencillo: hace referencia al nombre del evento como un atributo del elemento que se va a escuchar para este evento.  A continuación, establezca el valor del atributo con el nombre del controlador de eventos que se define, basado en un delegado.  El controlador de eventos debe escribirse en código como [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] y puede incluirse en un archivo de código subyacente.  
  
 Eventos de teclado ocurren cuando el sistema operativo notifica acciones de teclas que se producen mientras el foco del teclado está en un elemento. Eventos del mouse y lápiz cada se dividen en dos categorías: eventos que informan de cambios en la posición del puntero en relación con el elemento y eventos que informan de cambios en el estado de los botones del dispositivo.  
  
### <a name="keyboard-input-event-example"></a>Ejemplo de evento de entrada de teclado  
 En el ejemplo siguiente se realiza escuchas para presionar una tecla de flecha izquierda.  Un <xref:System.Windows.Controls.StackPanel> se crea que tiene un <xref:System.Windows.Controls.Button>.  Un controlador de eventos para escuchar las presionar la tecla de flecha izquierda se adjunta a la <xref:System.Windows.Controls.Button> instancia.  
  
 La primera sección del ejemplo crea el <xref:System.Windows.Controls.StackPanel> y <xref:System.Windows.Controls.Button> y asocia el controlador de eventos para el <xref:System.Windows.UIElement.KeyDown>.  
  
 [!code-xml[InputOvw#Input_OvwKeyboardExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwkeyboardexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexampleuicodebehind)]  
  
 La segunda sección está escrita en código y define el controlador de eventos.  Cuando se presiona la tecla de flecha izquierda y la <xref:System.Windows.Controls.Button> tiene el foco de teclado, se ejecuta el controlador y el <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> ha cambiado.  Si se presiona la tecla, pero no es la tecla de flecha izquierda, el <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> se vuelve a cambiar su color inicial.  
  
 [!code-csharp[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwkeyboardexamplehandlercodebehind)]
 [!code-vb[InputOvw#Input_OvwKeyboardExampleHandlerCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwkeyboardexamplehandlercodebehind)]  
  
### <a name="mouse-input-event-example"></a>Ejemplo de evento de entrada de mouse  
 En el ejemplo siguiente, la <xref:System.Windows.Controls.Control.Background%2A> color de un <xref:System.Windows.Controls.Button> cambia cuando el puntero del mouse entra en el <xref:System.Windows.Controls.Button>.  El <xref:System.Windows.Controls.Control.Background%2A> color se restaura cuando el mouse sale de la <xref:System.Windows.Controls.Button>.  
  
 La primera sección del ejemplo crea el <xref:System.Windows.Controls.StackPanel> y la <xref:System.Windows.Controls.Button> controlar y adjunta los controladores de eventos para el <xref:System.Windows.UIElement.MouseEnter> y <xref:System.Windows.UIElement.MouseLeave> eventos a la <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[InputOvw#Input_OvwMouseExampleXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwmouseexamplexaml)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleuicodebehind)]
 [!code-vb[InputOvw#Input_OvwMouseExampleUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleuicodebehind)]  
  
 La segunda sección del ejemplo está escrita en código y define los controladores de eventos.  Cuando el mouse entra en el <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> cambia a <xref:System.Windows.Media.Brushes.SlateGray%2A>.  Cuando el mouse sale de la <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.Control.Background%2A> color de la <xref:System.Windows.Controls.Button> se vuelve a cambiar <xref:System.Windows.Media.Brushes.AliceBlue%2A>.  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleeneterhandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleEneterHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleeneterhandler)]  
  
 [!code-csharp[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwmouseexampleleavehandler)]
 [!code-vb[InputOvw#Input_OvwMouseExampleLeaveHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwmouseexampleleavehandler)]  
  
<a name="text_input"></a>   
## <a name="text-input"></a>Entrada de texto  
 El <xref:System.Windows.ContentElement.TextInput> evento le permite realizar escuchas de entrada de texto de una manera independiente del dispositivo. El teclado es el medio principal de escritura de entrada, pero la voz, texto y otros dispositivos de entrada pueden generar también la entrada de texto.  
  
 Para la entrada de teclado, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] envía primero adecuado <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> eventos. Si no se controlan los eventos y la tecla es de texto en lugar de (una clave de control como flechas direccionales) o las teclas de función, un <xref:System.Windows.ContentElement.TextInput> provoca el evento.  No siempre hay una asignación unívoca simple entre <xref:System.Windows.ContentElement.KeyDown>/<xref:System.Windows.ContentElement.KeyUp> y <xref:System.Windows.ContentElement.TextInput> eventos porque varias pulsaciones de tecla pueden generar un único carácter de entrada de texto y las pulsaciones de teclas solo pueden generar cadenas de varios caracteres.  Esto es especialmente cierto para idiomas como el chino, japonés y coreano que usen [!INCLUDE[TLA#tla_ime#plural](../../../../includes/tlasharptla-imesharpplural-md.md)] para generar los miles de caracteres posibles de sus alfabetos correspondientes.  
  
 Cuando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] envía una <xref:System.Windows.ContentElement.KeyUp>/<xref:System.Windows.ContentElement.KeyDown> evento, <xref:System.Windows.Input.KeyEventArgs.Key%2A> está establecido en <xref:System.Windows.Input.Key?displayProperty=fullName> si las pulsaciones de teclas podrían formar parte de un <xref:System.Windows.ContentElement.TextInput> evento (si se presiona ALT + S, por ejemplo). Esto permite que el código en un <xref:System.Windows.ContentElement.KeyDown> controlador de eventos para buscar <xref:System.Windows.Input.Key?displayProperty=fullName> y, si lo encuentra, dejar el procesamiento para el controlador de posteriormente presionado <xref:System.Windows.ContentElement.TextInput> eventos. En estos casos, las diversas propiedades de la <xref:System.Windows.Input.TextCompositionEventArgs> argumento se puede utilizar para determinar las pulsaciones de teclas originales. De forma similar, si una [!INCLUDE[TLA2#tla_ime](../../../../includes/tla2sharptla-ime-md.md)] está activo, <xref:System.Windows.Input.Key> tiene el valor de <xref:System.Windows.Input.Key?displayProperty=fullName>, y <xref:System.Windows.Input.KeyEventArgs.ImeProcessedKey%2A> ofrece la pulsación de tecla o pulsaciones de teclas original.  
  
 En el ejemplo siguiente se define un controlador para el <xref:System.Windows.Controls.Primitives.ButtonBase.Click> evento y un controlador para el <xref:System.Windows.UIElement.KeyDown> eventos.  
  
 El primer segmento de código o marcado crea la interfaz de usuario.  
  
 [!code-xml[InputOvw#Input_OvwTextInputXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#input_ovwtextinputxaml)]  
  
 [!code-csharp[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputuicodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputUICodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputuicodebehind)]  
  
 El segundo segmento de código contiene los controladores de eventos.  
  
 [!code-csharp[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml.cs#input_ovwtextinputhandlerscodebehind)]
 [!code-vb[InputOvw#Input_OvwTextInputHandlersCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InputOvw/VisualBasic/Page1.xaml.vb#input_ovwtextinputhandlerscodebehind)]  
  
 Porque los eventos de entrada se propagan la ruta del evento, el <xref:System.Windows.Controls.StackPanel> recibe la entrada independientemente del elemento que tiene el foco del teclado. El <xref:System.Windows.Controls.TextBox> se notifica al control primero y el `OnTextInputKeyDown` se llama controlador sólo si la <xref:System.Windows.Controls.TextBox> no controló la entrada. Si el <xref:System.Windows.UIElement.PreviewKeyDown> evento se utiliza en lugar de la <xref:System.Windows.UIElement.KeyDown> evento, el `OnTextInputKeyDown` se llama primero al controlador.  
  
 En este ejemplo, la lógica de control se escribe dos veces: una vez para CTRL+O y nuevo del botón, haga clic en eventos. Esto se puede simplificar mediante el uso de comandos, en lugar de controlar los eventos de entrada directamente.  Comandos se describen en esta información general y en [comandos Introducción](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="touch_and_manipulation"></a>   
## <a name="touch-and-manipulation"></a>Manipulación y toque  
 Nuevo hardware y API en el sistema operativo Windows 7 proporcionan aplicaciones la capacidad de recibir la entrada de varios toques simultáneamente. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]permite que las aplicaciones detectar y responder a la entrada táctil de una manera similar a otra entrada, como el mouse o el teclado, provocando eventos cuando se produce la interacción.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]expone dos tipos de eventos cuando se produce la interacción: eventos de toque y eventos de manipulación. Eventos de toque proporcionan los datos sin procesar de cada dedo en una pantalla táctil y su movimiento. Eventos de manipulación interpretan la entrada como acciones. Ambos tipos de eventos se describen en esta sección.  
  
### <a name="prerequisites"></a>Requisitos previos  
 Necesita los componentes siguientes para desarrollar una aplicación que responde a la entrada táctil.  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)].  
  
-   Windows 7.  
  
-   Un dispositivo, como una pantalla táctil, compatible con Windows Touch.  
  
### <a name="terminology"></a>Terminología  
 Los siguientes términos se usan cuando se explica la interacción.  
  
-   **Touch** es un tipo de entrada de usuario es reconocido por Windows 7. Normalmente, se inicia colocando los dedos en una pantalla táctil. Tenga en cuenta que dispositivos como un pantalla táctil que es común en los equipos portátiles no admiten touch si el dispositivo se convierte simplemente el dedo posición y movimiento como entrada del mouse.  
  
-   **Multitoque** es interacción que se produce más de un punto de forma simultánea. Windows 7 y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] admiten multitoque. Cada vez que toque se describe en la documentación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], los conceptos se aplican a la entrada multitoque.  
  
-   Un **manipulación** se produce cuando el toque se interpreta como una acción física que se aplica a un objeto. En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], eventos de manipulación interpretan la entrada como una traducción, expansión o manipulación de rotación.  
  
-   Un `touch device` representa un dispositivo que genera entrada táctil, como un solo dedo en una pantalla táctil.  
  
### <a name="controls-that-respond-to-touch"></a>Controles que responden a la entrada táctil  
 Los siguientes controles se pueden desplazar arrastrando un dedo por el control si tiene contenido que se desplaza fuera de la vista.  
  
-   <xref:System.Windows.Controls.ComboBox>  
  
-   <xref:System.Windows.Controls.ContextMenu>  
  
-   <xref:System.Windows.Controls.DataGrid>  
  
-   <xref:System.Windows.Controls.ListBox>  
  
-   <xref:System.Windows.Controls.ListView>  
  
-   <xref:System.Windows.Controls.MenuItem>  
  
-   <xref:System.Windows.Controls.TextBox>  
  
-   <xref:System.Windows.Controls.ToolBar>  
  
-   <xref:System.Windows.Controls.TreeView>  
  
 El <xref:System.Windows.Controls.ScrollViewer> define la <xref:System.Windows.Controls.ScrollViewer.PanningMode%2A?displayProperty=fullName> adjunta la propiedad que le permite especificar si se habilita la panorámica táctil horizontal, vertical, ambas o ninguna. El <xref:System.Windows.Controls.ScrollViewer.PanningDeceleration%2A?displayProperty=fullName> propiedad especifica cómo rápidamente el desplazamiento reduce la velocidad cuando el usuario levanta el dedo de la pantalla táctil. El <xref:System.Windows.Controls.ScrollViewer.PanningRatio%2A?displayProperty=fullName> propiedad adjunta especifica la proporción de desplazamiento para traducir el desplazamiento de manipulación.  
  
### <a name="touch-events"></a>Touch (eventos)  
 Las clases base, <xref:System.Windows.UIElement>, <xref:System.Windows.UIElement3D>, y <xref:System.Windows.ContentElement>, definir los eventos que se pueden suscribir a por lo que la aplicación responda a la entrada táctil. Eventos Touch son útiles cuando la aplicación interpreta la entrada táctil como algo distinto de manipulación de un objeto. Por ejemplo, una aplicación que permite a un usuario dibujar con uno o más dedos podría suscribirse eventos de toque.  
  
 Las tres clases definen los siguientes eventos, que se comportan de igual forma, independientemente de la definición de clase.  
  
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
  
 Al igual que los eventos de teclado y mouse, los eventos touch son eventos enrutados. Los eventos que empiezan por `Preview` tunelización de eventos y los eventos que empiezan por `Touch` son los eventos de propagación. Para obtener más información sobre eventos enrutados, vea [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md). Al controlar estos eventos, puede obtener la posición de la entrada, con respecto a cualquier elemento, llamando a la <xref:System.Windows.Input.TouchEventArgs.GetTouchPoint%2A> o <xref:System.Windows.Input.TouchEventArgs.GetIntermediateTouchPoints%2A> método.  
  
 Para entender la interacción entre los eventos touch, considere el escenario donde un usuario coloca un dedo en un elemento, mueve el dedo en el elemento y, a continuación, levante el dedo del elemento. La ilustración siguiente muestra la ejecución de los eventos de propagación (los eventos de tunelización se omiten por motivos de simplicidad).  
  
 ![La secuencia de eventos de toque.](../../../../docs/framework/wpf/advanced/media/ndp-touchevents.png "NDP_TouchEvents")  
Touch (eventos)  
  
 En la lista siguiente describe la secuencia de los eventos en la ilustración anterior.  
  
1.  El <xref:System.Windows.UIElement.TouchEnter> evento se produce una vez cuando el usuario coloca un dedo en el elemento.  
  
2.  El <xref:System.Windows.UIElement.TouchDown> una vez se produce el evento.  
  
3.  El <xref:System.Windows.UIElement.TouchMove> evento aparece varias veces cuando el usuario mueve el dedo dentro del elemento.  
  
4.  El <xref:System.Windows.UIElement.TouchUp> evento se produce una vez cuando el usuario levanta el dedo del elemento.  
  
5.  El <xref:System.Windows.UIElement.TouchLeave> una vez se produce el evento.  
  
 Cuando se utilizan más de dos dedos, se producen los eventos para cada dedo.  
  
### <a name="manipulation-events"></a>Eventos de manipulación  
 Para los casos donde una aplicación permite a los usuarios manipular un objeto, el <xref:System.Windows.UIElement> clase define los eventos de manipulación. A diferencia de los eventos touch que simplemente notifican la posición de interacción, los eventos de manipulación de informes cómo se puede interpretar la entrada. Hay tres tipos de manipulaciones, traducción, expansión y rotación. En la lista siguiente describe cómo invocar los tres tipos de manipulaciones.  
  
-   Coloque un dedo en un objeto y mueva el dedo por la pantalla táctil para invocar una manipulación de traducción. Esto normalmente mueve el objeto.  
  
-   Coloque dos dedos en un objeto y mueva los dedos, acerque o aparte para invocar una manipulación de expansión. Normalmente, este tamaño del objeto.  
  
-   Coloque dos dedos en un objeto y rote los dedos para invocar una manipulación de rotación. Esto normalmente gira el objeto.  
  
 Más de un tipo de manipulación se puede producir al mismo tiempo.  
  
 Cuando hace que los objetos respondan a las manipulaciones, puede hacer que el objeto aparezca tiene inercia. Esto puede hacer que los objetos simulen el mundo físico. Por ejemplo, cuando inserte un libro en una tabla, si se inserta el disco duro el libro continuará moviéndose después de liberarla. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]le permite simular este comportamiento generando eventos de manipulación después de que los dedos del usuario se libera el objeto.  
  
 Para obtener información sobre cómo crear una aplicación que permite al usuario mover, cambiar el tamaño y girar un objeto, vea [Walkthrough: Creating Your First Touch Application](../../../../docs/framework/wpf/advanced/walkthrough-creating-your-first-touch-application.md).  
  
 El <xref:System.Windows.UIElement> define los siguientes eventos de manipulación.  
  
-   <xref:System.Windows.UIElement.ManipulationStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationStarted>  
  
-   <xref:System.Windows.UIElement.ManipulationDelta>  
  
-   <xref:System.Windows.UIElement.ManipulationInertiaStarting>  
  
-   <xref:System.Windows.UIElement.ManipulationCompleted>  
  
-   <xref:System.Windows.UIElement.ManipulationBoundaryFeedback>  
  
 De forma predeterminada, un <xref:System.Windows.UIElement> no recibe estos eventos de manipulación. Para recibir eventos de manipulación en una <xref:System.Windows.UIElement>, establezca <xref:System.Windows.UIElement.IsManipulationEnabled%2A?displayProperty=fullName> a `true`.  
  
#### <a name="the-execution-path-of-manipulation-events"></a>La ruta de acceso de ejecución de eventos de manipulación  
 Considere un escenario donde un usuario "produce" un objeto. El usuario coloca un dedo en el objeto, mueve el dedo por la pantalla táctil una distancia corta y, a continuación, levante el dedo mientras se está moviendo. El resultado de esto es que el objeto se mueva en los dedos del usuario y continuará moviéndose cuando el usuario levante el dedo.  
  
 La ilustración siguiente muestra la ruta de acceso de ejecución de eventos de manipulación e información importante sobre cada evento.  
  
 ![La secuencia de eventos de manipulación.](../../../../docs/framework/wpf/advanced/media/ndp-manipulationevents.png "NDP_ManipulationEvents")  
Eventos de manipulación  
  
 En la lista siguiente describe la secuencia de los eventos en la ilustración anterior.  
  
1.  El <xref:System.Windows.UIElement.ManipulationStarting> evento se produce cuando el usuario coloca un dedo en el objeto. Entre otras cosas, este evento permite establecer el <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> propiedad. En los eventos posteriores, la posición de la manipulación será relativa a la <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A>. Eventos de <xref:System.Windows.UIElement.ManipulationStarting>, esta propiedad es de sólo lectura, por lo que la <xref:System.Windows.UIElement.ManipulationStarting> evento es el único momento en que se puede establecer esta propiedad.  
  
2.  El <xref:System.Windows.UIElement.ManipulationStarted> a continuación se produce el evento. Este evento indica que el origen de la manipulación.  
  
3.  El <xref:System.Windows.UIElement.ManipulationDelta> evento aparece varias veces como movimiento de dedos del usuario en una pantalla táctil. El <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> propiedad de la <xref:System.Windows.Input.ManipulationDeltaEventArgs> clase notifica si la manipulación se interpreta como el movimiento, expansión o traducción. Esto es donde realiza la mayoría del trabajo de manipulación de un objeto.  
  
4.  El <xref:System.Windows.UIElement.ManipulationInertiaStarting> evento se produce cuando los dedos del usuario pierden el contacto con el objeto. Este evento permite especificar la desaceleración de las manipulaciones durante la inercia. Esto es para que el objeto puede emular espacios físicos diferentes o atributos si elige. Por ejemplo, suponga que la aplicación tiene dos objetos que representan los elementos en el mundo físico y uno es más pesado que el otro. Puede hacer que el objeto más pesado disminuya la velocidad más rápidamente que el objeto más claro.  
  
5.  El <xref:System.Windows.UIElement.ManipulationDelta> varias veces cuando tiene lugar la inercia se produce el evento. Tenga en cuenta que este evento se produce cuando los dedos del usuario se mueva por la pantalla táctil y [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] simula la inercia. En otras palabras, <xref:System.Windows.UIElement.ManipulationDelta> se produce antes y después de la <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos. El <xref:System.Windows.Input.ManipulationDeltaEventArgs.IsInertial%2A?displayProperty=fullName> propiedad informes si el <xref:System.Windows.UIElement.ManipulationDelta> evento se produce durante la inercia, para que pueda comprobar esa propiedad y realizar acciones diferentes, dependiendo de su valor.  
  
6.  El <xref:System.Windows.UIElement.ManipulationCompleted> evento se produce cuando finaliza la manipulación y la inercia. Es decir, después todos los <xref:System.Windows.UIElement.ManipulationDelta> eventos se producen, el <xref:System.Windows.UIElement.ManipulationCompleted> se produce un evento para señalar que la manipulación está completa.  
  
 El <xref:System.Windows.UIElement> también define la <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos. Este evento se produce cuando el <xref:System.Windows.Input.ManipulationDeltaEventArgs.ReportBoundaryFeedback%2A> método se llama en el <xref:System.Windows.UIElement.ManipulationDelta> eventos. El <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos permite que aplicaciones o componentes proporcionar comentarios visuales cuando un objeto alcanza un límite. Por ejemplo, el <xref:System.Windows.Window> clase controla el <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> evento hace que la ventana se mueva ligeramente cuando se encuentra su borde.  
  
 Puede cancelar la manipulación llamando a la <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> método en los argumentos de evento de cualquier evento de manipulación excepto <xref:System.Windows.UIElement.ManipulationBoundaryFeedback> eventos. Cuando se llama a <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A>, ya no se generan los eventos de manipulación y los eventos del mouse se producen con el tacto. En la tabla siguiente describe la relación entre el momento en que se cancela la manipulación y los eventos del mouse que se producen.  
  
|El evento que cancela se llama|Los eventos del mouse que se producen para la entrada que ya se han producido|  
|----------------------------------------|-----------------------------------------------------------------|  
|<xref:System.Windows.UIElement.ManipulationStarting> y <xref:System.Windows.UIElement.ManipulationStarted>|Mueva el mouse hacia abajo de eventos.|  
|<xref:System.Windows.UIElement.ManipulationDelta>|Mouse hacia abajo y los eventos de movimiento del mouse.|  
|<xref:System.Windows.UIElement.ManipulationInertiaStarting> y <xref:System.Windows.UIElement.ManipulationCompleted>|Down, mouse move y mouse eventos del mouse.|  
  
 Tenga en cuenta que si se llama a <xref:System.Windows.Input.ManipulationStartingEventArgs.Cancel%2A> cuando la manipulación está en inercia, el método devuelve `false` y la entrada no genera eventos del mouse.  
  
### <a name="the-relationship-between-touch-and-manipulation-events"></a>La relación entre los eventos de manipulación y toque  
 Un <xref:System.Windows.UIElement> siempre puede recibir eventos de toque. Cuando el <xref:System.Windows.UIElement.IsManipulationEnabled%2A> propiedad está establecida en `true`, <xref:System.Windows.UIElement> puede recibir eventos de manipulación y toque.  Si el <xref:System.Windows.UIElement.TouchDown> no se controla el evento (es decir, el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad es `false`), la lógica de manipulación captura el toque al elemento y genera los eventos de manipulación. Si el <xref:System.Windows.RoutedEventArgs.Handled%2A> propiedad está establecida en `true` en el <xref:System.Windows.UIElement.TouchDown> evento, la lógica de manipulación genera eventos de manipulación. La siguiente ilustración muestra la relación entre los eventos de toque y eventos de manipulación.  
  
 ![Relación entre los eventos de manipulación y toque](../../../../docs/framework/wpf/advanced/media/ndp-touchmanipulateevents.png "NDP_TouchManipulateEvents")  
Eventos de manipulación y toque  
  
 En la lista siguiente describe la relación entre los eventos de manipulación y toque que se muestra en la ilustración anterior.  
  
-   Cuando el primer dispositivo de toque genera un <xref:System.Windows.UIElement.TouchDown> evento en un <xref:System.Windows.UIElement>, las llamadas de la lógica de manipulación el <xref:System.Windows.UIElement.CaptureTouch%2A> método, que genera la <xref:System.Windows.UIElement.GotTouchCapture> eventos.  
  
-   Cuando el <xref:System.Windows.UIElement.GotTouchCapture> se produce, las llamadas de la lógica de manipulación el <xref:System.Windows.Input.Manipulation.AddManipulator%2A?displayProperty=fullName> método, que genera la <xref:System.Windows.UIElement.ManipulationStarting> eventos.  
  
-   Cuando el <xref:System.Windows.UIElement.TouchMove> se producen eventos, la lógica de manipulación genera el <xref:System.Windows.UIElement.ManipulationDelta> eventos que se producen antes de la <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos.  
  
-   Cuando el último dispositivo táctil el elemento provoca el <xref:System.Windows.UIElement.TouchUp> la lógica de manipulación genera el evento, el <xref:System.Windows.UIElement.ManipulationInertiaStarting> eventos.  
  
<a name="focus"></a>   
## <a name="focus"></a>Foco  
 Hay dos conceptos principales relacionados con el foco en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: foco de teclado y el foco lógico.  
  
### <a name="keyboard-focus"></a>Foco del teclado  
 Foco de teclado hace referencia al elemento que recibe las acciones del teclado.  Puede haber un único elemento en todo el escritorio que tiene el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento que tiene el foco de teclado tendrá <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> establecido en `true`.  Estático <xref:System.Windows.Input.Keyboard> método <xref:System.Windows.Input.Keyboard.FocusedElement%2A> devuelve el elemento que tiene el foco de teclado.  
  
 Foco de teclado puede obtenerse mediante tabulación a un elemento o haciendo clic con el mouse en determinados elementos, como un <xref:System.Windows.Controls.TextBox>.  Foco de teclado también puede obtenerse mediante programación utilizando la <xref:System.Windows.Input.Keyboard.Focus%2A> método en el <xref:System.Windows.Input.Keyboard> clase.  <xref:System.Windows.Input.Keyboard.Focus%2A> intenta dar el elemento especificado el foco del teclado.  Elemento devuelto por <xref:System.Windows.Input.Keyboard.Focus%2A> es el elemento que tiene el foco de teclado.  
  
 Para un elemento obtenga el foco de teclado del <xref:System.Windows.UIElement.Focusable%2A> propiedad y el <xref:System.Windows.UIElement.IsVisible%2A> propiedades deben establecerse en **true**.  Algunas clases, como <xref:System.Windows.Controls.Panel>, tienen <xref:System.Windows.UIElement.Focusable%2A> establecido en `false` de forma predeterminada; por lo tanto, tendrá que establecer esta propiedad en `true` si desea que ese elemento para poder obtener el foco.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Input.Keyboard.Focus%2A> para establecer el foco de teclado en un <xref:System.Windows.Controls.Button>.  Es el lugar recomendado para establecer el foco inicial en una aplicación en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 Para obtener más información acerca del foco de teclado, consulte [Focus Overview](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
### <a name="logical-focus"></a>Foco lógico  
 El foco lógico hace referencia a la <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> en un ámbito de foco.  Puede haber varios elementos que tienen el foco lógico en una aplicación, pero sólo puede haber un elemento que tiene el foco lógico en un ámbito de foco concreto.  
  
 Un ámbito de foco es un elemento contenedor que realiza un seguimiento de la <xref:System.Windows.Input.FocusManager.FocusedElement%2A> dentro de su ámbito.  Cuando el foco sale de un ámbito de foco, el elemento enfocado perderá el foco de teclado, pero conservará el foco lógico.  Cuando el foco se devuelve al ámbito de foco, el elemento enfocado obtendrá el foco del teclado.  Esto permite el foco de teclado cambiar entre varios ámbitos de foco, pero garantiza que el elemento enfocado dentro del ámbito de foco siga siendo el elemento enfocado cuando vuelve el foco.  
  
 Un elemento se puede convertir en un ámbito de foco en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] estableciendo la <xref:System.Windows.Input.FocusManager> propiedad adjunta <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> a `true`, o en el código estableciendo la propiedad adjunta mediante el <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> método.  
  
 El ejemplo siguiente hace una <xref:System.Windows.Controls.StackPanel> en un ámbito de foco estableciendo la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> propiedad adjunta.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 Las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que son ámbitos de foco de forma predeterminada son <xref:System.Windows.Window>, <xref:System.Windows.Controls.Menu>, <xref:System.Windows.Controls.ToolBar>, y <xref:System.Windows.Controls.ContextMenu>.  
  
 Un elemento que tiene el foco de teclado también tendrá el foco lógico para el ámbito de foco pertenece a; Por consiguiente, establecer el foco en un elemento con la <xref:System.Windows.Input.Keyboard.Focus%2A> método en el <xref:System.Windows.Input.Keyboard> clase o clases de elementos base intentará dar el foco de teclado de elemento y el foco lógico.  
  
 Para determinar el elemento enfocado en un ámbito de foco, utilice <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>. Para cambiar el elemento que tiene un ámbito de foco, utilice <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>.  
  
 Para obtener más información acerca del foco lógico, consulte [Focus Overview](../../../../docs/framework/wpf/advanced/focus-overview.md).  
  
<a name="mouse_position"></a>   
## <a name="mouse-position"></a>Posición del mouse  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] proporciona información útil con respecto a los espacios de coordenadas.  ¿Por ejemplo, coordinar `(0,0)` es la coordenada superior izquierda, pero la parte superior izquierda qué elemento del árbol? ¿El elemento que es el destino de la entrada? ¿El elemento que se adjunta el controlador de eventos? ¿O cualquier otra cosa? Para evitar confusiones, el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entrada [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] requiere que especifique el marco de referencia cuando se trabaja con coordenadas obtenidas a través del mouse. El <xref:System.Windows.Input.Mouse.GetPosition%2A> método devuelve la coordenada del puntero del mouse relativa al elemento especificado.  
  
<a name="mouse_capture"></a>   
## <a name="mouse-capture"></a>Captura del mouse  
 Dispositivos de mouse concretamente presentan una característica modal que se denomina captura del mouse. Captura del mouse se utiliza para mantener un estado transitorio de entrada cuando se inicia una operación de arrastrar y colocar, para que otras operaciones relacionadas con el nominal en pantalla la posición del puntero del mouse no necesariamente se produzcan. Durante la operación de arrastre, no haga clic en el usuario sin anular el arrastrar y colocar, lo que hace que la mayoría de las indicaciones de mouseover inadecuado mientras la captura del mouse se mantiene por el origen de arrastre. Expone el sistema de entrada [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que puede determinar el estado de la captura del mouse, así como [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] que puede forzar la captura del mouse a un elemento concreto o borrar el estado de la captura del mouse. Para obtener más información sobre las operaciones de arrastrar y colocar, vea [Drag and Drop Overview](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md).  
  
<a name="commands"></a>   
## <a name="commands"></a>Comandos  
 Los comandos permiten el control de entrada en un nivel más semántico que la entrada del dispositivo.  Comandos son directivas simples, como `Cut`, `Copy`, `Paste`, o `Open`.  Comandos son útiles para centralizar su lógica de comando.  El mismo comando puede obtenerse acceso desde una <xref:System.Windows.Controls.Menu>, en un <xref:System.Windows.Controls.ToolBar>, o a través de un método abreviado de teclado. Comandos también proporcionan un mecanismo para deshabilitar los controles cuando el comando deja de estar disponible.  
  
 <xref:System.Windows.Input.RoutedCommand> es el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación de <xref:System.Windows.Input.ICommand>.  Cuando un <xref:System.Windows.Input.RoutedCommand> se ejecuta, un <xref:System.Windows.Input.CommandManager.PreviewExecuted> y un <xref:System.Windows.Input.CommandManager.Executed> evento se genera en el destino del comando, el túnel y propagarse a través del árbol de elementos como otra entrada.  Si no se establece el destino del comando, el elemento con foco de teclado será el destino del comando.  La lógica que ejecuta el comando se adjunta a un <xref:System.Windows.Input.CommandBinding>.  Cuando un <xref:System.Windows.Input.CommandManager.Executed> evento alcanza un <xref:System.Windows.Input.CommandBinding> para ese comando concreto, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> en el <xref:System.Windows.Input.CommandBinding> se llama.  Este controlador realiza la acción del comando.  
  
 Para obtener más información sobre los comandos, consulte [comandos Introducción](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona una biblioteca de comandos comunes que consta de <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, y <xref:System.Windows.Documents.EditingCommands>, o puede definir los suyos propios.  
  
 En el ejemplo siguiente se muestra cómo configurar un <xref:System.Windows.Controls.MenuItem> para que cuando se hace clic en él invoque el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando el <xref:System.Windows.Controls.TextBox>, suponiendo que el <xref:System.Windows.Controls.TextBox> tiene el foco de teclado.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
 Para obtener más información acerca de los comandos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [comandos Introducción](../../../../docs/framework/wpf/advanced/commanding-overview.md).  
  
<a name="the_input_system_and_base_elements"></a>   
## <a name="the-input-system-and-base-elements"></a>El sistema de entrada y los elementos Base  
 Eventos de entrada como los eventos adjuntos definidos por el <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, y <xref:System.Windows.Input.Stylus> clases son generadas por el sistema de entrada e insertadas en una posición concreta del modelo de objetos basado en el árbol visual en tiempo de ejecución de la prueba de posicionamiento.  
  
 Cada uno de los eventos que <xref:System.Windows.Input.Mouse>, <xref:System.Windows.Input.Keyboard>, y <xref:System.Windows.Input.Stylus> definir como un evento adjunto también se vuelve a expuestas por las clases de elementos base <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> como un evento enrutado de nuevo. Los eventos enrutado de elemento base genera clases de controlar el evento adjunto original y reutilización de los datos del evento.  
  
 Cuando el evento de entrada se asocia con un elemento de origen determinado a través de su implementación de evento de entrada de elemento base, se puede enrutar a través del resto de una ruta de evento que se basa en una combinación de objetos del árbol lógico y visual y ser controlada por código de aplicación.  Por lo general, resulta más conveniente controlar estos eventos de entrada relacionados con dispositivos utilizando los eventos enrutados en <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>, ya puede utilizar la sintaxis más intuitiva eventos controlador tanto en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] y en el código. Si desea controlar el evento adjunto que inició el proceso, pero tendría que enfrentarse a varios problemas: el evento adjunto puede estar marcado como controlado por el control de la clase de elemento base, y debe utilizar métodos de descriptor de acceso en lugar de la sintaxis de eventos auténticos para asociar controladores a los eventos asociados.  
  
<a name="whats_next"></a>   
## <a name="whats-next"></a>Pasos adicionales  
 Ahora dispone de varias técnicas para controlar la entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  También debe tener una comprensión mejorada de los distintos tipos de eventos de entrada y los mecanismos de eventos enrutados utilizados por [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].  
  
 Existen recursos adicionales que explican [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elementos del marco y el enrutamiento de eventos con más detalle. Consulte los temas siguientes para obtener más información, [comandos Introducción](../../../../docs/framework/wpf/advanced/commanding-overview.md), [Focus Overview](../../../../docs/framework/wpf/advanced/focus-overview.md), [Base Elements Overview](../../../../docs/framework/wpf/advanced/base-elements-overview.md), [árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md), y [Routed Events Overview](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general de foco](../../../../docs/framework/wpf/advanced/focus-overview.md)   
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)   
 [Propiedades](../../../../docs/framework/wpf/advanced/properties-wpf.md)