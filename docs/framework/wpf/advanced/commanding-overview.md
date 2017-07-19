---
title: "Informaci&#243;n general sobre comandos | Microsoft Docs"
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
  - "clases, CommandBinding"
  - "biblioteca de comandos"
  - "CommandBindings"
  - "comandos"
  - "CommandManager"
  - "comandos, definición de"
  - "interfaces de ICommandSource"
  - "interfaces, ICommandSource"
ms.assetid: bc208dfe-367d-426a-99de-52b7e7511e81
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 34
---
# Informaci&#243;n general sobre comandos
<a name="introduction"></a> Los comandos constituyen un mecanismo de entrada en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] que ofrece la administración de acciones del usuario en un nivel más semántico que la entrada de dispositivo.  Los ejemplos de comandos son las operaciones **Copiar**, **Cortar**y **Pegar** que se encuentran en muchas aplicaciones.  
  
 Esta información general define qué comandos hay en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], qué clases forman parte del modelo de comandos, y cómo utilizar y crear comandos en las aplicaciones.  
  
 Este tema contiene las siguientes secciones:  
  
-   [¿Qué son los comandos?](#commands_at_10000_feet)  
  
-   [Ejemplo de comando simple en WPF](#simple_command)  
  
-   [Cuatro conceptos básicos en los comandos WPF](#Four_main_Concepts)  
  
-   [Biblioteca de comandos](#Command_Library)  
  
-   [Crear comandos personalizados](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>   
## ¿Qué son los comandos?  
 Los comandos tienen varios propósitos.  El primer propósito es separar la semántica y el objeto que invoca un comando de la lógica que lo ejecuta.  Esto permite que varios orígenes dispares invoquen la misma lógica de comando y permite personalizar la lógica de comando para diferentes destinos.  Por ejemplo, las operaciones de edición **Copiar**, **Cortar** y **Pegar**, que se encuentran en muchas aplicaciones, se pueden invocar mediante distintas acciones de usuario si se implementan con comandos.  Una aplicación podría permitir a un usuario cortar texto u objetos seleccionados haciendo clic en un botón, eligiendo un elemento en un menú o utilizando una combinación de teclas, como CTRL\+X.  Mediante el uso de comandos, puede enlazar cada tipo de acción del usuario a la misma lógica.  
  
 Otro propósito de los comandos es indicar si una acción está disponible.  Para continuar el ejemplo de cortar un objeto o texto, la acción tiene sentido sólo cuando algo está seleccionado.  Si un usuario intenta cortar un objeto o texto sin tener algo seleccionado, no pasaría nada.  Para indicar esto al usuario, muchas aplicaciones deshabilitan los botones y elementos de menú para que sepa si es posible realizar una acción.  Un comando puede indicar si una acción es posible implementando el método <xref:System.Windows.Input.ICommand.CanExecute%2A>.  Un botón puede suscribirse al evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> y estar deshabilitado si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `false` o estar habilitado si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `true`.  
  
 La semántica de un comando puede ser coherente entre aplicaciones y clases, pero la lógica de la acción es específica del objeto sobre el que se actúa.  La combinación de teclas CTRL\+X invoca el comando **Cortar** en clases de texto, clases de imagen y exploradores web, pero la lógica real para realizar la operación **Cortar** la define la aplicación que la realiza.  <xref:System.Windows.Input.RoutedCommand> permite a los clientes implementar la lógica.  Un objeto de texto puede cortar el texto seleccionado y pegarlo en el portapapeles, mientras que un objeto de imagen puede cortar la imagen seleccionada.  Cuando una aplicación controla el evento <xref:System.Windows.Input.CommandManager.Executed>, tiene acceso al destino del comando y puede realizar la acción correspondiente en función del tipo del destino.  
  
<a name="simple_command"></a>   
## Ejemplo de comando simple en WPF  
 La manera más simple de utilizar un comando en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es utilizar un objeto <xref:System.Windows.Input.RoutedCommand> predefinido de una de las clases de biblioteca de comandos; utilice un control con compatibilidad nativa para administrar el comando; y utilice un control con compatibilidad nativa para invocar un comando.  El comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> es uno de los comandos predefinidos de la clase <xref:System.Windows.Input.ApplicationCommands>.  El control <xref:System.Windows.Controls.TextBox> tiene lógica integrada para administrar el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  La clase <xref:System.Windows.Controls.MenuItem> tiene compatibilidad nativa para invocar comandos.  
  
 En el ejemplo siguiente se muestra cómo configurar un elemento <xref:System.Windows.Controls.MenuItem> para que, cuando se haga clic en él, invoque el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> en un objeto <xref:System.Windows.Controls.TextBox>, suponiendo que <xref:System.Windows.Controls.TextBox> tenga el foco de teclado.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>   
## Cuatro conceptos básicos en los comandos WPF  
 El modelo de comando enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede descomponer en cuatro conceptos básicos: el comando, el origen del comando, el destino del comando y el enlace del comando:  
  
-   El *comando* es la acción que se va a ejecutar.  
  
-   El *origen del comando* es el objeto que invoca el comando.  
  
-   El *destino del comando* es el objeto en el que se ejecuta el comando.  
  
-   El *enlace del comando* es el objeto que asigna la lógica de comando al comando.  
  
 En el ejemplo anterior, el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> es el comando, el objeto <xref:System.Windows.Controls.MenuItem> es el origen del comando, el objeto <xref:System.Windows.Controls.TextBox> es el destino del comando y en enlace del comando lo proporciona el control <xref:System.Windows.Controls.TextBox>.  Hay que indicar que no siempre sucede que el objeto <xref:System.Windows.Input.CommandBinding> lo suministre el control que es la clase de destino del comando.  Con frecuencia, el objeto <xref:System.Windows.Input.CommandBinding> debe ser creado por el desarrollador de la aplicación; también puede ocurrir que el objeto <xref:System.Windows.Input.CommandBinding> esté asociado a un antecesor del destino del comando.  
  
<a name="Commands"></a>   
### Comandos  
 Los comandos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crean mediante la implementación de la interfaz <xref:System.Windows.Input.ICommand>.  <xref:System.Windows.Input.ICommand> expone dos métodos, <xref:System.Windows.Input.ICommand.Execute%2A> y <xref:System.Windows.Input.ICommand.CanExecute%2A>, y un evento, <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  <xref:System.Windows.Input.ICommand.Execute%2A> realiza las acciones que están asociadas al comando. <xref:System.Windows.Input.ICommand.CanExecute%2A> determina si el comando se puede ejecutar en el destino del comando actual.  El evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> se produce si el administrador de comandos que centraliza las operaciones de comandos detecta un cambio en el origen del comando que podría invalidar un comando que se ha iniciado pero que el enlace de comando aún no ha ejecutado.  La implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de <xref:System.Windows.Input.ICommand> es la clase <xref:System.Windows.Input.RoutedCommand> y el centro de interés de esta información general.  
  
 Los principales orígenes de entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son el mouse, el teclado, la entrada de lápiz y los comandos enrutados.  Las entradas más orientadas a dispositivo utilizan un objeto <xref:System.Windows.RoutedEvent> para notificar a los objetos de una página de aplicación que se ha producido un evento de entrada.  Un <xref:System.Windows.Input.RoutedCommand> no es diferente.  Los métodos <xref:System.Windows.Input.RoutedCommand.Execute%2A> y <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> de una objeto <xref:System.Windows.Input.RoutedCommand> no contienen la lógica de aplicación para el comando, sino que provocan eventos enrutados que se tunelizan y se propagar a través del elemento hasta que encuentran un objeto con <xref:System.Windows.Input.CommandBinding>.  El objeto <xref:System.Windows.Input.CommandBinding> contiene los controladores para estos eventos y son los controladores los que realizan el comando.  Para obtener más información sobre el enrutamiento de eventos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], vea [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md).  
  
 El método <xref:System.Windows.Input.RoutedCommand.Execute%2A> de un objeto <xref:System.Windows.Input.RoutedCommand> provoca los eventos <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed> en el destino del comando.  El método <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> de un objeto <xref:System.Windows.Input.RoutedCommand> provoca los eventos <xref:System.Windows.Input.CommandManager.CanExecute> y <xref:System.Windows.Input.CommandManager.PreviewCanExecute> en el destino del comando.  Estos eventos se tunelizan y se propagan a través del árbol de elementos hasta que encuentran un objeto que tiene un objeto <xref:System.Windows.Input.CommandBinding> para ese comando en particular.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de comandos enrutados comunes distribuido entre varias clases: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> y <xref:System.Windows.Documents.EditingCommands>.  Estas clases constan solamente de los objetos <xref:System.Windows.Input.RoutedCommand> y no de la lógica de implementación del comando.  La lógica de implementación es responsabilidad del objeto en el que se ejecuta el comando.  
  
<a name="Command_Sources"></a>   
### Orígenes de comando  
 Un origen de comando es el objeto que invoca el comando.  Ejemplos de orígenes de comando son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> y <xref:System.Windows.Input.KeyGesture>.  
  
 Los orígenes de comando en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementan generalmente la interfaz <xref:System.Windows.Input.ICommandSource>.  
  
 <xref:System.Windows.Input.ICommandSource> expone tres propiedades: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> y <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
-   <xref:System.Windows.Input.ICommandSource.Command%2A> es el comando a ejecutar cuando se invoca el origen de comando.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> es el objeto en el que se ejecuta el comando.  Hay que destacar que en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> de <xref:System.Windows.Input.ICommandSource> solamente es aplicable cuando la interfaz <xref:System.Windows.Input.ICommand> es un objeto <xref:System.Windows.Input.RoutedCommand>.  Si se establece la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> en un objeto <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es de tipo <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando.  Si no se establece <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, el destino del comando será el elemento que tenga el foco del teclado.  
  
-   <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> es un tipo de datos definido por el usuario utilizado para pasar información a los controladores que implementan el comando.  
  
 Las clases [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que implementan <xref:System.Windows.Input.ICommandSource> son <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> y <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>y <xref:System.Windows.Documents.Hyperlink> invocan un comando cuando se hace clic en ellos y <xref:System.Windows.Input.InputBinding> invoca un comando cuando se realiza el <xref:System.Windows.Input.InputGesture> asociado.  
  
 En el ejemplo siguientes se muestra cómo usar un objeto <xref:System.Windows.Controls.MenuItem> en un objeto <xref:System.Windows.Controls.ContextMenu> como origen de comando para el comando <xref:System.Windows.Input.ApplicationCommands.Properties%2A>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Habitualmente, un origen de comando escuchará el evento <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>.  Este evento informa al origen de comando que es posible que haya cambiado la capacidad del comando para ejecutarse en el destino de comando actual.  El origen de comando puede consultar el estado actual del objeto <xref:System.Windows.Input.RoutedCommand> utilizando el método <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>.  El origen de comando se puede deshabilitar a sí mismo si no se puede ejecutar el comando.  Un ejemplo de esto es un objeto <xref:System.Windows.Controls.MenuItem> que se atenúa cuando un comando no se puede ejecutar.  
  
 Un objeto <xref:System.Windows.Input.InputGesture> se puede utilizar como origen de comando.  Dos tipos de gestos de entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son <xref:System.Windows.Input.KeyGesture> y <xref:System.Windows.Input.MouseGesture>.  Puede pensar en un objeto <xref:System.Windows.Input.KeyGesture> como en un método abreviado de teclado, tal como CTRL\+C.  Un objeto <xref:System.Windows.Input.KeyGesture> consta de un objeto <xref:System.Windows.Input.Key> y un conjunto de <xref:System.Windows.Input.ModifierKeys>.  Un objeto <xref:System.Windows.Input.MouseGesture> consta de un objeto <xref:System.Windows.Input.MouseAction> y un conjunto opcional de <xref:System.Windows.Input.ModifierKeys>.  
  
 Para que un <xref:System.Windows.Input.InputGesture> actúe como un origen de comando, debe estar asociado a un comando.  Hay varias maneras de lograrlo.  Una manera es utilizar un objeto <xref:System.Windows.Input.InputBinding>.  
  
 En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Input.KeyBinding> entre un objeto <xref:System.Windows.Input.KeyGesture> y un objeto <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Otra manera de asociar un objeto <xref:System.Windows.Input.InputGesture> a un objeto <xref:System.Windows.Input.RoutedCommand> es agregar el objeto <xref:System.Windows.Input.InputGesture> a la colección <xref:System.Windows.Input.InputGestureCollection> del objeto <xref:System.Windows.Input.RoutedCommand>.  
  
 En el ejemplo siguiente se muestra cómo agregar un objeto <xref:System.Windows.Input.KeyGesture> a la colección <xref:System.Windows.Input.InputGestureCollection> de un objeto <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>   
### CommandBinding  
 Un objeto <xref:System.Windows.Input.CommandBinding> asocia un comando con los controladores de eventos que implementan el comando.  
  
 La clase <xref:System.Windows.Input.CommandBinding> contiene una propiedad <xref:System.Windows.Input.CommandBinding.Command%2A>, y eventos <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> y <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> es el comando al que se está asociando <xref:System.Windows.Input.CommandBinding>.  Los controladores de eventos asociados a los eventos <xref:System.Windows.Input.CommandBinding.PreviewExecuted> y <xref:System.Windows.Input.CommandBinding.Executed> implementan la lógica del comando.  Los controladores de eventos asociados a los eventos <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> y <xref:System.Windows.Input.CommandBinding.CanExecute> determinan si el comando puede ejecutarse en el destino de comando actual.  
  
 En el ejemplo siguiente se muestra cómo crear un objeto <xref:System.Windows.Input.CommandBinding> en el objeto <xref:System.Windows.Window> raíz de una aplicación.  El comando <xref:System.Windows.Input.CommandBinding> asocia el comando <xref:System.Windows.Input.ApplicationCommands.Open%2A> con los controladores <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 [!code-xml[commandwithhandler#CommandHandlerCommandBinding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 A continuación, se crea el objeto <xref:System.Windows.Input.ExecutedRoutedEventHandler> y un objeto <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  El objeto <xref:System.Windows.Input.ExecutedRoutedEventHandler> abre un control <xref:System.Windows.MessageBox> que muestra una cadena que indica que se ha ejecutado el comando.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la propiedad <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> en `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 Un objeto <xref:System.Windows.Input.CommandBinding> se asocia a un objeto específico, tal como el objeto <xref:System.Windows.Window> raíz de la aplicación o un control.  El objeto al que se asocia <xref:System.Windows.Input.CommandBinding> define el ámbito del enlace.  Por ejemplo, un objeto <xref:System.Windows.Input.CommandBinding> asociado a un antecesor del destino de comando puede ser alcanzado por el evento <xref:System.Windows.Input.CommandBinding.Executed>, pero un objeto <xref:System.Windows.Input.CommandBinding> asociado a un descendiente del destino de comando no se puede alcanzar.  Ésta es una consecuencia directa de la manera en que los objetos <xref:System.Windows.RoutedEvent> se tuneliza y propagan desde el objeto que provoca el evento.  
  
 En algunas situaciones, el objeto <xref:System.Windows.Input.CommandBinding> está asociado al propio destino de comando, como ocurre con la clase <xref:System.Windows.Controls.TextBox> y los comandos <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> y <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  Bastante a menudo, sin embargo, es más cómodo asociar el objeto <xref:System.Windows.Input.CommandBinding> a un antecesor del destino de comando, tal como el objeto <xref:System.Windows.Window> principal o el objeto Application, sobre todo si el mismo objeto <xref:System.Windows.Input.CommandBinding> puede utilizarse para varios destinos de comando.  Estas son decisiones de diseño que deberá considerar cuando cree la infraestructura de comandos.  
  
<a name="Commane_Target"></a>   
### Destino de comando  
 El destino de comando es el elemento en el que se ejecuta el comando.  En lo referente a un objeto <xref:System.Windows.Input.RoutedCommand>, el destino de comando es el elemento en el que se inicia el enrutado de <xref:System.Windows.Input.CommandManager.CanExecute> y <xref:System.Windows.Input.CommandManager.Executed>.  Como se indicó previamente, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> de <xref:System.Windows.Input.ICommandSource> solamente se aplica cuando <xref:System.Windows.Input.ICommand> es <xref:System.Windows.Input.RoutedCommand>.  Si se establece la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> en un objeto <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es de tipo <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando.  
  
 El origen de comando puede establecer explícitamente el destino de comando.  Si el destino de comando no está definido, se utilizará como destino de comando el elemento que tenga el foco de teclado.  Una de las ventajas de utilizar el elemento con el foco de teclado como destino de comando es que permite al desarrollador de aplicaciones utilizar el mismo origen de comando para invocar un comando en varios destinos, sin tener que hacer un seguimiento del destino de comando.  Por ejemplo, si un objeto <xref:System.Windows.Controls.MenuItem> invoca el comando **Pegar** en una aplicación que tiene un control <xref:System.Windows.Controls.TextBox> y un control <xref:System.Windows.Controls.PasswordBox>, el destino puede ser el objeto <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.PasswordBox> según qué control tenga el foco de teclado.  
  
 En el ejemplo siguiente se muestra cómo establecer explícitamente el destino de comando en marcado y en código subyacente.  
  
 [!code-xml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>   
### CommandManager  
 El objeto <xref:System.Windows.Input.CommandManager> desempeña varias funciones relacionadas con comandos.  Proporciona un conjunto de métodos estáticos para agregar y quitar controladores de eventos <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> y <xref:System.Windows.Input.CommandManager.CanExecute> de un elemento concreto.  Proporciona un medio para registrar objetos <xref:System.Windows.Input.CommandBinding> y <xref:System.Windows.Input.InputBinding> en una clase concreta.  El objeto <xref:System.Windows.Input.CommandManager> también proporciona un medio, a través del evento <xref:System.Windows.Input.CommandManager.RequerySuggested>, para notificar a un comando cuándo debe provocar el evento <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  
  
 El método <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> fuerza al objeto <xref:System.Windows.Input.CommandManager> a provocar el evento <xref:System.Windows.Input.CommandManager.RequerySuggested>.  Esto es útil para condiciones que deban deshabilitar o habilitar un comando pero que no conozca el objeto <xref:System.Windows.Input.CommandManager>.  
  
<a name="Command_Library"></a>   
## Biblioteca de comandos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de comandos predefinidos.  La biblioteca de comandos está compuesta de las clases siguientes: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands>y <xref:System.Windows.Input.ComponentCommands>.  Estas clases proporcionan comandos como <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> y <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> y <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Muchos de estos comandos incluyen un conjunto de enlaces de entrada predeterminados.  Por ejemplo, si especifica que la aplicación administra el comando de copia, obtendrá automáticamente el enlace de teclado "CTRL \+ C". También obtendrá los enlaces para otros dispositivos de entrada, como los gestos de lápiz de [!INCLUDE[TLA2#tla_tpc](../../../../includes/tla2sharptla-tpc-md.md)] e información de voz.  
  
 Cuando haga referencia a comandos de las diversas bibliotecas de comandos utilizando [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], habitualmente podrá omitir el nombre de clase de la clase de biblioteca que exponga la propiedad de comando estática.  Generalmente, los nombres de comando son inequívocos como cadenas y los tipos propietarios existen para proporcionar una agrupación lógica de comandos, pero no son necesarios para la anulación de ambigüedades.  Por ejemplo, puede especificar `Command="Cut"` en lugar de `Command="ApplicationCommands.Cut"`, más detallado.  Éste es un mecanismo de conveniencia integrado en el procesador [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] para comandos \(más concretamente, es un comportamiento del convertidor de tipos de <xref:System.Windows.Input.ICommand>, al que el procesador de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia en el momento de la carga\).  
  
<a name="creating_commands"></a>   
## Crear comandos personalizados  
 Si los comandos de las clases de la biblioteca de comandos no satisfacen sus necesidades, puede crear comandos propios.  Hay dos formas de crear un comando personalizado.  La primera es empezar desde la nada e implementar la interfaz <xref:System.Windows.Input.ICommand>.  La otra manera, el enfoque más común consiste en crear un objeto <xref:System.Windows.Input.RoutedCommand> o <xref:System.Windows.Input.RoutedUICommand>.  
  
 Para obtener un ejemplo de la creación de un objeto <xref:System.Windows.Input.RoutedCommand> personalizado, vea [Ejemplo Create a Custom RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980).  
  
## Vea también  
 <xref:System.Windows.Input.RoutedCommand>   
 <xref:System.Windows.Input.CommandBinding>   
 <xref:System.Windows.Input.InputBinding>   
 <xref:System.Windows.Input.CommandManager>   
 [Información general sobre acciones del usuario](../../../../docs/framework/wpf/advanced/input-overview.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Implement ICommandSource \(ejemplo\)](../../../../docs/framework/wpf/advanced/how-to-implement-icommandsource.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/es-es/013d68a0-5373-4a68-bd91-5de574307370)   
 [Ejemplo Create a Custom RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980)