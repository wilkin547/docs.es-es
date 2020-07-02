---
title: Modelo de diseño de observador
description: Descubra el modelo de diseño de observador en .NET. Este modelo permite que un suscriptor se registre con un proveedor y reciba notificaciones de un proveedor.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- IObserver(Of T) interface
- IObservable<T> interface
- IObserver<T> interface
- IObservable(Of T) interface
- observer design pattern [.NET Framework]
ms.assetid: 3680171f-f522-453c-aa4a-54f755a78f88
ms.openlocfilehash: 4edcd2645b28095f4bd18f4918b9afa5c893bd39
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662737"
---
# <a name="observer-design-pattern"></a>Modelo de diseño de observador

El modelo de diseño de observador permite que un suscriptor se registre con un proveedor y reciba notificaciones de dicho proveedor. Este modelo es adecuado para cualquier escenario que requiera notificaciones push. El modelo define un *proveedor* (también conocido como un *tema* o una *observable*) y cero, uno o más *observadores*. Los observadores se registran con el proveedor y siempre que se produce una condición predefinida, un evento o un cambio de estado, el proveedor notifica automáticamente a todos los observadores mediante la llamada a uno de sus métodos. En esta llamada al método, el proveedor puede proporcionar también información sobre el estado actual a los observadores. En .NET Framework, el modelo de diseño de observador se aplica con la implementación de las interfaces genéricas <xref:System.IObservable%601?displayProperty=nameWithType> y <xref:System.IObserver%601?displayProperty=nameWithType>. El parámetro de tipo genérico representa el tipo que proporciona información de notificación.

## <a name="applying-the-pattern"></a>Aplicación del modelo

El modelo de diseño de observador es adecuado para las notificaciones distribuidas mediante push, ya que admite una separación clara entre dos componentes diferentes o capas de aplicación, como una capa de origen de datos (lógica de negocios) y una capa de interfaz de usuario (pantalla). El modelo puede implementarse cada vez que un proveedor usa devoluciones de llamada para proporcionar información actual a sus clientes.

Para implementar el modelo, es necesario proporcionar lo siguiente:

- Un proveedor o un tema, que es el objeto que envía notificaciones a los observadores. Un proveedor es una clase o estructura que implementa la interfaz <xref:System.IObservable%601>. El proveedor debe implementar un único método, <xref:System.IObservable%601.Subscribe%2A?displayProperty=nameWithType>, al que llaman los observadores que desean recibir notificaciones del proveedor.

- Un observador, que es un objeto que recibe notificaciones de un proveedor. Un observador es una clase o estructura que implementa la interfaz <xref:System.IObserver%601>. El observador debe implementar tres métodos, a los que llama el proveedor:

  - <xref:System.IObserver%601.OnNext%2A?displayProperty=nameWithType>, que proporciona al observador información nueva o actual.

  - <xref:System.IObserver%601.OnError%2A?displayProperty=nameWithType>, que informa al observador de que se ha producido un error.

  - <xref:System.IObserver%601.OnCompleted%2A?displayProperty=nameWithType>, que indica que el proveedor ha terminado de enviar notificaciones.

- Un mecanismo que permite al proveedor realizar el seguimiento de observadores. Normalmente, el proveedor usa un objeto contenedor, como <xref:System.Collections.Generic.List%601?displayProperty=nameWithType>, para mantener las referencias a las implementaciones de <xref:System.IObserver%601> que se han suscrito a las notificaciones. Gracias a un contenedor de almacenamiento específico para este fin, el proveedor puede controlar desde cero a un número ilimitado de observadores. El orden en que los observadores reciben las notificaciones no está definido y el proveedor es libre de usar cualquier método para determinar el orden.

- Una implementación de <xref:System.IDisposable> que permite al proveedor quitar los observadores cuando se completa la notificación. Los observadores reciben una referencia a la implementación de <xref:System.IDisposable> desde el método <xref:System.IObservable%601.Subscribe%2A>, por lo que también pueden llamar al método <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> para cancelar la suscripción antes de que el proveedor termine de enviar las notificaciones.

- Un objeto que contiene los datos que el proveedor envía a sus observadores. El tipo de este objeto se corresponde con el parámetro de tipo genérico de las interfaces <xref:System.IObservable%601> y <xref:System.IObserver%601>. Aunque este objeto puede ser el mismo que la implementación de <xref:System.IObservable%601>, normalmente es un tipo diferente.

> [!NOTE]
> Además de implementar el modelo de diseño de observador, es posible que le interese explorar las bibliotecas que se compilan con las interfaces <xref:System.IObservable%601> y <xref:System.IObserver%601>. Por ejemplo, las [extensiones reactivas para .NET (Rx)](https://docs.microsoft.com/previous-versions/dotnet/reactive-extensions/hh242985(v=vs.103)) constan de un conjunto de métodos de extensión y los operadores de secuencia estándar de LINQ para admitir la programación asincrónica.

## <a name="implementing-the-pattern"></a>Implementación del modelo

En el ejemplo siguiente se usa el modelo de diseño de observador para implementar un sistema de información de recogida de equipaje en un aeropuerto. Una clase `BaggageInfo` proporciona información sobre la llegada de los vuelos y la cinta de recogida de equipaje correspondiente a cada vuelo. Esta implementación se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#1)]
[!code-vb[Conceptual.ObserverDesignPattern#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#1)]

Una clase `BaggageHandler` es la responsable de recibir la información sobre la llegada de los vuelos y las cintas de recogida de equipaje. Internamente, mantiene dos colecciones:

- `observers`: colección de clientes que recibirán información actualizada.

- `flights`: colección de los vuelos y sus cintas asignadas.

Ambas colecciones están representadas por objetos <xref:System.Collections.Generic.List%601> genéricos de los que se crean instancias en el constructor de clase `BaggageHandler`. El código fuente de la clase `BaggageHandler` se muestra en el ejemplo siguiente.

[!code-csharp[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#2)]
[!code-vb[Conceptual.ObserverDesignPattern#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#2)]

Los clientes que deseen recibir información actualizada llaman al método `BaggageHandler.Subscribe`. Si el cliente no se ha suscrito previamente a las notificaciones, en la colección de `observers` se agrega una referencia a la implementación de <xref:System.IObserver%601> del cliente.

Se puede llamar al método `BaggageHandler.BaggageStatus` sobrecargado para indicar que el equipaje de un vuelo se está descargando o ya no se está descargando. En el primer caso, se pasa al método un número de vuelo, el aeropuerto de origen del vuelo y la cinta en la que se está descargando el equipaje. En el segundo caso, solo se pasa al método un número de vuelo. Para el equipaje que se está descargado, el método comprueba si la información `BaggageInfo` que se pasa al método existe en la colección `flights`. Si no es así, el método agrega la información y llama al método `OnNext` de cada observador. Para los vuelos cuyo equipaje ya no se está descargando, el método comprueba si la información del vuelo se almacena en la colección `flights`. Si es así, el método llama al método `OnNext` de cada observador y quita el objeto `BaggageInfo` de la colección `flights`.

Una vez que aterrice el último vuelo del día y se procese su equipaje, se llama al método `BaggageHandler.LastBaggageClaimed`. Este método llama al método `OnCompleted` de cada observador para indicar que se han completado todas las notificaciones y, a continuación, borra la colección `observers`.

El método <xref:System.IObservable%601.Subscribe%2A> del proveedor devuelve una implementación <xref:System.IDisposable> que permite a los observadores dejar de recibir notificaciones antes de que se llame al método <xref:System.IObserver%601.OnCompleted%2A>. El código fuente para esta clase `Unsubscriber(Of BaggageInfo)` se muestra en el ejemplo siguiente. Cuando se crea una instancia de la clase en el método `BaggageHandler.Subscribe`, se pasa una referencia a la colección `observers` y una referencia al observador que se agrega a la colección. Estas referencias se asignan a variables locales. Cuando se llama al método `Dispose` del objeto, comprueba si el observador todavía existe en la colección `observers` y, si es así, se quita el observador.

[!code-csharp[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/provider.cs#3)]
[!code-vb[Conceptual.ObserverDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/provider.vb#3)]

En el ejemplo siguiente se proporciona una implementación de <xref:System.IObserver%601> denominada `ArrivalsMonitor`, que es una clase base que muestra información sobre la recogida de equipaje. La información se muestra por orden alfabético, según el nombre de la ciudad de origen. Los métodos de `ArrivalsMonitor` se marcan como `overridable` (en Visual Basic) o `virtual` (en C#), por lo que se pueden invalidar mediante una clase derivada.

[!code-csharp[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/observer.cs#4)]
[!code-vb[Conceptual.ObserverDesignPattern#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/observer.vb#4)]

La clase `ArrivalsMonitor` contiene los métodos `Subscribe` y `Unsubscribe`. El método `Subscribe` permite que la clase guarde la implementación de <xref:System.IDisposable> devuelta por la llamada a <xref:System.IObservable%601.Subscribe%2A> a una variable privada. El método `Unsubscribe` permite que la clase cancele la suscripción a notificaciones mediante una llamada a la implementación de <xref:System.IDisposable.Dispose%2A> del proveedor. `ArrivalsMonitor` también proporciona implementaciones de los métodos <xref:System.IObserver%601.OnNext%2A>, <xref:System.IObserver%601.OnError%2A> y <xref:System.IObserver%601.OnCompleted%2A>. Tan solo la implementación de <xref:System.IObserver%601.OnNext%2A> contiene una cantidad significativa de código. El método funciona con un objeto <xref:System.Collections.Generic.List%601> privado, ordenado y genérico que posee información sobre los aeropuertos de origen de los vuelos de llegada y las cintas en las que está disponible el correspondiente equipaje. Si la clase `BaggageHandler` notifica la llegada de un nuevo vuelo, la implementación del método <xref:System.IObserver%601.OnNext%2A> agrega información sobre ese vuelo a la lista. Si la clase `BaggageHandler` informa de que el equipaje del vuelo se ha descargado, el método <xref:System.IObserver%601.OnNext%2A> quita este vuelo de la lista. Cada vez que se produce un cambio, la lista se ordena y se muestra en la consola.

El ejemplo siguiente contiene el punto de entrada de la aplicación que crea una instancia de la clase `BaggageHandler`, así como dos instancias de la clase `ArrivalsMonitor`, y usa el método `BaggageHandler.BaggageStatus` para agregar y quitar información sobre los vuelos de llegada. En cada caso, los observadores reciben actualizaciones y muestran correctamente la información de recogida de equipaje.

[!code-csharp[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.observerdesignpattern/cs/program.cs#5)]
[!code-vb[Conceptual.ObserverDesignPattern#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.observerdesignpattern/vb/module1.vb#5)]

## <a name="related-topics"></a>Temas relacionados

|Title|Descripción|
|-----------|-----------------|
|[Procedimientos recomendados para modelos de diseño de observador](observer-design-pattern-best-practices.md)|Describe los procedimientos recomendados que deben adoptarse en el desarrollo de aplicaciones que implementan el modelo de diseño de observador.|
|[Cómo: Implementar un proveedor](how-to-implement-a-provider.md)|Proporciona una implementación detallada de un proveedor para una aplicación de supervisión de temperatura.|
|[Cómo: Implementar un observador](how-to-implement-an-observer.md)|Proporciona una implementación detallada de un observador para una aplicación de supervisión de temperatura.|
