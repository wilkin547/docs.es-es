---
title: 'Cómo: Implementar ICommandSource'
ms.date: 12/05/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ICommandSource interfaces [WPF], implementing
ms.assetid: 7452dd39-6e11-44bf-806a-31d87f3772ac
ms.openlocfilehash: 755377d25a2deb48aa9da86d4182075e30763530
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345099"
---
# <a name="how-to-implement-icommandsource"></a>Cómo: Implementar ICommandSource

En este ejemplo se muestra cómo crear un origen de comando implementando <xref:System.Windows.Input.ICommandSource>. Un origen de comando es un objeto que sabe cómo invocar un comando. La interfaz <xref:System.Windows.Input.ICommandSource> expone tres miembros:

- <xref:System.Windows.Input.ICommandSource.Command%2A>: el comando que se invocará.
- <xref:System.Windows.Input.ICommandSource.CommandParameter%2A>: tipo de datos definido por el usuario que se pasa desde el origen del comando al método que controla el comando.
- <xref:System.Windows.Input.ICommandSource.CommandTarget%2A>: el objeto en el que se ejecuta el comando.

En este ejemplo, se crea una clase que hereda del control <xref:System.Windows.Controls.Slider> e implementa la interfaz <xref:System.Windows.Input.ICommandSource>.
  
## <a name="example"></a>Ejemplo

WPF proporciona una serie de clases que implementan <xref:System.Windows.Input.ICommandSource>, como <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.MenuItem>y <xref:System.Windows.Documents.Hyperlink>. Un origen de comando define cómo invoca un comando. Estas clases invocan un comando cuando se hace clic en él y solo se convierten en un origen de comando cuando se establece su propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.

En este ejemplo, invocará el comando cuando se mueva el control deslizante, o con más precisión, cuando cambie la propiedad <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A>.

A continuación se encuentra la definición de clase:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourceclassdefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceClassDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourceclassdefinition)]

El siguiente paso es implementar el <xref:System.Windows.Input.ICommandSource> miembros. En este ejemplo, las propiedades se implementan como objetos <xref:System.Windows.DependencyProperty>. Esto permite que las propiedades utilicen el enlace de datos. Para obtener más información sobre la clase <xref:System.Windows.DependencyProperty>, consulte la [información general sobre las propiedades de dependencia](dependency-properties-overview.md). Para obtener más información sobre el enlace de datos, vea [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.

Aquí solo se muestra la propiedad <xref:System.Windows.Input.ICommandSource.Command%2A>.
 
[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandpropertydefinition)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandPropertyDefinition](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandpropertydefinition)]  
  
A continuación se indican las devoluciones de llamada de <xref:System.Windows.DependencyProperty> cambio:

[!code-csharp[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcecommandchanged)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceCommandChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcecommandchanged)]

El siguiente paso consiste en agregar y quitar el comando que está asociado con el origen del comando. La propiedad <xref:System.Windows.Input.ICommandSource.Command%2A> no se puede sobrescribir simplemente cuando se agrega un nuevo comando, ya que los controladores de eventos asociados al comando anterior, si lo hubiera, se deben quitar primero.

[!code-csharp[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandsourcehookunhookcommands)]
[!code-vb[ImplementICommandSource#ImplementICommandSourceHookUnHookCommands](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandsourcehookunhookcommands)]

El siguiente paso consiste en crear una lógica para el controlador de <xref:System.Windows.Input.ICommand.CanExecuteChanged>.

El evento <xref:System.Windows.Input.ICommand.CanExecuteChanged> notifica al origen del comando que la capacidad del comando para ejecutarse en el destino del comando actual puede haber cambiado. Cuando un origen de comando recibe este evento, normalmente llama al método <xref:System.Windows.Input.ICommand.CanExecute%2A> en el comando. Si el comando no se puede ejecutar en el destino del comando actual, el origen del comando se deshabilitará normalmente. Si el comando se puede ejecutar en el destino del comando actual, el origen del comando se habilitará por lo general.

[!code-csharp[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandcanexecutechanged)]
[!code-vb[ImplementICommandSource#ImplementICommandCanExecuteChanged](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandcanexecutechanged)]

El último paso es el método <xref:System.Windows.Input.ICommand.Execute%2A>. Si el comando es un <xref:System.Windows.Input.RoutedCommand>, se llama al método <xref:System.Windows.Input.RoutedCommand.Execute%2A> <xref:System.Windows.Input.RoutedCommand>; de lo contrario, se llama al método de <xref:System.Windows.Input.ICommand.Execute%2A> de <xref:System.Windows.Input.ICommand>.

[!code-csharp[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/csharp/VS_Snippets_Wpf/ImplementICommandSource/CSharp/CommandSlider.cs#implementicommandexecute)]
[!code-vb[ImplementICommandSource#ImplementICommandExecute](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImplementICommandSource/visualbasic/commandslider.vb#implementicommandexecute)]

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Input.ICommandSource>
- <xref:System.Windows.Input.ICommand>
- <xref:System.Windows.Input.RoutedCommand>
- [Información general sobre comandos](commanding-overview.md)
