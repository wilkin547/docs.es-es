---
title: Información general sobre el foco
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: de788ec3f0628ff2f7c422c76c73ff7985424113
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186667"
---
# <a name="focus-overview"></a>Información general sobre el foco
En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], hay dos conceptos principales relacionados con el foco: el foco de teclado y el foco lógico.  El foco de teclado hace referencia al elemento que recibe la entrada del teclado, y el foco lógico hace referencia al elemento que tiene el foco en un ámbito de foco.  Estos conceptos se describen con detalle en esta información general.  Entender la diferencia entre estos conceptos es importante para crear aplicaciones complejas que tengan varias regiones donde se pueda obtener el foco.  
  
 Las clases principales que participan <xref:System.Windows.Input.Keyboard> en <xref:System.Windows.Input.FocusManager> la administración de foco son <xref:System.Windows.UIElement> la <xref:System.Windows.ContentElement>clase, la clase y las clases de elemento base, como y .  Para obtener más información sobre los elementos base, consulte [Información general sobre los elementos base](base-elements-overview.md).  
  
 La <xref:System.Windows.Input.Keyboard> clase se ocupa principalmente <xref:System.Windows.Input.FocusManager> del enfoque del teclado y el se refiere principalmente al enfoque lógico, pero esto no es una distinción absoluta.  Un elemento que tiene el foco de teclado también tendrá el foco lógico, pero un elemento que tiene el foco lógico no tendrá necesariamente el foco de teclado.  Esto es evidente cuando <xref:System.Windows.Input.Keyboard> se utiliza la clase para establecer el elemento que tiene el foco de teclado, ya que también establece el foco lógico en el elemento.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Foco de teclado  
 El foco de teclado hace referencia al elemento que recibe actualmente la entrada del teclado.  Puede haber un único elemento en todo el escritorio que tenga el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], el elemento que <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> tiene `true`el foco del teclado se tendrá establecido en .  La propiedad <xref:System.Windows.Input.Keyboard.FocusedElement%2A> static <xref:System.Windows.Input.Keyboard> de la clase obtiene el elemento que actualmente tiene el foco de teclado.  
  
 Para que un elemento obtenga el <xref:System.Windows.UIElement.Focusable%2A> foco <xref:System.Windows.UIElement.IsVisible%2A> del teclado, las propiedades `true`y las de los elementos base deben establecerse en .  Algunas clases, <xref:System.Windows.Controls.Panel> como la <xref:System.Windows.UIElement.Focusable%2A> clase `false` base, se han establecido de forma predeterminada; por lo tanto, debe establecer <xref:System.Windows.UIElement.Focusable%2A> `true` en si desea que un elemento de este tipo para poder obtener el foco del teclado.  
  
 El foco de teclado puede obtenerse a través de la interacción del usuario con la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], como desplazarse mediante la tecla TAB hasta un elemento o hacer clic con el mouse en determinados elementos.  El foco del teclado también se <xref:System.Windows.Input.Keyboard.Focus%2A> puede obtener <xref:System.Windows.Input.Keyboard> mediante programación mediante el método de la clase.  El <xref:System.Windows.Input.Keyboard.Focus%2A> método intenta proporcionar el foco de teclado del elemento especificado.  El elemento devuelto es el elemento que tiene el foco de teclado, que puede ser un elemento diferente al solicitado si el objeto que tenía el foco antes o el que tiene el foco ahora bloquean la solicitud.  
  
 En el ejemplo <xref:System.Windows.Input.Keyboard.Focus%2A> siguiente se utiliza <xref:System.Windows.Controls.Button>el método para establecer el foco del teclado en un archivo .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 La <xref:System.Windows.UIElement.IsKeyboardFocused%2A> propiedad de las clases de elemento base obtiene un valor que indica si el elemento tiene el foco de teclado.  La <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> propiedad de las clases de elemento base obtiene un valor que indica si el elemento o cualquiera de sus elementos secundarios visuales tiene el foco de teclado.  
  
 Al establecer el foco inicial al inicio de la aplicación, el elemento que se va a <xref:System.Windows.UIElement.Focusable%2A> recibir <xref:System.Windows.UIElement.IsVisible%2A> debe `true`estar en el árbol visual de la ventana inicial cargada por la aplicación y el elemento debe tener y establecer se en .  El lugar recomendado para establecer <xref:System.Windows.FrameworkElement.Loaded> el foco inicial está en el controlador de eventos.  Una <xref:System.Windows.Threading.Dispatcher> devolución de llamada <xref:System.Windows.Threading.Dispatcher.Invoke%2A> también <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>se puede utilizar llamando o .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Foco lógico  
 El enfoque lógico <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> se refiere al ámbito de enfoque en un enfoque.  Un ámbito de foco es un <xref:System.Windows.Input.FocusManager.FocusedElement%2A> elemento que realiza un seguimiento del ámbito dentro de su ámbito.  Cuando el foco de teclado sale de un ámbito de foco, el elemento enfocado pierde el foco de teclado, pero conserva el foco lógico.  Cuando el foco de teclado vuelve al ámbito de foco, el elemento enfocado recibe el foco de teclado.  Esto permite cambiar el foco de teclado entre varios ámbitos de foco, pero garantiza que el elemento enfocado dentro del ámbito de foco vuelva a obtener el foco de teclado cuando el foco vuelva al ámbito de foco.  
  
 Puede haber varios elementos que tengan el foco lógico en una aplicación, pero solo puede haber uno con el foco lógico en un ámbito de foco concreto.  
  
 Un elemento que tiene el foco de teclado tiene el foco lógico para el ámbito de foco al que pertenece.  
  
 Un elemento se puede convertir [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] en un <xref:System.Windows.Input.FocusManager> ámbito <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> `true`de foco estableciendo la propiedad adjunta en .  En el código, un elemento se puede <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>convertir en un ámbito de foco llamando a .  
  
 En el ejemplo <xref:System.Windows.Controls.StackPanel> siguiente se convierte <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> en un ámbito de foco estableciendo la propiedad adjunta.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>devuelve el ámbito de foco para el elemento especificado.  
  
 Las [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clases en las que <xref:System.Windows.Window> <xref:System.Windows.Controls.MenuItem>se <xref:System.Windows.Controls.ToolBar>encuentran <xref:System.Windows.Controls.ContextMenu>los ámbitos de foco de forma predeterminada son , , y .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>obtiene el elemento enfocado para el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>establece el elemento enfocado en el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>normalmente se utiliza para establecer el elemento enfocado inicial.  
  
 En el ejemplo siguiente se establece el elemento con foco en un ámbito de foco y se obtiene el elemento con foco de un ámbito de foco.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Navegación mediante teclado  
 La <xref:System.Windows.Input.KeyboardNavigation> clase es responsable de implementar la navegación de foco de teclado predeterminada cuando se presiona una de las teclas de navegación.  Las teclas de navegación son: TAB, MAYÚS+TAB, CTRL+TAB, CTRL+MAYÚS+TAB, flecha arriba, flecha abajo, flecha izquierda y flecha derecha.  
  
 El comportamiento de navegación de un contenedor <xref:System.Windows.Input.KeyboardNavigation> de <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>navegación <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>se puede cambiar estableciendo las propiedades adjuntas , , y .  Estas propiedades son <xref:System.Windows.Input.KeyboardNavigationMode> de tipo <xref:System.Windows.Input.KeyboardNavigationMode.Continue>y <xref:System.Windows.Input.KeyboardNavigationMode.Local> <xref:System.Windows.Input.KeyboardNavigationMode.Contained>los <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> <xref:System.Windows.Input.KeyboardNavigationMode.Once>valores <xref:System.Windows.Input.KeyboardNavigationMode.None>posibles son , , , , , y .  El valor <xref:System.Windows.Input.KeyboardNavigationMode.Continue>predeterminado es , lo que significa que el elemento no es un contenedor de navegación.  
  
 En el ejemplo <xref:System.Windows.Controls.Menu> siguiente se <xref:System.Windows.Controls.MenuItem> crea un con un número de objetos.  La <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> propiedad adjunta <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> se <xref:System.Windows.Controls.Menu>establece en el archivo .  Cuando se cambia el foco <xref:System.Windows.Controls.Menu>usando la tecla de tabulación dentro de la , el foco se moverá de cada elemento y cuando se alcance el último elemento el foco volverá al primer elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Navegar con el foco mediante programación  
 API adicional para trabajar <xref:System.Windows.UIElement.MoveFocus%2A> <xref:System.Windows.UIElement.PredictFocus%2A>con el foco son y .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>cambia el foco al siguiente elemento de la aplicación.  A <xref:System.Windows.Input.TraversalRequest> se utiliza para especificar la dirección.   El <xref:System.Windows.Input.FocusNavigationDirection> pasado <xref:System.Windows.UIElement.MoveFocus%2A> a especifica las diferentes direcciones <xref:System.Windows.Input.FocusNavigationDirection.First>de <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> enfoque <xref:System.Windows.Input.FocusNavigationDirection.Down>se puede mover, como , , y .  
  
 En el <xref:System.Windows.FrameworkElement.MoveFocus%2A> ejemplo siguiente se utiliza para cambiar el elemento enfocado.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>devuelve el objeto que recibiría el foco si se cambiara el foco.  Actualmente, <xref:System.Windows.Input.FocusNavigationDirection.Up> <xref:System.Windows.Input.FocusNavigationDirection.Down>solo <xref:System.Windows.Input.FocusNavigationDirection.Left>, <xref:System.Windows.Input.FocusNavigationDirection.Right> , <xref:System.Windows.FrameworkElement.PredictFocus%2A>, y son compatibles con .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Eventos de foco  
 Los eventos relacionados con <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> el <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>foco del teclado son , y , .  Los eventos se definen <xref:System.Windows.Input.Keyboard> como eventos adjuntos en la clase, pero son más fácilmente accesibles como eventos enrutados equivalentes en las clases de elemento base.  Para obtener más información sobre los eventos, consulte [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>se genera cuando el elemento obtiene el foco del teclado.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>se genera cuando el elemento pierde el foco del teclado.  Si <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> el evento <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> o el <xref:System.Windows.RoutedEventArgs.Handled%2A> evento se `true`controlan y se establecen en , el foco no cambiará.  
  
 En el ejemplo <xref:System.Windows.UIElement.GotKeyboardFocus> <xref:System.Windows.UIElement.LostKeyboardFocus> siguiente se adjuntan y controladores de eventos a un <xref:System.Windows.Controls.TextBox>archivo .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> el obtiene el <xref:System.Windows.Controls.Control.Background%2A> foco del <xref:System.Windows.Controls.TextBox> teclado, <xref:System.Windows.Media.Brushes.LightBlue%2A>la propiedad de la se cambia a .  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> el foco del <xref:System.Windows.Controls.Control.Background%2A> teclado pierde, la propiedad de la <xref:System.Windows.Controls.TextBox> se cambia de nuevo a blanco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Los eventos relacionados con <xref:System.Windows.UIElement.GotFocus> <xref:System.Windows.UIElement.LostFocus>el enfoque lógico son y .  Estos eventos se <xref:System.Windows.Input.FocusManager> definen en los <xref:System.Windows.Input.FocusManager> eventos adjuntos, pero no expone contenedores de eventos CLR.  <xref:System.Windows.UIElement>y <xref:System.Windows.ContentElement> exponer estos eventos más convenientemente.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre elementos base](base-elements-overview.md)
