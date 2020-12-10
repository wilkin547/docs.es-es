---
title: Origen del evento BinaryFormatter
description: Aprenda a usar el origen del evento BinaryFormatter para registrar cuándo se está produciendo serialización o deserialización.
ms.date: 12/03/2020
ms.author: levib
author: GrabYourPitchforks
ms.openlocfilehash: 9ae2af77b6cfc270207fb0f2969ada8c2eca1153
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740395"
---
# <a name="binaryformatter-event-source"></a>Origen del evento BinaryFormatter

A partir de .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> incluye un elemento <xref:System.Diagnostics.Tracing.EventSource> integrado que le permite ver cuándo se produce la serialización o deserialización de objetos. Las aplicaciones pueden usar tipos derivados de <xref:System.Diagnostics.Tracing.EventListener> para escuchar estas notificaciones y registrarlas.

Esta funcionalidad no sustituye a <xref:System.Runtime.Serialization.SerializationBinder> o <xref:System.Runtime.Serialization.ISerializationSurrogate> y se puede usar para modificar los datos que se serializan o deserializan. Más bien, este sistema de eventos está diseñado para proporcionar información sobre los tipos que se serializan o deserializan. También se puede usar para detectar llamadas imprevistas en la infraestructura `BinaryFormatter`, como las que se originan desde código de biblioteca de terceros.

## <a name="description-of-events"></a>Descripción de eventos

El origen del evento `BinaryFormatter` tiene el nombre conocido `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`. Los agentes de escucha se pueden suscribir a seis eventos.

### <a name="serializationstart-event-id--10"></a>Evento SerializationStart (id. = `10`)

Se genera cuando se ha llamado a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> y se ha iniciado el proceso de serialización. Este evento se empareja con el evento `SerializationEnd`. Se puede llamar al evento `SerializationStart` de forma recursiva si un objeto llama a `BinaryFormatter.Serialize` dentro de su propia rutina de serialización.

Este evento no contiene una carga útil.

### <a name="serializationend-event-id--11"></a>Evento SerializationEnd (id. = `11`)

Se genera cuando `BinaryFormatter.Serialize` ha completado su trabajo. Cada aparición de `SerializationEnd` indica la finalización del último evento de `SerializationStart` no emparejado.

Este evento no contiene una carga útil.

### <a name="serializingobject-event-id--12"></a>Evento SerializingObject (id. = `12`)

Se genera cuando `BinaryFormatter.Serialize` está en el proceso de serializar un tipo no primitivo. La infraestructura `BinaryFormatter` tiene determinados tipos de casos especiales (como `string` y `int`) y no genera un evento cuando se encuentran estos tipos. Este evento se genera para los tipos definidos por el usuario y otros tipos que `BinaryFormatter` no entiende de forma nativa.

Este evento puede producirse cero o más veces entre los eventos `SerializationStart` y `SerializationEnd`.

Este evento contiene una carga con un argumento:

* `typeName` (`string`): nombre calificado con el ensamblado (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) del tipo que se serializa.

### <a name="deserializationstart-event-id--20"></a>Evento DeserializationStart (id. = `20`)

Se genera cuando se ha llamado a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> y se ha iniciado el proceso de deserialización. Este evento se empareja con el evento `DeserializationEnd`. Se puede llamar al evento `DeserializationStart` de forma recursiva si un objeto llama a `BinaryFormatter.Deserialize` dentro de su propia rutina de deserialización.

Este evento no contiene una carga útil.

### <a name="deserializationend-event-id--21"></a>Evento DeserializationEnd (id. = `21`)

Se genera cuando `BinaryFormatter.Deserialize` ha completado su trabajo. Cada aparición de `DeserializationEnd` indica la finalización del último evento de `DeserializationStart` no emparejado.

Este evento no contiene una carga útil.

### <a name="deserializingobject-event-id--22"></a>Evento DeserializingObject (id. = `22`)

Se genera cuando `BinaryFormatter.Deserialize` está en el proceso de deserializar un tipo no primitivo. La infraestructura `BinaryFormatter` tiene determinados tipos de casos especiales (como `string` y `int`) y no genera un evento cuando se encuentran estos tipos. Este evento se genera para tipos definidos por el usuario y otros tipos que `BinaryFormatter` no entiende de forma nativa.

Este evento puede producirse cero o más veces entre los eventos `DeserializationStart` y `DeserializationEnd`.

Este evento contiene una carga con un argumento.

* `typeName` (`string`): nombre calificado con el ensamblado (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) del tipo que se deserializa.

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a>\[Advanced\] Suscripción a un subconjunto de notificaciones

Los agentes de escucha que deseen suscribirse solo a un subconjunto de notificaciones pueden elegir las palabras clave que desean permitir.

* `Serialization` = `(EventKeywords)1`: genera los eventos `SerializationStart`, `SerializationEnd` y `SerializingObject`.
* `Deserialization` = `(EventKeywords)2`: genera los eventos `DeserializationStart`, `DeserializationEnd` y `DeserializingObject`.

Si no se proporciona ningún filtro de palabras clave durante el registro de `EventListener`, se generan todos los eventos.

Para obtener más información, vea <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.

## <a name="sample-code"></a>Código de ejemplo

El código siguiente:

- crea un tipo derivado de `EventListener` que escribe en `System.Console`,
- suscribe ese agente de escucha a las notificaciones generadas por `BinaryFormatter`,
- serializa y deserializa un gráfico de objetos simple mediante `BinaryFormatter`, y
- analiza los eventos que se han generado.

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

El código anterior genera una salida similar al ejemplo siguiente:

```output
Event SerializationStart (id=10) received.
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializingObject (id=12) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event SerializationStop (id=11) received.
Event DeserializationStart (id=20) received.
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Person, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializingObject (id=22) received.
typeName = BinaryFormatterEventSample.Book, BinaryFormatterEventSample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null
Event DeserializationStop (id=21) received.
Rehydrated person Logan Edwards
Favorite book: A Tale of Two Cities by Charles Dickens, list price 10.25
```

En este ejemplo, la clase `EventListener` basada en consola registra que la serialización se inicia, se serializan las instancias de `Person` y `Book` y, luego, se completa la serialización. Del mismo modo, una vez que se ha iniciado la deserialización, se deserializan las instancias de `Person` y `Book` y, luego, se completa la operación.

A continuación, la aplicación imprime los valores contenidos en la instancia de `Person` deserializada para demostrar que el objeto en realidad se serializó y deserializó correctamente.

## <a name="see-also"></a>Vea también

Para más información sobre el uso de `EventListener` para recibir notificaciones basadas en `EventSource`, consulte [la clase`EventListener`](xref:System.Diagnostics.Tracing.EventListener).
