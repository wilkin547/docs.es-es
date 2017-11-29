---
title: "Información general sobre el foco"
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
- applications [WPF], focus
- focus in applications [WPF]
ms.assetid: 0230c4eb-0c8a-462b-ac4b-ae3e511659f4
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f4e10f7136b636829f99da34388db7676810cd06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="focus-overview"></a>Información general sobre el foco
En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], hay dos conceptos principales relacionados con el foco: el foco de teclado y el foco lógico.  El foco de teclado hace referencia al elemento que recibe la entrada del teclado, y el foco lógico hace referencia al elemento que tiene el foco en un ámbito de foco.  Estos conceptos se describen con detalle en esta información general.  Entender la diferencia entre estos conceptos es importante para crear aplicaciones complejas que tengan varias regiones donde se pueda obtener el foco.  
  
 Las clases principales que participan en la administración del enfoque son el <xref:System.Windows.Input.Keyboard> (clase), el <xref:System.Windows.Input.FocusManager> clase y el elemento base de las clases, como <xref:System.Windows.UIElement> y <xref:System.Windows.ContentElement>.  Para obtener más información sobre los elementos base, consulte [Información general sobre los elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md).  
  
 El <xref:System.Windows.Input.Keyboard> clase se ocupa principalmente de foco del teclado y el <xref:System.Windows.Input.FocusManager> se refiere principalmente con el foco lógico, pero esto no es una diferencia absoluta.  Un elemento que tiene el foco de teclado también tendrá el foco lógico, pero un elemento que tiene el foco lógico no tendrá necesariamente el foco de teclado.  Esto es evidente cuando se usa el <xref:System.Windows.Input.Keyboard> clase para establecer el elemento que tiene el foco de teclado, que también establece el foco lógico en el elemento.  
  

  
<a name="Keyboard_Focus"></a>   
## <a name="keyboard-focus"></a>Foco de teclado  
 El foco de teclado hace referencia al elemento que recibe actualmente la entrada del teclado.  Puede haber un único elemento en todo el escritorio que tenga el foco de teclado.  En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], tendrá el elemento que tiene el foco de teclado <xref:System.Windows.IInputElement.IsKeyboardFocused%2A> establecido en `true`.  La propiedad estática <xref:System.Windows.Input.Keyboard.FocusedElement%2A> en la <xref:System.Windows.Input.Keyboard> clase obtiene el elemento que tiene actualmente el foco del teclado.  
  
 En orden para un elemento que se va a obtener el foco del teclado, el <xref:System.Windows.UIElement.Focusable%2A> y <xref:System.Windows.UIElement.IsVisible%2A> propiedades en los elementos base deben establecerse en `true`.  Algunas clases, como la <xref:System.Windows.Controls.Panel> clase base, tener <xref:System.Windows.UIElement.Focusable%2A> establecido en `false` de forma predeterminada; por lo tanto, debe establecer <xref:System.Windows.UIElement.Focusable%2A> a `true` si desea que este tipo de elementos para poder obtener el foco del teclado.  
  
 El foco de teclado puede obtenerse a través de la interacción del usuario con la [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], como desplazarse mediante la tecla TAB hasta un elemento o hacer clic con el mouse en determinados elementos.  El foco de teclado también se puede obtener mediante programación utilizando la <xref:System.Windows.Input.Keyboard.Focus%2A> método en la <xref:System.Windows.Input.Keyboard> clase.  El <xref:System.Windows.Input.Keyboard.Focus%2A> método intenta dar el foco de teclado del elemento especificado.  El elemento devuelto es el elemento que tiene el foco de teclado, que puede ser un elemento diferente al solicitado si el objeto que tenía el foco antes o el que tiene el foco ahora bloquean la solicitud.  
  
 En el ejemplo siguiente se usa el <xref:System.Windows.Input.Keyboard.Focus%2A> método para establecer el foco de teclado en un <xref:System.Windows.Controls.Button>.  
  
 [!code-csharp[focussample#FocusSampleSetFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplesetfocus)]
 [!code-vb[focussample#FocusSampleSetFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplesetfocus)]  
  
 El <xref:System.Windows.UIElement.IsKeyboardFocused%2A> propiedad en las clases de elementos base Obtiene un valor que indica si el elemento tiene el foco de teclado.  El <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> propiedad en las clases de elementos base Obtiene un valor que indica si el elemento o cualquiera de sus elementos secundarios visuales tiene el foco de teclado.  
  
 Al establecer el foco inicial al iniciar la aplicación, debe ser el elemento que se va a recibir el foco en el árbol visual de la ventana inicial cargada por la aplicación y debe tener el elemento <xref:System.Windows.UIElement.Focusable%2A> y <xref:System.Windows.UIElement.IsVisible%2A> establecido en `true`.  El lugar recomendado para establecer el foco inicial está en el <xref:System.Windows.FrameworkElement.Loaded> controlador de eventos.  A <xref:System.Windows.Threading.Dispatcher> devolución de llamada también pueden utilizarse mediante una llamada a <xref:System.Windows.Threading.Dispatcher.Invoke%2A> o <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>.  
  
<a name="Logical_Focus"></a>   
## <a name="logical-focus"></a>Foco lógico  
 El foco lógico hace referencia a la <xref:System.Windows.Input.FocusManager.FocusedElement%2A?displayProperty=nameWithType> en un ámbito de foco.  Un ámbito de foco es un elemento que realiza un seguimiento de los <xref:System.Windows.Input.FocusManager.FocusedElement%2A> dentro de su ámbito.  Cuando el foco de teclado sale de un ámbito de foco, el elemento enfocado pierde el foco de teclado, pero conserva el foco lógico.  Cuando el foco de teclado vuelve al ámbito de foco, el elemento enfocado recibe el foco de teclado.  Esto permite cambiar el foco de teclado entre varios ámbitos de foco, pero garantiza que el elemento enfocado dentro del ámbito de foco vuelva a obtener el foco de teclado cuando el foco vuelva al ámbito de foco.  
  
 Puede haber varios elementos que tengan el foco lógico en una aplicación, pero solo puede haber uno con el foco lógico en un ámbito de foco concreto.  
  
 Un elemento que tiene el foco de teclado tiene el foco lógico para el ámbito de foco al que pertenece.  
  
 Un elemento se puede convertir en un ámbito de foco en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] estableciendo la <xref:System.Windows.Input.FocusManager> propiedad adjunta <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> a `true`.  En el código, se puede convertir un elemento en un ámbito de foco mediante una llamada a <xref:System.Windows.Input.FocusManager.SetIsFocusScope%2A>.  
  
 En el ejemplo siguiente se realiza una <xref:System.Windows.Controls.StackPanel> en un ámbito de foco estableciendo la <xref:System.Windows.Input.FocusManager.IsFocusScope%2A> propiedad adjunta.  
  
 [!code-xaml[MarkupSnippets#MarkupIsFocusScopeXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupisfocusscopexaml)]  
  
 [!code-csharp[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focussetisfocusscope)]
 [!code-vb[FocusSnippets#FocusSetIsFocusScope](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focussetisfocusscope)]  
  
 <xref:System.Windows.Input.FocusManager.GetFocusScope%2A>Devuelve el ámbito de foco para el elemento especificado.  
  
 Clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que son ámbitos de foco de forma predeterminada son <xref:System.Windows.Window>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.ToolBar>, y <xref:System.Windows.Controls.ContextMenu>.  
  
 <xref:System.Windows.Input.FocusManager.GetFocusedElement%2A>Obtiene el elemento tiene el foco para el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>establece el elemento tiene el foco en el ámbito de foco especificado.  <xref:System.Windows.Input.FocusManager.SetFocusedElement%2A>se utiliza normalmente para establecer el elemento tiene el foco inicial.  
  
 En el ejemplo siguiente se establece el elemento con foco en un ámbito de foco y se obtiene el elemento con foco de un ámbito de foco.  
  
 [!code-csharp[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSnippets/CSharp/Window1.xaml.cs#focusgetsetfocusedelement)]
 [!code-vb[FocusSnippets#FocusGetSetFocusedElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSnippets/visualbasic/window1.xaml.vb#focusgetsetfocusedelement)]  
  
<a name="Keyboard_Navigation"></a>   
## <a name="keyboard-navigation"></a>Navegación mediante teclado  
 La <xref:System.Windows.Input.KeyboardNavigation> clase es responsable de implementar la navegación del foco de teclado de manera predeterminada cuando se presiona una de las teclas de desplazamiento.  Las teclas de navegación son: TAB, MAYÚS+TAB, CTRL+TAB, CTRL+MAYÚS+TAB, flecha arriba, flecha abajo, flecha izquierda y flecha derecha.  
  
 Se puede cambiar el comportamiento de navegación de un contenedor de navegación estableciendo el archivo adjunto <xref:System.Windows.Input.KeyboardNavigation> propiedades <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A>, <xref:System.Windows.Input.KeyboardNavigation.ControlTabNavigation%2A>, y <xref:System.Windows.Input.KeyboardNavigation.DirectionalNavigation%2A>.  Estas propiedades son de tipo <xref:System.Windows.Input.KeyboardNavigationMode> y los valores posibles son <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, <xref:System.Windows.Input.KeyboardNavigationMode.Local>, <xref:System.Windows.Input.KeyboardNavigationMode.Contained>, <xref:System.Windows.Input.KeyboardNavigationMode.Cycle>, <xref:System.Windows.Input.KeyboardNavigationMode.Once>, y <xref:System.Windows.Input.KeyboardNavigationMode.None>.  El valor predeterminado es <xref:System.Windows.Input.KeyboardNavigationMode.Continue>, lo que significa que el elemento no es un contenedor de navegación.  
  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.Menu> con un número de <xref:System.Windows.Controls.MenuItem> objetos.  El <xref:System.Windows.Input.KeyboardNavigation.TabNavigation%2A> se establece la propiedad adjunta en <xref:System.Windows.Input.KeyboardNavigationMode.Cycle> en el <xref:System.Windows.Controls.Menu>.  Cuando se cambie el foco mediante la tecla tab en el <xref:System.Windows.Controls.Menu>, el enfoque se moverá desde cada elemento y cuando se llega al último elemento foco volverá al primer elemento.  
  
 [!code-xaml[MarkupSnippets#MarkupKeyboardNavigationTabNavigationXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml#markupkeyboardnavigationtabnavigationxaml)]  
  
 [!code-csharp[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MarkupSnippets/CSharp/Window1.xaml.cs#markupkeyboardnavigationtabnavigationcode)]
 [!code-vb[MarkupSnippets#MarkupKeyboardNavigationTabNavigationCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MarkupSnippets/visualbasic/window1.xaml.vb#markupkeyboardnavigationtabnavigationcode)]  
  
<a name="Manipulating_Focus_Programmatically"></a>   
## <a name="navigating-focus-programmatically"></a>Navegar con el foco mediante programación  
 Adicionales [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] para trabajar con foco son <xref:System.Windows.UIElement.MoveFocus%2A> y <xref:System.Windows.UIElement.PredictFocus%2A>.  
  
 <xref:System.Windows.FrameworkElement.MoveFocus%2A>cambia el foco al siguiente elemento en la aplicación.  Un <xref:System.Windows.Input.TraversalRequest> se utiliza para especificar la dirección.   El <xref:System.Windows.Input.FocusNavigationDirection> pasado a <xref:System.Windows.UIElement.MoveFocus%2A> especifica que se puede mover el foco de direcciones diferentes, como <xref:System.Windows.Input.FocusNavigationDirection.First>, <xref:System.Windows.Input.FocusNavigationDirection.Last>, <xref:System.Windows.Input.FocusNavigationDirection.Up> y <xref:System.Windows.Input.FocusNavigationDirection.Down>.  
  
 En el ejemplo siguiente se utiliza <xref:System.Windows.FrameworkElement.MoveFocus%2A> para cambiar el elemento tiene el foco.  
  
 [!code-csharp[focussample#FocusSampleMoveFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FocusSample/CSharp/Window1.xaml.cs#focussamplemovefocus)]
 [!code-vb[focussample#FocusSampleMoveFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FocusSample/visualbasic/window1.xaml.vb#focussamplemovefocus)]  
  
 <xref:System.Windows.FrameworkElement.PredictFocus%2A>Devuelve el objeto que recibiría el foco si el foco fuera a cambiarse.  Actualmente, solo <xref:System.Windows.Input.FocusNavigationDirection.Up>, <xref:System.Windows.Input.FocusNavigationDirection.Down>, <xref:System.Windows.Input.FocusNavigationDirection.Left>, y <xref:System.Windows.Input.FocusNavigationDirection.Right> son compatibles con <xref:System.Windows.FrameworkElement.PredictFocus%2A>.  
  
<a name="Focus_Events"></a>   
## <a name="focus-events"></a>Eventos de foco  
 Los eventos relacionados con el foco de teclado son <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus>, <xref:System.Windows.Input.Keyboard.GotKeyboardFocus> y <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocus>, <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>.  Los eventos se definen como eventos asociados en el <xref:System.Windows.Input.Keyboard> clase, pero son más fácilmente accesibles como eventos enrutados equivalentes de las clases de elementos base.  Para obtener más información sobre los eventos, consulte [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 <xref:System.Windows.Input.Keyboard.GotKeyboardFocus>se produce cuando el elemento obtiene el foco de teclado.  <xref:System.Windows.Input.Keyboard.LostKeyboardFocus>se produce cuando el elemento pierde el foco de teclado.  Si el <xref:System.Windows.Input.Keyboard.PreviewGotKeyboardFocus> eventos o el <xref:System.Windows.Input.Keyboard.PreviewLostKeyboardFocusEvent> evento está controlado y <xref:System.Windows.RoutedEventArgs.Handled%2A> se establece en `true`, a continuación, no cambia el foco.  
  
 En el ejemplo siguiente se adjuntan <xref:System.Windows.UIElement.GotKeyboardFocus> y <xref:System.Windows.UIElement.LostKeyboardFocus> controladores de eventos para un <xref:System.Windows.Controls.TextBox>.  
  
 [!code-xaml[keyboardsample#KeyboardSampleXAMLHandlerHookup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml#keyboardsamplexamlhandlerhookup)]  
  
 Cuando el <xref:System.Windows.Controls.TextBox> Obtiene el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.TextBox> se cambia a <xref:System.Windows.Media.Brushes.LightBlue%2A>.  
  
 [!code-csharp[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplegotfocus)]
 [!code-vb[keyboardsample#KeyboardSampleGotFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplegotfocus)]  
  
 Cuando el <xref:System.Windows.Controls.TextBox> pierde el foco de teclado, el <xref:System.Windows.Controls.Control.Background%2A> propiedad de la <xref:System.Windows.Controls.TextBox> vuelve a establecerse en blanco.  
  
 [!code-csharp[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/csharp/VS_Snippets_Wpf/KeyboardSample/CSharp/Window1.xaml.cs#keyboardsamplelostfocus)]
 [!code-vb[keyboardsample#KeyboardSampleLostFocus](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/KeyboardSample/visualbasic/window1.xaml.vb#keyboardsamplelostfocus)]  
  
 Los eventos relacionados con el foco lógico son <xref:System.Windows.UIElement.GotFocus> y <xref:System.Windows.UIElement.LostFocus>.  Estos eventos se definen en el <xref:System.Windows.Input.FocusManager> como eventos asociados, pero la <xref:System.Windows.Input.FocusManager> no expone contenedores de eventos CLR.  <xref:System.Windows.UIElement>y <xref:System.Windows.ContentElement> exponen estos eventos de manera más conveniente.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.FocusManager>  
 <xref:System.Windows.UIElement>  
 <xref:System.Windows.ContentElement>  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Información general sobre elementos base](../../../../docs/framework/wpf/advanced/base-elements-overview.md)
