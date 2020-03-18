---
title: Patrón de eventos estándar de .NET
description: Obtenga información sobre los patrones de eventos de .NET y cómo crear orígenes de eventos estándar, y suscribir y procesar eventos estándar en su código.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 8a3133d6-4ef2-46f9-9c8d-a8ea8898e4c9
ms.openlocfilehash: dec516767e43a6bf4edfa555e34f3adcc21a46e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146146"
---
# <a name="standard-net-event-patterns"></a>Patrón de eventos estándar de .NET

[Anterior](events-overview.md)

Los eventos de .NET generalmente siguen unos patrones conocidos. Estandarizar sobre estos patrones significa que los desarrolladores pueden aprovechar el conocimiento de esos patrones estándar, que se pueden aplicar a cualquier programa de evento de .NET.

Vamos a analizar los patrones estándar, para que tenga todos los conocimientos necesarios para crear orígenes de eventos estándar y suscribirse y procesar eventos estándar en el código.

## <a name="event-delegate-signatures"></a>Firmas de delegado de eventos

La firma estándar de un delegado de eventos de .NET es:

```csharp
void OnEventRaised(object sender, EventArgs args);
```

El tipo de valor devuelto es void. Los eventos se basan en delegados y son delegados de multidifusión. Eso admite varios suscriptores para cualquier origen de eventos. El único valor devuelto de un método no escala a varios suscriptores de eventos. ¿Qué valor devuelto ve el origen de evento después de generar un evento? Más adelante en este artículo verá cómo crear protocolos de evento que admiten suscriptores de eventos que notifican información al origen del evento.

La lista de argumentos contiene dos argumentos: el remitente y los argumentos del evento. El tipo de tiempo de compilación de `sender` es `System.Object`, aunque probablemente conozca un tipo más derivado que siempre será correcto. Por convención, use `object`.

Típicamente, el segundo argumento era un tipo que se derivaba de `System.EventArgs`. (Verá en la [siguiente sección](modern-events.md) que ya no se aplica esta convención). Si el tipo de evento no necesita ningún argumento adicional, aún tendrá que proporcionar los dos argumentos.
Hay un valor especial, `EventArgs.Empty`, que debe usarse para indicar que el evento no contiene ninguna información adicional.

Vamos a crear una clase que enumera los archivos en un directorio, o cualquiera de sus subdirectorios que siguen un patrón. Este componente genera un evento para cada archivo encontrado que coincida con el modelo.

El uso de un modelo de eventos proporciona algunas ventajas de diseño. Se pueden crear varios agentes de escucha de eventos que realicen acciones diferentes cuando se encuentre un archivo buscado. La combinación de los distintos agentes de escucha puede crear algoritmos más sólidos.

Esta es la declaración del argumento de evento inicial para buscar un archivo buscado:

[!code-csharp[EventArgs](../../samples/snippets/csharp/events/Program.cs#EventArgsV1 "Define event arguments")]

Aunque este tipo parece un tipo pequeño exclusivo para datos, debe seguir la convención y convertirlo en un tipo de referencia (`class`). Esto significa que el objeto de argumento se pasará por referencia y que todos los suscriptores verán las actualizaciones de los datos. La primera versión es un objeto inmutable. Es preferible hacer que las propiedades en el tipo de argumento de evento sean inmutables. De ese modo, un suscriptor no puede cambiar los valores antes de que los vea otro suscriptor. (Hay excepciones, como verá a continuación).  

Después, debemos crear la declaración de evento en la clase FileSearcher. Aprovechando el tipo `EventHandler<T>`, no es necesario crear otra definición de tipo más. Simplemente se puede usar una especialización genérica.

Vamos a rellenar la clase FileSearcher para buscar archivos que coincidan con un patrón y generar el evento correcto cuando se detecte una coincidencia.

[!code-csharp[FileSearcher](../../samples/snippets/csharp/events/Program.cs#FileSearcherV1 "Create the initial file searcher")]

## <a name="defining-and-raising-field-like-events"></a>Definición y generación de eventos como si fueran campos

La manera más sencilla de agregar un evento a la clase es declarar ese evento como un campo público, como en el ejemplo anterior:

[!code-csharp[DeclareEvent](../../samples/snippets/csharp/events/Program.cs#DeclareEvent "Declare the file found event")]

Parece que se está declarando un campo público, lo que podría parecer una práctica orientada a objetos incorrecta. Quiere proteger el acceso a los datos a través de propiedades o métodos. Aunque esto puede parecer una mala práctica, el código generado por el compilador crea contenedores para que solo se pueda acceder de forma segura a los objetos de evento. Las únicas operaciones disponibles en un evento con aspecto de campo son las de agregar controlador:

[!code-csharp[DeclareEventHandler](../../samples/snippets/csharp/events/Program.cs#DeclareEventHandler "Declare the file found event handler")]

y quitar controlador:

[!code-csharp[RemoveEventHandler](../../samples/snippets/csharp/events/Program.cs#RemoveHandler "Remove the event handler")]

Tenga en cuenta que hay una variable local para el controlador. Si usó el cuerpo de la expresión lambda, la eliminación no funcionará correctamente. Sería una instancia diferente del delegado y, en modo silencioso, no se hace nada.

El código fuera de la clase no puede generar el evento, ni puede realizar otras operaciones.

## <a name="returning-values-from-event-subscribers"></a>Devolución de valores desde los suscriptores de eventos

La versión simple funciona correctamente. Vamos a agregar otra característica: la cancelación.

Cuando se genera el evento encontrado, los agentes de escucha deberían ser capaces de detener el procesamiento, si este archivo es el último que se busca.

Los controladores de eventos no devuelven un valor, por lo que se necesita comunicarlo de otra forma. El patrón de eventos estándar usa el objeto EventArgs para incluir campos que los suscriptores de eventos pueden usar para comunicar la cancelación.

Existen dos patrones diferentes que podrían usarse, basándose en la semántica del contrato de cancelación. En ambos casos, se agrega un campo booleano a EventArguments para el evento del archivo encontrado.

Uno de los patrones permitiría a cualquier suscriptor cancelar la operación.
Para este patrón, el nuevo campo se inicializa en `false`. Los suscriptores pueden cambiarlo a `true`. Después de que todos los suscriptores hayan visto el evento generado, el componente FileSearcher examina el valor booleano y toma medidas.

El segundo patrón solo debería cancelar la operación si todos los suscriptores quieren que se cancele. En este patrón, el nuevo campo se inicializa para indicar que se debe cancelar la operación y cualquier suscriptor puede modificarlo para indicar que la operación debe continuar.
Después de que todos los suscriptores hayan visto el evento generado, el componente FileSearcher examina el valor booleano y toma medidas. Hay un paso adicional en este patrón: el componente necesita saber si los suscriptores vieron el evento. Si no hay ningún suscriptor, el campo indicaría incorrectamente una cancelación.

Vamos a implementar la primera versión de este ejemplo. Debe agregar un campo booleano denominado `CancelRequested` al tipo `FileFoundArgs`:

[!code-csharp[EventArgs](../../samples/snippets/csharp/events/Program.cs#EventArgs "Update event arguments")]

Este nuevo campo se inicializa automáticamente en `false`, el valor predeterminado de un campo booleano, por lo que no se cancela accidentalmente. El otro cambio en el componente consiste en comprobar el indicador después de generar el evento para ver si alguno de los suscriptores solicitó una cancelación:

```csharp
public void List(string directory, string searchPattern)
{
    foreach (var file in Directory.EnumerateFiles(directory, searchPattern))
    {
        var args = new FileFoundArgs(file);
        FileFound?.Invoke(this, args);
        if (args.CancelRequested)
            break;
    }
}
```

Una ventaja de este patrón es que no supone un cambio brusco.
Ninguno de los suscriptores solicitó una cancelación antes y siguen sin hacerlo. No debe actualizarse el código de ningún suscriptor a menos que quieran admitir el nuevo protocolo de cancelación. Está acoplado muy holgadamente.

Vamos a actualizar el suscriptor para que solicite una cancelación una vez que encuentra el primer ejecutable:

```csharp
EventHandler<FileFoundArgs> onFileFound = (sender, eventArgs) =>
{
    Console.WriteLine(eventArgs.FoundFile);
    eventArgs.CancelRequested = true;
};
```

## <a name="adding-another-event-declaration"></a>Agregar otra declaración de evento

Vamos a agregar una característica más y demostrar otras expresiones de lenguaje para los eventos. Vamos a agregar una sobrecarga del método `Search` que recorre todos los subdirectorios en busca de archivos.

Podría llegar a ser una operación de larga duración si el directorio tuviese muchos subdirectorios. Vamos a agregar un evento que se genera cuando comienza cada nueva búsqueda en el directorio. Esto permite a los suscriptores realizar el seguimiento y actualizar al usuario sobre el progreso. Todos los ejemplos creados hasta ahora son públicos. Convertiremos este evento en un evento interno. Eso significa que también se pueden convertir en internos los tipos que se usan para los argumentos.

Comenzará creando la nueva clase derivada de EventArgs para informar del nuevo directorio y del progreso.

[!code-csharp[DirEventArgs](../../samples/snippets/csharp/events/Program.cs#SearchDirEventArgs "Define search directory event arguments")]

De nuevo, puede seguir las recomendaciones para crear un tipo de referencia inmutable para los argumentos de evento.

Después, defina el evento. Esta vez, usará una sintaxis diferente. Además de usar la sintaxis de campos, puede crear explícitamente la propiedad con controladores add y remove. En este ejemplo, no necesitará código adicional en los controladores, pero aquí se muestra cómo se crean.

[!code-csharp[Declare event with add and remove handlers](../../samples/snippets/csharp/events/Program.cs#DeclareSearchEvent "Declare the event with add and remove handlers")]

En muchos aspectos, el código que se escribe aquí refleja el código que genera el compilador para las definiciones de evento de campo que se vieron anteriormente. El evento se crea mediante una sintaxis muy similar a la que se usó para las [propiedades](properties.md). Tenga en cuenta que los controladores tienen nombres diferentes: `add` y `remove`. Se llaman para suscribirse al evento o para cancelar la suscripción al evento. Tenga en cuenta que también debe declarar un campo de respaldo privado para almacenar la variable de evento. Se inicializa en null.

Después, se agregará la sobrecarga del método `Search` que recorre los subdirectorios y genera los dos eventos. La manera más fácil de hacerlo consiste en usar un argumento predeterminado para especificar que se quiere buscar en todos los directorios:

[!code-csharp[SearchImplementation](../../samples/snippets/csharp/events/Program.cs#FinalImplementation "Implementation to search directories")]

En este punto, puede ejecutar la aplicación mediante la llamada a la sobrecarga para buscar en todos los subdirectorios. No hay ningún suscriptor en el nuevo evento `ChangeDirectory`, pero al usar el elemento `?.Invoke()` se garantiza que esto funciona correctamente.

 Vamos a agregar un controlador para escribir una línea que muestre el progreso en la ventana de la consola.

[!code-csharp[Search](../../samples/snippets/csharp/events/Program.cs#Search "Declare event handler")]

Ha visto los patrones que se siguen en todo el ecosistema de. NET.
El aprendizaje de estos patrones y convenciones le permitirá escribir elementos de C# y .NET rápidamente.

Más adelante verá algunos cambios en estos patrones en la versión más reciente de. NET.

[Siguiente](modern-events.md)
