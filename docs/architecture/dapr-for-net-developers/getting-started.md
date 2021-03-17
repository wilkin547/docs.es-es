---
title: Introducción a DAPR
description: Una guía para preparar el entorno de desarrollo local y crear sus primeras aplicaciones .NET con DAPR.
author: amolenk
ms.date: 02/25/2021
ms.openlocfilehash: 1b6ecd2cc2bf077375262155f0866cfef2dab708
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623816"
---
# <a name="get-started-with-dapr"></a>Introducción a DAPR

En los dos primeros capítulos, ha aprendido conceptos básicos sobre DAPR. Es el momento de realizarla en una versión de *prueba*. Este capítulo le guiará a través de la preparación del entorno de desarrollo local y la compilación de dos aplicaciones .NET DAPR.

## <a name="install-dapr-into-your-local-environment"></a>Instalación de DAPR en su entorno local

Comenzará instalando DAPR en el equipo de desarrollo. Una vez que haya finalizado, puede compilar y ejecutar aplicaciones de DAPR en [modo autohospedado](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/).

1. [Instale la CLI de DAPR](https://docs.dapr.io/getting-started/install-dapr-cli/). Permite iniciar, ejecutar y administrar instancias de DAPR. También proporciona compatibilidad con la depuración.

1. Instale [Docker Desktop](https://docs.docker.com/get-docker/). Si está ejecutando en Windows, asegúrese de que **Docker Desktop para Windows** esté configurado para usar contenedores de Linux.

> [!NOTE]
> De forma predeterminada, DAPR usa contenedores de Docker para proporcionar la mejor experiencia rápida. Para ejecutar DAPR fuera de Docker, puede omitir este paso y [ejecutar una inicialización *delgada*](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/). Los ejemplos de este capítulo requieren el uso de contenedores de Docker.

1. [Inicialice DAPR](https://docs.dapr.io/getting-started/install-dapr/). En este paso se configura el entorno de desarrollo mediante la instalación de las imágenes de contenedor y los archivos binarios de DAPR más recientes.

1. Instale el [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1).

Ahora que DAPR está instalado, es el momento de compilar su primera aplicación de DAPR.

## <a name="build-your-first-dapr-application"></a>Cree su primera aplicación de DAPR

Comenzaremos por crear una sencilla aplicación de consola de .NET que consume el bloque de creación de [Administración de estado de DAPR](state-management.md) .

### <a name="create-the-application"></a>Creación de la aplicación

1. Abra el shell de comandos o el terminal de su elección. Puede considerar las funciones de terminal en [Visual Studio Code](https://code.visualstudio.com/). Navegue hasta la carpeta raíz en la que desea compilar la aplicación. Una vez allí, escriba el siguiente comando para crear una nueva aplicación de consola de .NET:

    ```dotnetcli
    dotnet new console -o DaprCounter
    ```

    El comando scaffolding una aplicación sencilla de .NET Core "Hola mundo".

1. A continuación, vaya al nuevo directorio creado por el comando anterior:

    ```console
    cd DaprCounter
    ```

1. Ejecute la aplicación recién creada con el `dotnet run` comando. Al hacerlo, se escribe "Hola mundo!" en la pantalla de la consola:

    ```dotnetcli
    dotnet run
    ```

### <a name="add-dapr-state-management"></a>Agregar administración de estado de DAPR

A continuación, usará el bloque de [creación de administración de estado](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) de DAPR para implementar un contador con estado en el programa.

Puede invocar las API de DAPR en cualquier plataforma de desarrollo mediante la compatibilidad nativa de DAPR con HTTP y gRPC. Sin embargo, los desarrolladores de .NET encontrarán el SDK de .NET de DAPR más natural e intuitivo. Proporciona un cliente .NET fuertemente tipado para llamar a las API de DAPR. El SDK de .NET también se integra estrechamente con ASP.NET Core.

1. En la ventana de terminal, agregue el `Dapr.Client` paquete NuGet a la aplicación:

    ```dotnetcli
    dotnet add package Dapr.Client
    ```

    > [!NOTE]
    > Si está trabajando con una versión preliminar de DAPR, asegúrese de agregar la `--prerelease` marca al comando.

1. Abra el `Program.cs` archivo en su editor favorito y actualice su contenido al código siguiente:

    ```csharp
    using System;
    using System.Threading.Tasks;
    using Dapr.Client;

    namespace DaprCounter
    {
        class Program
        {
            static async Task Main(string[] args)
            {
                const string storeName = "statestore";
                const string key = "counter";

                var daprClient = new DaprClientBuilder().Build();
                var counter = await daprClient.GetStateAsync<int>(storeName, key);

                while (true)
                {
                    Console.WriteLine($"Counter = {counter++}");

                    await daprClient.SaveStateAsync(storeName, key, counter);
                    await Task.Delay(1000);
                }
            }
        }
    }
    ```

    El código actualizado implementa los siguientes pasos:

    - Primero `DaprClient` se crea una nueva instancia de. Esta clase le permite interactuar con el sidecar de DAPR.
    - En el almacén de estado, `DaprClient.GetStateAsync` captura el valor de la `counter` clave. Si la clave no existe, `int` se devuelve el valor predeterminado (que es `0` ).
    - A continuación, el código recorre en iteración, escribiendo el `counter` valor en la consola y guardando un valor incrementado en el almacén de estado.

1. El comando de la CLI de DAPR `run` inicia la aplicación. Invoca el tiempo de ejecución de DAPR subyacente y permite que la aplicación y el sidecar de DAPR se ejecuten juntos. Si omite `app-id` , DAPR generará un nombre único para la aplicación. El segmento final del comando, `dotnet run` , indica al tiempo de ejecución de DAPR que ejecute la aplicación .net Core.

    > [!IMPORTANT]
    > Se debe tener cuidado para pasar siempre un `app-id` parámetro explícito al consumir el bloque de creación de la administración de estado. El bloque usa el valor de identificador de la aplicación como *prefijo* para su clave de estado para cada par clave-valor. Si el identificador de la aplicación cambia, ya no podrá tener acceso al estado almacenado previamente.

    Ahora ejecute la aplicación con el siguiente comando:

    ```console
    dapr run --app-id DaprCounter dotnet run
    ```

    Intente detener y reiniciar la aplicación. Verá que el contador no se restablece. En su lugar, continúa con respecto al estado guardado anteriormente. El bloque de creación DAPR hace que la aplicación tenga un estado.

> [!IMPORTANT]
> Es importante comprender que la aplicación de ejemplo se comunica con un componente de estado preconfigurado, pero no tiene ninguna dependencia directa. DAPR abstrae la dependencia. Como verá en breve, el componente almacén de estado subyacente se puede cambiar con una actualización de configuración simple.

Es posible que se pregunte ¿dónde se almacena exactamente el estado?

## <a name="component-configuration-files"></a>Archivos de configuración de componentes

La primera vez que se inicializa DAPR para el entorno local, se aprovisiona automáticamente un contenedor de Redis. A continuación, DAPR configuró el contenedor de Redis como el componente de almacén de estado predeterminado con un archivo de configuración de componente, titulado `statestore.yaml` . A continuación se muestra su contenido:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

> [!NOTE]
> Los archivos de configuración de componentes predeterminados se almacenan en la `$HOME/.dapr/components` carpeta en Linux/MacOS y en la `%USERPROFILE%\.dapr\components` carpeta en Windows.

Tenga en cuenta el formato del archivo de configuración de componentes anterior:

- Cada componente tiene un nombre. En el ejemplo anterior, el componente se denomina `statestore` . Usamos ese nombre en el primer ejemplo de código para indicar al DAPR sidecar qué componente usar.
- Cada archivo de configuración de componente tiene una `spec` sección. Contiene un `type` campo que especifica el tipo de componente. El `version` campo especifica la versión del componente. El `metadata` campo contiene información que el componente requiere, como detalles de conexión y otros valores de configuración. Los valores de metadatos variarán para los diferentes tipos de componentes.

Un sidecar de DAPR puede consumir cualquier componente de DAPR configurado en la aplicación. Pero, ¿qué ocurre si tuviera una justificación arquitectónica para limitar la accesibilidad de un componente? ¿Cómo se puede restringir el componente de Redis a DAPR sidecar que solo se ejecutan en un entorno de producción?

Para ello, puede definir un `namespace` para el entorno de producción. Puede asignarle el nombre `production` . En el modo autohospedado, especifique el espacio de nombres de un sidecar de DAPR estableciendo la `NAMESPACE` variable de entorno. Cuando se configura, el sidecar de DAPR solo cargará los componentes que coinciden con el espacio de nombres. En el caso de las implementaciones de Kubernetes, el espacio de nombres Kubernetes determina los componentes que se cargan. En el siguiente ejemplo se muestra el componente Redis colocado en un `production` espacio de nombres. Observe la `namespace` declaración en el `metadata` elemento:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
  namespace: production
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
```

> [!IMPORTANT]
> Un componente de espacio de nombres solo es accesible para las aplicaciones que se ejecutan en el mismo espacio de nombres. Si la aplicación DAPR no puede cargar un componente, asegúrese de que el espacio de nombres de la aplicación coincide con el espacio de nombres del componente. Esto puede ser especialmente complicado en el modo autohospedado, donde el espacio de nombres de la aplicación se almacena en una `NAMESPACE` variable de entorno.

Si es necesario, puede restringir aún más un componente a una aplicación determinada. Dentro del `production` espacio de nombres, puede que desee limitar el acceso de Redis cache solo a la `DaprCounter` aplicación. Para ello, especifique `scopes` en la configuración del componente. En el ejemplo siguiente se muestra cómo restringir el acceso al componente de Redis `statestore` a la aplicación `DaprCounter` en el `production` espacio de nombres:

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: statestore
  namespace: production
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: ""
  - name: actorStateStore
    value: "true"
  scopes:
  - DaprCounter
```

## <a name="build-a-multi-container-dapr-application"></a>Compilación de una aplicación DAPR de varios contenedores

En el primer ejemplo, ha creado una aplicación de consola de .NET simple que se ejecutó en paralelo con un sidecar de DAPR. Sin embargo, las aplicaciones distribuidas modernas suelen constar de muchas partes móviles. Pueden ejecutar simultáneamente microservicios independientes. Normalmente, estas aplicaciones modernas se incluyen en contenedores y requieren herramientas de orquestación de contenedores como Docker Compose o Kubernetes.

En el ejemplo siguiente, creará una aplicación de varios contenedores. También usará el bloque de creación de [invocación del servicio DAPR](service-invocation.md) para comunicarse entre los servicios. La solución consistirá en una aplicación web que recupera las previsiones meteorológicas de una API Web. Cada una de ellas se ejecutará en un contenedor de Docker. Usará Docker Compose para ejecutar el contenedor localmente y habilitar las capacidades de depuración.

Asegúrese de que ha configurado el entorno local para DAPR y que ha instalado las [herramientas de desarrollo de .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) (las instrucciones están disponibles al principio de este capítulo).

Además, necesitará completar este ejemplo con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) con la carga de trabajo de **desarrollo multiplataforma de .net Core** instalada.

### <a name="create-the-application"></a>Creación de la aplicación

1. En Visual Studio 2019, cree un proyecto de **aplicación Web de ASP.net Core** :

    :::image type="content" source="./media/getting-started/multicontainer-createproject.png" alt-text="Captura de pantalla de la creación de un nuevo proyecto":::

1. Asigne un nombre al proyecto `DaprFrontEnd` y a la solución `DaprMultiContainer` :

    :::image type="content" source="./media/getting-started/multicontainer-configureproject.png" alt-text="Captura de pantalla de la configuración del nuevo proyecto":::

1. Seleccione **Aplicación web** para crear una aplicación web con Razor Pages. No seleccione **Habilitar compatibilidad con Docker**. Esta se agrega más adelante.

    :::image type="content" source="./media/getting-started/multicontainer-createwebapp.png" alt-text="Captura de pantalla de la creación de una nueva aplicación Web ASP.NET Core":::

1. Agregue un proyecto de API Web ASP.NET Core a la misma solución y llámelo _DaprBackEnd_. Seleccione **API** como el tipo de proyecto. De forma predeterminada, un sidecar de DAPR se basa en el límite de red para limitar el acceso a su API pública. Por lo tanto, desactive la casilla **configurar para https**.

    :::image type="content" source="./media/getting-started/multicontainer-createwebapi.png" alt-text="Captura de pantalla de la creación de la API Web":::

### <a name="add-dapr-service-invocation"></a>Agregar invocación del servicio DAPR

Ahora, configurará la comunicación entre los servicios mediante el [bloque de creación de invocación de servicio](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/)de DAPR. Habilitará la aplicación web para recuperar las previsiones meteorológicas de la API Web. El bloque de creación de invocación de servicio presenta muchas ventajas. Incluye detección de servicios, reintentos automáticos, cifrado de mensajes (mediante mTLS) y observabilidad mejorada. Usará el SDK de .NET de DAPR para invocar la API de invocación de servicio en el sidecar de DAPR.

1. En Visual Studio, abra la consola del administrador de paquetes (**herramientas > administrador de paquetes NuGet > consola del administrador de paquetes**) y asegúrese de que `DaprFrontEnd` es el proyecto predeterminado. En la consola de, agregue el `Dapr.AspNetCore` paquete NuGet al proyecto:

    ```powershell
    Install-Package Dapr.AspNetCore
    ```

    > [!NOTE]
    > Si el destino es una versión de `Dapr.AspNetCore` que se encuentra en versión preliminar, debe especificar la `-Prerelease` marca.

1. En el `DaprFrontEnd` proyecto, abra el archivo *Startup.CS* y reemplace el `ConfigureServices` método por el código siguiente:

    ```csharp
    // This method gets called by the runtime. Use this method to add services to the container.
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers().AddDapr();
        services.AddRazorPages();
    }
    ```

    La llamada a `AddDapr` registra la `DaprClient` clase con el sistema de inserción de dependencias ASP.net Core. Con el cliente registrado, ahora puede inyectar una instancia de `DaprClient` en el código de servicio para comunicarse con el sidecar de DAPR, los bloques de creación y los componentes.

1. Agregue un nuevo archivo de clase de C# denominado *WeatherForecast* al `DaprFrontEnd` proyecto:

    ```csharp
    using System;

    namespace DaprFrontEnd
    {
        public class WeatherForecast
        {
            public DateTime Date { get; set; }

            public int TemperatureC { get; set; }

            public int TemperatureF { get; set; }

            public string Summary { get; set; }
        }
    }
    ```

1. Abra el archivo *index.cshtml.CS* en la carpeta *pages* y reemplace su contenido por el código siguiente:

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.Net.Http;
    using System.Threading.Tasks;
    using Dapr.Client;
    using Microsoft.AspNetCore.Mvc.RazorPages;

    namespace DaprFrontEnd.Pages
    {
        public class IndexModel : PageModel
        {
            private readonly DaprClient _daprClient;

            public IndexModel(DaprClient daprClient)
            {
                _daprClient = daprClient ?? throw new ArgumentNullException(nameof(daprClient));
            }

            public async Task OnGet()
            {
                var forecasts = await _daprClient.InvokeMethodAsync<IEnumerable<WeatherForecast>>(
                    HttpMethod.Get,
                    "daprbackend",
                    "weatherforecast");

                ViewData["WeatherForecastData"] = forecasts;
            }
        }
    }
    ```

    Para agregar funcionalidades de DAPR en la aplicación Web, inserte la `DaprClient` clase en el `IndexModel` constructor. En el `OnGet` método, se llama al servicio de API con el bloque de creación de invocación del servicio DAPR. El `OnGet` método se invoca cada vez que un usuario visita la Página principal. El método se usa `DaprClient.InvokeMethodAsync` para invocar el `weatherforecast` método del `daprbackend` servicio. Configurará la API Web para que la use `daprbackend` como su identificador de aplicación más adelante al configurarla para que se ejecute con DAPR. Por último, la respuesta del servicio se guarda en los datos de la vista.

1. Reemplace el contenido del archivo *index. cshtml* en la carpeta *pages* , con el código siguiente. Muestra las previsiones meteorológicas almacenadas en los datos de la vista al usuario:

    ```razor
    @page
    @model IndexModel
    @{
        ViewData["Title"] = "Home page";
    }

    <div class="text-center">
        <h1 class="display-4">Welcome</h1>
        <p>Learn about <a href="https://docs.microsoft.com/aspnet/core">building Web apps with ASP.NET Core</a>.</p>
        @foreach (var forecast in (IEnumerable<WeatherForecast>)ViewData["WeatherForecastData"])
        {
            <p>The forecast for @forecast.Date is @forecast.Summary!</p>
        }
    </div>
    ```

### <a name="add-container-support"></a>Adición de compatibilidad con contenedores

En la parte final de este ejemplo, agregará compatibilidad con contenedores y ejecutará la solución mediante Docker Compose.

1. Haga clic con el botón derecho en el `DaprFrontEnd` proyecto y elija **Agregar**  >  **compatibilidad con el orquestador del contenedor**. Aparece el cuadro de diálogo **Agregar compatibilidad con el orquestador de contenedor** :

    :::image type="content" source="./media/getting-started/multicontainer-addorchestrator.png" alt-text="Captura de pantalla de la compatibilidad con agregar orquestador de contenedor":::

    Seleccione **Docker Compose**.

1. En el siguiente cuadro de diálogo, seleccione **Linux** como sistema operativo de destino:

    :::image type="content" source="./media/getting-started/multicontainer-targetos.png" alt-text="Captura de pantalla de selección de sistema operativo de destino de Docker":::

    Visual Studio crea un archivo *Docker-Compose. yml* y un archivo *. dockerignore* en la carpeta **Docker-Compose** en la solución:

    :::image type="content" source="./media/getting-started/multicontainer-dockersolution.png" alt-text="Captura de pantalla del proyecto Docker-Compose":::

    El archivo *Docker-Compose. yml* tiene el siguiente contenido:

    ```yaml
    version: "3.4"

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
    ```

    El archivo *.dockerignore* contiene los tipos de archivo y las extensiones que no quiere que Docker incluya en el contenedor. Estos archivos están asociados con el entorno de desarrollo y el control de código fuente, y no con la aplicación o el servicio que se va a implementar.

    En la raíz del directorio del proyecto *DaprFrontEnd* , se creó una nueva *Dockerfile* . Una *Dockerfile* es una secuencia de comandos que se usan para compilar una imagen. Para obtener más información, consulte [referencia de Dockerfile](https://docs.docker.com/engine/reference/builder).

    *Dockerfile* contiene YAML:

    ```yml
    FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
    WORKDIR /app
    EXPOSE 80
    EXPOSE 443

    FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
    WORKDIR /src
    COPY ["DaprFrontEnd/DaprFrontEnd.csproj", "DaprFrontEnd/"]
    RUN dotnet restore "DaprFrontEnd/DaprFrontEnd.csproj"
    COPY . .
    WORKDIR "/src/DaprFrontEnd"
    RUN dotnet build "DaprFrontEnd.csproj" -c Release -o /app/build

    FROM build AS publish
    RUN dotnet publish "DaprFrontEnd.csproj" -c Release -o /app/publish

    FROM base AS final
    WORKDIR /app
    COPY --from=publish /app/publish .
    ENTRYPOINT ["dotnet", "DaprFrontEnd.dll"]
    ```

    El *Dockerfile* anterior realiza secuencialmente los pasos siguientes cuando se invoca:

    1. Extrae la `mcr.microsoft.com/dotnet/aspnet:3.1` imagen y la asigna su nombre `base` .
    1. Establece el directorio de trabajo en */App*.
    1. Expone el puerto `80` y `443` .
    1. Extrae la `mcr.microsoft.com/dotnet/sdk:3.1` imagen y la asigna su nombre `build` .
    1. Establece el directorio de trabajo en */src*.
    1. Copia _DaprFrontEnd/DaprFrontEnd. csproj_ en un nuevo directorio denominado *DaprFrontEnd/*.
    1. Llama a [`dotnet restore`](../../core/tools/dotnet-restore.md) en el proyecto.
    1. Copia todo el directorio raíz en la raíz de la imagen.
    1. Establece el directorio de trabajo en _/src/DaprFrontEnd_.
    1. Llama a [`dotnet build`](../../core/tools/dotnet-build.md) en el proyecto.
        - Se dirige a la configuración de **lanzamiento** y se envía a */App/Build*.
    1. Inicializa una nueva fase de compilación a partir de la `build` imagen base existente y la asigna a su nombre `publish` .
    1. Llama a `dotnet publish` en el proyecto.
        - Se dirige a la configuración de **lanzamiento** y se envía a */App/Publish*.
    1. Inicializa una nueva fase de compilación a partir de la `publish` imagen base existente y la asigna a su nombre `final` .
    1. Establece el directorio de trabajo en */App*.
    1. Copia el `/app/publish` Directorio de la `publish` imagen en la raíz de la `final` imagen.
    1. Establece el punto de entrada como la imagen en `dotnet` y pasa `DaprFrontEnd.dll` como un argumento.

1. En el `DaprBackEnd` proyecto de API Web, haga clic con el botón derecho en el nodo del proyecto y elija **Agregar**  >  **compatibilidad con el orquestador del contenedor**. Elija **Docker Compose** y, a continuación, seleccione de nuevo **Linux** como sistema operativo de destino.

    En la raíz del directorio del proyecto _DaprBackEnd_ , se creó una nueva *Dockerfile* . *Dockerfile* contiene los siguientes YAML:

    ```yml
    FROM mcr.microsoft.com/dotnet/aspnet:3.1 AS base
    WORKDIR /app
    EXPOSE 80

    FROM mcr.microsoft.com/dotnet/sdk:3.1 AS build
    WORKDIR /src
    COPY ["DaprBackEnd/DaprBackEnd.csproj", "DaprBackEnd/"]
    RUN dotnet restore "DaprBackEnd/DaprBackEnd.csproj"
    COPY . .
    WORKDIR "/src/DaprBackEnd"
    RUN dotnet build "DaprBackEnd.csproj" -c Release -o /app/build

    FROM build AS publish
    RUN dotnet publish "DaprBackEnd.csproj" -c Release -o /app/publish

    FROM base AS final
    WORKDIR /app
    COPY --from=publish /app/publish .
    ENTRYPOINT ["dotnet", "DaprBackEnd.dll"]
    ```

    Abra el archivo *Docker-Compose. yml* de nuevo y examine su contenido. Visual Studio ha actualizado el archivo de **Docker Compose** . Ahora se incluyen ambos servicios:

    ```yaml
    version: '3.4'

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile

      daprbackend:
        image: ${DOCKER_REGISTRY-}daprbackend
        build:
          context: .
          dockerfile: DaprBackEnd/Dockerfile
    ```

1. Para usar los bloques de creación de DAPR desde una aplicación en contenedor, deberá agregar los contenedores de DAPR sidecar al archivo de Compose. Actualice cuidadosamente el contenido del archivo *Docker-Compose. yml* para que coincida con el ejemplo siguiente. Preste mucha atención a las pestañas formato y espaciado y no usar.

    ```yaml
    version: '3.4'
    
    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
        ports:
          - "51000:50001"

      daprfrontend-dapr:
        image: "daprio/daprd:latest"
        command: [ "./daprd", "-app-id", "daprfrontend", "-app-port", "80" ]
        depends_on:
          - daprfrontend
        network_mode: "service:daprfrontend"

      daprbackend:
        image: ${DOCKER_REGISTRY-}daprbackend
        build:
          context: .
          dockerfile: DaprBackEnd/Dockerfile
        ports:
          - "52000:50001"

      daprbackend-dapr:
        image: "daprio/daprd:latest"
        command: [ "./daprd", "-app-id", "daprbackend", "-app-port", "80" ]
        depends_on:
          - daprfrontend
        network_mode: "service:daprbackend"
    ```

    En el archivo actualizado, hemos agregado `daprfrontend-dapr` y `daprbackend-dapr` sidecar para los servicios de `daprfrontend` y, `daprbackend` respectivamente. En el archivo actualizado, preste especial atención a los siguientes cambios:

    - Los sidecares usan la `daprio/daprd:latest` imagen de contenedor. No se recomienda el uso de la `latest` etiqueta para escenarios de producción. En el caso de producción, es mejor usar un número de versión específico.
    - Cada servicio definido en el archivo de Compose tiene su propio espacio de nombres de red con fines de aislamiento de red. Los sidecares usan `network_mode: "service:..."` para asegurarse de que se ejecutan en el mismo espacio de nombres de red que la aplicación. Esto permite que el sidecar y la aplicación se comuniquen mediante `localhost` .
    - Los puertos en los que los sidecares de DAPR escuchan la comunicación de gRPC (de forma predeterminada 50001) se deben exponer para permitir que los sidecars se comuniquen entre sí.

1. Ejecute la solución (<kbd>F5</kbd> o <kbd>Ctrl + F5</kbd>) para comprobar que funciona según lo previsto. Si todo está configurado correctamente, debería ver los datos de previsión meteorológica:

    :::image type="content" source="./media/getting-started/multicontainer-result.png" alt-text="Captura de pantalla de la solución final que muestra los datos de previsión meteorológica":::

    Si se ejecuta localmente con Docker Compose y Visual Studio 2019, puede establecer puntos de interrupción y depurar en la aplicación. En escenarios de producción, se recomienda hospedar la aplicación en Kubernetes. Este libro incluye una aplicación de referencia adjunta, [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr), que contiene scripts para implementar en Kubernetes.

    Para obtener más información sobre el bloque de creación de invocación del servicio DAPR usado en este tutorial, consulte el [capítulo 6](service-invocation.md).

## <a name="summary"></a>Resumen

En este capítulo, ha tenido la oportunidad de *probar* la versión de DAPR. Con el SDK de .NET de DAPR, vio cómo DAPR se integra con la plataforma de aplicaciones .NET.

El primer ejemplo era una aplicación de consola de .NET simple, con estado que usaba el bloque de creación de administración de estado de DAPR.

El segundo ejemplo implica una aplicación de varios contenedores que se ejecuta en Docker. Con Visual Studio con Docker Compose, ha experimentado la conocida *experiencia de depuración de F5* disponible en todas las aplicaciones .net.

También tiene una mirada más detallada a los archivos de configuración de los componentes de DAPR. Configuran la implementación de infraestructura real usada por los bloques de creación de DAPR. Puede utilizar espacios de nombres y ámbitos para restringir el acceso a componentes a entornos y aplicaciones concretos.

En los próximos capítulos, profundizaremos en los bloques de creación que ofrece DAPR.

### <a name="references"></a>Referencias

- [Documentación de DAPR: introducción](https://docs.dapr.io/getting-started)
- [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)

> [!div class="step-by-step"]
> [Anterior](dapr-at-20000-feet.md)
> [Siguiente](reference-application.md)
