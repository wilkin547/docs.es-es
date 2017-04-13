---
title: "C&#243;mo: Implementar ICommandSource | Microsoft Docs"
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
  - "interfaces de ICommandSource, implementar"
  - "interfaces, ICommandSource, implementar"
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Implementar ICommandSource
En este ejemplo se muestra cómo crear un origen de comando implementando <xref:System.Windows.Input.ICommandSource>.  Un origen de comando es un objeto que sabe cómo invocar un comando.  La interfaz <xref:System.Windows.Input.ICommandSource> expone tres miembros: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> y <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A> es el comando que se invocará.  <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> es un tipo de datos definido por el usuario que se pasa desde el origen de comando al método que administra el comando.  <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> es el objeto en que se ejecuta el comando.  
  
 En este ejemplo, se crea una clase que crea una subclase del control <xref:System.Windows.Controls.Slider> e implementa <xref:System.Windows.Input.ICommandSource>.  
  
## Ejemplo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proporciona varias clases que implementan <xref:System.Windows.Input.ICommandSource>, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem> y <xref:System.Windows.Controls.ListBoxItem>.  El origen de comando define cómo invoca un comando.  Los objetos <xref:System.Windows.Controls.Button> y <xref:System.Windows.Controls.MenuItem> invocan un comando cuando se hace clic en ellos.  Un objeto <xref:System.Windows.Controls.ListBoxItem> invoca un comando cuando se hacer doble clic en él.  Estas clases sólo se convierten en el origen de un comando cuando se establece su propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 En este ejemplo se invoca al comando cuando se mueve el control deslizante, o dicho con más exactitud, cuando se cambia la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.  
  
 A continuación, se muestra la definición de clase.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 El paso siguiente es implementar los miembros de <xref:System.Windows.Input.ICommandSource>.  En este ejemplo, las propiedades se implementan como objetos <xref:System.Windows.DependencyProperty>.  Esto permite que las propiedades utilicen el enlace de datos.  Para obtener más información sobre la clase <xref:System.Windows.DependencyProperty>, vea [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para obtener más información sobre el enlace a datos, vea [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Aquí se muestra únicamente la propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Lo siguiente es la devolución de llamada de cambio de <xref:System.Windows.DependencyProperty>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 El paso siguiente consiste en agregar y quitar el comando que está asociado al origen de comando.  No se puede sobrescribir simplemente la propiedad <xref:System.Windows.Input.ICommandSource.Command%2A> cuando se agrega un nuevo comando, porque antes se deben quitar los controladores de eventos asociados al comando anterior, si lo hay.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 El último paso consiste en crear la lógica para el controlador de <xref:System.Windows.Input.ICommand.CanExecuteChanged> y el método <xref:System.Windows.Input.ICommand.Execute%2A>.  
  
 El evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica al origen de comando que es posible que haya cambiado la capacidad del comando para ejecutarse en el destino de comando actual.  Cuando un origen de comando recibe este evento, normalmente llama al método <xref:System.Windows.Input.ICommand.CanExecute%2A> del comando.  Si el comando no se puede ejecutar en el destino de comando actual, el origen de comando se suele deshabilitar.  Si el comando sí se puede ejecutar en el destino de comando actual, el origen de comando se suele habilitar.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 El último paso es el método <xref:System.Windows.Input.ICommand.Execute%2A>.  Si el comando es <xref:System.Windows.Input.RoutedCommand>, se llama al método <xref:System.Windows.Input.RoutedCommand.Execute%2A> de <xref:System.Windows.Input.RoutedCommand>; de lo contrario, se llama al método <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A>.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## Vea también  
 <xref:System.Windows.Input.ICommandSource>   
 <xref:System.Windows.Input.ICommand>   
 <xref:System.Windows.Input.RoutedCommand>   
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)