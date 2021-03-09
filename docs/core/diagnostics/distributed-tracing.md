---
title: 'Seguimiento distribuido: .NET'
description: Una introducción al seguimiento distribuido de .NET.
ms.date: 02/02/2021
ms.openlocfilehash: 44022232d4451f8d8a255a352206d7bdc9cb4e5c
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105576"
---
# <a name="net-distributed-tracing"></a><span data-ttu-id="a054e-103">Seguimiento distribuido de .NET</span><span class="sxs-lookup"><span data-stu-id="a054e-103">.NET Distributed Tracing</span></span>

<span data-ttu-id="a054e-104">El seguimiento distribuido es la manera de publicar y observar los datos de seguimiento en un sistema distribuido.</span><span class="sxs-lookup"><span data-stu-id="a054e-104">Distributed tracing is the way to publish and observe tracing data in a distributed system.</span></span>
<span data-ttu-id="a054e-105">.NET Framework y .NET Core han admitido el seguimiento a través de las API de <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="a054e-105">.NET Framework and .NET Core has been supporting tracing through the <xref:System.Diagnostics> APIs.</span></span>

- <span data-ttu-id="a054e-106">Clase <xref:System.Diagnostics.Activity?displayProperty=nameWithType>, que permite almacenar el contexto de diagnósticos, acceder a él y consumirlo con el sistema de registro.</span><span class="sxs-lookup"><span data-stu-id="a054e-106"><xref:System.Diagnostics.Activity?displayProperty=nameWithType> class which allows storing and accessing diagnostics context and consuming it with logging system.</span></span>
- <span data-ttu-id="a054e-107"><xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>, que permite instrumentar el código para el registro en tiempo de producción de las cargas de datos enriquecidos para su uso dentro del proceso que se ha instrumentado.</span><span class="sxs-lookup"><span data-stu-id="a054e-107"><xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType> that allows code to be instrumented for production-time logging of rich data payloads for consumption within the process that was instrumented.</span></span>

<span data-ttu-id="a054e-108">Este es un ejemplo que muestra cómo publicar datos de seguimiento de las solicitudes HTTP entrantes:</span><span class="sxs-lookup"><span data-stu-id="a054e-108">Here is an example that shows how to publish tracing data from the HTTP incoming requests:</span></span>

```csharp
   public void OnIncomingRequest(DiagnosticListener httpListener, HttpContext context)
   {
       if (httpListener.IsEnabled("Http_In"))
       {
           var activity = new Activity("Http_In");

           //add tags, baggage, etc.
           activity.SetParentId(context.Request.headers["Request-id"])
           foreach (var pair in context.Request.Headers["Correlation-Context"])
           {
               var baggageItem = NameValueHeaderValue.Parse(pair);
               activity.AddBaggage(baggageItem.Key, baggageItem.Value);
           }
           httpListener.StartActivity(activity, new { context });
           try
           {
               //process request ...
           }
           finally
           {
               //stop activity
               httpListener.StopActivity(activity, new {context} );
           }
       }
   }
```

<span data-ttu-id="a054e-109">Este es un ejemplo de cómo escuchar los eventos Activity:</span><span class="sxs-lookup"><span data-stu-id="a054e-109">Here is example for how to listen to the Activity events:</span></span>

```csharp
    DiagnosticListener.AllListeners.Subscribe(delegate (DiagnosticListener listener)
    {
        if (listener.Name == "MyActivitySource")
        {
            listener.Subscribe(delegate (KeyValuePair<string, object> value)
            {
                if (value.Key.EndsWith("Start", StringComparison.Ordinal))
                    LogActivityStart();
                else if (value.Key.EndsWith("Stop", StringComparison.Ordinal))
                    LogActivityStop();
            });
        }
    }
```

<span data-ttu-id="a054e-110">.NET 5.0 ha extendido la capacidad del seguimiento distribuido para permitir los escenarios de seguimiento de [OpenTelemetry](https://opentelemetry.io/), las funcionalidades de muestreo agregadas, el patrón de codificación de seguimiento simplificado y ha hecho que la escucha de eventos Activity sea más sencilla y flexible.</span><span class="sxs-lookup"><span data-stu-id="a054e-110">.NET 5.0 has extended the capability of the distributed tracing to allow the [OpenTelemetry](https://opentelemetry.io/) tracing scenarios, added Sampling capabilities, simplified the tracing coding pattern, and made listening to the Activity events easier and flexible.</span></span>

> [!NOTE]
> <span data-ttu-id="a054e-111">Para acceder a todas las funcionalidades de .NET 5.0 agregadas, asegúrese de que el proyecto hace referencia a la versión 5.0 o posterior del paquete NuGet [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/).</span><span class="sxs-lookup"><span data-stu-id="a054e-111">To access all added .NET 5.0 capabilities, ensure your project references the [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/) NuGet package version 5.0 or later.</span></span> <span data-ttu-id="a054e-112">Este paquete se puede usar en bibliotecas y aplicaciones que tienen como destino cualquier versión compatible de .NET Framework, .NET Core y .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="a054e-112">This package can be used in libraries and apps targeting any supported version of the .NET Framework, .NET Core, and .NET Standard.</span></span> <span data-ttu-id="a054e-113">Si el destino es .NET 5.0 o posterior, no es necesario hacer referencia manualmente al paquete, ya que se incluye en la biblioteca compartida instalada con el entorno de ejecución .NET.</span><span class="sxs-lookup"><span data-stu-id="a054e-113">If targeting .NET 5.0 or later, there is no need to manually reference the package as it is included in the shared library installed with the .NET Runtime.</span></span>

## <a name="getting-started-with-tracing"></a><span data-ttu-id="a054e-114">Introducción al seguimiento</span><span class="sxs-lookup"><span data-stu-id="a054e-114">Getting Started With Tracing</span></span>

<span data-ttu-id="a054e-115">Las aplicaciones y bibliotecas pueden publicar fácilmente datos de seguimiento simplemente usando las clases <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> y <xref:System.Diagnostics.Activity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a054e-115">Applications and libraries can easily publish tracing data by simply using the <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> and the <xref:System.Diagnostics.Activity?displayProperty=nameWithType> classes.</span></span>

### <a name="activitysource"></a><span data-ttu-id="a054e-116">ActivitySource</span><span class="sxs-lookup"><span data-stu-id="a054e-116">ActivitySource</span></span>

<span data-ttu-id="a054e-117">El primer paso para publicar datos de seguimiento es crear una instancia de la clase ActivitySource.</span><span class="sxs-lookup"><span data-stu-id="a054e-117">The first step to publish tracing data is to create an instance of the ActivitySource class.</span></span> <span data-ttu-id="a054e-118">ActivitySource es la clase que proporciona las API para crear e iniciar objetos Activity y registrar objetos ActivityListener para escuchar los eventos Activity.</span><span class="sxs-lookup"><span data-stu-id="a054e-118">The ActivitySource is the class that provides APIs to create and start Activity objects and to register ActivityListener objects to listen to the Activity events.</span></span>

```csharp
    private static ActivitySource source = new ActivitySource("MyCompany.MyComponent.SourceName", "v1");
```

#### <a name="best-practices"></a><span data-ttu-id="a054e-119">Prácticas recomendadas</span><span class="sxs-lookup"><span data-stu-id="a054e-119">Best Practices</span></span>

- <span data-ttu-id="a054e-120">Cree la clase ActivitySource una vez, almacénela en una variable estática y use esa instancia siempre que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="a054e-120">Create the ActivitySource once and store it in a static variable and use that instance as long as needed.</span></span>

- <span data-ttu-id="a054e-121">El nombre de origen que se pasa al constructor debe ser único para evitar conflictos con otros orígenes.</span><span class="sxs-lookup"><span data-stu-id="a054e-121">The source name passed to the constructor has to be unique to avoid the conflicts with any other sources.</span></span> <span data-ttu-id="a054e-122">Se recomienda usar un nombre jerárquico que contenga el nombre de la compañía, el nombre del componente y el nombre del origen.</span><span class="sxs-lookup"><span data-stu-id="a054e-122">It is recommended to use a hierarchical name contains the company name, the component name, and the source name.</span></span> <span data-ttu-id="a054e-123">Por ejemplo, `Microsoft.System.HttpClient.HttpInOutRequests`.</span><span class="sxs-lookup"><span data-stu-id="a054e-123">For example, `Microsoft.System.HttpClient.HttpInOutRequests`.</span></span>

- <span data-ttu-id="a054e-124">El parámetro de versión es opcional.</span><span class="sxs-lookup"><span data-stu-id="a054e-124">The version parameter is optional.</span></span> <span data-ttu-id="a054e-125">Se recomienda proporcionar la versión en caso de que tenga previsto publicar varias versiones de la biblioteca o la aplicación y desee distinguir entre los orígenes de versiones diferentes.</span><span class="sxs-lookup"><span data-stu-id="a054e-125">It is recommended to provide the version in case you plan to release multiple versions of the library or the application and want to distinguish between the sources of different versions.</span></span>

### <a name="activity-creation"></a><span data-ttu-id="a054e-126">Creación de objetos Activity</span><span class="sxs-lookup"><span data-stu-id="a054e-126">Activity Creation</span></span>

<span data-ttu-id="a054e-127">Ahora se puede usar el objeto ActivitySource creado para crear e iniciar objetos Activity que se usan para registrar los datos de seguimiento en cualquier lugar deseado del código.</span><span class="sxs-lookup"><span data-stu-id="a054e-127">Now the created ActivitySource object can be used to create and start Activity objects which are used to log any tracing data in any desired places in the code.</span></span>

```csharp
        using (Activity activity = source.StartActivity("OperationName"))
        {
            // Do something

            activity?.AddTag("key", "value"); // log the tracing
        }
```

<span data-ttu-id="a054e-128">Este código de ejemplo intenta crear el objeto de actividad y, a continuación, registra algunas `key` de etiqueta de seguimiento y `value`.</span><span class="sxs-lookup"><span data-stu-id="a054e-128">This sample code tries to create the Activity object and then logs some tracing tag `key` and `value`.</span></span>

#### <a name="notes"></a><span data-ttu-id="a054e-129">Notas</span><span class="sxs-lookup"><span data-stu-id="a054e-129">Notes</span></span>

- <span data-ttu-id="a054e-130">`ActivitySource.StartActivity` intenta crear e iniciar la actividad al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="a054e-130">`ActivitySource.StartActivity` tries to create and start the activity at the same time.</span></span> <span data-ttu-id="a054e-131">El patrón de código escuchado usa el bloque `using`, que desecha automáticamente el objeto Activity creado después de ejecutar el bloque.</span><span class="sxs-lookup"><span data-stu-id="a054e-131">The listed code pattern is using the `using` block which automatically disposes the created Activity object after executing the block.</span></span> <span data-ttu-id="a054e-132">Al desechar el objeto Activity, se detendrá esta actividad iniciada y el código no tendrá que detener explícitamente la actividad.</span><span class="sxs-lookup"><span data-stu-id="a054e-132">Disposing the Activity object will stop this started activity and the code doesn't have to explicitly stop the activity.</span></span> <span data-ttu-id="a054e-133">Esto simplifica el patrón de codificación.</span><span class="sxs-lookup"><span data-stu-id="a054e-133">That simplifies the coding pattern.</span></span>

- <span data-ttu-id="a054e-134">`ActivitySource.StartActivity` averigua internamente si hay agentes de escucha en tales eventos.</span><span class="sxs-lookup"><span data-stu-id="a054e-134">`ActivitySource.StartActivity` internally figures out if there are any listeners to such events.</span></span> <span data-ttu-id="a054e-135">Si no hay agentes de escucha registrados o hay agentes de escucha que no están interesados en este tipo de evento, `ActivitySource.StartActivity` simplemente devolverá `null` y evitará la creación del objeto Activity.</span><span class="sxs-lookup"><span data-stu-id="a054e-135">If there are no registered listeners or there are listeners which are not interested in such an event, `ActivitySource.StartActivity` simply will return `null` and avoid creating the Activity object.</span></span> <span data-ttu-id="a054e-136">Esa es la razón por la que el código utilizó el operador que admite un valor NULL `?` en la instrucción `activity?.AddTag`.</span><span class="sxs-lookup"><span data-stu-id="a054e-136">That is why the code used the nullable operator `?`  in the statement `activity?.AddTag`.</span></span> <span data-ttu-id="a054e-137">En general, dentro del bloque `using`, use siempre el operador que admite un valor NULL `?` después del nombre del objeto de la actividad.</span><span class="sxs-lookup"><span data-stu-id="a054e-137">In general, inside the `using` block, always use the nullable operator `?` after the activity object name.</span></span>

## <a name="listening-to-the-activity-events"></a><span data-ttu-id="a054e-138">Escucha de eventos Activity</span><span class="sxs-lookup"><span data-stu-id="a054e-138">Listening to the Activity Events</span></span>

<span data-ttu-id="a054e-139">.NET proporciona la clase <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType>, que se puede utilizar para escuchar los eventos Activity desencadenados desde uno o varios ActivitySources.</span><span class="sxs-lookup"><span data-stu-id="a054e-139">.NET provides the class <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType> which can be used to listen to the Activity events triggered from one or more ActivitySources.</span></span>
<span data-ttu-id="a054e-140">El agente de escucha se puede usar para recopilar datos de seguimiento, muestrear o exigir la creación del objeto Activity.</span><span class="sxs-lookup"><span data-stu-id="a054e-140">The listener can be used to collect tracing data, sample, or force creating the Activity object.</span></span>

<span data-ttu-id="a054e-141">La clase `ActivityListener` proporciona distintas devoluciones de llamada para controlar los distintos eventos.</span><span class="sxs-lookup"><span data-stu-id="a054e-141">The `ActivityListener` class provides a different callbacks to handle different events.</span></span>

```csharp
var listener = new ActivityListener
{
    ShouldListenTo = (activitySource) => object.ReferenceEquals(source, activitySource),
    ActivityStarted = activity => /* Handle the Activity start event here */ DoSomething(),
    ActivityStopped = activity => /* Handle the Activity stop event here */ DoSomething(),
    SampleUsingParentId = (ref ActivityCreationOptions<string> activityOptions) => ActivitySamplingResult.AllData,
    Sample = (ref ActivityCreationOptions<ActivityContext> activityOptions) => ActivitySamplingResult.AllData
};

// Enable the listener
ActivitySource.AddActivityListener(listener);
```

- <span data-ttu-id="a054e-142">`ShouldListenTo` permite escuchar objetos `ActivitySource` específicos.</span><span class="sxs-lookup"><span data-stu-id="a054e-142">`ShouldListenTo` enables listening to specific `ActivitySource` objects.</span></span> <span data-ttu-id="a054e-143">En el ejemplo, permite escuchar el objeto `ActivitySource` que se ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a054e-143">In the example, it enables listening to the `ActivitySource` object we have previously created.</span></span> <span data-ttu-id="a054e-144">Hay más flexibilidad para escuchar cualquier otro objeto `ActivitySource` comprobando los parámetros `Name` y `Version` de la entrada `ActivitySource`.</span><span class="sxs-lookup"><span data-stu-id="a054e-144">There is more flexibility to listen to any other `ActivitySource` objects by checking the `Name` and `Version` of the input `ActivitySource`.</span></span>

- <span data-ttu-id="a054e-145">`ActivityStarted` y `ActivityStopped` permiten obtener los eventos Start y Open de `Activity` para todos los objetos `Activity` creados por los objetos `ActivitySource` que se habilitaron mediante la devolución de llamada `ShouldListenTo`.</span><span class="sxs-lookup"><span data-stu-id="a054e-145">`ActivityStarted` and `ActivityStopped` enable getting the `Activity` Start and Stop events for all `Activity` objects created by the `ActivitySource` objects which were enabled by the `ShouldListenTo` callback.</span></span>

- <span data-ttu-id="a054e-146">`Sample` y `SampleUsingParentId` son las devoluciones de llamada principales destinadas al muestreo.</span><span class="sxs-lookup"><span data-stu-id="a054e-146">`Sample` and `SampleUsingParentId` are the main callbacks which intended for sampling.</span></span> <span data-ttu-id="a054e-147">Estas dos devoluciones de llamada devuelven el valor de enumeración `ActivitySamplingResult`, que puede indicar si se muestrea dentro o fuera de la solicitud de creación de `Activity` actual.</span><span class="sxs-lookup"><span data-stu-id="a054e-147">These two callbacks return the `ActivitySamplingResult` enum value which can tell either to sample in or out the current `Activity` creation request.</span></span> <span data-ttu-id="a054e-148">Si la devolución de llamada devuelve `ActivitySamplingResult.None` y ningún otro agente de escucha habilitado devuelve un valor diferente, el objeto Activity no se creará y `ActivitySource.StartActivity` devolverá `null`.</span><span class="sxs-lookup"><span data-stu-id="a054e-148">If the callback returns `ActivitySamplingResult.None` and no other enabled listeners return different value, then the Activity will not get created and `ActivitySource.StartActivity` will return `null`.</span></span> <span data-ttu-id="a054e-149">De lo contrario, se creará el objeto `Activity`.</span><span class="sxs-lookup"><span data-stu-id="a054e-149">Otherwise, the `Activity` object will get created.</span></span>

## <a name="net-50-new-features"></a><span data-ttu-id="a054e-150">Nuevas características de .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a054e-150">.NET 5.0 New Features</span></span>

<span data-ttu-id="a054e-151">Durante un tiempo, la clase `Activity` ha admitido escenarios de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a054e-151">For awhile the `Activity` class has been supporting tracing scenarios.</span></span> <span data-ttu-id="a054e-152">Permitía agregar etiquetas, que son pares clave-valor de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a054e-152">It allowed adding tags which are key-value pairs of tracing data.</span></span> <span data-ttu-id="a054e-153">Ha admitido equipajes, que son pares clave-valor pensados para propagarse a través de la conexión.</span><span class="sxs-lookup"><span data-stu-id="a054e-153">It has been supporting Baggage which is are key-value pairs intended to be propagated across the wire.</span></span>

<span data-ttu-id="a054e-154">.NET 5.0 admite más características, principalmente para habilitar escenarios OpenTelemetry.</span><span class="sxs-lookup"><span data-stu-id="a054e-154">.NET 5.0 supports more features mainly to enable OpenTelemetry scenarios.</span></span>

### <a name="activitycontext"></a><span data-ttu-id="a054e-155">ActivityContext</span><span class="sxs-lookup"><span data-stu-id="a054e-155">ActivityContext</span></span>

<span data-ttu-id="a054e-156"><xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType> es el struct que lleva el contexto de las operaciones de seguimiento (por ejemplo, el identificador de seguimiento, el identificador de intervalo, las marcas de seguimiento y el estado de seguimiento).</span><span class="sxs-lookup"><span data-stu-id="a054e-156"><xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType> is the struct carrying the context of the tracing operations (e.g. the trace Id, Span Id, trace flags, and trace state).</span></span> <span data-ttu-id="a054e-157">Ahora es posible crear un nuevo `Activity` proporcionando el contexto de seguimiento primario.</span><span class="sxs-lookup"><span data-stu-id="a054e-157">Now it is possible to create a new `Activity` providing the parent tracing context.</span></span> <span data-ttu-id="a054e-158">Además, es fácil extraer el contexto de seguimiento a partir de cualquier objeto `Activity` llamando a la propiedad `Activity.Context`.</span><span class="sxs-lookup"><span data-stu-id="a054e-158">Also, it is easy to extract the tracing context from any `Activity` object by calling `Activity.Context` property.</span></span>

### <a name="activitylink"></a><span data-ttu-id="a054e-159">ActivityLink</span><span class="sxs-lookup"><span data-stu-id="a054e-159">ActivityLink</span></span>

<span data-ttu-id="a054e-160"><xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType> es el struct que contiene la instancia de contexto de seguimiento, que se puede vincular a objetos `Activity` relacionados de forma ocasional.</span><span class="sxs-lookup"><span data-stu-id="a054e-160"><xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType> is the struct containing the tracing context instance which can be linked to casually related `Activity` objects.</span></span> <span data-ttu-id="a054e-161">Se pueden agregar vínculos al objeto `Activity` si se pasa la lista de vínculos al método `ActivitySource.StartActivity` al crear `Activity`.</span><span class="sxs-lookup"><span data-stu-id="a054e-161">Links can be added to the `Activity` object by passing the links list to `ActivitySource.StartActivity` method when creating the `Activity`.</span></span> <span data-ttu-id="a054e-162">Los vínculos adjuntos del objeto `Activity` se pueden recuperar mediante la propiedad `Activity.Links`.</span><span class="sxs-lookup"><span data-stu-id="a054e-162">The `Activity` object attached links can be retrieved using the property `Activity.Links`.</span></span>

### <a name="activityevent"></a><span data-ttu-id="a054e-163">ActivityEvent</span><span class="sxs-lookup"><span data-stu-id="a054e-163">ActivityEvent</span></span>

<span data-ttu-id="a054e-164"><xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType> un evento que contiene un nombre y una marca de tiempo, así como una lista opcional de etiquetas.</span><span class="sxs-lookup"><span data-stu-id="a054e-164"><xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType> represents an event containing a name and a timestamp, as well as an optional list of tags.</span></span> <span data-ttu-id="a054e-165">Se pueden agregar eventos al objeto `Activity` llamando al método `Activity.AddEvent`.</span><span class="sxs-lookup"><span data-stu-id="a054e-165">Events can be added to the `Activity` object by calling `Activity.AddEvent` method.</span></span> <span data-ttu-id="a054e-166">La lista completa de los eventos del objeto `Activity` se puede recuperar utilizando la propiedad `Activity.Events`.</span><span class="sxs-lookup"><span data-stu-id="a054e-166">The whole list of the `Activity` object Events can be retrieved using the property `Activity.Events`.</span></span>

### <a name="activitykind"></a><span data-ttu-id="a054e-167">ActivityKind</span><span class="sxs-lookup"><span data-stu-id="a054e-167">ActivityKind</span></span>

<span data-ttu-id="a054e-168"><xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType> describe la relación entre la actividad, sus elementos primarios y sus elementos secundarios en un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a054e-168"><xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType> describes the relationship between the activity, its parents and its children in a trace.</span></span> <span data-ttu-id="a054e-169">El tipo se puede establecer en el objeto `Activity` si se pasa el valor del tipo al método `ActivitySource.StartActivity` al crear `Activity`.</span><span class="sxs-lookup"><span data-stu-id="a054e-169">Kind can be set to the `Activity` object by passing the kind value to `ActivitySource.StartActivity` method when creating the `Activity`.</span></span> <span data-ttu-id="a054e-170">El tipo del objeto `Activity` se recupera con la propiedad `Activity.Kind`.</span><span class="sxs-lookup"><span data-stu-id="a054e-170">The `Activity` object kind can be retrieved using the property `Activity.Kind`.</span></span>

### <a name="isalldatarequested"></a><span data-ttu-id="a054e-171">IsAllDataRequested</span><span class="sxs-lookup"><span data-stu-id="a054e-171">IsAllDataRequested</span></span>

<span data-ttu-id="a054e-172"><xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType> indica si esta actividad se debe rellenar con toda la información de propagación, así como todas las demás propiedades, como vínculos, etiquetas y eventos.</span><span class="sxs-lookup"><span data-stu-id="a054e-172"><xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType> indicates whether this activity should be populated with all the propagation information, as well as all the other properties, such as links, tags, and events.</span></span> <span data-ttu-id="a054e-173">El valor de `IsAllDataRequested` se determina a partir del resultado devuelto de todas las devoluciones de llamada `Sample` y `SampleUsingParentId` de los agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="a054e-173">The value of `IsAllDataRequested` is determined from the result returned from all listeners `Sample` and `SampleUsingParentId` callbacks.</span></span> <span data-ttu-id="a054e-174">El valor se puede recuperar mediante la propiedad `Activity.IsAllDataRequested`.</span><span class="sxs-lookup"><span data-stu-id="a054e-174">The value can be retrieved using `Activity.IsAllDataRequested` property.</span></span>

### <a name="activitysource"></a><span data-ttu-id="a054e-175">Activity.Source</span><span class="sxs-lookup"><span data-stu-id="a054e-175">Activity.Source</span></span>

<span data-ttu-id="a054e-176"><xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType> obtiene el origen de la actividad asociado a esta actividad.</span><span class="sxs-lookup"><span data-stu-id="a054e-176"><xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType> gets the activity source associated with this activity.</span></span>

### <a name="activitydisplayname"></a><span data-ttu-id="a054e-177">Activity.DisplayName</span><span class="sxs-lookup"><span data-stu-id="a054e-177">Activity.DisplayName</span></span>

<span data-ttu-id="a054e-178"><xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType> permite obtener o establecer un nombre para mostrar para la actividad.</span><span class="sxs-lookup"><span data-stu-id="a054e-178"><xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType> allows getting or setting a display name for the activity.</span></span>

### <a name="activitytagobjects"></a><span data-ttu-id="a054e-179">Activity.TagObjects</span><span class="sxs-lookup"><span data-stu-id="a054e-179">Activity.TagObjects</span></span>

<span data-ttu-id="a054e-180">La clase `Activity` tiene la propiedad `Activity.Tags` que devuelve la lista de pares clave-valor de las etiquetas de tipo cadena para la clave y el valor.</span><span class="sxs-lookup"><span data-stu-id="a054e-180">`Activity` class has the property `Activity.Tags` which return the a key-value pair list of the tags of type string for the key and value.</span></span> <span data-ttu-id="a054e-181">Tales etiquetas se agregan a `Activity` mediante el método `AddTag(string, string)`.</span><span class="sxs-lookup"><span data-stu-id="a054e-181">Such Tags can be added to the `Activity` using the method `AddTag(string, string)`.</span></span> <span data-ttu-id="a054e-182">`Activity` ha ampliado la compatibilidad de etiquetas proporcionando el método sobrecargado `AddTag(string, object)` que permite valores de cualquier tipo.</span><span class="sxs-lookup"><span data-stu-id="a054e-182">`Activity` has extended the support of tags by providing the overloaded method `AddTag(string, object)` allowing values of any type.</span></span>  <span data-ttu-id="a054e-183">La lista completa de estas etiquetas se puede recuperar mediante <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a054e-183">The complete list of such tags can be retrieved using <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>.</span></span>

## <a name="sampling"></a><span data-ttu-id="a054e-184">muestreo</span><span class="sxs-lookup"><span data-stu-id="a054e-184">Sampling</span></span>

<span data-ttu-id="a054e-185">El muestreo es un mecanismo para controlar el ruido y la sobrecarga mediante la reducción del número de muestras de seguimiento recopiladas y enviadas al back-end.</span><span class="sxs-lookup"><span data-stu-id="a054e-185">Sampling is a mechanism to control the noise and overhead by reducing the number of samples of traces collected and sent to the backend.</span></span> <span data-ttu-id="a054e-186">El muestreo es un escenario importante de OpenTelemetry.</span><span class="sxs-lookup"><span data-stu-id="a054e-186">Sampling is an important OpenTelemetry scenario.</span></span> <span data-ttu-id="a054e-187">En .NET 5.0 es fácil permitir el muestreo.</span><span class="sxs-lookup"><span data-stu-id="a054e-187">In .NET 5.0 it is easy to allow sampling.</span></span> <span data-ttu-id="a054e-188">Una buena práctica es crear los nuevos objetos `Activity` mediante `ActivitySource.StartActivity` e intentar proporcionar todos los datos disponibles posibles (por ejemplo, etiquetas, tipo, vínculos, etc.). al llamar a este método.</span><span class="sxs-lookup"><span data-stu-id="a054e-188">A good practice is to create the new `Activity` objects using `ActivitySource.StartActivity` and try to provide all possible available data (e.g. tags, kind, links, ...etc.) when calling this method.</span></span> <span data-ttu-id="a054e-189">El suministro de los datos permitirá que los muestreadores implementados mediante el `ActivityListener` tengan una decisión de muestreo adecuada.</span><span class="sxs-lookup"><span data-stu-id="a054e-189">Providing the data will allow the samplers implemented using the `ActivityListener` to have a proper sampling decision.</span></span> <span data-ttu-id="a054e-190">Si el rendimiento es crítico para evitar la creación de los datos antes de crear el objeto `Activity`, la propiedad `ActivitySource.HasListeners` resulta útil para comprobar si hay agentes de escucha antes de crear los datos necesarios.</span><span class="sxs-lookup"><span data-stu-id="a054e-190">If the performance is critical to avoid creating the data before creating the `Activity` object, the property `ActivitySource.HasListeners` comes in handy to check if there are any listeners before creating the needed data.</span></span>

## <a name="opentelemetry"></a><span data-ttu-id="a054e-191">OpenTelemetry</span><span class="sxs-lookup"><span data-stu-id="a054e-191">OpenTelemetry</span></span>

<span data-ttu-id="a054e-192">El SDK de OpenTelemetry incluye muchas características que admiten escenarios de seguimiento distribuido de un extremo a otro.</span><span class="sxs-lookup"><span data-stu-id="a054e-192">OpenTelemetry SDK comes with many features that support end-to-end distributed tracing scenarios.</span></span> <span data-ttu-id="a054e-193">Proporciona varios ejemplos y exportadores entre los que puede elegir.</span><span class="sxs-lookup"><span data-stu-id="a054e-193">It provides multiple samplers and exporters which you can choose from.</span></span> <span data-ttu-id="a054e-194">También permite crear muestreadores y exportadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="a054e-194">It allows creating a custom samplers and exporters too.</span></span>

<span data-ttu-id="a054e-195">OpenTelemetry admite la exportación de los datos de seguimiento recopilados a diferentes back-ends (por ejemplo, Jaeger, Zipkin, New Relic, etc.).</span><span class="sxs-lookup"><span data-stu-id="a054e-195">OpenTelemetry supports exporting the collected tracing data to different backends (e.g. Jaeger, Zipkin, New Relic,...etc.).</span></span> <span data-ttu-id="a054e-196">Consulte [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/) para obtener más información y busque Nuget.org para paquetes que comiencen con `OpenTelemetry.Exporter.` para obtener la lista de paquetes del exportador.</span><span class="sxs-lookup"><span data-stu-id="a054e-196">Refer to [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/) for more details and search Nuget.org for packages starting with `OpenTelemetry.Exporter.` to get the exporter packages list.</span></span>

<span data-ttu-id="a054e-197">Este es un código de ejemplo de [Introducción a OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started) que muestra lo fácil que es muestrear datos de seguimiento y exportarlos a la consola.</span><span class="sxs-lookup"><span data-stu-id="a054e-197">Here is sample code ported from [OpenTelemetry-dotnet getting started](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started) showing how easy it is to sample and export tracing data to the console.</span></span>

```csharp
// <copyright file="Program.cs" company="OpenTelemetry Authors">
// Copyright The OpenTelemetry Authors
//
// Licensed under the Apache License, Version 2.0 (the "License");
// you may not use this file except in compliance with the License.
// You may obtain a copy of the License at
//
//     http://www.apache.org/licenses/LICENSE-2.0
//
// Unless required by applicable law or agreed to in writing, software
// distributed under the License is distributed on an "AS IS" BASIS,
// WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
// See the License for the specific language governing permissions and
// limitations under the License.
// </copyright>

using System.Diagnostics;
using OpenTelemetry;
using OpenTelemetry.Trace;

public class Program
{
    private static readonly ActivitySource MyActivitySource = new ActivitySource(
        "MyCompany.MyProduct.MyLibrary");

    public static void Main()
    {
        using var tracerProvider = Sdk.CreateTracerProviderBuilder()
            .SetSampler(new AlwaysOnSampler())
            .AddSource("MyCompany.MyProduct.MyLibrary")
            .AddConsoleExporter()
            .Build();

        using (var activity = MyActivitySource.StartActivity("SayHello"))
        {
            activity?.SetTag("foo", 1);
            activity?.SetTag("bar", "Hello, World!");
            activity?.SetTag("baz", new int[] { 1, 2, 3 });
        }
    }
}
```

<span data-ttu-id="a054e-198">El ejemplo debe hacer referencia al paquete [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2).</span><span class="sxs-lookup"><span data-stu-id="a054e-198">The sample needs to reference the package [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2).</span></span>
