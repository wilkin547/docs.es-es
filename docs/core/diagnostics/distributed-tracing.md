---
title: 'Seguimiento distribuido: .NET'
description: Una introducción al seguimiento distribuido de .NET.
ms.date: 02/02/2021
ms.openlocfilehash: d21d2a978cfe58d89db689dec07107f089363912
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640126"
---
# <a name="net-distributed-tracing"></a>Seguimiento distribuido de .NET

El seguimiento distribuido es la manera de publicar y observar los datos de seguimiento en un sistema distribuido.
.NET Framework y .NET Core han admitido el seguimiento a través de las API de <xref:System.Diagnostics>.

- Clase <xref:System.Diagnostics.Activity?displayProperty=nameWithType>, que permite almacenar el contexto de diagnósticos, acceder a él y consumirlo con el sistema de registro.
- <xref:System.Diagnostics.DiagnosticSource?displayProperty=nameWithType>, que permite instrumentar el código para el registro en tiempo de producción de las cargas de datos enriquecidos para su uso dentro del proceso que se ha instrumentado.

Este es un ejemplo que muestra cómo publicar datos de seguimiento de las solicitudes HTTP entrantes:

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

Este es un ejemplo de cómo escuchar los eventos Activity:

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

.NET 5.0 ha extendido la capacidad del seguimiento distribuido para permitir los escenarios de seguimiento de [OpenTelemetry](https://opentelemetry.io/), las funcionalidades de muestreo agregadas, el patrón de codificación de seguimiento simplificado y ha hecho que la escucha de eventos Activity sea más sencilla y flexible.

> [!NOTE]
> Para acceder a todas las funcionalidades de .NET 5.0 agregadas, asegúrese de que el proyecto hace referencia a la versión 5.0 o posterior del paquete NuGet [System.Diagnostics.DiagnosticSource](https://www.nuget.org/packages/System.Diagnostics.DiagnosticSource/). Este paquete se puede usar en bibliotecas y aplicaciones que tienen como destino cualquier versión compatible de .NET Framework, .NET Core y .NET Standard. Si el destino es .NET 5.0 o posterior, no es necesario hacer referencia manualmente al paquete, ya que se incluye en la biblioteca compartida instalada con el entorno de ejecución .NET.

## <a name="getting-started-with-tracing"></a>Introducción al seguimiento

Las aplicaciones y bibliotecas pueden publicar fácilmente datos de seguimiento simplemente usando las clases <xref:System.Diagnostics.ActivitySource?displayProperty=nameWithType> y <xref:System.Diagnostics.Activity?displayProperty=nameWithType>.

### <a name="activitysource"></a>ActivitySource

El primer paso para publicar datos de seguimiento es crear una instancia de la clase ActivitySource. ActivitySource es la clase que proporciona las API para crear e iniciar objetos Activity y registrar objetos ActivityListener para escuchar los eventos Activity.

```csharp
    internal static ActivitySource source = new ActivitySource("MyCompany.MyComponent.SourceName", "v1");
```

#### <a name="best-practices"></a>Prácticas recomendadas

- Cree la clase ActivitySource una vez, almacénela en una variable estática y use esa instancia siempre que sea necesario.

- El nombre de origen que se pasa al constructor debe ser único para evitar conflictos con otros orígenes. Se recomienda usar un nombre jerárquico que contenga el nombre de la compañía, el nombre del componente y el nombre del origen. Por ejemplo, `Microsoft.System.HttpClient.HttpInOutRequests`.

- El parámetro de versión es opcional. Se recomienda proporcionar la versión en caso de que tenga previsto publicar varias versiones de la biblioteca o la aplicación y desee distinguir entre los orígenes de versiones diferentes.

### <a name="activity-creation"></a>Creación de objetos Activity

Ahora se puede usar el objeto ActivitySource creado para crear e iniciar objetos Activity que se usan para registrar los datos de seguimiento en cualquier lugar deseado del código.

```csharp
        using (Activity activity = source.StartActivity("OperationName"))
        {
            // Do something

            activity?.AddTag("key", "value"); // log the tracing
        }
```

Este código de ejemplo intenta crear el objeto de actividad y, a continuación, registra algunas `key` de etiqueta de seguimiento y `value`.

#### <a name="notes"></a>Notas

- `ActivitySource.StartActivity` intenta crear e iniciar la actividad al mismo tiempo. El patrón de código escuchado usa el bloque `using`, que desecha automáticamente el objeto Activity creado después de ejecutar el bloque. Al desechar el objeto Activity, se detendrá esta actividad iniciada y el código no tendrá que detener explícitamente la actividad. Esto simplifica el patrón de codificación.

- `ActivitySource.StartActivity` averigua internamente si hay agentes de escucha en tales eventos. Si no hay agentes de escucha registrados o hay agentes de escucha que no están interesados en este tipo de evento, `ActivitySource.StartActivity` simplemente devolverá `null` y evitará la creación del objeto Activity. Esa es la razón por la que el código utilizó el operador que admite un valor NULL `?` en la instrucción `activity?.AddTag`. En general, dentro del bloque `using`, use siempre el operador que admite un valor NULL `?` después del nombre del objeto de la actividad.

## <a name="listening-to-the-activity-events"></a>Escucha de eventos Activity

.NET proporciona la clase <xref:System.Diagnostics.ActivityListener?displayProperty=nameWithType>, que se puede utilizar para escuchar los eventos Activity desencadenados desde uno o varios ActivitySources.
El agente de escucha se puede usar para recopilar datos de seguimiento, muestrear o exigir la creación del objeto Activity.

La clase `ActivityListener` proporciona distintas devoluciones de llamada para controlar los distintos eventos.

```csharp

ActivityListener listener = new ActivityListener()

ShouldListenTo = (activitySource) => object.ReferenceEquals(source, activitySource),
ActivityStarted = activity => /* Handle the Activity start event here */ DoSomething(),
ActivityStopped = activity => /* Handle the Activity stop event here */ DoSomething(),
SampleUsingParentId = (ref ActivityCreationOptions<string> activityOptions) => ActivitySamplingResult.AllData,
Sample = (ref ActivityCreationOptions<ActivityContext> activityOptions) => ActivitySamplingResult.AllData

// Enable the listener
ActivitySource.AddActivityListener(listener);
```

- `ShouldListenTo` permite escuchar objetos `ActivitySource` específicos. En el ejemplo, permite escuchar el objeto `ActivitySource` que se ha creado anteriormente. Hay más flexibilidad para escuchar cualquier otro objeto `ActivitySource` comprobando los parámetros `Name` y `Version` de la entrada `ActivitySource`.

- `ActivityStarted` y `ActivityStopped` permiten obtener los eventos Start y Open de `Activity` para todos los objetos `Activity` creados por los objetos `ActivitySource` que se habilitaron mediante la devolución de llamada `ShouldListenTo`.

- `Sample` y `SampleUsingParentId` son las devoluciones de llamada principales destinadas al muestreo. Estas dos devoluciones de llamada devuelven el valor de enumeración `ActivitySamplingResult`, que puede indicar si se muestrea dentro o fuera de la solicitud de creación de `Activity` actual. Si la devolución de llamada devuelve `ActivitySamplingResult.None` y ningún otro agente de escucha habilitado devuelve un valor diferente, el objeto Activity no se creará y `ActivitySource.StartActivity` devolverá `null`. De lo contrario, se creará el objeto `Activity`.

## <a name="net-50-new-features"></a>Nuevas características de .NET 5.0

Durante un tiempo, la clase `Activity` ha admitido escenarios de seguimiento. Permitía agregar etiquetas, que son pares clave-valor de datos de seguimiento. Ha admitido equipajes, que son pares clave-valor pensados para propagarse a través de la conexión.

.NET 5.0 admite más características, principalmente para habilitar escenarios OpenTelemetry.

### <a name="activitycontext"></a>ActivityContext

<xref:System.Diagnostics.ActivityContext?displayProperty=nameWithType> es el struct que lleva el contexto de las operaciones de seguimiento (por ejemplo, el identificador de seguimiento, el identificador de intervalo, las marcas de seguimiento y el estado de seguimiento). Ahora es posible crear un nuevo `Activity` proporcionando el contexto de seguimiento primario. Además, es fácil extraer el contexto de seguimiento a partir de cualquier objeto `Activity` llamando a la propiedad `Activity.Context`.

### <a name="activitylink"></a>ActivityLink

<xref:System.Diagnostics.ActivityLink?displayProperty=nameWithType> es el struct que contiene la instancia de contexto de seguimiento, que se puede vincular a objetos `Activity` relacionados de forma ocasional. Se pueden agregar vínculos al objeto `Activity` si se pasa la lista de vínculos al método `ActivitySource.StartActivity` al crear `Activity`. Los vínculos adjuntos del objeto `Activity` se pueden recuperar mediante la propiedad `Activity.Links`.

### <a name="activityevent"></a>ActivityEvent

<xref:System.Diagnostics.ActivityEvent?displayProperty=nameWithType> un evento que contiene un nombre y una marca de tiempo, así como una lista opcional de etiquetas. Se pueden agregar eventos al objeto `Activity` llamando al método `Activity.AddEvent`. La lista completa de los eventos del objeto `Activity` se puede recuperar utilizando la propiedad `Activity.Events`.

### <a name="activitykind"></a>ActivityKind

<xref:System.Diagnostics.ActivityKind?displayProperty=nameWithType> describe la relación entre la actividad, sus elementos primarios y sus elementos secundarios en un seguimiento. El tipo se puede establecer en el objeto `Activity` si se pasa el valor del tipo al método `ActivitySource.StartActivity` al crear `Activity`. El tipo del objeto `Activity` se recupera con la propiedad `Activity.Kind`.

### <a name="isalldatarequested"></a>IsAllDataRequested

<xref:System.Diagnostics.Activity.IsAllDataRequested?displayProperty=nameWithType> indica si esta actividad se debe rellenar con toda la información de propagación, así como todas las demás propiedades, como vínculos, etiquetas y eventos. El valor de `IsAllDataRequested` se determina a partir del resultado devuelto de todas las devoluciones de llamada `Sample` y `SampleUsingParentId` de los agentes de escucha. El valor se puede recuperar mediante la propiedad `Activity.IsAllDataRequested`.

### <a name="activitysource"></a>Activity.Source

<xref:System.Diagnostics.Activity.Source?displayProperty=nameWithType> obtiene el origen de la actividad asociado a esta actividad.

### <a name="activitydisplayname"></a>Activity.DisplayName

<xref:System.Diagnostics.Activity.DisplayName?displayProperty=nameWithType> permite obtener o establecer un nombre para mostrar para la actividad.

### <a name="activitytagobjects"></a>Activity.TagObjects

La clase `Activity` tiene la propiedad `Activity.Tags` que devuelve la lista de pares clave-valor de las etiquetas de tipo cadena para la clave y el valor. Tales etiquetas se agregan a `Activity` mediante el método `AddTag(string, string)`. `Activity` ha ampliado la compatibilidad de etiquetas proporcionando el método sobrecargado `AddTag(string, object)` que permite valores de cualquier tipo.  La lista completa de estas etiquetas se puede recuperar mediante <xref:System.Diagnostics.Activity.TagObjects?displayProperty=nameWithType>.

## <a name="sampling"></a>muestreo

El muestreo es un mecanismo para controlar el ruido y la sobrecarga mediante la reducción del número de muestras de seguimiento recopiladas y enviadas al back-end. El muestreo es un escenario importante de OpenTelemetry. En .NET 5.0 es fácil permitir el muestreo. Una buena práctica es crear los nuevos objetos `Activity` mediante `ActivitySource.StartActivity` e intentar proporcionar todos los datos disponibles posibles (por ejemplo, etiquetas, tipo, vínculos, etc.). al llamar a este método. El suministro de los datos permitirá que los muestreadores implementados mediante el `ActivityListener` tengan una decisión de muestreo adecuada. Si el rendimiento es crítico para evitar la creación de los datos antes de crear el objeto `Activity`, la propiedad `ActivitySource.HasListeners` resulta útil para comprobar si hay agentes de escucha antes de crear los datos necesarios.

## <a name="opentelemetry"></a>OpenTelemetry

El SDK de OpenTelemetry incluye muchas características que admiten escenarios de seguimiento distribuido de un extremo a otro. Proporciona varios ejemplos y exportadores entre los que puede elegir. También permite crear muestreadores y exportadores personalizados.

OpenTelemetry admite la exportación de los datos de seguimiento recopilados a diferentes back-ends (por ejemplo, Jaeger, Zipkin, New Relic, etc.). Consulte [OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/) para obtener más información y busque Nuget.org para paquetes que comiencen con `OpenTelemetry.Exporter.` para obtener la lista de paquetes del exportador.

Este es un código de ejemplo de [Introducción a OpenTelemetry-dotnet](https://github.com/open-telemetry/opentelemetry-dotnet/tree/main/docs/trace/getting-started) que muestra lo fácil que es muestrear datos de seguimiento y exportarlos a la consola.

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

El ejemplo debe hacer referencia al paquete [OpenTelemetry.Exporter.Console](https://www.nuget.org/packages/OpenTelemetry.Exporter.Console/1.0.0-rc2).
