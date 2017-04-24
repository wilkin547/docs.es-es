---
title: "Informaci&#243;n general sobre el foco | Microsoft Docs"
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
  - "aplicaciones, foco"
  - "foco en aplicaciones"
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# Informaci&#243;n general sobre el foco
En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hay dos conceptos principales relacionados con el foco: el foco de teclado y el foco lógico.  El foco de teclado se refiere al elemento que recibe las acciones del teclado y el foco lógico se refiere al elemento que tiene el foco dentro de un ámbito de foco.  Estos conceptos se describen con detalle en esta información general.  Entender la diferencia entre estos conceptos es importante para crear aplicaciones complejas que tienen varias zonas donde se puede obtener el foco.  
  
 Las principales clases que participan en administración del foco son <xref:System.Windows.Input.Keyboard>, <xref:System.Windows.Input.FocusManager> y las clases de elementos base, como <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>.  Para obtener más información sobre los elementos base, vea [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 La clase <xref:System.Windows.Input.Keyboard> corresponde principalmente al foco de teclado y la clase <xref:System.Windows.Input.FocusManager>, al foco lógico, aunque no se trata de una distinción absoluta.  Un elemento que tiene el foco de teclado también tiene el foco lógico, pero un elemento que tiene el foco lógico no tiene necesariamente el de teclado.  Esto resulta patente cuando se usa la clase <xref:System.Windows.Input.Keyboard> para establecer el elemento que tiene el foco de teclado, ya que también establece el foco lógico en él.  
  
   
  
<a name="Keyboard_Focus"></a>   
## Foco de teclado  
 El foco de teclado se refiere al elemento que está recibiendo actualmente las acciones del teclado.  Sólo puede haber un elemento en todo el escritorio que tenga el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento que tenga el foco de teclado tendrá la propiedad <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> establecida en `true`.  La propiedad estática <xref:System.Windows.Input.Keyboard.FocusedElement%2A> de la clase <xref:System.Windows.Input.Keyboard> obtiene el elemento que tiene actualmente el foco de teclado.  
  
 Para que un elemento obtenga el foco de teclado, las propiedades <xref:System.Windows.UIElement.Focusable%2A> y <xref:System.Windows.UIElement.IsVisible%2A> de los elementos base deben estar establecidas en `true`.  Algunas clases, como la clase base <xref:System.Windows.Controls.Panel>, tienen la propiedad <xref:System.Windows.UIElement.Focusable%2A> establecida en `false` de manera predeterminada; por consiguiente, debe establecer <xref:System.Windows.UIElement.Focusable%2A> en `true` si desea que un elemento de este tipo pueda obtener el foco de teclado.  
  
 El foco de teclado se puede obtener a través de la interacción con el usuario con la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], por ejemplo, cuando presiona la tecla de tabulación para desplazarse hasta un elemento o hace clic con el mouse en algunos elementos.  El foco de teclado también se puede obtener mediante programación utilizando el método <xref:System.Windows.Input.Keyboard.Focus%2A> de la clase <xref:System.Windows.Input.Keyboard>.  El método <xref:System.Windows.Input.Keyboard.Focus%2A> intenta proporcionar el foco de teclado al elemento especificado.  El elemento devuelto es aquél que tiene el foco de teclado, y que puede ser un elemento diferente al solicitado el objeto que tenía el foco anterior o el que tiene el nuevo bloquea la solicitud.  
  
 En el ejemplo siguiente se utiliza el método <xref:System.Windows.Input.Keyboard.Focus%2A> para establecer el foco de teclado en un control <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 La propiedad <xref:System.Windows.UIElement.IsKeyboardFocused%2A> de las clases de elementos base obtiene un valor que indica si el elemento tiene el foco de teclado.  La propiedad <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> de las clases de elementos base obtiene un valor que indica si el elemento o cualquiera de sus elementos secundarios visuales tiene el foco de teclado.  
  
 Cuando se establece el foco inicial al inicio de la aplicación, el elemento que recibe el foco debe estar en el árbol visual de la ventana inicial cargada por la aplicación y las propiedades <xref:System.Windows.UIElement.Focusable%2A> e <xref:System.Windows.UIElement.IsVisible%2A> del elemento deben estar establecidas en `true`.  El lugar recomendado para establecer el foco inicial en una aplicación es el controlador de eventos <xref:System.Windows.FrameworkElement.Loaded>.  También se puede utilizar una devolución de llamada <xref:System.Windows.Threading.Dispatcher> llamando a <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o a <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## Foco lógico  
 El foco lógico hace referencia al <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=fullName> de un ámbito de foco.  Un ámbito de foco es un elemento que realiza un seguimiento de la propiedad <xref:System.Windows.Input.FocusManager.FocusedElement%2A> dentro de su ámbito.  Cuando el foco de teclado salga de un ámbito de foco, el elemento que tenga el foco perderá el foco de teclado, pero conservará el foco lógico.  Cuando el foco de teclado regrese al ámbito de foco, el elemento que tenga el foco obtendrá el foco de teclado.  Esto permite cambiar el foco de teclado entre varios ámbitos de foco, pero garantiza que el elemento que tiene el foco dentro del ámbito de foco recupere el foco de teclado cuando este regrese al ámbito de foco.  
  
 Puede haber varios elementos con el foco lógico en una aplicación, pero sólo puede haber uno con el foco lógico en un ámbito de foco determinado.  
  
 Un elemento que tiene el foco de teclado también tiene el foco lógico para el ámbito de foco al que pertenece.  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], un elemento se puede convertir en un ámbito de foco si la propiedad <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> adjunta a <xref:System.Windows.Input.FocusManager> se establece en `true`.  En código, un elemento se puede convertir en un ámbito de foco llamando a <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 En el ejemplo siguiente, un <xref:System.Windows.Controls.StackPanel> se convierte en un ámbito de foco estableciendo la propiedad adjunta <xref:System.Windows.Input.FocusManager.IsFocusScope%2A>.  
  
 [!code-xml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A> devuelve el ámbito de foco del elemento especificado.  
  
 Las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], que son ámbitos de foco de forma predeterminada, son <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar> y <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A> obtiene el elemento que tiene el foco dentro del ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> establece el elemento que tiene el foco dentro del ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A> se utiliza normalmente para establecer el elemento que tiene el foco inicial.  
  
 En el ejemplo siguiente se establece el elemento que tiene el foco en un ámbito de foco y se obtiene el elemento que tiene el foco de un ámbito de foco.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## Navegación mediante teclado  
 La clase <xref:System.Windows.Input.KeyboardNavigation> es responsable de implementar la navegación mediante foco de teclado predeterminada cuando se presiona una de las teclas de navegación.  Las teclas de navegación son: TAB, MAYÚS\+TAB, CTRL\+TAB, CTRL\+MAYÚS\+TAB, y las teclas de dirección ARRIBA, ABAJO, IZQUIERDA y DERECHA.  
  
 El comportamiento de navegación de un contenedor de navegación se puede cambiar estableciendo las propiedades adjuntas <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> y <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A> de <xref:System.Windows.Input.KeyboardNavigation>.  Estas propiedades son del tipo <xref:System.Windows.Input.KeyboardNavigationMode> y sus valores posibles son <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode>, <xref:System.Windows.Input.KeyboardNavigationMode> y <xref:System.Windows.Input.KeyboardNavigationMode>.  El valor predeterminado es <xref:System.Windows.Input.KeyboardNavigationMode>, que significa que el elemento no es un contenedor de navegación.  
  
 En el ejemplo siguiente se crea un control <xref:System.Windows.Controls.Menu> con varios objetos <xref:System.Windows.Controls.MenuItem>.  La propiedad adjunta <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> se establece en <xref:System.Windows.Input.KeyboardNavigationMode> en el control <xref:System.Windows.Controls.Menu>.  Cuando se cambie el foco mediante la tecla de tabulación en <xref:System.Windows.Controls.Menu>, el foco se desplazará desde cada elemento y, cuando se alcance el último elemento, volverá al primero.  
  
 [!code-xml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## Navegación con el foco mediante programación  
 Las [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] adicionales para trabajar con el foco son <xref:System.Windows.UIElement.MoveFocus%2A> y <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A> cambia el foco al elemento siguiente en la aplicación.  Se utiliza <xref:System.Windows.Input.TraversalRequest> para especificar la dirección.  El objeto <xref:System.Windows.Input.FocusNavigationDirection> que se pasa a <xref:System.Windows.UIElement.MoveFocus%2A> especifica las distintas direcciones en que se puede mover el foco, como <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> y <xref:System.Windows.Input.FocusNavigationDirection>.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.FrameworkElement.MoveFocus%2A> para cambiar el elemento que tiene el foco.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A> devuelve el objeto que recibiría el foco si este se cambiara.  En la actualidad, el método <xref:System.Windows.FrameworkElement.PredictFocus%2A> únicamente admite los valores <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection>, <xref:System.Windows.Input.FocusNavigationDirection> y <xref:System.Windows.Input.FocusNavigationDirection>.  
  
<a name="Focus_Events"></a>   
## Eventos de foco  
 Los eventos relacionados con el foco de teclado son <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> y <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Los eventos se definen como eventos adjuntos de la clase <xref:System.Windows.Input.Keyboard>, pero resulta más directo tener acceso a ellos como los eventos enrutados equivalentes de las clases de elementos base.  Para obtener más información sobre los eventos, vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> se provoca cuando el elemento obtiene el foco de teclado.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> se provoca cuando el elemento pierde el foco de teclado.  Si se administra el evento <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> o <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> y la propiedad <xref:System.Windows.RoutedEventArgs.Handled%2A> se establece en `true`, el foco no cambiará.  
  
 En el ejemplo siguiente se asocian los controladores de eventos de <xref:System.Windows.UIElement.GotKeyboardFocus> y <xref:System.Windows.UIElement.LostKeyboardFocus> a <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> obtiene el foco de teclado, la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.TextBox> se cambia a <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> pierde el foco del teclado, la propiedad <xref:System.Windows.Controls.Control.Background%2A> de <xref:System.Windows.Controls.TextBox> se vuelve a establecer en el color blanco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Los eventos relacionados con el foco lógico son <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  Estos eventos se definen en <xref:System.Windows.Input.FocusManager> como eventos adjuntos, pero <xref:System.Windows.Input.FocusManager> no expone contenedores de eventos CLR.  <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> exponen estos eventos de un modo más conveniente.  
  
## Vea también  
 <xref:System.Windows.Input.FocusManager>   
 <xref:System.Windows.UIElement>   
 <xref:System.Windows.ContentElement>   
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)