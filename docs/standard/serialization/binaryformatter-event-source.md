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
# <a name="binaryformatter-event-source"></a><span data-ttu-id="76e55-103">Origen del evento BinaryFormatter</span><span class="sxs-lookup"><span data-stu-id="76e55-103">BinaryFormatter event source</span></span>

<span data-ttu-id="76e55-104">A partir de .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> incluye un elemento <xref:System.Diagnostics.Tracing.EventSource> integrado que le permite ver cuándo se produce la serialización o deserialización de objetos.</span><span class="sxs-lookup"><span data-stu-id="76e55-104">Starting with .NET 5.0, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> includes a built-in <xref:System.Diagnostics.Tracing.EventSource> that gives you visibility into when an object serialization or deserialization is occurring.</span></span> <span data-ttu-id="76e55-105">Las aplicaciones pueden usar tipos derivados de <xref:System.Diagnostics.Tracing.EventListener> para escuchar estas notificaciones y registrarlas.</span><span class="sxs-lookup"><span data-stu-id="76e55-105">Apps can use <xref:System.Diagnostics.Tracing.EventListener>-derived types to listen for these notifications and log them.</span></span>

<span data-ttu-id="76e55-106">Esta funcionalidad no sustituye a <xref:System.Runtime.Serialization.SerializationBinder> o <xref:System.Runtime.Serialization.ISerializationSurrogate> y se puede usar para modificar los datos que se serializan o deserializan.</span><span class="sxs-lookup"><span data-stu-id="76e55-106">This functionality is not a substitute for a <xref:System.Runtime.Serialization.SerializationBinder> or an <xref:System.Runtime.Serialization.ISerializationSurrogate> and can't be used to modify the data being serialized or deserialized.</span></span> <span data-ttu-id="76e55-107">Más bien, este sistema de eventos está diseñado para proporcionar información sobre los tipos que se serializan o deserializan.</span><span class="sxs-lookup"><span data-stu-id="76e55-107">Rather, this eventing system is intended to provide insight into the types being serialized or deserialized.</span></span> <span data-ttu-id="76e55-108">También se puede usar para detectar llamadas imprevistas en la infraestructura `BinaryFormatter`, como las que se originan desde código de biblioteca de terceros.</span><span class="sxs-lookup"><span data-stu-id="76e55-108">It can also be used to detect unintended calls into the `BinaryFormatter` infrastructure, such as calls originating from third-party library code.</span></span>

## <a name="description-of-events"></a><span data-ttu-id="76e55-109">Descripción de eventos</span><span class="sxs-lookup"><span data-stu-id="76e55-109">Description of events</span></span>

<span data-ttu-id="76e55-110">El origen del evento `BinaryFormatter` tiene el nombre conocido `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span><span class="sxs-lookup"><span data-stu-id="76e55-110">The `BinaryFormatter` event source has the well-known name `System.Runtime.Serialization.Formatters.Binary.BinaryFormatterEventSource`.</span></span> <span data-ttu-id="76e55-111">Los agentes de escucha se pueden suscribir a seis eventos.</span><span class="sxs-lookup"><span data-stu-id="76e55-111">Listeners may subscribe to 6 events.</span></span>

### <a name="serializationstart-event-id--10"></a><span data-ttu-id="76e55-112">Evento SerializationStart (id. = `10`)</span><span class="sxs-lookup"><span data-stu-id="76e55-112">SerializationStart event (id = `10`)</span></span>

<span data-ttu-id="76e55-113">Se genera cuando se ha llamado a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> y se ha iniciado el proceso de serialización.</span><span class="sxs-lookup"><span data-stu-id="76e55-113">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Serialize%2A?displayProperty=nameWithType> has been called and has started the serialization process.</span></span> <span data-ttu-id="76e55-114">Este evento se empareja con el evento `SerializationEnd`.</span><span class="sxs-lookup"><span data-stu-id="76e55-114">This event is paired with the `SerializationEnd` event.</span></span> <span data-ttu-id="76e55-115">Se puede llamar al evento `SerializationStart` de forma recursiva si un objeto llama a `BinaryFormatter.Serialize` dentro de su propia rutina de serialización.</span><span class="sxs-lookup"><span data-stu-id="76e55-115">The `SerializationStart` event can be called recursively if an object calls `BinaryFormatter.Serialize` within its own serialization routine.</span></span>

<span data-ttu-id="76e55-116">Este evento no contiene una carga útil.</span><span class="sxs-lookup"><span data-stu-id="76e55-116">This event doesn't contain a payload.</span></span>

### <a name="serializationend-event-id--11"></a><span data-ttu-id="76e55-117">Evento SerializationEnd (id. = `11`)</span><span class="sxs-lookup"><span data-stu-id="76e55-117">SerializationEnd event (id = `11`)</span></span>

<span data-ttu-id="76e55-118">Se genera cuando `BinaryFormatter.Serialize` ha completado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="76e55-118">Raised when `BinaryFormatter.Serialize` has completed its work.</span></span> <span data-ttu-id="76e55-119">Cada aparición de `SerializationEnd` indica la finalización del último evento de `SerializationStart` no emparejado.</span><span class="sxs-lookup"><span data-stu-id="76e55-119">Each occurrence of `SerializationEnd` denotes the completion of the last unpaired `SerializationStart` event.</span></span>

<span data-ttu-id="76e55-120">Este evento no contiene una carga útil.</span><span class="sxs-lookup"><span data-stu-id="76e55-120">This event doesn't contain a payload.</span></span>

### <a name="serializingobject-event-id--12"></a><span data-ttu-id="76e55-121">Evento SerializingObject (id. = `12`)</span><span class="sxs-lookup"><span data-stu-id="76e55-121">SerializingObject event (id = `12`)</span></span>

<span data-ttu-id="76e55-122">Se genera cuando `BinaryFormatter.Serialize` está en el proceso de serializar un tipo no primitivo.</span><span class="sxs-lookup"><span data-stu-id="76e55-122">Raised when `BinaryFormatter.Serialize` is in the process of serializing a non-primitive type.</span></span> <span data-ttu-id="76e55-123">La infraestructura `BinaryFormatter` tiene determinados tipos de casos especiales (como `string` y `int`) y no genera un evento cuando se encuentran estos tipos.</span><span class="sxs-lookup"><span data-stu-id="76e55-123">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="76e55-124">Este evento se genera para los tipos definidos por el usuario y otros tipos que `BinaryFormatter` no entiende de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="76e55-124">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="76e55-125">Este evento puede producirse cero o más veces entre los eventos `SerializationStart` y `SerializationEnd`.</span><span class="sxs-lookup"><span data-stu-id="76e55-125">This event may be raised zero or more times between `SerializationStart` and `SerializationEnd` events.</span></span>

<span data-ttu-id="76e55-126">Este evento contiene una carga con un argumento:</span><span class="sxs-lookup"><span data-stu-id="76e55-126">This event contains a payload with one argument:</span></span>

* <span data-ttu-id="76e55-127">`typeName` (`string`): nombre calificado con el ensamblado (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) del tipo que se serializa.</span><span class="sxs-lookup"><span data-stu-id="76e55-127">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being serialized.</span></span>

### <a name="deserializationstart-event-id--20"></a><span data-ttu-id="76e55-128">Evento DeserializationStart (id. = `20`)</span><span class="sxs-lookup"><span data-stu-id="76e55-128">DeserializationStart event (id = `20`)</span></span>

<span data-ttu-id="76e55-129">Se genera cuando se ha llamado a <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> y se ha iniciado el proceso de deserialización.</span><span class="sxs-lookup"><span data-stu-id="76e55-129">Raised when <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter.Deserialize%2A?displayProperty=nameWithType> has been called and has started the deserialization process.</span></span> <span data-ttu-id="76e55-130">Este evento se empareja con el evento `DeserializationEnd`.</span><span class="sxs-lookup"><span data-stu-id="76e55-130">This event is paired with the `DeserializationEnd` event.</span></span> <span data-ttu-id="76e55-131">Se puede llamar al evento `DeserializationStart` de forma recursiva si un objeto llama a `BinaryFormatter.Deserialize` dentro de su propia rutina de deserialización.</span><span class="sxs-lookup"><span data-stu-id="76e55-131">The `DeserializationStart` event can be called recursively if an object calls `BinaryFormatter.Deserialize` within its own deserialization routine.</span></span>

<span data-ttu-id="76e55-132">Este evento no contiene una carga útil.</span><span class="sxs-lookup"><span data-stu-id="76e55-132">This event doesn't contain a payload.</span></span>

### <a name="deserializationend-event-id--21"></a><span data-ttu-id="76e55-133">Evento DeserializationEnd (id. = `21`)</span><span class="sxs-lookup"><span data-stu-id="76e55-133">DeserializationEnd event (id = `21`)</span></span>

<span data-ttu-id="76e55-134">Se genera cuando `BinaryFormatter.Deserialize` ha completado su trabajo.</span><span class="sxs-lookup"><span data-stu-id="76e55-134">Raised when `BinaryFormatter.Deserialize` has completed its work.</span></span> <span data-ttu-id="76e55-135">Cada aparición de `DeserializationEnd` indica la finalización del último evento de `DeserializationStart` no emparejado.</span><span class="sxs-lookup"><span data-stu-id="76e55-135">Each occurrence of `DeserializationEnd` denotes the completion of the last unpaired `DeserializationStart` event.</span></span>

<span data-ttu-id="76e55-136">Este evento no contiene una carga útil.</span><span class="sxs-lookup"><span data-stu-id="76e55-136">This event doesn't contain a payload.</span></span>

### <a name="deserializingobject-event-id--22"></a><span data-ttu-id="76e55-137">Evento DeserializingObject (id. = `22`)</span><span class="sxs-lookup"><span data-stu-id="76e55-137">DeserializingObject event (id = `22`)</span></span>

<span data-ttu-id="76e55-138">Se genera cuando `BinaryFormatter.Deserialize` está en el proceso de deserializar un tipo no primitivo.</span><span class="sxs-lookup"><span data-stu-id="76e55-138">Raised when `BinaryFormatter.Deserialize` is in the process of deserializing a non-primitive type.</span></span> <span data-ttu-id="76e55-139">La infraestructura `BinaryFormatter` tiene determinados tipos de casos especiales (como `string` y `int`) y no genera un evento cuando se encuentran estos tipos.</span><span class="sxs-lookup"><span data-stu-id="76e55-139">The `BinaryFormatter` infrastructure special-cases certain types (such as `string` and `int`) and doesn't raise this event when these types are encountered.</span></span> <span data-ttu-id="76e55-140">Este evento se genera para tipos definidos por el usuario y otros tipos que `BinaryFormatter` no entiende de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="76e55-140">This event is raised for user-defined types and other types that `BinaryFormatter` doesn't natively understand.</span></span>

<span data-ttu-id="76e55-141">Este evento puede producirse cero o más veces entre los eventos `DeserializationStart` y `DeserializationEnd`.</span><span class="sxs-lookup"><span data-stu-id="76e55-141">This event may be raised zero or more times between `DeserializationStart` and `DeserializationEnd` events.</span></span>

<span data-ttu-id="76e55-142">Este evento contiene una carga con un argumento.</span><span class="sxs-lookup"><span data-stu-id="76e55-142">This event contains a payload with one argument.</span></span>

* <span data-ttu-id="76e55-143">`typeName` (`string`): nombre calificado con el ensamblado (consulte <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) del tipo que se deserializa.</span><span class="sxs-lookup"><span data-stu-id="76e55-143">`typeName` (`string`): The assembly-qualified name (see <xref:System.Type.AssemblyQualifiedName?displayProperty=nameWithType>) of the type being deserialized.</span></span>

### <a name="advanced-subscribing-to-a-subset-of-notifications"></a><span data-ttu-id="76e55-144">\[Advanced\] Suscripción a un subconjunto de notificaciones</span><span class="sxs-lookup"><span data-stu-id="76e55-144">\[Advanced\] Subscribing to a subset of notifications</span></span>

<span data-ttu-id="76e55-145">Los agentes de escucha que deseen suscribirse solo a un subconjunto de notificaciones pueden elegir las palabras clave que desean permitir.</span><span class="sxs-lookup"><span data-stu-id="76e55-145">Listeners who wish to subscribe to only a subset of notifications can choose which keywords to enable.</span></span>

* <span data-ttu-id="76e55-146">`Serialization` = `(EventKeywords)1`: genera los eventos `SerializationStart`, `SerializationEnd` y `SerializingObject`.</span><span class="sxs-lookup"><span data-stu-id="76e55-146">`Serialization` = `(EventKeywords)1`: Raises the `SerializationStart`, `SerializationEnd`, and `SerializingObject` events.</span></span>
* <span data-ttu-id="76e55-147">`Deserialization` = `(EventKeywords)2`: genera los eventos `DeserializationStart`, `DeserializationEnd` y `DeserializingObject`.</span><span class="sxs-lookup"><span data-stu-id="76e55-147">`Deserialization` = `(EventKeywords)2`: Raises the `DeserializationStart`, `DeserializationEnd`, and `DeserializingObject` events.</span></span>

<span data-ttu-id="76e55-148">Si no se proporciona ningún filtro de palabras clave durante el registro de `EventListener`, se generan todos los eventos.</span><span class="sxs-lookup"><span data-stu-id="76e55-148">If no keyword filters are provided during `EventListener` registration, all events are raised.</span></span>

<span data-ttu-id="76e55-149">Para obtener más información, vea <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="76e55-149">For more information, see <xref:System.Diagnostics.Tracing.EventKeywords?displayProperty=nameWithType>.</span></span>

## <a name="sample-code"></a><span data-ttu-id="76e55-150">Código de ejemplo</span><span class="sxs-lookup"><span data-stu-id="76e55-150">Sample code</span></span>

<span data-ttu-id="76e55-151">El código siguiente:</span><span class="sxs-lookup"><span data-stu-id="76e55-151">The following code:</span></span>

- <span data-ttu-id="76e55-152">crea un tipo derivado de `EventListener` que escribe en `System.Console`,</span><span class="sxs-lookup"><span data-stu-id="76e55-152">creates an `EventListener`-derived type that writes to `System.Console`,</span></span>
- <span data-ttu-id="76e55-153">suscribe ese agente de escucha a las notificaciones generadas por `BinaryFormatter`,</span><span class="sxs-lookup"><span data-stu-id="76e55-153">subscribes that listener to `BinaryFormatter`-produced notifications,</span></span>
- <span data-ttu-id="76e55-154">serializa y deserializa un gráfico de objetos simple mediante `BinaryFormatter`, y</span><span class="sxs-lookup"><span data-stu-id="76e55-154">serializes and deserializes a simple object graph using `BinaryFormatter`, and</span></span>
- <span data-ttu-id="76e55-155">analiza los eventos que se han generado.</span><span class="sxs-lookup"><span data-stu-id="76e55-155">analyzes the events that have been raised.</span></span>

:::code language="csharp" source="snippets/binaryformatter-event-source/csharp/Program.cs":::

<span data-ttu-id="76e55-156">El código anterior genera una salida similar al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="76e55-156">The preceding code produces output similar to the following example:</span></span>

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

<span data-ttu-id="76e55-157">En este ejemplo, la clase `EventListener` basada en consola registra que la serialización se inicia, se serializan las instancias de `Person` y `Book` y, luego, se completa la serialización.</span><span class="sxs-lookup"><span data-stu-id="76e55-157">In this sample, the console-based `EventListener` logs that serialization starts, instances of `Person` and `Book` are serialized, and then serialization completes.</span></span> <span data-ttu-id="76e55-158">Del mismo modo, una vez que se ha iniciado la deserialización, se deserializan las instancias de `Person` y `Book` y, luego, se completa la operación.</span><span class="sxs-lookup"><span data-stu-id="76e55-158">Similarly, once deserialization has started, instances of `Person` and `Book` are deserialized, and then deserialization completes.</span></span>

<span data-ttu-id="76e55-159">A continuación, la aplicación imprime los valores contenidos en la instancia de `Person` deserializada para demostrar que el objeto en realidad se serializó y deserializó correctamente.</span><span class="sxs-lookup"><span data-stu-id="76e55-159">The app then prints the values contained in the deserialized `Person` to demonstrate that the object did in fact serialize and deserialize properly.</span></span>

## <a name="see-also"></a><span data-ttu-id="76e55-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="76e55-160">See also</span></span>

<span data-ttu-id="76e55-161">Para más información sobre el uso de `EventListener` para recibir notificaciones basadas en `EventSource`, consulte [la clase`EventListener`](xref:System.Diagnostics.Tracing.EventListener).</span><span class="sxs-lookup"><span data-stu-id="76e55-161">For more information on using `EventListener` to receive `EventSource`-based notifications, see [the `EventListener` class](xref:System.Diagnostics.Tracing.EventListener).</span></span>
