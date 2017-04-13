---
title: "C&#243;mo: Enlazar un comando a un control con la compatibilidad de comandos | Microsoft Docs"
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
  - "Clase de control, asociar RoutedCommand"
  - "clases, Control, asociar RoutedCommand"
  - "RoutedCommand (clase), asociar a un Control"
  - "clases, RoutedCommand, asociar a un Control"
ms.assetid: 8d8592ae-0c91-469e-a1cd-d179c4544548
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Enlazar un comando a un control con la compatibilidad de comandos
En el ejemplo siguiente se muestra cómo enlazar un <xref:System.Windows.Input.RoutedCommand> a una <xref:System.Windows.Controls.Control> que tiene compatibilidad integrada para el comando.  Para obtener un ejemplo completo que enlaza comandos a varios orígenes, vea el [ejemplo Create a Custom RoutedCommand](http://go.microsoft.com/fwlink/?LinkID=159980) ejemplo.  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]Proporciona una biblioteca de comandos comunes que los programadores de aplicaciones se encuentren con regularidad.  Las clases que componen la biblioteca de comandos son: <xref:System.Windows.Input.ApplicationCommands>, <xref:System.Windows.Input.ComponentCommands>, <xref:System.Windows.Input.NavigationCommands>, <xref:System.Windows.Input.MediaCommands>, y <xref:System.Windows.Documents.EditingCommands>.  
  
 Estático <xref:System.Windows.Input.RoutedCommand> objetos que componen estas clases no proporcionan la lógica de comandos.  La lógica para el comando está asociada con el comando con un <xref:System.Windows.Input.CommandBinding>.  Algunos controles tienen integrada CommandBindings para algunos comandos.  Este mecanismo permite que la semántica de un comando permanezca igual, mientras que la implementación real puede cambiar.  Un <xref:System.Windows.Controls.TextBox>, por ejemplo, controla el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando diferente de un control diseñado para admitir imágenes, pero la idea básica del significado de pegar algo permanece igual.  La lógica de comando no puede proporcionar el comando, pero debe proporcionarla el control o la aplicación.  
  
 Muchos controles de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tienen compatibilidad integrada para algunos de los comandos de la biblioteca de comandos.  <xref:System.Windows.Controls.TextBox>, por ejemplo, admite muchos de los comandos de edición de la aplicación como <xref:System.Windows.Input.ApplicationCommands.Paste%2A>, <xref:System.Windows.Input.ApplicationCommands.Copy%2A>, <xref:System.Windows.Input.ApplicationCommands.Cut%2A>, <xref:System.Windows.Input.ApplicationCommands.Redo%2A>, y <xref:System.Windows.Input.ApplicationCommands.Undo%2A>.  El desarrollador de aplicaciones no tiene que hacer nada especial para obtener estos comandos para trabajar con estos controles.  Si el <xref:System.Windows.Controls.TextBox> es el destino del comando cuando se ejecuta el comando, administrará el comando mediante el <xref:System.Windows.Input.CommandBinding> que está integrado en el control.  
  
 La siguiente muestra cómo utilizar un <xref:System.Windows.Controls.MenuItem> como origen de comando para la <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando, donde un <xref:System.Windows.Controls.TextBox> es el destino del comando.  Toda la lógica que define cómo el <xref:System.Windows.Controls.TextBox> realiza el pegado está integrado en el <xref:System.Windows.Controls.TextBox> control.  
  
 Un <xref:System.Windows.Controls.MenuItem> se crea y es <xref:System.Windows.Controls.MenuItem.Command%2A> propiedad se establece en el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando.  El <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece explícitamente en el <xref:System.Windows.Controls.TextBox> objeto.  Cuando el <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> no se establece, el destino para el comando es el elemento que tiene el foco de teclado.  Si el elemento que tiene el foco de teclado no admite el <xref:System.Windows.Input.ApplicationCommands.Paste%2A> comando o actualmente no se puede ejecutar el comando Pegar (el Portapapeles está vacío, por ejemplo), el <xref:System.Windows.Controls.MenuItem> estará deshabilitado.  
  
 [!code-xml[MenuItemCommandTask_XAML#MenuItemCommanding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask_XAML/CS/Window1.xaml#menuitemcommanding)]  
  
 [!code-csharp[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandTask/CSharp/Window1.xaml.cs#menuitemcommandingcodebehind)]
 [!code-vb[MenuItemCommandTask#MenuItemCommandingCodeBehind](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandTask/VisualBasic/Window1.xaml.vb#menuitemcommandingcodebehind)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [Enlazar un comando a un Control sin soporte de comando](../../../../docs/framework/wpf/advanced/how-to-hook-up-a-command-to-a-control-with-no-command-support.md)