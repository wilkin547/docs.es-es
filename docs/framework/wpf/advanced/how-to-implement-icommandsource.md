---
title: 'Cómo: Implementar ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 6c18e0b77ec53d9bd3e7ce610f2940effe603c88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174698"
---
# <a name="how-to-implement-icommandsource"></a>Cómo: Implementar ICommandSource

En este ejemplo se muestra cómo <xref:System.Windows.Input.ICommandSource>crear un origen de comandos implementando . Un origen de comandos es un objeto que sabe cómo invocar un comando. La <xref:System.Windows.Input.ICommandSource> interfaz expone tres miembros:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: el comando que se invocará.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: un tipo de datos definido por el usuario que se pasa desde el origen del comando al método que controla el comando.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: el objeto en el que se ejecuta el comando.

En este ejemplo, se crea una <xref:System.Windows.Controls.Slider> clase que hereda del control e implementa la <xref:System.Windows.Input.ICommandSource> interfaz.
  
## <a name="example"></a>Ejemplo

WPFWPF proporciona varias clases <xref:System.Windows.Input.ICommandSource>que <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.MenuItem>implementan <xref:System.Windows.Documents.Hyperlink>, como , , y . Un origen de comandos define cómo invoca un comando. Estas clases invocan un comando cuando se hace clic <xref:System.Windows.Input.ICommandSource.Command%2A> en ellas y solo se convierten en un origen de comandos cuando se establece su propiedad.

En este ejemplo, invocará el comando cuando se mueva el <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> control deslizante, o más exactamente, cuando se cambie la propiedad.

La siguiente es la definición de clase:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

El siguiente paso es <xref:System.Windows.Input.ICommandSource> implementar los miembros. En este ejemplo, las propiedades <xref:System.Windows.DependencyProperty> se implementan como objetos. Esto permite que las propiedades usen el enlace de datos. Para obtener más <xref:System.Windows.DependencyProperty> información acerca de la clase, vea [Información general](dependency-properties-overview.md)sobre propiedades de dependencia . Para obtener más información sobre el enlace de datos, vea [Información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos .

Aquí <xref:System.Windows.Input.ICommandSource.Command%2A> solo se muestra la propiedad.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
A continuación <xref:System.Windows.DependencyProperty> se muestra la devolución de llamada de cambio:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

El siguiente paso es agregar y quitar el comando que está asociado con el origen del comando. La <xref:System.Windows.Input.ICommandSource.Command%2A> propiedad no se puede sobrescribir simplemente cuando se agrega un nuevo comando, porque los controladores de eventos asociados con el comando anterior, si lo hubo, deben quitarse primero.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

El siguiente paso es crear <xref:System.Windows.Input.ICommand.CanExecuteChanged> lógica para el controlador.

El <xref:System.Windows.Input.ICommand.CanExecuteChanged> evento notifica al origen del comando que la capacidad del comando para ejecutarse en el destino del comando actual puede haber cambiado. Cuando un origen de comandos recibe este <xref:System.Windows.Input.ICommand.CanExecute%2A> evento, normalmente llama al método en el comando. Si el comando no se puede ejecutar en el destino del comando actual, el origen del comando normalmente se deshabilitará a sí mismo. Si el comando se puede ejecutar en el destino del comando actual, el origen del comando normalmente se habilitará a sí mismo.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

El último paso <xref:System.Windows.Input.ICommand.Execute%2A> es el método. Si el comando <xref:System.Windows.Input.RoutedCommand>es <xref:System.Windows.Input.RoutedCommand> <xref:System.Windows.Input.RoutedCommand.Execute%2A> un , se llama al método; de lo <xref:System.Windows.Input.ICommand> <xref:System.Windows.Input.ICommand.Execute%2A> contrario, se llama al método.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Información general sobre comandos](commanding-overview.md)
