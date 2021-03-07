---
title: Introducción a DAPR
description: Una guía para preparar el entorno de desarrollo local y crear sus primeras aplicaciones .NET con DAPR.
author: amolenk
ms.date: 02/25/2021
ms.openlocfilehash: 68b1982c7283e0717ff7e1e254e5f313cd480d7b
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2021
ms.locfileid: "102401905"
---
# <a name="get-started-with-dapr"></a><span data-ttu-id="e74c6-103">Introducción a DAPR</span><span class="sxs-lookup"><span data-stu-id="e74c6-103">Get started with Dapr</span></span>

<span data-ttu-id="e74c6-104">En los dos primeros capítulos, ha aprendido conceptos básicos sobre DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-104">In the first two chapters, you learned basic concepts about Dapr.</span></span> <span data-ttu-id="e74c6-105">Es el momento de realizarla en una versión de *prueba*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-105">It's time to take it for a *test drive*.</span></span> <span data-ttu-id="e74c6-106">Este capítulo le guiará a través de la preparación del entorno de desarrollo local y la compilación de dos aplicaciones .NET DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-106">This chapter will guide you through preparing your local development environment and building two Dapr .NET applications.</span></span>

## <a name="install-dapr-into-your-local-environment"></a><span data-ttu-id="e74c6-107">Instalación de DAPR en su entorno local</span><span class="sxs-lookup"><span data-stu-id="e74c6-107">Install Dapr into your local environment</span></span>

<span data-ttu-id="e74c6-108">Comenzará instalando DAPR en el equipo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="e74c6-108">You'll start by installing Dapr on your development computer.</span></span> <span data-ttu-id="e74c6-109">Una vez que haya finalizado, puede compilar y ejecutar aplicaciones de DAPR en [modo autohospedado](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-109">Once complete, you can build and run Dapr applications in [self-hosted mode](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-overview/).</span></span>

1. <span data-ttu-id="e74c6-110">[Instale la CLI de DAPR](https://docs.dapr.io/getting-started/install-dapr-cli/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-110">[Install the Dapr CLI](https://docs.dapr.io/getting-started/install-dapr-cli/).</span></span> <span data-ttu-id="e74c6-111">Permite iniciar, ejecutar y administrar instancias de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-111">It enables you to launch, run, and manage Dapr instances.</span></span> <span data-ttu-id="e74c6-112">También proporciona compatibilidad con la depuración.</span><span class="sxs-lookup"><span data-stu-id="e74c6-112">It also provides debugging support.</span></span>

1. <span data-ttu-id="e74c6-113">Instale [Docker Desktop](https://docs.docker.com/get-docker/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-113">Install [Docker Desktop](https://docs.docker.com/get-docker/).</span></span> <span data-ttu-id="e74c6-114">Si está ejecutando en Windows, asegúrese de que **Docker Desktop para Windows** esté configurado para usar contenedores de Linux.</span><span class="sxs-lookup"><span data-stu-id="e74c6-114">If you're running on Windows, make sure that **Docker Desktop for Windows** is configured to use Linux containers.</span></span>

> [!NOTE]
> <span data-ttu-id="e74c6-115">De forma predeterminada, DAPR usa contenedores de Docker para proporcionar la mejor experiencia rápida.</span><span class="sxs-lookup"><span data-stu-id="e74c6-115">By default, Dapr uses Docker containers to provide you the best out-of-the-box experience.</span></span> <span data-ttu-id="e74c6-116">Para ejecutar DAPR fuera de Docker, puede omitir este paso y [ejecutar una inicialización *delgada*](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-116">To run Dapr outside of Docker, you can skip this step and [execute a *slim* initialization](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/).</span></span> <span data-ttu-id="e74c6-117">Los ejemplos de este capítulo requieren el uso de contenedores de Docker.</span><span class="sxs-lookup"><span data-stu-id="e74c6-117">The examples in this chapter require you use Docker containers.</span></span>

1. <span data-ttu-id="e74c6-118">[Inicialice DAPR](https://docs.dapr.io/getting-started/install-dapr/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-118">[Initialize Dapr](https://docs.dapr.io/getting-started/install-dapr/).</span></span> <span data-ttu-id="e74c6-119">En este paso se configura el entorno de desarrollo mediante la instalación de las imágenes de contenedor y los archivos binarios de DAPR más recientes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-119">This step sets up your development environment by installing the latest Dapr binaries and container images.</span></span>

1. <span data-ttu-id="e74c6-120">Instale el [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet/3.1).</span><span class="sxs-lookup"><span data-stu-id="e74c6-120">Install the [.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet/3.1).</span></span>

<span data-ttu-id="e74c6-121">Ahora que DAPR está instalado, es el momento de compilar su primera aplicación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-121">Now that Dapr is installed, it's time to build your first Dapr application!</span></span>

## <a name="build-your-first-dapr-application"></a><span data-ttu-id="e74c6-122">Cree su primera aplicación de DAPR</span><span class="sxs-lookup"><span data-stu-id="e74c6-122">Build your first Dapr application</span></span>

<span data-ttu-id="e74c6-123">Comenzaremos por crear una sencilla aplicación de consola de .NET que consume el bloque de creación de [Administración de estado de DAPR](state-management.md) .</span><span class="sxs-lookup"><span data-stu-id="e74c6-123">You'll start by building a simple .NET Console application that consumes the [Dapr state management](state-management.md) building block.</span></span>

### <a name="create-the-application"></a><span data-ttu-id="e74c6-124">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e74c6-124">Create the application</span></span>

1. <span data-ttu-id="e74c6-125">Abra el shell de comandos o el terminal de su elección.</span><span class="sxs-lookup"><span data-stu-id="e74c6-125">Open up the command shell or terminal of your choice.</span></span> <span data-ttu-id="e74c6-126">Puede considerar las funciones de terminal en [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="e74c6-126">You might consider the terminal capabilities in [Visual Studio Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="e74c6-127">Navegue hasta la carpeta raíz en la que desea compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-127">Navigate to the root folder in which you want to build your application.</span></span> <span data-ttu-id="e74c6-128">Una vez allí, escriba el siguiente comando para crear una nueva aplicación de consola de .NET:</span><span class="sxs-lookup"><span data-stu-id="e74c6-128">Once there, enter the following command to create a new .NET Console application:</span></span>

    ```dotnetcli
    dotnet new console -o DaprCounter
    ```

    <span data-ttu-id="e74c6-129">El comando scaffolding una aplicación sencilla de .NET Core "Hola mundo".</span><span class="sxs-lookup"><span data-stu-id="e74c6-129">The command scaffolds a simple "Hello World" .NET Core application.</span></span>

1. <span data-ttu-id="e74c6-130">A continuación, vaya al nuevo directorio creado por el comando anterior:</span><span class="sxs-lookup"><span data-stu-id="e74c6-130">Then, navigate into the new directory created by the previous command:</span></span>

    ```console
    cd DaprCounter
    ```

1. <span data-ttu-id="e74c6-131">Ejecute la aplicación recién creada con el `dotnet run` comando.</span><span class="sxs-lookup"><span data-stu-id="e74c6-131">Run the newly created application using the `dotnet run` command.</span></span> <span data-ttu-id="e74c6-132">Al hacerlo, se escribe "Hola mundo!"</span><span class="sxs-lookup"><span data-stu-id="e74c6-132">Doing so writes "Hello World!"</span></span> <span data-ttu-id="e74c6-133">en la pantalla de la consola:</span><span class="sxs-lookup"><span data-stu-id="e74c6-133">to the console screen:</span></span>

    ```dotnetcli
    dotnet run
    ```

### <a name="add-dapr-state-management"></a><span data-ttu-id="e74c6-134">Agregar administración de estado de DAPR</span><span class="sxs-lookup"><span data-stu-id="e74c6-134">Add Dapr State Management</span></span>

<span data-ttu-id="e74c6-135">A continuación, usará el bloque de [creación de administración de estado](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) de DAPR para implementar un contador con estado en el programa.</span><span class="sxs-lookup"><span data-stu-id="e74c6-135">Next, you'll use the Dapr [state management building block](https://docs.dapr.io/developing-applications/building-blocks/state-management/state-management-overview/) to implement a stateful counter in the program.</span></span>

<span data-ttu-id="e74c6-136">Puede invocar las API de DAPR en cualquier plataforma de desarrollo mediante la compatibilidad nativa de DAPR con HTTP y gRPC.</span><span class="sxs-lookup"><span data-stu-id="e74c6-136">You can invoke Dapr APIs across any development platform using Dapr's native support for HTTP and gRPC.</span></span> <span data-ttu-id="e74c6-137">Sin embargo, los desarrolladores de .NET encontrarán el SDK de .NET de DAPR más natural e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="e74c6-137">However, .NET Developers will find the Dapr .NET SDK more natural and intuitive.</span></span> <span data-ttu-id="e74c6-138">Proporciona un cliente .NET fuertemente tipado para llamar a las API de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-138">It provides a strongly typed .NET client to call the Dapr APIs.</span></span> <span data-ttu-id="e74c6-139">El SDK de .NET también se integra estrechamente con ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="e74c6-139">The .NET SDK also tightly integrates with ASP.NET Core.</span></span>

1. <span data-ttu-id="e74c6-140">En la ventana de terminal, agregue el `Dapr.Client` paquete NuGet a la aplicación:</span><span class="sxs-lookup"><span data-stu-id="e74c6-140">From the terminal window, add the `Dapr.Client` NuGet package to your application:</span></span>

    ```dotnetcli
    dotnet add package Dapr.Client
    ```

    > [!NOTE]
    > <span data-ttu-id="e74c6-141">Si está trabajando con una versión preliminar de DAPR, asegúrese de agregar la `--prerelease` marca al comando.</span><span class="sxs-lookup"><span data-stu-id="e74c6-141">If you're working with a pre-release version of Dapr, be sure to add the `--prerelease` flag to the command.</span></span>

1. <span data-ttu-id="e74c6-142">Abra el `Program.cs` archivo en su editor favorito y actualice su contenido al código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e74c6-142">Open the `Program.cs` file in your favorite editor and update its contents to the following code:</span></span>

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

    <span data-ttu-id="e74c6-143">El código actualizado implementa los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="e74c6-143">The updated code implements the following steps:</span></span>

    - <span data-ttu-id="e74c6-144">Primero `DaprClient` se crea una nueva instancia de.</span><span class="sxs-lookup"><span data-stu-id="e74c6-144">First a new `DaprClient` instance is instantiated.</span></span> <span data-ttu-id="e74c6-145">Esta clase le permite interactuar con el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-145">This class enables you to interact with the Dapr sidecar.</span></span>
    - <span data-ttu-id="e74c6-146">En el almacén de estado, `DaprClient.GetStateAsync` captura el valor de la `counter` clave.</span><span class="sxs-lookup"><span data-stu-id="e74c6-146">From the state store, `DaprClient.GetStateAsync` fetches the value for the `counter` key.</span></span> <span data-ttu-id="e74c6-147">Si la clave no existe, `int` se devuelve el valor predeterminado (que es `0` ).</span><span class="sxs-lookup"><span data-stu-id="e74c6-147">If the key doesn't exist, the default `int` value (which is `0`) is returned.</span></span>
    - <span data-ttu-id="e74c6-148">A continuación, el código recorre en iteración, escribiendo el `counter` valor en la consola y guardando un valor incrementado en el almacén de estado.</span><span class="sxs-lookup"><span data-stu-id="e74c6-148">The code then iterates, writing the `counter` value to the console and saving an incremented value to the state store.</span></span>

1. <span data-ttu-id="e74c6-149">El comando de la CLI de DAPR `run` inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-149">The Dapr CLI `run` command starts the application.</span></span> <span data-ttu-id="e74c6-150">Invoca el tiempo de ejecución de DAPR subyacente y permite que la aplicación y el sidecar de DAPR se ejecuten juntos.</span><span class="sxs-lookup"><span data-stu-id="e74c6-150">It invokes the underlying Dapr runtime and enables both the application and Dapr sidecar to run together.</span></span> <span data-ttu-id="e74c6-151">Si omite `app-id` , DAPR generará un nombre único para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-151">If you omit the `app-id`, Dapr will generate a unique name for the application.</span></span> <span data-ttu-id="e74c6-152">El segmento final del comando, `dotnet run` , indica al tiempo de ejecución de DAPR que ejecute la aplicación .net Core.</span><span class="sxs-lookup"><span data-stu-id="e74c6-152">The final segment of the command, `dotnet run`, instructs the Dapr runtime to run the .NET core application.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e74c6-153">Se debe tener cuidado para pasar siempre un `app-id` parámetro explícito al consumir el bloque de creación de la administración de estado.</span><span class="sxs-lookup"><span data-stu-id="e74c6-153">Care must be taken to always pass an explicit `app-id` parameter when consuming the state management building block.</span></span> <span data-ttu-id="e74c6-154">El bloque usa el valor de identificador de la aplicación como *prefijo* para su clave de estado para cada par clave-valor.</span><span class="sxs-lookup"><span data-stu-id="e74c6-154">The block uses the application id value as a *prefix* for its state key for each key/value pair.</span></span> <span data-ttu-id="e74c6-155">Si el identificador de la aplicación cambia, ya no podrá tener acceso al estado almacenado previamente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-155">If the application id changes, you can no longer access the previously stored state.</span></span>

    <span data-ttu-id="e74c6-156">Ahora ejecute la aplicación con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="e74c6-156">Now run the application with the following command:</span></span>

    ```console
    dapr run --app-id DaprCounter dotnet run
    ```

    <span data-ttu-id="e74c6-157">Intente detener y reiniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-157">Try stopping and restarting the application.</span></span> <span data-ttu-id="e74c6-158">Verá que el contador no se restablece.</span><span class="sxs-lookup"><span data-stu-id="e74c6-158">You'll see that the counter doesn't reset.</span></span> <span data-ttu-id="e74c6-159">En su lugar, continúa con respecto al estado guardado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-159">Instead it continues from the previously saved state.</span></span> <span data-ttu-id="e74c6-160">El bloque de creación DAPR hace que la aplicación tenga un estado.</span><span class="sxs-lookup"><span data-stu-id="e74c6-160">The Dapr building block makes the application stateful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e74c6-161">Es importante comprender que la aplicación de ejemplo se comunica con un componente de estado preconfigurado, pero no tiene ninguna dependencia directa.</span><span class="sxs-lookup"><span data-stu-id="e74c6-161">It's important to understand your sample application communicates with a pre-configured state component, but has no direct dependency on it.</span></span> <span data-ttu-id="e74c6-162">DAPR abstrae la dependencia.</span><span class="sxs-lookup"><span data-stu-id="e74c6-162">Dapr abstracts away the dependency.</span></span> <span data-ttu-id="e74c6-163">Como verá en breve, el componente almacén de estado subyacente se puede cambiar con una actualización de configuración simple.</span><span class="sxs-lookup"><span data-stu-id="e74c6-163">As you'll shortly see, the underlying state store component can be changed with a simple configuration update.</span></span>

<span data-ttu-id="e74c6-164">Es posible que se pregunte ¿dónde se almacena exactamente el estado?</span><span class="sxs-lookup"><span data-stu-id="e74c6-164">You might be wondering, where exactly is the state stored?</span></span>

## <a name="component-configuration-files"></a><span data-ttu-id="e74c6-165">Archivos de configuración de componentes</span><span class="sxs-lookup"><span data-stu-id="e74c6-165">Component configuration files</span></span>

<span data-ttu-id="e74c6-166">La primera vez que se inicializa DAPR para el entorno local, se aprovisiona automáticamente un contenedor de Redis.</span><span class="sxs-lookup"><span data-stu-id="e74c6-166">When you first initialized Dapr for your local environment, it automatically provisioned a Redis container.</span></span> <span data-ttu-id="e74c6-167">A continuación, DAPR configuró el contenedor de Redis como el componente de almacén de estado predeterminado con un archivo de configuración de componente, titulado `statestore.yaml` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-167">Dapr then configured the Redis container as the default state store component with a component configuration file, entitled `statestore.yaml`.</span></span> <span data-ttu-id="e74c6-168">A continuación se muestra su contenido:</span><span class="sxs-lookup"><span data-stu-id="e74c6-168">Here's a look at its contents:</span></span>

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
> <span data-ttu-id="e74c6-169">Los archivos de configuración de componentes predeterminados se almacenan en la `$HOME/.dapr/components` carpeta en Linux/MacOS y en la `%USERPROFILE%\.dapr\components` carpeta en Windows.</span><span class="sxs-lookup"><span data-stu-id="e74c6-169">Default component configuration files are stored in the `$HOME/.dapr/components` folder on Linux/macOS, and in the `%USERPROFILE%\.dapr\components` folder on Windows.</span></span>

<span data-ttu-id="e74c6-170">Tenga en cuenta el formato del archivo de configuración de componentes anterior:</span><span class="sxs-lookup"><span data-stu-id="e74c6-170">Note the format of the previous component configuration file:</span></span>

- <span data-ttu-id="e74c6-171">Cada componente tiene un nombre.</span><span class="sxs-lookup"><span data-stu-id="e74c6-171">Each component has a name.</span></span> <span data-ttu-id="e74c6-172">En el ejemplo anterior, el componente se denomina `statestore` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-172">In the sample above, the component is named `statestore`.</span></span> <span data-ttu-id="e74c6-173">Usamos ese nombre en el primer ejemplo de código para indicar al DAPR sidecar qué componente usar.</span><span class="sxs-lookup"><span data-stu-id="e74c6-173">We used that name in our first code example to tell the Dapr sidecar which component to use.</span></span>
- <span data-ttu-id="e74c6-174">Cada archivo de configuración de componente tiene una `spec` sección.</span><span class="sxs-lookup"><span data-stu-id="e74c6-174">Each component configuration file has a `spec` section.</span></span> <span data-ttu-id="e74c6-175">Contiene un `type` campo que especifica el tipo de componente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-175">It contains a `type` field that specifies the component type.</span></span> <span data-ttu-id="e74c6-176">El `version` campo especifica la versión del componente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-176">The `version` field specifies the component version.</span></span> <span data-ttu-id="e74c6-177">El `metadata` campo contiene información que el componente requiere, como detalles de conexión y otros valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="e74c6-177">The `metadata` field contains information that the component requires, such as connection details and other settings.</span></span> <span data-ttu-id="e74c6-178">Los valores de metadatos variarán para los diferentes tipos de componentes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-178">The metadata values will vary for the different types of components.</span></span>

<span data-ttu-id="e74c6-179">Un sidecar de DAPR puede consumir cualquier componente de DAPR configurado en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-179">A Dapr sidecar can consume any Dapr component configured in your application.</span></span> <span data-ttu-id="e74c6-180">Pero, ¿qué ocurre si tuviera una justificación arquitectónica para limitar la accesibilidad de un componente?</span><span class="sxs-lookup"><span data-stu-id="e74c6-180">But, what if you had an architectural justification to limit the accessibility of a component?</span></span> <span data-ttu-id="e74c6-181">¿Cómo se puede restringir el componente de Redis a DAPR sidecar que solo se ejecutan en un entorno de producción?</span><span class="sxs-lookup"><span data-stu-id="e74c6-181">How could you restrict the Redis component to Dapr sidecars running only in a production environment?</span></span>

<span data-ttu-id="e74c6-182">Para ello, puede definir un `namespace` para el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="e74c6-182">To do so, you could define a `namespace` for the production environment.</span></span> <span data-ttu-id="e74c6-183">Puede asignarle el nombre `production` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-183">You might name it `production`.</span></span> <span data-ttu-id="e74c6-184">En el modo autohospedado, especifique el espacio de nombres de un sidecar de DAPR estableciendo la `NAMESPACE` variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="e74c6-184">In self-hosted mode, you specify the namespace of a Dapr sidecar by setting the `NAMESPACE` environment variable.</span></span> <span data-ttu-id="e74c6-185">Cuando se configura, el sidecar de DAPR solo cargará los componentes que coinciden con el espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e74c6-185">When configured, the Dapr sidecar will only load the components that match the namespace.</span></span> <span data-ttu-id="e74c6-186">En el caso de las implementaciones de Kubernetes, el espacio de nombres Kubernetes determina los componentes que se cargan.</span><span class="sxs-lookup"><span data-stu-id="e74c6-186">For Kubernetes deployments, the Kubernetes namespace determines the components that are loaded.</span></span> <span data-ttu-id="e74c6-187">En el siguiente ejemplo se muestra el componente Redis colocado en un `production` espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e74c6-187">The following sample shows the Redis component placed in a `production` namespace.</span></span> <span data-ttu-id="e74c6-188">Observe la `namespace` declaración en el `metadata` elemento:</span><span class="sxs-lookup"><span data-stu-id="e74c6-188">Note the `namespace` declaration in the `metadata` element:</span></span>

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
> <span data-ttu-id="e74c6-189">Un componente de espacio de nombres solo es accesible para las aplicaciones que se ejecutan en el mismo espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="e74c6-189">A namespaced component is only accessible to applications running in the same namespace.</span></span> <span data-ttu-id="e74c6-190">Si la aplicación DAPR no puede cargar un componente, asegúrese de que el espacio de nombres de la aplicación coincide con el espacio de nombres del componente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-190">If your Dapr application fails to load a component, make sure that the application namespace matches the component namespace.</span></span> <span data-ttu-id="e74c6-191">Esto puede ser especialmente complicado en el modo autohospedado, donde el espacio de nombres de la aplicación se almacena en una `NAMESPACE` variable de entorno.</span><span class="sxs-lookup"><span data-stu-id="e74c6-191">This can be especially tricky in self-hosted mode where the application namespace is stored in a `NAMESPACE` environment variable.</span></span>

<span data-ttu-id="e74c6-192">Si es necesario, puede restringir aún más un componente a una aplicación determinada.</span><span class="sxs-lookup"><span data-stu-id="e74c6-192">If needed, you could further restrict a component to a particular application.</span></span> <span data-ttu-id="e74c6-193">Dentro del `production` espacio de nombres, puede que desee limitar el acceso de Redis cache solo a la `DaprCounter` aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-193">Within the `production` namespace, you may want to limit access of the Redis cache to only the `DaprCounter` application.</span></span> <span data-ttu-id="e74c6-194">Para ello, especifique `scopes` en la configuración del componente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-194">You do so by specifying `scopes` in the component configuration.</span></span> <span data-ttu-id="e74c6-195">En el ejemplo siguiente se muestra cómo restringir el acceso al componente de Redis `statestore` a la aplicación `DaprCounter` en el `production` espacio de nombres:</span><span class="sxs-lookup"><span data-stu-id="e74c6-195">The following example shows how to restrict access to the Redis `statestore` component to the application `DaprCounter` in the `production` namespace:</span></span>

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

## <a name="build-a-multi-container-dapr-application"></a><span data-ttu-id="e74c6-196">Compilación de una aplicación DAPR de varios contenedores</span><span class="sxs-lookup"><span data-stu-id="e74c6-196">Build a multi-container Dapr application</span></span>

<span data-ttu-id="e74c6-197">En el primer ejemplo, ha creado una aplicación de consola de .NET simple que se ejecutó en paralelo con un sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-197">In the first example, you created a simple .NET console application that ran side-by-side with a Dapr sidecar.</span></span> <span data-ttu-id="e74c6-198">Sin embargo, las aplicaciones distribuidas modernas suelen constar de muchas partes móviles.</span><span class="sxs-lookup"><span data-stu-id="e74c6-198">Modern distributed applications, however, often consist of many moving parts.</span></span> <span data-ttu-id="e74c6-199">Pueden ejecutar simultáneamente microservicios independientes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-199">They can simultaneously run independent microservices.</span></span> <span data-ttu-id="e74c6-200">Normalmente, estas aplicaciones modernas se incluyen en contenedores y requieren herramientas de orquestación de contenedores como Docker Compose o Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-200">These modern applications are typically containerized and require container orchestration tools such as Docker Compose or Kubernetes.</span></span>

<span data-ttu-id="e74c6-201">En el ejemplo siguiente, creará una aplicación de varios contenedores.</span><span class="sxs-lookup"><span data-stu-id="e74c6-201">In the next example, you'll create a multi-container application.</span></span> <span data-ttu-id="e74c6-202">También usará el bloque de creación de [invocación del servicio DAPR](service-invocation.md) para comunicarse entre los servicios.</span><span class="sxs-lookup"><span data-stu-id="e74c6-202">You'll also use the [Dapr service invocation](service-invocation.md) building block to communicate between services.</span></span> <span data-ttu-id="e74c6-203">La solución consistirá en una aplicación web que recupera las previsiones meteorológicas de una API Web.</span><span class="sxs-lookup"><span data-stu-id="e74c6-203">The solution will consist of a web application that retrieves weather forecasts from a web API.</span></span> <span data-ttu-id="e74c6-204">Cada una de ellas se ejecutará en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="e74c6-204">They will each run in a Docker container.</span></span> <span data-ttu-id="e74c6-205">Usará Docker Compose para ejecutar el contenedor localmente y habilitar las capacidades de depuración.</span><span class="sxs-lookup"><span data-stu-id="e74c6-205">You'll use Docker Compose to run the container locally and enable debugging capabilities.</span></span>

<span data-ttu-id="e74c6-206">Asegúrese de que ha configurado el entorno local para DAPR y que ha instalado las [herramientas de desarrollo de .net Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1) (las instrucciones están disponibles al principio de este capítulo).</span><span class="sxs-lookup"><span data-stu-id="e74c6-206">Make sure you've configured your local environment for Dapr and installed the [.NET Core 3.1 Development Tools](https://dotnet.microsoft.com/download/dotnet-core/3.1) (instructions are available at the beginning of this chapter).</span></span>

<span data-ttu-id="e74c6-207">Además, necesitará completar este ejemplo con [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) con la carga de trabajo de **desarrollo multiplataforma de .net Core** instalada.</span><span class="sxs-lookup"><span data-stu-id="e74c6-207">Additionally, you'll need complete this sample using [Visual Studio 2019](https://visualstudio.microsoft.com/downloads) with the **.NET Core cross-platform development** workload installed.</span></span>

### <a name="create-the-application"></a><span data-ttu-id="e74c6-208">Creación de la aplicación</span><span class="sxs-lookup"><span data-stu-id="e74c6-208">Create the application</span></span>

1. <span data-ttu-id="e74c6-209">En Visual Studio 2019, cree un proyecto de **aplicación Web de ASP.net Core** :</span><span class="sxs-lookup"><span data-stu-id="e74c6-209">In Visual Studio 2019, create an **ASP.NET Core Web App** project:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createproject.png" alt-text="Captura de pantalla de la creación de un nuevo proyecto":::

1. <span data-ttu-id="e74c6-211">Asigne un nombre al proyecto `DaprFrontEnd` y a la solución `DaprMultiContainer` :</span><span class="sxs-lookup"><span data-stu-id="e74c6-211">Name your project `DaprFrontEnd` and your solution `DaprMultiContainer`:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-configureproject.png" alt-text="Captura de pantalla de la configuración del nuevo proyecto":::

1. <span data-ttu-id="e74c6-213">Seleccione **Aplicación web** para crear una aplicación web con Razor Pages.</span><span class="sxs-lookup"><span data-stu-id="e74c6-213">Select **Web Application** to create a web application with Razor pages.</span></span> <span data-ttu-id="e74c6-214">No seleccione **Habilitar compatibilidad con Docker**.</span><span class="sxs-lookup"><span data-stu-id="e74c6-214">Don't select **Enable Docker Support**.</span></span> <span data-ttu-id="e74c6-215">Esta se agrega más adelante.</span><span class="sxs-lookup"><span data-stu-id="e74c6-215">You'll add Docker support later.</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createwebapp.png" alt-text="Captura de pantalla de la creación de una nueva aplicación Web ASP.NET Core":::

1. <span data-ttu-id="e74c6-217">Agregue un proyecto de API Web ASP.NET Core a la misma solución y llámelo _DaprBackEnd_.</span><span class="sxs-lookup"><span data-stu-id="e74c6-217">Add a ASP.NET Core Web API project to the same solution and call it _DaprBackEnd_.</span></span> <span data-ttu-id="e74c6-218">Seleccione **API** como el tipo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="e74c6-218">Select **API** as the project type.</span></span> <span data-ttu-id="e74c6-219">De forma predeterminada, un sidecar de DAPR se basa en el límite de red para limitar el acceso a su API pública.</span><span class="sxs-lookup"><span data-stu-id="e74c6-219">By default, a Dapr sidecar relies on the network boundary to limit access to its public API.</span></span> <span data-ttu-id="e74c6-220">Por lo tanto, desactive la casilla **configurar para https**.</span><span class="sxs-lookup"><span data-stu-id="e74c6-220">So, clear the checkbox for **Configure for HTTPS**.</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-createwebapi.png" alt-text="Captura de pantalla de la creación de la API Web":::

### <a name="add-dapr-service-invocation"></a><span data-ttu-id="e74c6-222">Agregar invocación del servicio DAPR</span><span class="sxs-lookup"><span data-stu-id="e74c6-222">Add Dapr service invocation</span></span>

<span data-ttu-id="e74c6-223">Ahora, configurará la comunicación entre los servicios mediante el [bloque de creación de invocación de servicio](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/)de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-223">Now, you'll configure communication between the services using Dapr [service invocation building block](https://docs.dapr.io/developing-applications/building-blocks/service-invocation/service-invocation-overview/).</span></span> <span data-ttu-id="e74c6-224">Habilitará la aplicación web para recuperar las previsiones meteorológicas de la API Web.</span><span class="sxs-lookup"><span data-stu-id="e74c6-224">You'll enable the web app to retrieve weather forecasts from the web API.</span></span> <span data-ttu-id="e74c6-225">El bloque de creación de invocación de servicio presenta muchas ventajas.</span><span class="sxs-lookup"><span data-stu-id="e74c6-225">The service invocation building block features many benefits.</span></span> <span data-ttu-id="e74c6-226">Incluye detección de servicios, reintentos automáticos, cifrado de mensajes (mediante mTLS) y observabilidad mejorada.</span><span class="sxs-lookup"><span data-stu-id="e74c6-226">It includes service discovery, automatic retries, message encryption (using mTLS), and improved observability.</span></span> <span data-ttu-id="e74c6-227">Usará el SDK de .NET de DAPR para invocar la API de invocación de servicio en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-227">You'll use the Dapr .NET SDK to invoke the service invocation API on the Dapr sidecar.</span></span>

1. <span data-ttu-id="e74c6-228">En Visual Studio, abra la consola del administrador de paquetes (**herramientas > administrador de paquetes NuGet > consola del administrador de paquetes**) y asegúrese de que `DaprFrontEnd` es el proyecto predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e74c6-228">In Visual Studio, open the Package Manager Console (**Tools > NuGet Package Manager > Package Manager Console**) and make sure that `DaprFrontEnd` is the default project.</span></span> <span data-ttu-id="e74c6-229">En la consola de, agregue el `Dapr.AspNetCore` paquete NuGet al proyecto:</span><span class="sxs-lookup"><span data-stu-id="e74c6-229">From the console, add the `Dapr.AspNetCore` NuGet package to the project:</span></span>

    ```powershell
    Install-Package Dapr.AspNetCore
    ```

    > [!NOTE]
    > <span data-ttu-id="e74c6-230">Si el destino es una versión de `Dapr.AspNetCore` que se encuentra en versión preliminar, debe especificar la `-Prerelease` marca.</span><span class="sxs-lookup"><span data-stu-id="e74c6-230">If you're targeting a version of `Dapr.AspNetCore` that is in prerelease, you need to specify the `-Prerelease` flag.</span></span>

1. <span data-ttu-id="e74c6-231">En el `DaprFrontEnd` proyecto, abra el archivo *Startup.CS* y reemplace el `ConfigureServices` método por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e74c6-231">In the `DaprFrontEnd` project, open the *Startup.cs* file, and replace the `ConfigureServices` method with the following code:</span></span>

    ```csharp
    // This method gets called by the runtime. Use this method to add services to the container.
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddControllers().AddDapr();
        services.AddRazorPages();
    }
    ```

    <span data-ttu-id="e74c6-232">La llamada a `AddDapr` registra la `DaprClient` clase con el sistema de inserción de dependencias ASP.net Core.</span><span class="sxs-lookup"><span data-stu-id="e74c6-232">The call to `AddDapr` registers the `DaprClient` class with the ASP.NET Core dependency injection system.</span></span> <span data-ttu-id="e74c6-233">Usará la `DaprClient` clase más adelante para comunicarse con el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-233">You'll use the `DaprClient` class later on to communicate with the Dapr sidecar.</span></span>

1. <span data-ttu-id="e74c6-234">Agregue un nuevo archivo de clase de C# denominado *WeatherForecast* al `DaprFrontEnd` proyecto:</span><span class="sxs-lookup"><span data-stu-id="e74c6-234">Add a new C# class file named *WeatherForecast* to the `DaprFrontEnd` project:</span></span>

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

1. <span data-ttu-id="e74c6-235">Abra el archivo *index.cshtml.CS* en la carpeta *pages* y reemplace su contenido por el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="e74c6-235">Open the *Index.cshtml.cs* file in the *Pages* folder, and replace its contents with the following code:</span></span>

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

    <span data-ttu-id="e74c6-236">Para agregar funcionalidades de DAPR en la aplicación Web, inserte la `DaprClient` clase en el `IndexModel` constructor.</span><span class="sxs-lookup"><span data-stu-id="e74c6-236">You add Dapr capabilities into the web app by injecting the `DaprClient` class into `IndexModel` constructor.</span></span> <span data-ttu-id="e74c6-237">En el `OnGet` método, se llama al servicio de API con el bloque de creación de invocación del servicio DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-237">In the `OnGet` method, you call the API service with the Dapr service invocation building block.</span></span> <span data-ttu-id="e74c6-238">El `OnGet` método se invoca cada vez que un usuario visita la Página principal.</span><span class="sxs-lookup"><span data-stu-id="e74c6-238">The `OnGet` method is invoked whenever a user visits the home page.</span></span> <span data-ttu-id="e74c6-239">El método se usa `DaprClient.InvokeMethodAsync` para invocar el `weatherforecast` método del `daprbackend` servicio.</span><span class="sxs-lookup"><span data-stu-id="e74c6-239">You use the `DaprClient.InvokeMethodAsync` method to invoke the `weatherforecast` method of the `daprbackend` service.</span></span> <span data-ttu-id="e74c6-240">Configurará la API Web para que la use `daprbackend` como su identificador de aplicación más adelante al configurarla para que se ejecute con DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-240">You'll configure the web API to use `daprbackend` as its application ID later on when configuring it to run with Dapr.</span></span> <span data-ttu-id="e74c6-241">Por último, la respuesta del servicio se guarda en los datos de la vista.</span><span class="sxs-lookup"><span data-stu-id="e74c6-241">Finally, the service response is saved in view data.</span></span>

1. <span data-ttu-id="e74c6-242">Reemplace el contenido del archivo *index. cshtml* en la carpeta *pages* , con el código siguiente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-242">Replace the contents of the *Index.cshtml* file in the *Pages* folder, with the following code.</span></span> <span data-ttu-id="e74c6-243">Muestra las previsiones meteorológicas almacenadas en los datos de la vista al usuario:</span><span class="sxs-lookup"><span data-stu-id="e74c6-243">It displays the weather forecasts stored in the view data to the user:</span></span>

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

### <a name="add-container-support"></a><span data-ttu-id="e74c6-244">Adición de compatibilidad con contenedores</span><span class="sxs-lookup"><span data-stu-id="e74c6-244">Add container support</span></span>

<span data-ttu-id="e74c6-245">En la parte final de este ejemplo, agregará compatibilidad con contenedores y ejecutará la solución mediante Docker Compose.</span><span class="sxs-lookup"><span data-stu-id="e74c6-245">In the final part of this example, you'll add container support and run the solution using Docker Compose.</span></span>

1. <span data-ttu-id="e74c6-246">Haga clic con el botón derecho en el `DaprFrontEnd` proyecto y elija **Agregar**  >  **compatibilidad con el orquestador del contenedor**.</span><span class="sxs-lookup"><span data-stu-id="e74c6-246">Right-click the `DaprFrontEnd` project, and choose **Add** > **Container Orchestrator Support**.</span></span> <span data-ttu-id="e74c6-247">Aparece el cuadro de diálogo **Agregar compatibilidad con el orquestador de contenedor** :</span><span class="sxs-lookup"><span data-stu-id="e74c6-247">The **Add Container Orchestrator Support** dialog appears:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-addorchestrator.png" alt-text="Captura de pantalla de la compatibilidad con agregar orquestador de contenedor":::

    <span data-ttu-id="e74c6-249">Seleccione **Docker Compose**.</span><span class="sxs-lookup"><span data-stu-id="e74c6-249">Choose **Docker Compose**.</span></span>

1. <span data-ttu-id="e74c6-250">En el siguiente cuadro de diálogo, seleccione **Linux** como sistema operativo de destino:</span><span class="sxs-lookup"><span data-stu-id="e74c6-250">In the next dialog, select **Linux** as the Target OS:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-targetos.png" alt-text="Captura de pantalla de selección de sistema operativo de destino de Docker":::

    <span data-ttu-id="e74c6-252">Visual Studio crea un archivo *Docker-Compose. yml* y un archivo *. dockerignore* en la carpeta **Docker-Compose** en la solución:</span><span class="sxs-lookup"><span data-stu-id="e74c6-252">Visual Studio creates a *docker-compose.yml* file and a *.dockerignore* file in the **docker-compose** folder in the solution:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-dockersolution.png" alt-text="Captura de pantalla del proyecto Docker-Compose":::

    <span data-ttu-id="e74c6-254">El archivo *Docker-Compose. yml* tiene el siguiente contenido:</span><span class="sxs-lookup"><span data-stu-id="e74c6-254">The *docker-compose.yml* file has the following content:</span></span>

    ```yaml
    version: "3.4"

    services:
      daprfrontend:
        image: ${DOCKER_REGISTRY-}daprfrontend
        build:
          context: .
          dockerfile: DaprFrontEnd/Dockerfile
    ```

    <span data-ttu-id="e74c6-255">El archivo *.dockerignore* contiene los tipos de archivo y las extensiones que no quiere que Docker incluya en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="e74c6-255">The *.dockerignore* file contains file types and extensions that you don't want Docker to include in the container.</span></span> <span data-ttu-id="e74c6-256">Estos archivos están asociados con el entorno de desarrollo y el control de código fuente, y no con la aplicación o el servicio que se va a implementar.</span><span class="sxs-lookup"><span data-stu-id="e74c6-256">These files are associated with the development environment and source control and not the app or service you're deploying.</span></span>

    <span data-ttu-id="e74c6-257">En la raíz del directorio del proyecto *DaprFrontEnd* , se creó una nueva *Dockerfile* .</span><span class="sxs-lookup"><span data-stu-id="e74c6-257">In the root of the *DaprFrontEnd* project directory, a new *Dockerfile* was created.</span></span> <span data-ttu-id="e74c6-258">Una *Dockerfile* es una secuencia de comandos que se usan para compilar una imagen.</span><span class="sxs-lookup"><span data-stu-id="e74c6-258">A *Dockerfile* is a sequence of commands that are used to build an image.</span></span> <span data-ttu-id="e74c6-259">Para obtener más información, consulte [referencia de Dockerfile](https://docs.docker.com/engine/reference/builder).</span><span class="sxs-lookup"><span data-stu-id="e74c6-259">For more information, see [Dockerfile reference](https://docs.docker.com/engine/reference/builder).</span></span>

    <span data-ttu-id="e74c6-260">*Dockerfile* contiene YAML:</span><span class="sxs-lookup"><span data-stu-id="e74c6-260">The *Dockerfile* contains the YAML:</span></span>

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

    <span data-ttu-id="e74c6-261">El *Dockerfile* anterior realiza secuencialmente los pasos siguientes cuando se invoca:</span><span class="sxs-lookup"><span data-stu-id="e74c6-261">The preceding *Dockerfile* sequentially performs the following steps when invoked:</span></span>

    1. <span data-ttu-id="e74c6-262">Extrae la `mcr.microsoft.com/dotnet/aspnet:3.1` imagen y la asigna su nombre `base` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-262">Pulls the `mcr.microsoft.com/dotnet/aspnet:3.1` image and names it `base`.</span></span>
    1. <span data-ttu-id="e74c6-263">Establece el directorio de trabajo en */App*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-263">Sets the working directory to */app*.</span></span>
    1. <span data-ttu-id="e74c6-264">Expone el puerto `80` y `443` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-264">Exposes port `80` and `443`.</span></span>
    1. <span data-ttu-id="e74c6-265">Extrae la `mcr.microsoft.com/dotnet/sdk:3.1` imagen y la asigna su nombre `build` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-265">Pulls the `mcr.microsoft.com/dotnet/sdk:3.1` image and names it `build`.</span></span>
    1. <span data-ttu-id="e74c6-266">Establece el directorio de trabajo en */src*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-266">Sets the working directory to */src*.</span></span>
    1. <span data-ttu-id="e74c6-267">Copia _DaprFrontEnd/DaprFrontEnd. csproj_ en un nuevo directorio denominado *DaprFrontEnd/*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-267">Copies the _DaprFrontEnd/DaprFrontEnd.csproj_ to a new directory named *DaprFrontEnd/*.</span></span>
    1. <span data-ttu-id="e74c6-268">Llama a [`dotnet restore`](../../core/tools/dotnet-restore.md) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e74c6-268">Calls [`dotnet restore`](../../core/tools/dotnet-restore.md) on the project.</span></span>
    1. <span data-ttu-id="e74c6-269">Copia todo el directorio raíz en la raíz de la imagen.</span><span class="sxs-lookup"><span data-stu-id="e74c6-269">Copies everything from the root directory into the image's root.</span></span>
    1. <span data-ttu-id="e74c6-270">Establece el directorio de trabajo en _/src/DaprFrontEnd_.</span><span class="sxs-lookup"><span data-stu-id="e74c6-270">Sets the working directory to _/src/DaprFrontEnd_.</span></span>
    1. <span data-ttu-id="e74c6-271">Llama a [`dotnet build`](../../core/tools/dotnet-build.md) en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e74c6-271">Calls [`dotnet build`](../../core/tools/dotnet-build.md) on the project.</span></span>
        - <span data-ttu-id="e74c6-272">Se dirige a la configuración de **lanzamiento** y se envía a */App/Build*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-272">Targeting the **Release** configuration and outputs to */app/build*.</span></span>
    1. <span data-ttu-id="e74c6-273">Inicializa una nueva fase de compilación a partir de la `build` imagen base existente y la asigna a su nombre `publish` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-273">Initializes a new build stage from the existing `build` base image and names it `publish`.</span></span>
    1. <span data-ttu-id="e74c6-274">Llama a `dotnet publish` en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="e74c6-274">Calls `dotnet publish` on the project.</span></span>
        - <span data-ttu-id="e74c6-275">Se dirige a la configuración de **lanzamiento** y se envía a */App/Publish*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-275">Targeting the **Release** configuration and outputs to */app/publish*.</span></span>
    1. <span data-ttu-id="e74c6-276">Inicializa una nueva fase de compilación a partir de la `publish` imagen base existente y la asigna a su nombre `final` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-276">Initializes a new build stage from the existing `publish` base image and names it `final`.</span></span>
    1. <span data-ttu-id="e74c6-277">Establece el directorio de trabajo en */App*.</span><span class="sxs-lookup"><span data-stu-id="e74c6-277">Sets the working directory to */app*.</span></span>
    1. <span data-ttu-id="e74c6-278">Copia el `/app/publish` Directorio de la `publish` imagen en la raíz de la `final` imagen.</span><span class="sxs-lookup"><span data-stu-id="e74c6-278">Copies the `/app/publish` directory from the `publish` image into the root of the `final` image.</span></span>
    1. <span data-ttu-id="e74c6-279">Establece el punto de entrada como la imagen en `dotnet` y pasa `DaprFrontEnd.dll` como un argumento.</span><span class="sxs-lookup"><span data-stu-id="e74c6-279">Sets the entry point as the image to `dotnet` and passes the `DaprFrontEnd.dll` as an arg.</span></span>

1. <span data-ttu-id="e74c6-280">En el `DaprBackEnd` proyecto de API Web, haga clic con el botón derecho en el nodo del proyecto y elija **Agregar**  >  **compatibilidad con el orquestador del contenedor**.</span><span class="sxs-lookup"><span data-stu-id="e74c6-280">In the `DaprBackEnd` web API project, right-click on the project node, and choose **Add** > **Container Orchestrator Support**.</span></span> <span data-ttu-id="e74c6-281">Elija **Docker Compose** y, a continuación, seleccione de nuevo **Linux** como sistema operativo de destino.</span><span class="sxs-lookup"><span data-stu-id="e74c6-281">Choose **Docker Compose**, and then select **Linux** again as the target OS.</span></span>

    <span data-ttu-id="e74c6-282">En la raíz del directorio del proyecto _DaprBackEnd_ , se creó una nueva *Dockerfile* .</span><span class="sxs-lookup"><span data-stu-id="e74c6-282">In the root of the _DaprBackEnd_ project directory, a new *Dockerfile* was created.</span></span> <span data-ttu-id="e74c6-283">*Dockerfile* contiene los siguientes YAML:</span><span class="sxs-lookup"><span data-stu-id="e74c6-283">The *Dockerfile* contains the following YAML:</span></span>

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

    <span data-ttu-id="e74c6-284">Abra el archivo *Docker-Compose. yml* de nuevo y examine su contenido.</span><span class="sxs-lookup"><span data-stu-id="e74c6-284">Open the *docker-compose.yml* file again and examine its contents.</span></span> <span data-ttu-id="e74c6-285">Visual Studio ha actualizado el archivo de **Docker Compose** .</span><span class="sxs-lookup"><span data-stu-id="e74c6-285">Visual Studio has updated the **Docker Compose** file.</span></span> <span data-ttu-id="e74c6-286">Ahora se incluyen ambos servicios:</span><span class="sxs-lookup"><span data-stu-id="e74c6-286">Now both services are included:</span></span>

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

1. <span data-ttu-id="e74c6-287">Para usar los bloques de creación de DAPR desde una aplicación en contenedor, deberá agregar los contenedores de DAPR sidecar al archivo de Compose.</span><span class="sxs-lookup"><span data-stu-id="e74c6-287">To use Dapr building blocks from inside a containerized application, you'll need to add the Dapr sidecars containers to your Compose file.</span></span> <span data-ttu-id="e74c6-288">Actualice cuidadosamente el contenido del archivo *Docker-Compose. yml* para que coincida con el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-288">Carefully update the content of the *docker-compose.yml* file to match the following example.</span></span> <span data-ttu-id="e74c6-289">Preste mucha atención a las pestañas formato y espaciado y no usar.</span><span class="sxs-lookup"><span data-stu-id="e74c6-289">Pay close attention to the formatting and spacing and don't use tabs.</span></span>

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

    <span data-ttu-id="e74c6-290">En el archivo actualizado, hemos agregado `daprfrontend-dapr` y `daprbackend-dapr` sidecar para los servicios de `daprfrontend` y, `daprbackend` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e74c6-290">In the updated file, we've added `daprfrontend-dapr` and `daprbackend-dapr` sidecars for the `daprfrontend` and `daprbackend` services respectively.</span></span> <span data-ttu-id="e74c6-291">En el archivo actualizado, preste especial atención a los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="e74c6-291">In the updated file, pay close attention to the following changes:</span></span>

    - <span data-ttu-id="e74c6-292">Los sidecares usan la `daprio/daprd:latest` imagen de contenedor.</span><span class="sxs-lookup"><span data-stu-id="e74c6-292">The sidecars use the `daprio/daprd:latest` container image.</span></span> <span data-ttu-id="e74c6-293">No se recomienda el uso de la `latest` etiqueta para escenarios de producción.</span><span class="sxs-lookup"><span data-stu-id="e74c6-293">The use of the `latest` tag isn't recommended for production scenarios.</span></span> <span data-ttu-id="e74c6-294">En el caso de producción, es mejor usar un número de versión específico.</span><span class="sxs-lookup"><span data-stu-id="e74c6-294">For production, it's better to use a specific version number.</span></span>
    - <span data-ttu-id="e74c6-295">Cada servicio definido en el archivo de Compose tiene su propio espacio de nombres de red con fines de aislamiento de red.</span><span class="sxs-lookup"><span data-stu-id="e74c6-295">Each service defined in the Compose file has its own network namespace for network isolation purposes.</span></span> <span data-ttu-id="e74c6-296">Los sidecares usan `network_mode: "service:..."` para asegurarse de que se ejecutan en el mismo espacio de nombres de red que la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-296">The sidecars use `network_mode: "service:..."` to ensure they run in the same network namespace as the application.</span></span> <span data-ttu-id="e74c6-297">Esto permite que el sidecar y la aplicación se comuniquen mediante `localhost` .</span><span class="sxs-lookup"><span data-stu-id="e74c6-297">Doing so allows the sidecar and the application to communicate using `localhost`.</span></span>
    - <span data-ttu-id="e74c6-298">Los puertos en los que los sidecares de DAPR escuchan la comunicación de gRPC (de forma predeterminada 50001) se deben exponer para permitir que los sidecars se comuniquen entre sí.</span><span class="sxs-lookup"><span data-stu-id="e74c6-298">The ports on which the Dapr sidecars are listening for gRPC communication (by default 50001) must be exposed to allow the sidecars to communicate with each other.</span></span>

1. <span data-ttu-id="e74c6-299">Ejecute la solución (<kbd>F5</kbd> o <kbd>Ctrl + F5</kbd>) para comprobar que funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="e74c6-299">Run the solution (<kbd>F5</kbd> or <kbd>Ctrl+F5</kbd>) to verify that it works as expected.</span></span> <span data-ttu-id="e74c6-300">Si todo está configurado correctamente, debería ver los datos de previsión meteorológica:</span><span class="sxs-lookup"><span data-stu-id="e74c6-300">If everything is configured correctly, you should see the weather forecast data:</span></span>

    :::image type="content" source="./media/getting-started/multicontainer-result.png" alt-text="Captura de pantalla de la solución final que muestra los datos de previsión meteorológica":::

    <span data-ttu-id="e74c6-302">Si se ejecuta localmente con Docker Compose y Visual Studio 2019, puede establecer puntos de interrupción y depurar en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e74c6-302">Running locally with Docker Compose and Visual Studio 2019, you can set breakpoints and debug into the application.</span></span> <span data-ttu-id="e74c6-303">En escenarios de producción, se recomienda hospedar la aplicación en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-303">For production scenarios, it's recommended to host your application in Kubernetes.</span></span> <span data-ttu-id="e74c6-304">Este libro incluye una aplicación de referencia adjunta, [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr), que contiene scripts para implementar en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="e74c6-304">This book includes an accompanying reference application, [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr), that contains scripts to deploy to Kubernetes.</span></span>

    <span data-ttu-id="e74c6-305">Para obtener más información sobre el bloque de creación de invocación del servicio DAPR usado en este tutorial, consulte el [capítulo 6](service-invocation.md).</span><span class="sxs-lookup"><span data-stu-id="e74c6-305">To learn more about the Dapr service invocation building block used in this walkthrough, refer to [chapter 6](service-invocation.md).</span></span>

## <a name="summary"></a><span data-ttu-id="e74c6-306">Resumen</span><span class="sxs-lookup"><span data-stu-id="e74c6-306">Summary</span></span>

<span data-ttu-id="e74c6-307">En este capítulo, ha tenido la oportunidad de *probar* la versión de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-307">In this chapter, you had an opportunity to *test drive* Dapr.</span></span> <span data-ttu-id="e74c6-308">Con el SDK de .NET de DAPR, vio cómo DAPR se integra con la plataforma de aplicaciones .NET.</span><span class="sxs-lookup"><span data-stu-id="e74c6-308">Using the Dapr .NET SDK, you saw how Dapr integrates with the .NET application platform.</span></span>

<span data-ttu-id="e74c6-309">El primer ejemplo era una aplicación de consola de .NET simple, con estado que usaba el bloque de creación de administración de estado de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-309">The first example was a simple, stateful, .NET Console application that used the Dapr state management building block.</span></span>

<span data-ttu-id="e74c6-310">El segundo ejemplo implica una aplicación de varios contenedores que se ejecuta en Docker.</span><span class="sxs-lookup"><span data-stu-id="e74c6-310">The second example involved a multi-container application running in Docker.</span></span> <span data-ttu-id="e74c6-311">Con Visual Studio con Docker Compose, ha experimentado la conocida *experiencia de depuración de F5* disponible en todas las aplicaciones .net.</span><span class="sxs-lookup"><span data-stu-id="e74c6-311">By using Visual Studio with Docker Compose, you experienced the familiar *F5 debugging experience* available across all .NET apps.</span></span>

<span data-ttu-id="e74c6-312">También tiene una mirada más detallada a los archivos de configuración de los componentes de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-312">You also got a closer look at Dapr component configuration files.</span></span> <span data-ttu-id="e74c6-313">Configuran la implementación de infraestructura real usada por los bloques de creación de DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-313">They configure the actual infrastructure implementation used by the Dapr building blocks.</span></span> <span data-ttu-id="e74c6-314">Puede utilizar espacios de nombres y ámbitos para restringir el acceso a componentes a entornos y aplicaciones concretos.</span><span class="sxs-lookup"><span data-stu-id="e74c6-314">You can use namespaces and scopes to restrict component access to particular environments and applications.</span></span>

<span data-ttu-id="e74c6-315">En los próximos capítulos, profundizaremos en los bloques de creación que ofrece DAPR.</span><span class="sxs-lookup"><span data-stu-id="e74c6-315">In the upcoming chapters, you'll dive deep into the building blocks offered by Dapr.</span></span>

### <a name="references"></a><span data-ttu-id="e74c6-316">Referencias</span><span class="sxs-lookup"><span data-stu-id="e74c6-316">References</span></span>

- [<span data-ttu-id="e74c6-317">Documentación de DAPR: introducción</span><span class="sxs-lookup"><span data-stu-id="e74c6-317">Dapr documentation - Getting started</span></span>](https://docs.dapr.io/getting-started)
- [<span data-ttu-id="e74c6-318">eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="e74c6-318">eShopOnDapr</span></span>](https://github.com/dotnet-architecture/eShopOnDapr)

> [!div class="step-by-step"]
> <span data-ttu-id="e74c6-319">[Anterior](dapr-at-20000-feet.md)
> [Siguiente](reference-application.md)</span><span class="sxs-lookup"><span data-stu-id="e74c6-319">[Previous](dapr-at-20000-feet.md)
[Next](reference-application.md)</span></span>
