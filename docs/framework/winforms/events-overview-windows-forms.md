---
title: Información general sobre eventos (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, event handling
- events [Windows Forms], about events
- delegates [Windows Forms], multicast
- delegates [Windows Forms], events and
- multicast event delegates
- Windows Forms controls, events
ms.assetid: 814a6a43-a312-4791-88d8-f75f9a4f8c4c
ms.openlocfilehash: 4abcf20b851f349a2b5df78c1fe1d15f729a5462
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345002"
---
# <a name="events-overview-windows-forms"></a>Información general sobre eventos (Windows Forms)
Un evento es una acción a la que puede responder o que puede "controlar" en el código. Los eventos se pueden generar por una acción del usuario, como hacer clic con el mouse o presionar una tecla, por código de programa o por el sistema.

 Las aplicaciones controladas por eventos ejecutan código en respuesta a un evento. Cada formulario y control expone un conjunto predefinido de eventos que puede programar. Si se produce uno de estos eventos y hay código en el controlador de evento asociado, se invoca ese código.

 Los tipos de eventos que puede generar un objeto varían, pero muchos tipos son comunes a la mayoría de los controles. Por ejemplo, la mayoría de los objetos controlará un evento <xref:System.Windows.Forms.Control.Click>. Si un usuario hace clic en un formulario, se ejecuta el código del controlador de evento <xref:System.Windows.Forms.Control.Click> del formulario.

> [!NOTE]
> Muchos eventos se producen junto con otros eventos. Por ejemplo, mientras se produce el evento <xref:System.Windows.Forms.Control.DoubleClick>, se producen los eventos <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseUp> y <xref:System.Windows.Forms.Control.Click>.

 Para obtener información sobre cómo generar y usar un evento, vea [eventos](../../standard/events/index.md).

## <a name="delegates-and-their-role"></a>Delegados y sus roles
 Los delegados son clases utilizadas normalmente en el .NET Framework para compilar mecanismos de control de eventos. Los delegados aproximadamente equivalen a los punteros de función C++ , que se usan normalmente en objetos visuales y otros lenguajes orientados a objetos. Sin embargo, a diferencia de los punteros de función, los delegados están orientados a objetos, proporcionan seguridad de tipos y son seguros. Además, mientras que un puntero de función solo contiene una referencia a una función determinada, un delegado consta de una referencia a un objeto y de referencias a uno o varios métodos dentro del objeto.

 Este modelo de eventos utiliza *delegados* para enlazar eventos a los métodos que se usan para controlarlos. El delegado permite especificar un método de controlador para registrar otras clases para la notificación de eventos. Cuando el evento se produce, el delegado llama al método enlazado. Para obtener más información sobre cómo definir los delegados, vea [eventos](../../standard/events/index.md).

Los delegados se pueden enlazar a un único método o a varios métodos, lo que se conoce como multidifusión. Al crear un delegado para un evento, usted (o Windows) normalmente crea un evento de multidifusión. Una excepción rara podría ser un evento que produce un procedimiento específico (tal como mostrar un cuadro de diálogo) que lógicamente no se repetiría varias veces por evento. Para obtener información sobre cómo crear un delegado de multidifusión, vea [Cómo combinar delegados (delegados de multidifusión)](../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md).

 Un delegado de multidifusión mantiene una lista de invocación de los métodos a los que está enlazado. El delegado de multidifusión admite un método <xref:System.Delegate.Combine%2A> para agregar un método a la lista de invocación y un método <xref:System.Delegate.Remove%2A> para quitarlo.

 Cuando la aplicación registra un evento, el control invoca al delegado de ese evento para generarlo. A su vez, el delegado llama al método enlazado. En el caso más frecuente (un delegado de multidifusión), el delegado llama a su vez a cada método enlazado en la lista de invocación, lo que proporciona una notificación de uno a varios. En esta estrategia, el control no necesita mantener una lista de objetos de destino para cada evento; el delegado controla todo el registro y la notificación.

 Los delegados también permiten enlazar varios eventos al mismo método, lo que permite una notificación de varios a uno. Por ejemplo, tanto un evento de clic en botón como un evento de clic en comando de menú pueden invocar al mismo delegado que, después, llama a un único método para controlar estos eventos diferentes de la misma manera.

 El mecanismo de enlace que se usa con los delegados es dinámico: un delegado se puede enlazar en tiempo de ejecución a cualquier método cuya firma coincida con la del controlador de eventos. Con esta característica, puede configurar o cambiar el método de enlace según una condición, y asociar dinámicamente un controlador de evento a un control.

## <a name="see-also"></a>Vea también

- [Crear controladores de eventos en Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Información general sobre controladores de eventos](event-handlers-overview-windows-forms.md)
