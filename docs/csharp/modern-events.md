---
title: Patrón de eventos actualizado de .NET Core
description: Obtenga información sobre cómo el patrón de eventos de .NET Core permite la flexibilidad con la compatibilidad con versiones anteriores y cómo implementar un procesamiento de eventos seguro con suscriptores asincrónicos.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 9aa627c3-3222-4094-9ca8-7e88e1071e06
ms.openlocfilehash: c8858158ede761db8a3002beb26e521880f77feb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170441"
---
# <a name="the-updated-net-core-event-pattern"></a>Patrón de eventos actualizado de .NET Core

[Anterior](event-pattern.md)

En el artículo anterior se describían los patrones de eventos más comunes. .NET Core tiene un patrón menos estricto. En esta versión, la definición `EventHandler<TEventArgs>` ya no tiene la restricción que obliga a que `TEventArgs` sea una clase derivada de `System.EventArgs`.

Esto aumenta la flexibilidad y es compatible con versiones anteriores. Comencemos con la flexibilidad. La clase System.EventArgs introduce un método, `MemberwiseClone()`, que crea una copia superficial del objeto.
Dicho método debe usar la reflexión para implementar su función en cualquier clase derivada de `EventArgs`. Esta funcionalidad es más fácil de crear en una clase derivada concreta. Esto significa que derivar de System.EventArgs es una restricción que limita los diseños, pero no proporciona ninguna ventaja adicional.
De hecho, puede cambiar las definiciones de `FileFoundArgs` y `SearchDirectoryArgs` para que no deriven de `EventArgs`.
El programa funcionará exactamente igual.

También puede cambiar `SearchDirectoryArgs` a un struct si realiza un cambio más:

```csharp
internal struct SearchDirectoryArgs
{
    internal string CurrentSearchDirectory { get; }
    internal int TotalDirs { get; }
    internal int CompletedDirs { get; }

    internal SearchDirectoryArgs(string dir, int totalDirs, int completedDirs) : this()
    {
        CurrentSearchDirectory = dir;
        TotalDirs = totalDirs;
        CompletedDirs = completedDirs;
    }
}
```

El cambio adicional consiste en llamar al constructor sin parámetros antes de entrar en el constructor que inicializa todos los campos. Sin esta adición, las reglas de C# informarán de que se está teniendo acceso a las propiedades antes de que se hayan asignado.

No debe cambiar `FileFoundArgs` de una clase (tipo de referencia) a un struct (tipo de valor). Esto se debe a que el protocolo para controlar la cancelación requiere que los argumentos de evento se pasen por referencia. Si realizase el mismo cambio, la clase de búsqueda de archivos no podría observar nunca los cambios realizados por ninguno de los suscriptores de eventos. Se usaría una nueva copia de la estructura para cada suscriptor, y dicha copia sería diferente de la que ve el objeto de búsqueda de archivos.

Ahora veamos cómo este cambio puede ser compatible con versiones anteriores.
La eliminación de la restricción no afecta al código existente. Los tipos de argumento de evento existentes siguen derivando de `System.EventArgs`.
La compatibilidad con versiones anteriores es uno de los motivos principales por los que siguen derivando de `System.EventArgs`. Los suscriptores de eventos existentes serán suscriptores a un evento que haya seguido el patrón clásico.

Según una lógica similar, cualquier tipo de argumento de evento creado ahora no tendría ningún suscriptor en el código base existente. Los nuevos tipos de evento que no deriven de `System.EventArgs` no interrumpirán ese código base.

## <a name="events-with-async-subscribers"></a>Eventos con suscriptores Async

Le queda un último patrón que aprender: Cómo escribir correctamente suscriptores de eventos que llaman a código asincrónico. Este reto se describe en el artículo sobre [async y await](async.md). Los métodos asincrónicos pueden tener un tipo de valor devuelto void, pero esto no es recomendable. Cuando el código de suscriptor de eventos llama a un método asincrónico, no le queda otra opción que crear un método `async void`, ya que lo requiere la firma del controlador de eventos.

Debe conciliar estas instrucciones contradictorias. De alguna manera, debe crear un método `async void` seguro. A continuación se muestran los aspectos básicos del patrón que debe implementar:

```csharp
worker.StartWorking += async (sender, eventArgs) =>
{
    try
    {
        await DoWorkAsync();
    }
    catch (Exception e)
    {
        //Some form of logging.
        Console.WriteLine($"Async task failure: {e.ToString()}");
        // Consider gracefully, and quickly exiting.
    }
};
```

En primer lugar, observe que el controlador está marcado como un controlador asincrónico. Dado que se va a asignar a un tipo de delegado de controlador de eventos, tendrá un tipo de valor devuelto void. Esto significa que debe seguir el patrón que se muestra en el controlador y no debe permitir que se produzca ninguna excepción fuera del contexto del controlador asincrónico. Como no devuelve una tarea, no hay ninguna tarea que pueda notificar el error entrando en el estado de error. Dado que el método es asincrónico, no puede producir la excepción. (El método de llamada ha continuado con la ejecución porque es `async`). El comportamiento real en tiempo de ejecución se definirá de forma diferente para diferentes entornos. Se puede terminar el subproceso o el proceso que posee el subproceso, o dejar el proceso en un estado indeterminado. Todas estas salidas potenciales son altamente no deseables.

Por eso debe encapsular la instrucción await para la tarea asincrónica en su propio bloque try. Si esto genera una tarea con error, puede registrar el error. Si se produce un error del que no se puede recuperar la aplicación, puede salir del programa de forma rápida y correctamente.

Estas son las principales actualizaciones del patrón de eventos de .NET. Verá numerosos ejemplos de las versiones anteriores de las bibliotecas con las que trabaje. Aun así, también debe entender los patrones más recientes.

El siguiente artículo de esta serie le ayudará a distinguir entre el uso de `delegates` y `events` en los diseños. Dado que se trata de conceptos similares, el artículo le ayudará a tomar la mejor decisión para sus programas.

[Siguiente](distinguish-delegates-events.md)
