---
title: Introducción a los eventos
description: Obtenga información sobre los eventos en .NET Core y nuestros objetivos de diseño del lenguaje para los eventos en esta introducción.
ms.date: 06/20/2016
ms.assetid: 9b8d2a00-1584-4a5b-8994-5003d54d8e0c
ms.openlocfilehash: 4da44c151244e8b5de34f550040c271131d9598c
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465239"
---
# <a name="introduction-to-events"></a>Introducción a los eventos

[Anterior](delegates-patterns.md)

Los eventos son, como los delegados, un mecanismo de *enlace en tiempo de ejecución*. De hecho, los eventos se crean con compatibilidad de lenguaje para los delegados.

Los eventos son una manera para que un objeto difunda (a todos los componentes interesados del sistema) que algo ha sucedido. Cualquier otro componente puede suscribirse al evento, y recibir una notificación cuando se genere uno.

Probablemente ha usado eventos en alguna programación. Muchos sistemas gráficos tienen un modelo de eventos para notificar la interacción del usuario. Estos eventos notificarán movimiento del mouse, pulsaciones de botón e interacciones similares. Ese es uno de los más comunes, pero realmente no es el único escenario donde se usan eventos.

Puede definir eventos que deben generarse para las clases. Una consideración importante a la hora de trabajar con eventos es que puede que no haya ningún objeto registrado para un evento determinado. Debe escribir el código de manera que no genere eventos cuando no esté configurado ningún agente de escucha.

La suscripción a un evento también crea un acoplamiento entre dos objetos (el origen del evento y el receptor del evento). Necesita asegurarse de que el receptor del evento cancela la suscripción del origen del evento cuando ya no está interesado en eventos.

## <a name="design-goals-for-event-support"></a>Diseño de objetivos para la compatibilidad con eventos

El diseño del lenguaje para eventos tiene como destino estos objetivos:

- Permita un acoplamiento mínimo entre un origen de eventos y un receptor de eventos. Estos dos componentes puede que no se hayan escrito por la misma organización e incluso pueden actualizarse en programaciones totalmente diferentes.

- Debe ser muy sencillo suscribirse a un evento y cancelar la suscripción de este.

- Los orígenes de eventos deben admitir varios suscriptores de eventos. También deben admitir no tener ningún suscriptor de eventos asociado.

Puede observar que los objetivos de los eventos son muy similares a los de los delegados.
Este es el motivo por el que la compatibilidad del lenguaje de eventos se basa en la compatibilidad del lenguaje de delegados.

## <a name="language-support-for-events"></a>Compatibilidad del lenguaje para eventos

La sintaxis para definir eventos, y suscribirse o cancelar la suscripción de eventos, es una extensión de la sintaxis de los delegados.

Para definir un evento, use la palabra clave `event`:

```csharp
public event EventHandler<FileListArgs> Progress;
```

El tipo del evento (`EventHandler<FileListArgs>` en este ejemplo) debe ser un tipo de delegado. Existen varias convenciones que debe seguir al declarar un evento. Normalmente, el tipo de delegado de eventos tiene un valor devuelto void.
Las declaraciones de eventos deben ser un verbo o una frase verbal.
Use un tiempo verbal pasado cuando el evento notifique algo que ha ocurrido. Use un tiempo verbal presente (por ejemplo, `Closing`) para notificar algo que está a punto de suceder. A menudo, el uso del tiempo presente indica que su clase admite algún tipo de comportamiento de personalización. Uno de los escenarios más comunes es admitir la cancelación. Por ejemplo, un evento `Closing` puede incluir un argumento que indicará si la operación de cierre debe continuar o no.  Otros escenarios pueden permitir que los autores de la llamada modifiquen el comportamiento actualizando propiedades de los argumentos de eventos. Puede generar un evento para indicar la siguiente acción propuesta que realizará un algoritmo. El controlador de eventos puede exigir una acción diferente modificando las propiedades del argumento de eventos.

Cuando quiera generar el evento, llame a los controladores de eventos mediante la sintaxis de invocación del delegado:

```csharp
Progress?.Invoke(this, new FileListArgs(file));
```

Como se ha tratado en la sección sobre [delegados](delegates-patterns.md), el operador ?.
hace que se garantice más fácilmente que no intenta generar el evento cuando no existen suscriptores en este.

Se suscribe a un evento con el operador `+=`:

```csharp
EventHandler<FileListArgs> onProgress = (sender, eventArgs) =>
    Console.WriteLine(eventArgs.FoundFile);

fileLister.Progress += onProgress;
```

El método de controlador normalmente tiene el prefijo "On" seguido del nombre del evento, como se ha mostrado anteriormente.

Cancela la suscripción con el operador `-=`:

```csharp
fileLister.Progress -= onProgress;
```

Es importante que declare una variable local para la expresión que representa el controlador de eventos. Eso garantiza que la cancelación de la suscripción quita el controlador.
Si, en su lugar, ha usado el cuerpo de la expresión lambda, está intentando quitar un controlador que nunca ha estado asociado, lo que no produce ninguna acción.

En el artículo siguiente, obtendrá más información sobre los modelos de eventos típicos y las diferentes variaciones de este ejemplo.

[Siguiente](event-pattern.md)
