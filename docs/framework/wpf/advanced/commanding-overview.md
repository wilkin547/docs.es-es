---
title: Información general sobre comandos
description: Obtenga información sobre los comandos, un mecanismo de entrada en Windows Presentation Foundation que proporciona control de entrada en un nivel más semántico que la entrada de dispositivo.
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
ms.openlocfilehash: 4f7d12fbf0de9b1546f15061ab7eb1318378bbbb
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87168123"
---
# <a name="commanding-overview"></a>Información general sobre comandos
<a name="introduction"></a> Los comandos constituyen un mecanismo de entrada de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)], que permite el control de entrada en un nivel más semántico que la entrada del dispositivo. Algunos ejemplos de comandos son las operaciones **Copiar**, **Cortar** y **Pegar** presentes en numerosas aplicaciones.  
  
 Esta información general define los comandos que se encuentran en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], las clases que forman parte del modelo de comandos, y el procedimiento para usar y crear comandos en las aplicaciones.  
  
 Este tema contiene las siguientes secciones:  
  
- [¿Qué son los comandos?](#commands_at_10000_feet)  
  
- [Ejemplo de comando simple en WPF](#simple_command)  
  
- [Cuatro conceptos básicos de los comandos de WPF](#Four_main_Concepts)  
  
- [Biblioteca de comandos](#Command_Library)  
  
- [Creación de comandos personalizados](#creating_commands)  
  
<a name="commands_at_10000_feet"></a>
## <a name="what-are-commands"></a>¿Qué son los comandos?  
 Los comandos tienen varios propósitos. El primer propósito es separar la semántica y el objeto que invoca un comando de la lógica que ejecuta el comando. Esto permite que varios orígenes dispares invoquen la misma lógica de comando, así como personalizar la lógica de comando para distintos destinos. Por ejemplo, las operaciones de edición **Copiar**, **Cortar** y **Pegar**, que se encuentran en muchas aplicaciones, se pueden invocar mediante acciones de usuario diferentes si se implementan mediante comandos. Una aplicación podría permitir a un usuario cortar texto u objetos seleccionados mediante un clic en un botón, la selección de un elemento en un menú o una combinación de teclas, como CTRL+X. El uso de comandos permite enlazar cada tipo de acción del usuario a la misma lógica.  
  
 Otra finalidad de los comandos es indicar si una acción está disponible. Para continuar con el ejemplo del corte de un objeto o de texto, la acción solo tiene sentido si se selecciona algún elemento. Si un usuario intenta cortar un objeto o texto sin tener nada seleccionado, no ocurrirá nada. Para indicárselo al usuario, muchas aplicaciones deshabilitan los botones y elementos de menú para indicar si es posible realizar una acción. Un comando puede indicar si una acción es posible mediante la implementación del método <xref:System.Windows.Input.ICommand.CanExecute%2A>. Un botón se puede suscribir al evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> y se puede deshabilitar si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `false`, o bien habilitar si <xref:System.Windows.Input.ICommand.CanExecute%2A> devuelve `true`.  
  
 La semántica de un comando puede ser coherente entre aplicaciones y clases, pero la lógica de la acción es específica del objeto determinado sobre el que actúa. La combinación de teclas CTRL+X invoca el comando **Cortar** en clases de texto, clases de imagen y exploradores web, pero la lógica real para realizar la operación **Cortar** la define la aplicación que realiza el corte. Un <xref:System.Windows.Input.RoutedCommand> permite a los clientes implementar la lógica. Un objeto de texto puede cortar el texto seleccionado en el Portapapeles, mientras que un objeto de imagen puede cortar la imagen seleccionada. Cuando una aplicación controla el evento <xref:System.Windows.Input.CommandManager.Executed>, tiene acceso al destino del comando y puede emprender la acción adecuada según el tipo del destino.  
  
<a name="simple_command"></a>
## <a name="simple-command-example-in-wpf"></a>Ejemplo de comando simple en WPF  
 La manera más sencilla de usar un comando en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] es usar un objeto <xref:System.Windows.Input.RoutedCommand> predefinido de una de las clases de la biblioteca de comandos; use un control con compatibilidad nativa para controlar el comando y un control con compatibilidad nativa para invocar un comando.  El comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> es uno de los comandos predefinidos en la clase <xref:System.Windows.Input.ApplicationCommands>.  El control <xref:System.Windows.Controls.TextBox> incorpora lógica para controlar el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A>.  Y la clase <xref:System.Windows.Controls.MenuItem> ofrece compatibilidad nativa para invocar comandos.  
  
 En el ejemplo siguiente se muestra cómo configurar un <xref:System.Windows.Controls.MenuItem> para que cuando se hace clic en él invoque el comando <xref:System.Windows.Input.ApplicationCommands.Paste%2A> en <xref:System.Windows.Controls.TextBox>, suponiendo que <xref:System.Windows.Controls.TextBox> tenga el foco de teclado.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewSimpleCommand](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewsimplecommand)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Four_main_Concepts"></a>
## <a name="four-main-concepts-in-wpf-commanding"></a>Cuatro conceptos básicos de los comandos de WPF  
 El modelo de comando enrutado de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se puede dividir en cuatro conceptos básicos: el comando, el origen del comando, el destino del comando y el enlace del comando:  
  
- El *comando* es la acción que se va a ejecutar.  
  
- El *origen del comando* es el objeto que invoca el comando.  
  
- El *destino del comando* objeto en el que se ejecuta el comando.  
  
- El *enlace del comando* es el objeto que asigna la lógica del comando al comando.  
  
 En el ejemplo anterior, el comando es <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Controls.MenuItem> es el origen del comando, <xref:System.Windows.Controls.TextBox> es el destino del comando y el enlace de comando lo proporciona el control <xref:System.Windows.Controls.TextBox>.  Es importante destacar que <xref:System.Windows.Input.CommandBinding> no siempre lo proporciona el control que es la clase de destino del comando.  Con bastante frecuencia, el desarrollador de la aplicación debe crear <xref:System.Windows.Input.CommandBinding>, o es posible que <xref:System.Windows.Input.CommandBinding> se conecte a un antecesor del destino de comando.  
  
<a name="Commands"></a>
### <a name="commands"></a>Comandos  
 Los comandos de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se crean mediante la implementación de la interfaz <xref:System.Windows.Input.ICommand>.  <xref:System.Windows.Input.ICommand> expone dos métodos (<xref:System.Windows.Input.ICommand.Execute%2A> y <xref:System.Windows.Input.ICommand.CanExecute%2A>) y un evento (<xref:System.Windows.Input.ICommand.CanExecuteChanged>). <xref:System.Windows.Input.ICommand.Execute%2A> realiza las acciones que están asociadas con el comando. <xref:System.Windows.Input.ICommand.CanExecute%2A> determina si el comando se puede ejecutar en el destino del comando actual. <xref:System.Windows.Input.ICommand.CanExecuteChanged> se genera si el administrador de comandos que centraliza las operaciones de comandos detecta un cambio en el origen del comando que podría invalidar un comando que se ha generado, pero que el enlace del comando todavía no ha ejecutado.  La implementación de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de <xref:System.Windows.Input.ICommand> es la clase <xref:System.Windows.Input.RoutedCommand> y es el foco de esta introducción.  
  
 Los orígenes principales de la entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son el mouse, el teclado, el lápiz y los comandos enrutados.  Las entradas más orientadas al dispositivo usan un <xref:System.Windows.RoutedEvent> para notificar a los objetos de una página de la aplicación que se produjo un evento de entrada.  Un <xref:System.Windows.Input.RoutedCommand> no es diferente.  Los métodos <xref:System.Windows.Input.RoutedCommand.Execute%2A> y <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> de un <xref:System.Windows.Input.RoutedCommand> no contienen la lógica de aplicación para el comando, sino que en su lugar generan eventos enrutados que se canalizan y propagan a través del árbol de elementos hasta que encuentran un objeto con un <xref:System.Windows.Input.CommandBinding>.  El <xref:System.Windows.Input.CommandBinding> contiene los controladores para estos eventos, que son los que ejecutan el comando.  Para obtener más información sobre el enrutamiento de eventos en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], consulte [Información general sobre eventos enrutados](routed-events-overview.md).  
  
 El método <xref:System.Windows.Input.RoutedCommand.Execute%2A> de un <xref:System.Windows.Input.RoutedCommand> genera los eventos <xref:System.Windows.Input.CommandManager.PreviewExecuted> y <xref:System.Windows.Input.CommandManager.Executed> en el destino del comando.  El método <xref:System.Windows.Input.RoutedCommand.CanExecute%2A> de un <xref:System.Windows.Input.RoutedCommand> genera los eventos <xref:System.Windows.Input.CommandManager.CanExecute> y <xref:System.Windows.Input.CommandManager.PreviewCanExecute> en el destino del comando.  Estos eventos se tunelizan y propagan a través del árbol de elementos hasta que encuentran un objeto que tiene un <xref:System.Windows.Input.CommandBinding> para ese comando concreto.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de comandos enrutados comunes distribuido entre varias clases: <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.ComponentCommands> y <xref:System.Windows.Documents.EditingCommands>.  Estas clases solo constan de los objetos <xref:System.Windows.Input.RoutedCommand> y no de la lógica de implementación del comando.  La lógica de implementación es responsabilidad del objeto en el que se ejecuta el comando.  
  
<a name="Command_Sources"></a>
### <a name="command-sources"></a>Orígenes del comando  
 El origen del comando es el objeto que invoca el comando.  Ejemplos de orígenes de comando son <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.Button> y <xref:System.Windows.Input.KeyGesture>.  
  
 Por lo general, los orígenes de comando de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] implementan la interfaz <xref:System.Windows.Input.ICommandSource>.  
  
 <xref:System.Windows.Input.ICommandSource> expone tres propiedades: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> y <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>:  
  
- <xref:System.Windows.Input.ICommandSource.Command%2A> es el comando que se va a ejecutar cuando se invoque el origen del comando.  
  
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> es el objeto en el que se va a ejecutar el comando.  Merece la pena mencionar que en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> de <xref:System.Windows.Input.ICommandSource> solo es aplicable cuando <xref:System.Windows.Input.ICommand> es <xref:System.Windows.Input.RoutedCommand>.  Si <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> se establece en un <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es un <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando. Si no se establece <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>, el elemento con el foco de teclado será el destino del comando.  
  
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> es un tipo de datos definido por el usuario que se usa para pasar información a los controladores que implementan el comando.  
  
 Las clases de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que implementan <xref:System.Windows.Input.ICommandSource> son <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Documents.Hyperlink> y <xref:System.Windows.Input.InputBinding>.  <xref:System.Windows.Controls.Primitives.ButtonBase>, <xref:System.Windows.Controls.MenuItem> y <xref:System.Windows.Documents.Hyperlink> invocan un comando cuando se hace clic en ellas, y <xref:System.Windows.Input.InputBinding> invoca un comando cuando se ejecuta el <xref:System.Windows.Input.InputGesture> que tiene asociado.  
  
 En el ejemplo siguiente se muestra cómo usar un <xref:System.Windows.Controls.MenuItem> en un <xref:System.Windows.Controls.ContextMenu> como origen de comando para el comando <xref:System.Windows.Input.ApplicationCommands.Properties%2A>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewCmdSourceXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewcmdsourcexaml)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcmdsource)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCmdSource](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcmdsource)]  
  
 Normalmente, un origen de comando escuchará el evento <xref:System.Windows.Input.RoutedCommand.CanExecuteChanged>.  Este evento informa al origen del comando de un posible cambio en la capacidad del comando para ejecutarse en el destino del comando actual.  El origen del comando puede consultar el estado actual de <xref:System.Windows.Input.RoutedCommand> mediante el método <xref:System.Windows.Input.RoutedCommand.CanExecute%2A>.  A continuación, el origen del comando puede deshabilitarse automáticamente si no se puede ejecutar el comando.  Un ejemplo de esto es un <xref:System.Windows.Controls.MenuItem> que se atenúa automáticamente cuando no se puede ejecutar un comando.  
  
 Se puede usar un <xref:System.Windows.Input.InputGesture> como un origen de comando.  Dos tipos de gestos de entrada en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] son <xref:System.Windows.Input.KeyGesture> y <xref:System.Windows.Input.MouseGesture>.  Se puede considerar un <xref:System.Windows.Input.KeyGesture> como un método abreviado de teclado, como CTRL+C.  Un <xref:System.Windows.Input.KeyGesture> está formado por una <xref:System.Windows.Input.Key> y un conjunto de <xref:System.Windows.Input.ModifierKeys>.  Un <xref:System.Windows.Input.MouseGesture> está formado por una <xref:System.Windows.Input.MouseAction> y un conjunto opcional de <xref:System.Windows.Input.ModifierKeys>.  
  
 Para que un <xref:System.Windows.Input.InputGesture> actúe como un origen del comando, debe estar asociado con un comando. Existen dos maneras de lograrlo.  Una manera consiste en usar un <xref:System.Windows.Input.InputBinding>.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Input.KeyBinding> entre un <xref:System.Windows.Input.KeyGesture> y un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlkeybinding)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeybinding)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyBinding](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeybinding)]  
  
 Otra manera de asociar un <xref:System.Windows.Input.InputGesture> a un <xref:System.Windows.Input.RoutedCommand> consiste en agregar el <xref:System.Windows.Input.InputGesture> a la <xref:System.Windows.Input.InputGestureCollection> en el <xref:System.Windows.Input.RoutedCommand>.  
  
 En el ejemplo siguiente se muestra cómo agregar un <xref:System.Windows.Input.KeyGesture> a la <xref:System.Windows.Input.InputGestureCollection> de un <xref:System.Windows.Input.RoutedCommand>.  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewkeygestureoncmd)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewKeyGestureOnCmd](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewkeygestureoncmd)]  
  
<a name="Command_Binding"></a>
### <a name="commandbinding"></a>CommandBinding  
 Un <xref:System.Windows.Input.CommandBinding> asocia un comando a los controladores de eventos que implementan el comando.  
  
 La clase <xref:System.Windows.Input.CommandBinding> contiene una propiedad <xref:System.Windows.Input.CommandBinding.Command%2A> y los eventos <xref:System.Windows.Input.CommandBinding.PreviewExecuted>, <xref:System.Windows.Input.CommandBinding.Executed>, <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> y <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 <xref:System.Windows.Input.CommandBinding.Command%2A> es el comando con el que se asocia <xref:System.Windows.Input.CommandBinding>.  Los controladores de eventos que están conectados a los eventos <xref:System.Windows.Input.CommandBinding.PreviewExecuted> y <xref:System.Windows.Input.CommandBinding.Executed> implementan la lógica de comando.  Los controladores de eventos conectados a los eventos <xref:System.Windows.Input.CommandBinding.PreviewCanExecute> y <xref:System.Windows.Input.CommandBinding.CanExecute> determinan si el comando se puede ejecutar en el destino del comando actual.  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Input.CommandBinding> en la <xref:System.Windows.Window> raíz de una aplicación.  El <xref:System.Windows.Input.CommandBinding> asocia el comando <xref:System.Windows.Input.ApplicationCommands.Open%2A> con los controladores <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandBinding.CanExecute>.  
  
 [!code-xaml[commandwithhandler#CommandHandlerCommandBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml#commandhandlercommandbinding)]  
  
 [!code-csharp[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandHandlerProcedural/CSharp/Window1.xaml.cs#commandhandlerbindinginit)]
 [!code-vb[CommandHandlerProcedural#CommandHandlerBindingInit](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandHandlerProcedural/visualbasic/window1.xaml.vb#commandhandlerbindinginit)]  
  
 Después, se crean <xref:System.Windows.Input.ExecutedRoutedEventHandler> y <xref:System.Windows.Input.CanExecuteRoutedEventHandler>.  <xref:System.Windows.Input.ExecutedRoutedEventHandler> abre un <xref:System.Windows.MessageBox> que muestra una cadena en la que se indica que se ha ejecutado el comando.  <xref:System.Windows.Input.CanExecuteRoutedEventHandler> establece la propiedad <xref:System.Windows.Input.CanExecuteRoutedEventArgs.CanExecute%2A> en `true`.  
  
 [!code-csharp[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlerexecutedhandler)]
 [!code-vb[commandwithhandler#CommandHandlerExecutedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlerexecutedhandler)]  
  
 [!code-csharp[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/commandWithHandler/CSharp/Window1.xaml.cs#commandhandlercanexecutehandler)]
 [!code-vb[commandwithhandler#CommandHandlerCanExecuteHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/commandWithHandler/VisualBasic/Window1.xaml.vb#commandhandlercanexecutehandler)]  
  
 A <xref:System.Windows.Input.CommandBinding> se adjunta a un objeto específico, como el elemento <xref:System.Windows.Window> raíz de la aplicación o un control.  El objeto al que se adjunta <xref:System.Windows.Input.CommandBinding> define el ámbito del enlace.  Por ejemplo, el evento <xref:System.Windows.Input.CommandBinding.Executed> puede alcanzar un <xref:System.Windows.Input.CommandBinding> conectado a un antecesor del destino de comando, pero un <xref:System.Windows.Input.CommandBinding> conectado a un descendiente del destino de comando no se puede alcanzar.  Esta es una consecuencia directa de la manera en que un evento <xref:System.Windows.RoutedEvent> se tuneliza y propaga desde el objeto que genera el evento.  
  
 En algunas situaciones <xref:System.Windows.Input.CommandBinding> se adjunta al propio destino del comando, como sucede con la clase <xref:System.Windows.Controls.TextBox> y los comandos <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A> y <xref:System.Windows.Input.ApplicationCommands.Paste%2A>. Pero a menudo resulta más conveniente adjuntar <xref:System.Windows.Input.CommandBinding> a un antecesor del destino del comando, como la <xref:System.Windows.Window> principal o el objeto de aplicación, especialmente si se puede usar el mismo <xref:System.Windows.Input.CommandBinding> para varios destinos del comando.  Estas son las decisiones de diseño que querrá tener en cuenta al crear la infraestructura de comandos.  
  
<a name="Commane_Target"></a>
### <a name="command-target"></a>Destino del comando  
 El destino del comando es el elemento en el que se ejecuta el comando.  En lo que se refiere a un <xref:System.Windows.Input.RoutedCommand>, el destino del comando es el elemento en el que se inicia el enrutamiento de <xref:System.Windows.Input.CommandManager.Executed> y <xref:System.Windows.Input.CommandManager.CanExecute>.  Como se mencionó anteriormente, en [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], la propiedad <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> de <xref:System.Windows.Input.ICommandSource> solo es aplicable cuando <xref:System.Windows.Input.ICommand> es <xref:System.Windows.Input.RoutedCommand>.  Si <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> se establece en un <xref:System.Windows.Input.ICommandSource> y el comando correspondiente no es un <xref:System.Windows.Input.RoutedCommand>, se omite el destino del comando.  
  
 El origen del comando puede establecer de manera explícita el destino del comando.  Si no se define el destino del comando, el elemento con el foco del teclado se usará como el destino del comando.  Una de las ventajas de usar el elemento con el foco del teclado como el destino del comando es que permite al desarrollador de la aplicación usar el mismo origen del comando para invocar un comando en varios destinos sin necesidad de realizar un seguimiento del destino del comando.  Por ejemplo, si un <xref:System.Windows.Controls.MenuItem> invoca el comando **Pegar** en una aplicación que tiene un control <xref:System.Windows.Controls.TextBox> y otro control <xref:System.Windows.Controls.PasswordBox>, el destino puede ser <xref:System.Windows.Controls.TextBox> o <xref:System.Windows.Controls.PasswordBox>, en función del control que tenga el foco de teclado.  
  
 En el ejemplo siguiente se muestra cómo establecer de forma explícita el destino del comando en el marcado y en el código subyacente.  
  
 [!code-xaml[CommandingOverviewSnippets#CommandingOverviewXAMLCommandTarget](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml#commandingoverviewxamlcommandtarget)]  
  
 [!code-csharp[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#commandingoverviewcommandtargetcodebehind)]
 [!code-vb[CommandingOverviewSnippets#CommandingOverviewCommandTargetCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#commandingoverviewcommandtargetcodebehind)]  
  
<a name="Command_Manager"></a>
### <a name="the-commandmanager"></a>CommandManager  
 <xref:System.Windows.Input.CommandManager> proporciona una serie de funciones relacionadas con los comandos.  Proporciona un conjunto de métodos estáticos para agregar y quitar los controladores de eventos <xref:System.Windows.Input.CommandManager.PreviewExecuted>, <xref:System.Windows.Input.CommandManager.Executed>, <xref:System.Windows.Input.CommandManager.PreviewCanExecute> y <xref:System.Windows.Input.CommandManager.CanExecute> a y desde un elemento específico.  Proporciona un medio para registrar objetos <xref:System.Windows.Input.CommandBinding> y <xref:System.Windows.Input.InputBinding> en una clase específica.  <xref:System.Windows.Input.CommandManager> también proporciona un medio, a través del evento <xref:System.Windows.Input.CommandManager.RequerySuggested>, para notificar a un comando cuándo debe generar el evento <xref:System.Windows.Input.ICommand.CanExecuteChanged>.  
  
 El método <xref:System.Windows.Input.CommandManager.InvalidateRequerySuggested%2A> fuerza a <xref:System.Windows.Input.CommandManager> a generar el evento <xref:System.Windows.Input.CommandManager.RequerySuggested>.  Esto es útil para las condiciones que deben deshabilitar o habilitar un comando, pero de las que <xref:System.Windows.Input.CommandManager> no es consciente.  
  
<a name="Command_Library"></a>
## <a name="command-library"></a>Biblioteca de comandos  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona un conjunto de comandos predefinidos.  La biblioteca de comandos se compone de las clases siguientes: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, <xref:System.Windows.Documents.EditingCommands> y <xref:System.Windows.Input.ComponentCommands>.  Estas clases proporcionan comandos como <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.NavigationCommands.BrowseBack%2A> y <xref:System.Windows.Input.NavigationCommands.BrowseForward%2A>, <xref:System.Windows.Input.MediaCommands.Play%2A>, <xref:System.Windows.Input.MediaCommands.Stop%2A> y <xref:System.Windows.Input.MediaCommands.Pause%2A>.  
  
 Muchos de estos comandos incluyen un conjunto de enlaces de entrada predeterminados.  Por ejemplo, si especifica que la aplicación controle el comando Copiar, obtendrá automáticamente el enlace de teclado "CTRL + C" también obtiene enlaces para otros dispositivos de entrada, como la información de voz y los gestos del lápiz de Tablet PC.  
  
 Al hacer referencia a los comandos de las diversas bibliotecas de comandos mediante [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], normalmente puede omitir el nombre de clase de la clase de biblioteca que expone la propiedad de comando estática. En general, los nombres de comando son inequívocos como cadenas y los tipos propietarios existen para proporcionar una agrupación lógica de comandos, pero no son necesarios para la desambiguación. Por ejemplo, puede especificar `Command="Cut"` en lugar del comando `Command="ApplicationCommands.Cut"` más detallado. Se trata de un mecanismo de comodidad que se integra en el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador para los comandos (más concretamente, es un comportamiento del convertidor de tipos de <xref:System.Windows.Input.ICommand> , que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] hace referencia al procesador en el momento de la carga).  
  
<a name="creating_commands"></a>
## <a name="creating-custom-commands"></a>Creación de comandos personalizados  
 Si los comandos de las clases de la biblioteca de comandos no satisfacen sus necesidades, puede crear sus propios comandos.  Existen dos maneras de crear un comando personalizado.  La primera es empezar desde cero e implementar la interfaz <xref:System.Windows.Input.ICommand>.  La otra forma, y el enfoque más común, consiste en crear un comando <xref:System.Windows.Input.RoutedCommand> o <xref:System.Windows.Input.RoutedUICommand>.  
  
 Para obtener un ejemplo de cómo crear un <xref:System.Windows.Input.RoutedCommand> personalizado, vea [Create a Custom RoutedCommand Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand) (Crear un ejemplo de RoutedCommand personalizado).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Input.RoutedCommand>
- <xref:System.Windows.Input.CommandBinding>
- <xref:System.Windows.Input.InputBinding>
- <xref:System.Windows.Input.CommandManager>
- [Información general sobre acciones del usuario](input-overview.md)
- [Información general sobre eventos enrutados](routed-events-overview.md)
- [Implementar ICommandSource](how-to-implement-icommandsource.md)
- [Cómo: Agregar un comando a un elemento de menú](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))
- [Crear un objeto RoutedCommand de muestra personalizado](https://github.com/Microsoft/WPF-Samples/tree/master/Input%20and%20Commands/CustomRoutedCommand)
