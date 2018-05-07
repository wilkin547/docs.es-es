---
title: Información general sobre comandos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interfaces [WPF], ICommandSource
- command library [WPF]
- commands [WPF], definition of
- CommandBindings [WPF]
- ICommandSource interfaces [WPF]
- commanding [WPF]
- CommandManager [WPF]
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
ms.openlocfilehash: 0d426d8cf174a61c724e97b5e7af5c1428679716
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="commanding-overview"></a>Información general sobre comandos
<a name="introduction"></a> Los comandos constituyen un mecanismo de entrada de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], que permite el control de entrada en un nivel más semántico que la entrada del dispositivo. Algunos ejemplos de comandos son las operaciones **Copiar**, **Cortar** y **Pegar** presentes en numerosas aplicaciones.  
  
 Esta información general define los comandos que se encuentran en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las clases que forman parte del modelo de comandos, y el procedimiento para usar y crear comandos en las aplicaciones.  
  
 Este tema contiene las siguientes secciones:  
  
-   [¿Qué son los comandos?](#commands_at_10000_feet)  
  
-   [Ejemplo de comando simple en WPF](#simple_command)  
  
-   [Cuatro conceptos básicos de los comandos de WPF](#Four_main_Concepts)  
  
-   [Biblioteca de comandos](#Command_Library)  
  
-   [Creación de comandos personalizados](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## <a name="what-are-commands"></a>¿Qué son los comandos?  
 Los comandos tienen varios propósitos. El primer propósito es separar la semántica y el objeto que invoca un comando de la lógica que ejecuta el comando. Esto permite que varios orígenes dispares invoquen la misma lógica de comando, así como personalizar la lógica de comando para distintos destinos. Por ejemplo, las operaciones de edición **Copiar**, **Cortar** y **Pegar**, que se encuentran en muchas aplicaciones, se pueden invocar mediante acciones de usuario diferentes si se implementan mediante comandos. Una aplicación podría permitir a un usuario cortar texto u objetos seleccionados mediante un clic en un botón, la selección de un elemento en un menú o una combinación de teclas, como CTRL+X. El uso de comandos permite enlazar cada tipo de acción del usuario a la misma lógica.  
  
 Otra finalidad de los comandos es indicar si una acción está disponible. Para continuar con el ejemplo del corte de un objeto o de texto, la acción solo tiene sentido si se selecciona algún elemento. Si un usuario intenta cortar un objeto o texto sin tener nada seleccionado, no ocurrirá nada. Para indicárselo al usuario, muchas aplicaciones deshabilitan los botones y elementos de menú para indicar si es posible realizar una acción. Un comando puede indicar si una acción es posible mediante la implementación de la <xref:System.Windows.Input.ICommand.CanExecute%2A> método. Un botón puede suscribirse a la <xref:System.Windows.Input.ICommand.CanExecuteChanged> eventos y puede deshabilitarse si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `false` o habilitarse si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `true`.  
  
 La semántica de un comando puede ser coherente entre aplicaciones y clases, pero la lógica de la acción es específica del objeto determinado sobre el que actúa. La combinación de teclas CTRL+X invoca el comando **Cortar** en clases de texto, clases de imagen y exploradores web, pero la lógica real para realizar la operación **Cortar** la define la aplicación que realiza el corte. Un <xref:System.Windows.Input.RoutedCommand> permite a los clientes implementar la lógica. Un objeto de texto puede cortar el texto seleccionado en el Portapapeles, mientras que un objeto de imagen puede cortar la imagen seleccionada. Cuando una aplicación controla el <xref:System.Windows.Input.CommandManager.Executed> evento, se tiene acceso al destino del comando y se pueda realizar una acción adecuada dependiendo del tipo del destino.  
  
<a name="simple_command"></a>   
## <a name="simple-command-example-in-wpf"></a>Ejemplo de comando simple en WPF  
 La manera más sencilla de usar un comando en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consiste en usar predefinido <xref:System.Windows.Input.RoutedCommand> desde una de las clases de biblioteca de comandos; use un control con compatibilidad nativa para controlar el comando; y usar un control que ofrece compatibilidad nativa para invocar un comando.  El <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando es uno de los comandos predefinidos en la <xref:System.Windows.Input.ApplicationCommands> clase.  El <xref:System.Windows.Controls.TextBox> control incorpora lógica para controlar la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando.  Y la <xref:System.Windows.Controls.MenuItem> clase ofrece compatibilidad nativa para invocar comandos.  
  
 En el ejemplo siguiente se muestra cómo configurar un <xref:System.Windows.Controls.MenuItem> para que cuando se hace clic en invocará la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando un <xref:System.Windows.Controls.TextBox>, suponiendo que el <xref:System.Windows.Controls.TextBox> tiene el foco de teclado.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## <a name="four-main-concepts-in-wpf-commanding"></a>Cuatro conceptos básicos de los comandos de WPF  
 El modelo de comando enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede dividir en cuatro conceptos básicos: el comando, el origen del comando, el destino del comando y el enlace del comando:  
  
-   El *comando* es la acción que se va a ejecutar.  
  
-   El *origen del comando* es el objeto que invoca el comando.  
  
-   El *destino del comando* objeto en el que se ejecuta el comando.  
  
-   El *enlace del comando* es el objeto que asigna la lógica del comando al comando.  
  
 En el ejemplo anterior, el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando es el comando, el <xref:System.Windows.Controls.MenuItem> es el origen del comando, el <xref:System.Windows.Controls.TextBox> es el destino del comando y el enlace de comando proporcionado por el <xref:System.Windows.Controls.TextBox> control.  Cabe mencionar que no siempre es el caso de que el <xref:System.Windows.Input.CommandBinding> proporcionado por el control que es la clase de destino del comando.  Con bastante frecuencia la <xref:System.Windows.Input.CommandBinding> debe crearse el desarrollador de aplicaciones, o la <xref:System.Windows.Input.CommandBinding> estar conectado a un antecesor del destino de comando.  
  
<a name="Commands"></a>   
### <a name="commands"></a>Comandos  
 Comandos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crean implementando la <xref:System.Windows.Input.ICommand> interfaz.  <xref:System.Windows.Input.ICommand> expone dos métodos, <xref:System.Windows.Input.ICommand.Execute%2A>, y <xref:System.Windows.Input.ICommand.CanExecute%2A>y un evento <xref:System.Windows.Input.ICommand.CanExecuteChanged>. <xref:System.Windows.Input.ICommand.Execute%2A> realiza las acciones que están asociadas con el comando. <xref:System.Windows.Input.ICommand.CanExecute%2A> Determina si el comando puede ejecutarse en el destino del comando actual. <xref:System.Windows.Input.ICommand.CanExecuteChanged> se produce si el Administrador de comandos que centraliza las operaciones de comandos detecta un cambio en el origen del comando que podría invalidar un comando que se ha generado pero aún no se ha ejecutado por el enlace de comando.  El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementación de <xref:System.Windows.Input.ICommand> es la <xref:System.Windows.Input.RoutedCommand> clase y es el foco de esta información general.  
  
 Los orígenes principales de la entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son el mouse, el teclado, el lápiz y los comandos enrutados.  Las entradas más orientadas a dispositivo use un <xref:System.Windows.RoutedEvent> para notificar a los objetos en una página de aplicación que se ha producido un evento de entrada.  A <xref:System.Windows.Input.RoutedCommand> no es diferente.  El <xref:System.Windows.Input.RoutedCommand.Execute%2A> y <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> métodos de un <xref:System.Windows.Input.RoutedCommand> no contienen la lógica de aplicación para el comando, pero en su lugar provocar eventos enrutados que túnel y propagarse a través del árbol de elementos hasta que encuentran un objeto con un <xref:System.Windows.Input.CommandBinding>.  El <xref:System.Windows.Input.CommandBinding> contiene los controladores para estos eventos y los controladores que realizan el comando.  Para obtener más información sobre el enrutamiento de eventos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 El <xref:System.Windows.Input.RoutedCommand.Execute%2A> método en un <xref:System.Windows.Input.RoutedCommand> provoca la <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed> eventos en el destino del comando.  El <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> método en un <xref:System.Windows.Input.RoutedCommand> provoca la <xref:System.Windows.Input.CommandManager.CanExecute> y <xref:System.Windows.Input.CommandManager.PreviewCanExecute> eventos en el destino del comando.  Estos túnel de eventos y de burbujas a través del árbol de elementos hasta que encuentran un objeto que tiene un <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Proporciona un conjunto de comandos enrutados comunes distribuido entre varias clases: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands>, y <xref:System.Windows.Documents.EditingCommands>.  Estas clases se componen únicamente de los <xref:System.Windows.Input.RoutedCommand> objetos y no la lógica de implementación del comando.  La lógica de implementación es responsabilidad del objeto en el que se ejecuta el comando.  
  
<a name="Command_Sources"></a>   
### <a name="command-sources"></a>Orígenes del comando  
 El origen del comando es el objeto que invoca el comando.  Son ejemplos de orígenes de comando <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button>, y <xref:System.Windows.Input.KeyGesture>.  
  
 Comando orígenes en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] generalmente implementar la <xref:System.Windows.Input.ICommandSource> interfaz.  
  
 <xref:System.Windows.Input.ICommandSource> expone tres propiedades: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, y <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> es el comando que se ejecutará cuando se invoque el origen de comando.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> es el objeto en el que se ejecute el comando.  Merece la pena mencionar que en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> propiedad <xref:System.Windows.Input.ICommandSource> solo es aplicable cuando la <xref:System.Windows.Input.ICommand> es una <xref:System.Windows.Input.RoutedCommand>.  Si el <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> se establece en un <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es un <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando. Si el <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> no se establece, el elemento tiene el foco de teclado será el destino del comando.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> es un tipo de datos definido por el usuario que se utilizan para pasar información a los controladores de implementar el comando.  
  
 El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] las clases que implementan <xref:System.Windows.Input.ICommandSource> son <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink>, y <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, y <xref:System.Windows.Documents.Hyperlink> invocar un comando cuando se hace clic en y un <xref:System.Windows.Input.InputBinding> un comando, se invoca cuando el <xref:System.Windows.Input.InputGesture> asociados con se lleva a cabo.  
  
 En el ejemplo siguiente se muestra cómo utilizar un <xref:System.Windows.Controls.MenuItem> en un <xref:System.Windows.Controls.ContextMenu> como origen de comando para el <xref:System.Windows.Input.ApplicationCommands.Properties%2A> comando.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Normalmente, un origen de comando escuchará el <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged> eventos.  Este evento informa al origen del comando de un posible cambio en la capacidad del comando para ejecutarse en el destino del comando actual.  El origen del comando puede consultar el estado actual de la <xref:System.Windows.Input.RoutedCommand> utilizando el <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> método.  A continuación, el origen del comando puede deshabilitarse automáticamente si no se puede ejecutar el comando.  Un ejemplo de esto es un <xref:System.Windows.Controls.MenuItem> se atenúa out cuando no se puede ejecutar un comando.  
  
 Un <xref:System.Windows.Input.InputGesture> puede usarse como un origen de comando.  Dos tipos de gestos de entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son la <xref:System.Windows.Input.KeyGesture> y <xref:System.Windows.Input.MouseGesture>.  Se puede considerar un <xref:System.Windows.Input.KeyGesture> como un método abreviado de teclado, como CTRL + C.  A <xref:System.Windows.Input.KeyGesture> está formada por un <xref:System.Windows.Input.Key> y un conjunto de <xref:System.Windows.Input.ModifierKeys>.  A <xref:System.Windows.Input.MouseGesture> está formada por un <xref:System.Windows.Input.MouseAction> y un conjunto opcional de <xref:System.Windows.Input.ModifierKeys>.  
  
 En orden para un <xref:System.Windows.Input.InputGesture> para actuar como un origen de comando, debe estar asociado con un comando. Existen dos maneras de lograrlo.  Es una manera de usar un <xref:System.Windows.Input.InputBinding>.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Input.KeyBinding> entre un <xref:System.Windows.Input.KeyGesture> y <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Otra manera de asociar un <xref:System.Windows.Input.InputGesture> a una <xref:System.Windows.Input.RoutedCommand> consiste en agregar el <xref:System.Windows.Input.InputGesture> a la <xref:System.Windows.Input.InputGestureCollection> en el <xref:System.Windows.Input.RoutedCommand>.  
  
 En el ejemplo siguiente se muestra cómo agregar un <xref:System.Windows.Input.KeyGesture> a la <xref:System.Windows.Input.InputGestureCollection> de un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### <a name="commandbinding"></a>CommandBinding  
 Un <xref:System.Windows.Input.CommandBinding> asocia un comando con los controladores de eventos que implementan el comando.  
  
 El <xref:System.Windows.Input.CommandBinding> clase contiene un <xref:System.Windows.Input.CommandBinding.Command%2A> propiedad, y <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute>, y <xref:System.Windows.Input.CommandBinding.CanExecute> eventos.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> es el comando que el <xref:System.Windows.Input.CommandBinding> se está asociando.  Los controladores de eventos que están conectados a la <xref:System.Windows.Input.CommandBinding.PreviewExecuted> y <xref:System.Windows.Input.CommandBinding.Executed> eventos implementan la lógica de comando.  Los controladores de eventos que se adjunta a la <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> y <xref:System.Windows.Input.CommandBinding.CanExecute> eventos determinan si el comando puede ejecutarse en el destino del comando actual.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Input.CommandBinding> en el directorio raíz <xref:System.Windows.Window> de una aplicación.  El <xref:System.Windows.Input.CommandBinding> asocia la <xref:System.Windows.Input.ApplicationCommands.Open%2A> con <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute> controladores.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Después, el <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler> se crean.  El <xref:System.Windows.Input.ExecutedRoutedEventHandler> abre un <xref:System.Windows.MessageBox> que muestra una cadena que indica que se ha ejecutado el comando.  El <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> propiedad `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 A <xref:System.Windows.Input.CommandBinding> se adjunta a un objeto específico, como la raíz <xref:System.Windows.Window> de la aplicación o un control.  El objeto que la <xref:System.Windows.Input.CommandBinding> se adjunta a define el ámbito del enlace.  Por ejemplo, un <xref:System.Windows.Input.CommandBinding> adjunta a un antecesor del comando se puede alcanzar el destino por la <xref:System.Windows.Input.CommandBinding.Executed> eventos, pero un <xref:System.Windows.Input.CommandBinding> adjunta a un descendiente del comando no se puede alcanzar el destino.  Esta es una consecuencia directa de la forma un <xref:System.Windows.RoutedEvent> túneles y burbujas desde el objeto que genera el evento.  
  
 En algunas situaciones la <xref:System.Windows.Input.CommandBinding> se adjunta en el destino del comando, como con la <xref:System.Windows.Controls.TextBox> clase y la <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, y <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comandos. Con bastante frecuencia no obstante, resulta más conveniente adjuntar el <xref:System.Windows.Input.CommandBinding> a un antecesor del destino de comando, como el método main <xref:System.Windows.Window> o el objeto de aplicación, especialmente si el mismo <xref:System.Windows.Input.CommandBinding> puede utilizarse para varios destinos de comando.  Estas son las decisiones de diseño que querrá tener en cuenta al crear la infraestructura de comandos.  
  
<a name="Commane_Target"></a>   
### <a name="command-target"></a>Destino del comando  
 El destino del comando es el elemento en el que se ejecuta el comando.  Con lo que se refiere a un <xref:System.Windows.Input.RoutedCommand>, el destino del comando es el elemento en el que el enrutamiento de la <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandManager.CanExecute> se inicia.  Como se indicó anteriormente, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> propiedad <xref:System.Windows.Input.ICommandSource> solo es aplicable cuando la <xref:System.Windows.Input.ICommand> es una <xref:System.Windows.Input.RoutedCommand>.  Si el <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> se establece en un <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es un <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando.  
  
 El origen del comando puede establecer de manera explícita el destino del comando.  Si no se define el destino del comando, el elemento con el foco del teclado se usará como el destino del comando.  Una de las ventajas de usar el elemento con el foco del teclado como el destino del comando es que permite al desarrollador de la aplicación usar el mismo origen del comando para invocar un comando en varios destinos sin necesidad de realizar un seguimiento del destino del comando.  Por ejemplo, si un <xref:System.Windows.Controls.MenuItem> , se invoca el **pegar** comando en una aplicación que tenga un <xref:System.Windows.Controls.TextBox> control y un <xref:System.Windows.Controls.PasswordBox> (control), el destino puede ser el <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.PasswordBox> dependiendo de qué control tiene el foco de teclado.  
  
 En el ejemplo siguiente se muestra cómo establecer de forma explícita el destino del comando en el marcado y en el código subyacente.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### <a name="the-commandmanager"></a>CommandManager  
 El <xref:System.Windows.Input.CommandManager> actúa un número de comandos relacionados con las funciones.  Proporciona un conjunto de métodos estáticos para agregar y quitar <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute>, y <xref:System.Windows.Input.CommandManager.CanExecute> controladores de eventos a y desde un elemento específico.  Proporciona un medio para registrar <xref:System.Windows.Input.CommandBinding> y <xref:System.Windows.Input.InputBinding> objetos en una clase específica.  El <xref:System.Windows.Input.CommandManager> también proporciona un medio, a través de la <xref:System.Windows.Input.CommandManager.RequerySuggested> eventos para notificar a un comando cuándo debe provocar la <xref:System.Windows.Input.ICommand.CanExecuteChanged> eventos.  
  
 El <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> método fuerza la <xref:System.Windows.Input.CommandManager> para generar el <xref:System.Windows.Input.CommandManager.RequerySuggested> eventos.  Esto es útil para las condiciones que deben habilitar o deshabilitar un comando, aunque no están las condiciones que la <xref:System.Windows.Input.CommandManager> es consciente de.  
  
<a name="Command_Library"></a>   
## <a name="command-library"></a>Biblioteca de comandos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de comandos predefinidos.  La biblioteca de comandos se compone de las siguientes clases: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>y el <xref:System.Windows.Input.ComponentCommands>.  Estas clases proporcionan comandos como <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> y <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A>, y <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Muchos de estos comandos incluyen un conjunto de enlaces de entrada predeterminados.  Por ejemplo, si especifica que la aplicación controla el comando Copiar, obtendrá automáticamente el enlace de teclado "CTRL + C". También obtendrá enlaces para otros dispositivos de entrada, como información de voz y gestos del lápiz de [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)].  
  
 Al hacer referencia a los comandos de las diversas bibliotecas de comandos mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], normalmente puede omitir el nombre de clase de la clase de biblioteca que expone la propiedad de comando estática. En general, los nombres de comando son inequívocos como cadenas y los tipos propietarios existen para proporcionar una agrupación lógica de comandos, pero no son necesarios para la desambiguación. Por ejemplo, puede especificar `Command="Cut"` en lugar del comando `Command="ApplicationCommands.Cut"` más detallado. Se trata de un mecanismo de conveniencia que se halla integrado en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador de comandos (más concretamente, es un comportamiento del convertidor de tipos de <xref:System.Windows.Input.ICommand>, que la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] referencias de procesador en tiempo de carga).  
  
<a name="creating_commands"></a>   
## <a name="creating-custom-commands"></a>Creación de comandos personalizados  
 Si los comandos de las clases de la biblioteca de comandos no satisfacen sus necesidades, puede crear sus propios comandos.  Existen dos maneras de crear un comando personalizado.  La primera consiste en empezar desde el principio de e implementar el <xref:System.Windows.Input.ICommand> interfaz.  La otra forma y el enfoque más común consiste en crear un <xref:System.Windows.Input.RoutedCommand> o <xref:System.Windows.Input.RoutedUICommand>.  
  
 Para obtener un ejemplo de creación de un archivo <xref:System.Windows.Input.RoutedCommand>, consulte [crear un ejemplo de RoutedCommand personalizado](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.RoutedCommand>  
 <xref:System.Windows.Input.CommandBinding>  
 <xref:System.Windows.Input.InputBinding>  
 <xref:System.Windows.Input.CommandManager>  
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)  
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)  
 [Implement ICommandSource (ejemplo)](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)  
 [Cómo: Agregar un comando a un elemento de menú](http://msdn.microsoft.com/library/013d68a0-5373-4a68-bd91-5de574307370)  
 [Crear un objeto RoutedCommand de muestra personalizado](http://go.microsoft.com/fwlink/?LinkID=159980)
