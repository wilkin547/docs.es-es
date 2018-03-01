---
title: "Cómo: Implementar ICommandSource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d82a211f59fbdecdc932b7e57b242274e91cd5b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-icommandsource"></a>Cómo: Implementar ICommandSource
Este ejemplo muestra cómo crear un origen de comando implementando <xref:System.Windows.Input.ICommandSource>.  Un origen de comando es un objeto que sabe cómo invocar un comando.  El <xref:System.Windows.Input.ICommandSource> interfaz expone tres miembros: <xref:System.Windows.Input.ICommandSource.Command%2A>, <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>, y <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>.  <xref:System.Windows.Input.ICommandSource.Command%2A>es el comando que se invocará. El <xref:System.Windows.Input.ICommandSource.CommandParameter%2A> es un tipo de datos definido por el usuario que se pasa desde el origen del comando al método que controla el comando. El <xref:System.Windows.Input.ICommandSource.CommandTarget%2A> es el objeto que se ejecuta en el comando.  
  
 En este ejemplo, se crea una clase que las subclases el <xref:System.Windows.Controls.Slider> control e implementa <xref:System.Windows.Input.ICommandSource>.  
  
## <a name="example"></a>Ejemplo  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]Proporciona una serie de clases que implementan <xref:System.Windows.Input.ICommandSource>, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>, y <xref:System.Windows.Controls.ListBoxItem>.  Un origen de comando define cómo invoca un comando.   <xref:System.Windows.Controls.Button>y <xref:System.Windows.Controls.MenuItem> invocar un comando cuando se hace clic en.  A <xref:System.Windows.Controls.ListBoxItem> cuando hace doble clic, se invoca un comando. Estas clases solo se convierten en un comando de origen cuando sus <xref:System.Windows.Input.ICommandSource.Command%2A> se establece la propiedad.  
  
 En este ejemplo se invoca el comando cuando se mueve el control deslizante, o más concretamente, cuando el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> se cambia la propiedad.  
  
 La siguiente es la definición de clase.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]  
  
 El paso siguiente consiste en implementar el <xref:System.Windows.Input.ICommandSource> miembros.  En este ejemplo, las propiedades se implementan como <xref:System.Windows.DependencyProperty> objetos.  Esto permite que las propiedades utilizar el enlace de datos.  Para obtener más información sobre la <xref:System.Windows.DependencyProperty> de clases, consulte la [información general sobre propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md).  Para obtener más información sobre el enlace de datos, vea el [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Solo el <xref:System.Windows.Input.ICommandSource.Command%2A> propiedad se muestra aquí.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
 Éste es el <xref:System.Windows.DependencyProperty> cambiar la devolución de llamada.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]  
  
 El siguiente paso es agregar y quitar el comando que está asociado con el origen del comando.  El <xref:System.Windows.Input.ICommandSource.Command%2A> propiedad no se puede simplemente se sobrescribe cuando se agrega un nuevo comando, porque los controladores de eventos asociados con el comando anterior, si hubiera, primero hay que quitar.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
 [!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]  
  
 El último paso consiste en crear la lógica de la <xref:System.Windows.Input.ICommand.CanExecuteChanged> controlador y el <xref:System.Windows.Input.ICommand.Execute%2A> método.  
  
 El <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento le notifica el origen del comando que puede haber cambiado la capacidad del comando para ejecutar en el destino del comando actual.  Cuando un origen de comando recibe este evento, normalmente llama el <xref:System.Windows.Input.ICommand.CanExecute%2A> método en el comando.  Si el comando no se puede ejecutar en el destino del comando actual, el origen del comando normalmente se deshabilitará.  Si el comando puede ejecutarse en el destino del comando actual, el origen del comando habilitará normalmente sí.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
 [!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]  
  
 El último paso es la <xref:System.Windows.Input.ICommand.Execute%2A> método.  Si el comando es un <xref:System.Windows.Input.RoutedCommand>, <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> método es llamado; de lo contrario, el <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> se llama al método.  
  
 [!code-csharp[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
 [!code-vb[ImplementICommandSource#ImplementICommandExecute](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Input.ICommandSource>  
 <xref:System.Windows.Input.ICommand>  
 <xref:System.Windows.Input.RoutedCommand>  
 [Información general sobre comandos](../../../../docs/framework/wpf/advanced/commanding-overview.md)
