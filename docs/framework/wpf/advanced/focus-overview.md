---
title: Información general sobre el foco
description: 'Obtenga información sobre los dos conceptos principales de Windows Presentation Foundation que pertenecen al foco: el foco de teclado y el foco lógico.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
ms.openlocfilehash: 71aeb577cccd2c3b16df1c5a3cb772dd1f5479e2
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165111"
---
# <a name="focus-overview"></a>Información general sobre el foco
En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], hay dos conceptos principales relacionados con el foco: el foco de teclado y el foco lógico.  El foco de teclado hace referencia al elemento que recibe la entrada del teclado, y el foco lógico hace referencia al elemento que tiene el foco en un ámbito de foco.  Estos conceptos se describen con detalle en esta información general.  Entender la diferencia entre estos conceptos es importante para crear aplicaciones complejas que tengan varias regiones donde se pueda obtener el foco.  
  
 Las clases principales que participan en la administración del foco son la <xref:System.Windows.Input.Keyboard> clase, la <xref:System.Windows.Input.FocusManager> clase y las clases de elementos base, como <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement> .  Para obtener más información sobre los elementos base, consulte [Información general sobre los elementos base](base-elements-overview.md).  
  
 La <xref:System.Windows.Input.Keyboard> clase está preocupada principalmente por el foco de teclado y <xref:System.Windows.Input.FocusManager> está relacionado principalmente con el foco lógico, pero no es una distinción absoluta.  Un elemento que tiene el foco de teclado también tendrá el foco lógico, pero un elemento que tiene el foco lógico no tendrá necesariamente el foco de teclado.  Esto es evidente cuando se usa la <xref:System.Windows.Input.Keyboard> clase para establecer el elemento que tiene el foco de teclado; también establece el foco lógico en el elemento.  

<a name="Keyboard_Focus"></a>
## <a name="keyboard-focus"></a>Foco de teclado  
 El foco de teclado hace referencia al elemento que recibe actualmente la entrada del teclado.  Puede haber un único elemento en todo el escritorio que tenga el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , el elemento que tiene el foco de teclado tendrá <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> establecido en `true` .  La propiedad estática <xref:System.Windows.Input.Keyboard.FocusedElement%2A> de la <xref:System.Windows.Input.Keyboard> clase obtiene el elemento que tiene actualmente el foco de teclado.  
  
 Para que un elemento obtenga el foco de teclado, las <xref:System.Windows.UIElement.Focusable%2A> propiedades y <xref:System.Windows.UIElement.IsVisible%2A> de los elementos base deben establecerse en `true` .  Algunas clases, como la <xref:System.Windows.Controls.Panel> clase base, tienen <xref:System.Windows.UIElement.Focusable%2A> establecido en de `false` forma predeterminada; por lo tanto, debe establecer <xref:System.Windows.UIElement.Focusable%2A> en `true` si desea que dicho elemento pueda obtener el foco de teclado.  
  
 El foco de teclado puede obtenerse a través de la interacción del usuario con la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], como desplazarse mediante la tecla TAB hasta un elemento o hacer clic con el mouse en determinados elementos.  El foco de teclado también se puede obtener mediante programación con el <xref:System.Windows.Input.Keyboard.Focus%2A> método en la <xref:System.Windows.Input.Keyboard> clase.  El <xref:System.Windows.Input.Keyboard.Focus%2A> método intenta proporcionar el foco de teclado del elemento especificado.  El elemento devuelto es el elemento que tiene el foco de teclado, que puede ser un elemento diferente al solicitado si el objeto que tenía el foco antes o el que tiene el foco ahora bloquean la solicitud.  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Input.Keyboard.Focus%2A> método para establecer el foco de teclado en un <xref:System.Windows.Controls.Button> .  
  
 [!code-csharp[focussample#FocusSampleSetFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 La <xref:System.Windows.UIElement.IsKeyboardFocused%2A> propiedad de las clases de elementos base obtiene un valor que indica si el elemento tiene el foco de teclado.  La <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> propiedad de las clases de elementos base obtiene un valor que indica si el elemento o cualquiera de sus elementos visuales secundarios tiene el foco de teclado.  
  
 Al establecer el foco inicial en el inicio de la aplicación, el elemento para recibir el foco debe estar en el árbol visual de la ventana inicial cargada por la aplicación y el elemento debe tener <xref:System.Windows.UIElement.Focusable%2A> y <xref:System.Windows.UIElement.IsVisible%2A> establecido en `true` .  El lugar recomendado para establecer el foco inicial es el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.  <xref:System.Windows.Threading.Dispatcher>También se puede usar una devolución de llamada mediante una llamada a <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> .  
  
<a name="Logical_Focus"></a>
## <a name="logical-focus"></a>Foco lógico  
 El foco lógico hace referencia a <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> en un ámbito de foco.  Un ámbito de foco es un elemento que realiza un seguimiento de <xref:System.Windows.Input.FocusManager.FocusedElement%2A> dentro de su ámbito.  Cuando el foco de teclado sale de un ámbito de foco, el elemento enfocado pierde el foco de teclado, pero conserva el foco lógico.  Cuando el foco de teclado vuelve al ámbito de foco, el elemento enfocado recibe el foco de teclado.  Esto permite cambiar el foco de teclado entre varios ámbitos de foco, pero garantiza que el elemento enfocado dentro del ámbito de foco vuelva a obtener el foco de teclado cuando el foco vuelva al ámbito de foco.  
  
 Puede haber varios elementos que tengan el foco lógico en una aplicación, pero solo puede haber uno con el foco lógico en un ámbito de foco concreto.  
  
 Un elemento que tiene el foco de teclado tiene el foco lógico para el ámbito de foco al que pertenece.  
  
 Un elemento se puede convertir en un ámbito de foco en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] estableciendo la <xref:System.Windows.Input.FocusManager> propiedad adjunta <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> en `true` .  En el código, un elemento se puede convertir en un ámbito de foco llamando a <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A> .  
  
 En el ejemplo siguiente se convierte un <xref:System.Windows.Controls.StackPanel> en un ámbito de foco estableciendo la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> propiedad adjunta.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>Devuelve el ámbito del foco del elemento especificado.  
  
 Las clases en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que son ámbitos de foco de forma predeterminada son <xref:System.Windows.Window> , <xref:System.Windows.Controls.MenuItem> , <xref:System.Windows.Controls.ToolBar> y <xref:System.Windows.Controls.ContextMenu> .  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Obtiene el elemento enfocado para el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>establece el elemento con foco en el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>se utiliza normalmente para establecer el elemento que tiene el foco inicial.  
  
 En el ejemplo siguiente se establece el elemento con foco en un ámbito de foco y se obtiene el elemento con foco de un ámbito de foco.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>
## <a name="keyboard-navigation"></a>Navegación mediante teclado  
 La <xref:System.Windows.Input.KeyboardNavigation> clase es responsable de implementar la navegación predeterminada del foco de teclado cuando se presiona una de las teclas de navegación.  Las teclas de navegación son: TAB, MAYÚS+TAB, CTRL+TAB, CTRL+MAYÚS+TAB, flecha arriba, flecha abajo, flecha izquierda y flecha derecha.  
  
 El comportamiento de navegación de un contenedor de navegación se puede cambiar estableciendo las propiedades adjuntas <xref:System.Windows.Input.KeyboardNavigation> <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> , <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A> y <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A> .  Estas propiedades son del tipo <xref:System.Windows.Input.KeyboardNavigationMode> y los valores posibles son <xref:System.Windows.Input.KeyboardNavigationMode.Continue> , <xref:System.Windows.Input.KeyboardNavigationMode.Local> , <xref:System.Windows.Input.KeyboardNavigationMode.Contained> , <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> , <xref:System.Windows.Input.KeyboardNavigationMode.Once> y <xref:System.Windows.Input.KeyboardNavigationMode.None> .  El valor predeterminado es <xref:System.Windows.Input.KeyboardNavigationMode.Continue> , lo que significa que el elemento no es un contenedor de navegación.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Menu> objeto con un número de <xref:System.Windows.Controls.MenuItem> objetos.  La <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> propiedad adjunta se establece en <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> en <xref:System.Windows.Controls.Menu> .  Cuando se cambia el foco mediante la tecla TAB dentro de <xref:System.Windows.Controls.Menu> , el foco se desplaza de cada elemento y, cuando se alcanza el último elemento, el foco volverá al primer elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>
## <a name="navigating-focus-programmatically"></a>Navegar con el foco mediante programación  
 La API adicional para trabajar con el foco es <xref:System.Windows.UIElement.MoveFocus%2A> y <xref:System.Windows.UIElement.PredictFocus%2A> .  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>cambia el foco al siguiente elemento de la aplicación.  <xref:System.Windows.Input.TraversalRequest>Se utiliza para especificar la dirección.   El <xref:System.Windows.Input.FocusNavigationDirection> que se pasa a <xref:System.Windows.UIElement.MoveFocus%2A> especifica el foco de direcciones diferentes que se puede desplazar, como <xref:System.Windows.Input.FocusNavigationDirection.First> , <xref:System.Windows.Input.FocusNavigationDirection.Last> <xref:System.Windows.Input.FocusNavigationDirection.Up> y <xref:System.Windows.Input.FocusNavigationDirection.Down> .  
  
 En el ejemplo siguiente <xref:System.Windows.FrameworkElement.MoveFocus%2A> se utiliza para cambiar el elemento que tiene el foco.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>Devuelve el objeto que recibiría el foco si se cambiara el foco.  Actualmente, solo <xref:System.Windows.Input.FocusNavigationDirection.Up> <xref:System.Windows.Input.FocusNavigationDirection.Down> <xref:System.Windows.Input.FocusNavigationDirection.Left> <xref:System.Windows.Input.FocusNavigationDirection.Right> se admiten,, y <xref:System.Windows.FrameworkElement.PredictFocus%2A> .  
  
<a name="Focus_Events"></a>
## <a name="focus-events"></a>Eventos de foco  
 Los eventos relacionados con el foco de teclado son <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> , <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> y <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus> <xref:System.Windows.Input.Keyboard.LostKeyboardFocus> .  Los eventos se definen como eventos adjuntos en la <xref:System.Windows.Input.Keyboard> clase, pero se puede acceder a ellos más fácilmente como eventos enrutados equivalentes en las clases de elementos base.  Para obtener más información sobre los eventos, consulte [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>se genera cuando el elemento obtiene el foco de teclado.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>se genera cuando el elemento pierde el foco de teclado.  Si el <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> evento o el <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> evento se administran y <xref:System.Windows.RoutedEventArgs.Handled%2A> se establece en `true` , el foco no cambiará.  
  
 En el ejemplo siguiente se adjuntan los <xref:System.Windows.UIElement.GotKeyboardFocus> <xref:System.Windows.UIElement.LostKeyboardFocus> controladores de eventos y a un <xref:System.Windows.Controls.TextBox> .  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> obtiene el foco de teclado, la <xref:System.Windows.Controls.Control.Background%2A> propiedad de <xref:System.Windows.Controls.TextBox> se cambia a <xref:System.Windows.Media.Brushes.LightBlue%2A> .  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Cuando <xref:System.Windows.Controls.TextBox> pierde el foco de teclado, la <xref:System.Windows.Controls.Control.Background%2A> propiedad de <xref:System.Windows.Controls.TextBox> se vuelve a cambiar a blanco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](~/samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Los eventos relacionados con el foco lógico son <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus> .  Estos eventos se definen en <xref:System.Windows.Input.FocusManager> como eventos adjuntos, pero <xref:System.Windows.Input.FocusManager> no expone contenedores de eventos CLR.  <xref:System.Windows.UIElement>y <xref:System.Windows.ContentElement> exponen estos eventos de forma más cómoda.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Input.FocusManager>
- <xref:System.Windows.UIElement>
- <xref:System.Windows.ContentElement>
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre elementos base](base-elements-overview.md)
