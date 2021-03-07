---
title: El bloque de creación de secretos de DAPR
description: Una descripción del bloque de creación de secretos, sus características, ventajas y cómo aplicarlo
author: edwinvw
ms.date: 02/07/2021
ms.openlocfilehash: 94942b396af947b2a3e49b918b2b082c15f4bb08
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401851"
---
# <a name="the-dapr-secrets-building-block"></a><span data-ttu-id="617d4-103">El bloque de creación de secretos de DAPR</span><span class="sxs-lookup"><span data-stu-id="617d4-103">The Dapr secrets building block</span></span>

<span data-ttu-id="617d4-104">Las aplicaciones empresariales requieren secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-104">Enterprise applications require secrets.</span></span> <span data-ttu-id="617d4-105">Algunos ejemplos frecuentes son:</span><span class="sxs-lookup"><span data-stu-id="617d4-105">Common examples include:</span></span>

- <span data-ttu-id="617d4-106">Una cadena de conexión de base de datos que contiene un nombre de usuario y una contraseña.</span><span class="sxs-lookup"><span data-stu-id="617d4-106">A database connection string that contains a username and password.</span></span>
- <span data-ttu-id="617d4-107">Una clave de API para llamar a una API web externa.</span><span class="sxs-lookup"><span data-stu-id="617d4-107">An API key for calling an external web API.</span></span>
- <span data-ttu-id="617d4-108">Un certificado de cliente para autenticarse en un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="617d4-108">A client certificate for authenticating to an external system.</span></span>

<span data-ttu-id="617d4-109">Los secretos deben administrarse con cuidado para que nunca se revelen fuera de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-109">Secrets must be carefully managed so that they're never disclosed outside of the application.</span></span>

<span data-ttu-id="617d4-110">No hace mucho tiempo, era popular almacenar los secretos de aplicación en un archivo de configuración dentro del código base de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-110">Not long ago, it was popular to store application secrets in a configuration file inside the application codebase.</span></span> <span data-ttu-id="617d4-111">Los desarrolladores de .NET recordarán el archivo de *web.config* .</span><span class="sxs-lookup"><span data-stu-id="617d4-111">.NET developers will fondly recall the *web.config* file.</span></span> <span data-ttu-id="617d4-112">Aunque es fácil de implementar, la integración de secretos en junto con el código era muy segura.</span><span class="sxs-lookup"><span data-stu-id="617d4-112">While simple to implement, integrating secrets to along with code was far from secure.</span></span> <span data-ttu-id="617d4-113">Un error frecuente era incluir el archivo al insertarlo en un repositorio de GIT público y exponer los secretos al mundo.</span><span class="sxs-lookup"><span data-stu-id="617d4-113">A common misstep was to include the file when pushing to a public GIT repository, exposing the secrets to the world.</span></span>

<span data-ttu-id="617d4-114">Una metodología ampliamente aceptada para construir aplicaciones distribuidas modernas es [la aplicación Twelve-Factor](https://12factor.net/).</span><span class="sxs-lookup"><span data-stu-id="617d4-114">A widely accepted methodology for constructing modern distributed applications is [The Twelve-Factor App](https://12factor.net/).</span></span> <span data-ttu-id="617d4-115">Describe un conjunto de principios y prácticas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="617d4-115">It describes a set of principles and best practices.</span></span> <span data-ttu-id="617d4-116">Su tercer factor prescribe que *la configuración y los secretos se externalizan fuera de la base de código.*</span><span class="sxs-lookup"><span data-stu-id="617d4-116">Its third factor prescribes that *configuration and secrets be externalized outside of the code base.*</span></span>

<span data-ttu-id="617d4-117">Para solucionar este problema, la plataforma .NET Core incluye una característica de [Administrador secreto](/aspnet/core/security/app-secrets#secret-manager) que almacena datos confidenciales en una carpeta física fuera del árbol del proyecto.</span><span class="sxs-lookup"><span data-stu-id="617d4-117">To address this concern, the .NET Core platform includes a [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) feature that stores sensitive data in a physical folder outside of the project tree.</span></span> <span data-ttu-id="617d4-118">Aunque los secretos están fuera del control de código fuente, esta característica no cifra los datos.</span><span class="sxs-lookup"><span data-stu-id="617d4-118">While secrets are outside of source control, this feature doesn't encrypt data.</span></span> <span data-ttu-id="617d4-119">Está diseñado solo para **fines de desarrollo** .</span><span class="sxs-lookup"><span data-stu-id="617d4-119">It's designed for **development purposes** only.</span></span>

<span data-ttu-id="617d4-120">Una práctica más moderna y segura consiste en aislar secretos en una herramienta de administración de secretos como **Hashicorp Vault** o **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="617d4-120">A more modern and secure practice is to isolate secrets in a secrets management tool like **Hashicorp Vault** or **Azure Key Vault**.</span></span>  <span data-ttu-id="617d4-121">Estas herramientas permiten almacenar secretos externamente, variar las credenciales entre entornos y hacer referencia a ellos desde el código de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-121">These tools enable you to store secrets externally, vary credentials across environments, and reference them from application code.</span></span> <span data-ttu-id="617d4-122">Sin embargo, cada herramienta tiene sus complejidades y la curva de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="617d4-122">However, each tool has its complexities and learning curve.</span></span>

<span data-ttu-id="617d4-123">DAPR ofrece un bloque de creación que simplifica la administración de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-123">Dapr offers a building block that simplifies managing secrets.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="617d4-124">Qué resuelve</span><span class="sxs-lookup"><span data-stu-id="617d4-124">What it solves</span></span>

<span data-ttu-id="617d4-125">El [bloque de creación de secretos](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) de DAPR abstrae la complejidad del trabajo con secretos y herramientas de administración de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-125">The Dapr [secrets building block](https://docs.dapr.io/developing-applications/building-blocks/secrets/secrets-overview/) abstracts away the complexity of working with secrets and secret management tools.</span></span>

- <span data-ttu-id="617d4-126">Oculta la fontanería subyacente a través de una interfaz unificada.</span><span class="sxs-lookup"><span data-stu-id="617d4-126">It hides the underlying plumbing through a unified interface.</span></span>
- <span data-ttu-id="617d4-127">Admite varios componentes del almacén de secretos *conectables* , que pueden variar entre el desarrollo y la producción.</span><span class="sxs-lookup"><span data-stu-id="617d4-127">It supports various *pluggable* secret store components, which can vary between development and production.</span></span>
- <span data-ttu-id="617d4-128">Las aplicaciones no requieren dependencias directas en las bibliotecas de almacenamiento de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-128">Applications don't require direct dependencies on secret store libraries.</span></span>
- <span data-ttu-id="617d4-129">Los desarrolladores no requieren un conocimiento detallado de cada almacén de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-129">Developers don't require detailed knowledge of each secret store.</span></span>

<span data-ttu-id="617d4-130">DAPR controla todos los problemas anteriores.</span><span class="sxs-lookup"><span data-stu-id="617d4-130">Dapr handles all of the above concerns.</span></span>

<span data-ttu-id="617d4-131">El acceso a los secretos se protege a través de la autenticación y la autorización.</span><span class="sxs-lookup"><span data-stu-id="617d4-131">Access to the secrets is secured through authentication and authorization.</span></span> <span data-ttu-id="617d4-132">Solo una aplicación con derechos suficientes puede acceder a los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-132">Only an application with sufficient rights can access secrets.</span></span> <span data-ttu-id="617d4-133">Las aplicaciones que se ejecutan en Kubernetes también pueden usar su mecanismo de administración de secretos integrado.</span><span class="sxs-lookup"><span data-stu-id="617d4-133">Applications running in Kubernetes can also use its built-in secrets management mechanism.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="617d4-134">Funcionamiento</span><span class="sxs-lookup"><span data-stu-id="617d4-134">How it works</span></span>

<span data-ttu-id="617d4-135">Las aplicaciones usan el bloque de creación de secretos de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="617d4-135">Applications use the secrets building block in two ways:</span></span>

- <span data-ttu-id="617d4-136">Recupere un secreto directamente desde el bloque de aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-136">Retrieve a secret directly from the application block.</span></span>
- <span data-ttu-id="617d4-137">Hacer referencia a un secreto indirectamente desde una configuración de componente de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-137">Reference a secret indirectly from a Dapr component configuration.</span></span>

<span data-ttu-id="617d4-138">Primero se trata la recuperación de secretos directamente.</span><span class="sxs-lookup"><span data-stu-id="617d4-138">Retrieving secrets directly is covered first.</span></span> <span data-ttu-id="617d4-139">La referencia a un secreto desde un archivo de configuración de componentes de DAPR se trata en una sección posterior.</span><span class="sxs-lookup"><span data-stu-id="617d4-139">Referencing a secret from a Dapr component configuration file is addressed in a later section.</span></span>

<span data-ttu-id="617d4-140">La aplicación interactúa con un sidecar de DAPR cuando se usa el bloque de creación de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-140">The application interacts with a Dapr sidecar when using the secrets building block.</span></span> <span data-ttu-id="617d4-141">El sidecar expone la API de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-141">The sidecar exposes the secrets API.</span></span> <span data-ttu-id="617d4-142">Se puede llamar a la API con HTTP o gRPC.</span><span class="sxs-lookup"><span data-stu-id="617d4-142">The API can be called with either HTTP or gRPC.</span></span> <span data-ttu-id="617d4-143">Use la siguiente dirección URL para llamar a la API HTTP:</span><span class="sxs-lookup"><span data-stu-id="617d4-143">Use the following URL to call the HTTP API:</span></span>

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/<name>?<metadata>
```

<span data-ttu-id="617d4-144">La dirección URL contiene los segmentos siguientes:</span><span class="sxs-lookup"><span data-stu-id="617d4-144">The URL contains the following segments:</span></span>

- <span data-ttu-id="617d4-145">`<dapr-port>` especifica el número de puerto en el que escucha el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-145">`<dapr-port>` specifies the port number upon which the Dapr sidecar is listening.</span></span>
- <span data-ttu-id="617d4-146">`<store-name>` especifica el nombre del almacén de secretos de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-146">`<store-name>` specifies the name of the Dapr secret store.</span></span>
- <span data-ttu-id="617d4-147">`<name>` especifica el nombre del secreto que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="617d4-147">`<name>` specifies  the name of the secret to retrieve.</span></span>
- <span data-ttu-id="617d4-148">`<metadata>` proporciona información adicional para el secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-148">`<metadata>` provides additional information for the secret.</span></span> <span data-ttu-id="617d4-149">Este segmento es opcional y las propiedades de metadatos difieren en cada almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-149">This segment is optional and metadata properties differ per secret store.</span></span> <span data-ttu-id="617d4-150">Para obtener más información sobre las propiedades de metadatos, consulte la referencia de la [API de secretos]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/)).</span><span class="sxs-lookup"><span data-stu-id="617d4-150">For more information on metadata properties, see the [secrets API reference]([Secrets API reference | Dapr Docs](https://docs.dapr.io/reference/api/secrets_api/)).</span></span>

 > [!NOTE]
 > <span data-ttu-id="617d4-151">La dirección URL anterior representa la llamada de API de DAPR nativa disponible para cualquier plataforma de desarrollo que admita HTTP o gRPC.</span><span class="sxs-lookup"><span data-stu-id="617d4-151">The above URL represents the native Dapr API call available to any development platform that supports HTTP or gRPC.</span></span> <span data-ttu-id="617d4-152">Las plataformas populares como .NET, Java y go tienen sus propias API personalizadas.</span><span class="sxs-lookup"><span data-stu-id="617d4-152">Popular platforms like .NET, Java, and Go have their own custom APIs.</span></span>

<span data-ttu-id="617d4-153">La respuesta JSON contiene la clave y el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-153">The JSON response contains the key and value of the secret.</span></span>

<span data-ttu-id="617d4-154">En la figura 10-1 se muestra cómo DAPR controla una solicitud de la API de secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-154">Figure 10-1 shows how Dapr handles a request for the secrets API:</span></span>

![Diagrama de recuperación de un secreto mediante la API de secretos de DAPR.](media/secrets/secrets-flow.png)

<span data-ttu-id="617d4-156">**Figura 10-1**.</span><span class="sxs-lookup"><span data-stu-id="617d4-156">**Figure 10-1**.</span></span> <span data-ttu-id="617d4-157">Recuperación de un secreto con la API de secretos de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-157">Retrieving a secret with the Dapr secrets API.</span></span>

1. <span data-ttu-id="617d4-158">El servicio llama a la API DAPR Secrets, junto con el nombre del almacén secreto y el secreto que se va a recuperar.</span><span class="sxs-lookup"><span data-stu-id="617d4-158">The service calls the Dapr secrets API, along with the name of the secret store, and secret to retrieve.</span></span>
1. <span data-ttu-id="617d4-159">El sidecar de DAPR recupera el secreto especificado del almacén de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-159">The Dapr sidecar retrieves the specified secret from the secret store.</span></span>
1. <span data-ttu-id="617d4-160">El sidecar DAPR devuelve la información secreta al servicio.</span><span class="sxs-lookup"><span data-stu-id="617d4-160">The Dapr sidecar returns the secret information back to the service.</span></span>

<span data-ttu-id="617d4-161">Algunos almacenes secretos admiten el almacenamiento de varios pares clave-valor en un único secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-161">Some secret stores support storing multiple key/value pairs in a single secret.</span></span> <span data-ttu-id="617d4-162">En estos casos, la respuesta contendría varios pares clave-valor en una única respuesta JSON como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="617d4-162">For those scenarios, the response would contain multiple key/value pairs in a single JSON response as in the following example:</span></span>

```http
GET http://localhost:3500/v1.0/secrets/secret-store/interestRates?metadata.version_id=3
```

```json
{
  "tier1-percentage": "2.5",
  "tier2-percentage": "3.8",
  "tier3-percentage": "5.1"
}
```

<span data-ttu-id="617d4-163">La API DAPR Secrets también ofrece una operación para recuperar todos los secretos a los que la aplicación tiene acceso:</span><span class="sxs-lookup"><span data-stu-id="617d4-163">The Dapr secrets API also offers an operation to retrieve all the secrets the application has access to:</span></span>

```http
http://localhost:<dapr-port>/v1.0/secrets/<store-name>/bulk
```

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="617d4-164">Uso del SDK de .NET para DAPR</span><span class="sxs-lookup"><span data-stu-id="617d4-164">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="617d4-165">Para los desarrolladores de .NET, el SDK de .NET para DAPR simplifica la administración de secretos de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-165">For .NET developers, the Dapr .NET SDK streamlines Dapr secret management.</span></span> <span data-ttu-id="617d4-166">Considere el `DaprClient.GetSecretAsync` método.</span><span class="sxs-lookup"><span data-stu-id="617d4-166">Consider the `DaprClient.GetSecretAsync` method.</span></span> <span data-ttu-id="617d4-167">Permite recuperar un secreto directamente de cualquier almacén de secretos de DAPR con un esfuerzo mínimo.</span><span class="sxs-lookup"><span data-stu-id="617d4-167">It enables you to retrieve a secret directly from any Dapr secret store with minimal effort.</span></span> <span data-ttu-id="617d4-168">A continuación se muestra un ejemplo de obtención de un secreto de cadena de conexión para una base de datos SQL Server:</span><span class="sxs-lookup"><span data-stu-id="617d4-168">Here's an example of fetching a connection string secret for a SQL Server database:</span></span>

```csharp
var metadata = new Dictionary<string, string> { ["version_id"] = "3" };
Dictionary<string, string> secrets = await daprClient.GetSecretAsync("secret-store", "eshopsecrets", metadata);
string connectionString = secrets["customerdb"];
```

<span data-ttu-id="617d4-169">Los argumentos del `GetSecretAsync` método incluyen:</span><span class="sxs-lookup"><span data-stu-id="617d4-169">Arguments for the `GetSecretAsync` method include:</span></span>

- <span data-ttu-id="617d4-170">Nombre del componente de almacén de secretos de DAPR (' almacén de secretos ')</span><span class="sxs-lookup"><span data-stu-id="617d4-170">The name of the Dapr secret store component ('secret-store')</span></span>
- <span data-ttu-id="617d4-171">Secreto que se va a recuperar (' eshopsecrets ')</span><span class="sxs-lookup"><span data-stu-id="617d4-171">The secret to retrieve ('eshopsecrets')</span></span>
- <span data-ttu-id="617d4-172">Pares de clave/valor de metadatos opcionales (' version_id = 3 ')</span><span class="sxs-lookup"><span data-stu-id="617d4-172">Optional metadata key/value pairs ('version_id=3')</span></span>

<span data-ttu-id="617d4-173">El método responde con un objeto de diccionario como secreto puede contener varios pares clave-valor.</span><span class="sxs-lookup"><span data-stu-id="617d4-173">The method responds with a dictionary object as a secret can contain multiple key/value pairs.</span></span> <span data-ttu-id="617d4-174">En el ejemplo anterior, `customerdb` se hace referencia al secreto denominado desde la colección para devolver una cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="617d4-174">In the example above, the secret named `customerdb` is referenced from the collection to return a connection string.</span></span>

<span data-ttu-id="617d4-175">El SDK de .NET de DAPR también incluye un proveedor de configuración de .NET.</span><span class="sxs-lookup"><span data-stu-id="617d4-175">The Dapr .NET SDK also features a .NET configuration provider.</span></span> <span data-ttu-id="617d4-176">Carga los secretos especificados en la [API de configuración subyacente de .net Core](../../core/extensions/configuration.md).</span><span class="sxs-lookup"><span data-stu-id="617d4-176">It loads specified secrets into the underlying [.NET Core configuration API](../../core/extensions/configuration.md).</span></span> <span data-ttu-id="617d4-177">La aplicación en ejecución puede hacer referencia a los secretos del `IConfiguration` Diccionario registrado en ASP.net Core la inserción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="617d4-177">The running application can then reference secrets from the `IConfiguration` dictionary that is registered in ASP.NET Core dependency injection.</span></span>

<span data-ttu-id="617d4-178">El proveedor de configuración de secretos está disponible en el paquete NuGet [Dapr.Extensions.Configprimario](https://www.nuget.org/packages/Dapr.Extensions.Configuration) .</span><span class="sxs-lookup"><span data-stu-id="617d4-178">The secrets configuration provider is available from the [Dapr.Extensions.Configuration](https://www.nuget.org/packages/Dapr.Extensions.Configuration) NuGet package.</span></span> <span data-ttu-id="617d4-179">El proveedor se puede registrar en la `Program.cs` de una aplicación ASP.net web API:</span><span class="sxs-lookup"><span data-stu-id="617d4-179">The provider can be registered in the `Program.cs` of an ASP.NET Web API application:</span></span>  

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureAppConfiguration(config =>
        {
            var daprClient = new DaprClientBuilder().Build();
            var secretDescriptors = new List<DaprSecretDescriptor>
            {
                new DaprSecretDescriptor("eshopsecrets")
            };
            config.AddDaprSecretStore("secret-store", secretDescriptors, daprClient);
        })
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

<span data-ttu-id="617d4-180">En el ejemplo anterior se carga la `eshopsecrets` colección Secrets en el sistema de configuración de .net en el inicio.</span><span class="sxs-lookup"><span data-stu-id="617d4-180">The above example loads the `eshopsecrets` secrets collection into the .NET configuration system at startup.</span></span> <span data-ttu-id="617d4-181">El registro del proveedor requiere una instancia de `DaprClient` para invocar la API de Secrets en el sidecar de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-181">Registering the provider requires an instance of `DaprClient` to invoke the secrets API on the Dapr sidecar.</span></span> <span data-ttu-id="617d4-182">Los demás argumentos incluyen el nombre del almacén secreto y un `DaprSecretDescriptor` objeto con el nombre del secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-182">The other arguments include the name of the secret store and a `DaprSecretDescriptor` object with the name of the secret.</span></span>

<span data-ttu-id="617d4-183">Una vez cargados, puede recuperar los secretos directamente del código de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="617d4-183">Once loaded, you can retrieve secrets directly from application code:</span></span>

```csharp
public void GetCustomer(IConfiguration config)
{
    var connectionString = config["eshopsecrets"]["customerdb"];
}
```

## <a name="secret-store-components"></a><span data-ttu-id="617d4-184">Componentes del almacén secreto</span><span class="sxs-lookup"><span data-stu-id="617d4-184">Secret store components</span></span>

<span data-ttu-id="617d4-185">El bloque de creación de secretos admite varios componentes de almacén de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-185">The secrets building block supports several secret store components.</span></span> <span data-ttu-id="617d4-186">En el momento de la escritura, están disponibles los siguientes almacenes secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-186">At the time of writing, the following secret stores are available:</span></span>

- <span data-ttu-id="617d4-187">Variables de entorno</span><span class="sxs-lookup"><span data-stu-id="617d4-187">Environment Variables</span></span>
- <span data-ttu-id="617d4-188">Archivo local</span><span class="sxs-lookup"><span data-stu-id="617d4-188">Local file</span></span>
- <span data-ttu-id="617d4-189">Secretos de Kubernetes</span><span class="sxs-lookup"><span data-stu-id="617d4-189">Kubernetes secrets</span></span>
- <span data-ttu-id="617d4-190">Administrador de secretos de AWS</span><span class="sxs-lookup"><span data-stu-id="617d4-190">AWS Secrets Manager</span></span>
- <span data-ttu-id="617d4-191">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="617d4-191">Azure Key Vault</span></span>
- <span data-ttu-id="617d4-192">Administrador de secretos de GCP</span><span class="sxs-lookup"><span data-stu-id="617d4-192">GCP Secret Manager</span></span>
- <span data-ttu-id="617d4-193">Almacén de HashiCorp</span><span class="sxs-lookup"><span data-stu-id="617d4-193">HashiCorp Vault</span></span>

> [!IMPORTANT]
> <span data-ttu-id="617d4-194">Las variables de entorno y los componentes de archivo local están diseñados solo para cargas de trabajo de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="617d4-194">The environment variables and local file components are designed for development workloads only.</span></span>

<span data-ttu-id="617d4-195">En las secciones siguientes se muestra cómo configurar un almacén de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-195">The following sections show how to configure a secret store.</span></span>

### <a name="configuration"></a><span data-ttu-id="617d4-196">Configuración</span><span class="sxs-lookup"><span data-stu-id="617d4-196">Configuration</span></span>

<span data-ttu-id="617d4-197">Un almacén de secretos se configura mediante un archivo de configuración de componentes de DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-197">You configure a secret store using a Dapr component configuration file.</span></span> <span data-ttu-id="617d4-198">A continuación se muestra la estructura típica del archivo:</span><span class="sxs-lookup"><span data-stu-id="617d4-198">The typical structure of the file is shown below:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: [component name]
  namespace: [namespace]
spec:
  type: secretstores.[secret store type]
  version: [secret store version]
  metadata:
  - name: [property name]
    value: [property value]
```

<span data-ttu-id="617d4-199">Todos los archivos de configuración de componentes de DAPR requieren un `name` junto con un `namespace` valor opcional.</span><span class="sxs-lookup"><span data-stu-id="617d4-199">All Dapr component configuration files require a `name` along with an optional `namespace` value.</span></span> <span data-ttu-id="617d4-200">Además, el `type` campo de la `spec` sección especifica el tipo de componente de almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-200">Additionally, the `type` field in the `spec` section specifies the type of secret store component.</span></span> <span data-ttu-id="617d4-201">Las propiedades de la `metadata` sección difieren en cada almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-201">The properties in the `metadata` section differ per secret store.</span></span>

### <a name="indirectly-consume-dapr-secrets"></a><span data-ttu-id="617d4-202">Consumo indirecto de secretos de DAPR</span><span class="sxs-lookup"><span data-stu-id="617d4-202">Indirectly consume Dapr secrets</span></span>

<span data-ttu-id="617d4-203">Como se mencionó anteriormente en este capítulo, las aplicaciones también pueden consumir secretos haciendo referencia a ellos en archivos de configuración de componentes.</span><span class="sxs-lookup"><span data-stu-id="617d4-203">As mentioned earlier in this chapter, applications can also consume secrets by referencing them in component configuration files.</span></span> <span data-ttu-id="617d4-204">Considere la posibilidad de usar un [componente de administración de estado](state-management.md) que use Redis cache para almacenar el estado:</span><span class="sxs-lookup"><span data-stu-id="617d4-204">Consider a [state management component](state-management.md) that uses Redis cache for storing state:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    value: e$h0p0nD@pr
```

<span data-ttu-id="617d4-205">El archivo de configuración anterior contiene una contraseña de **texto no cifrado** para conectarse al servidor de Redis.</span><span class="sxs-lookup"><span data-stu-id="617d4-205">The above configuration file contains a **clear-text** password for connecting to the Redis server.</span></span> <span data-ttu-id="617d4-206">Las contraseñas **codificadas** siempre son una buena idea.</span><span class="sxs-lookup"><span data-stu-id="617d4-206">**Hardcoded** passwords are always a bad idea.</span></span> <span data-ttu-id="617d4-207">La inserción de este archivo de configuración en un repositorio público expondría la contraseña.</span><span class="sxs-lookup"><span data-stu-id="617d4-207">Pushing this configuration file to a public repository would expose the password.</span></span> <span data-ttu-id="617d4-208">El almacenamiento de la contraseña en un almacén secreto mejoraría drásticamente este escenario.</span><span class="sxs-lookup"><span data-stu-id="617d4-208">Storing the password in a secret store would dramatically improve this scenario.</span></span>

<span data-ttu-id="617d4-209">En los siguientes ejemplos se muestra el uso de varios almacenes secretos diferentes.</span><span class="sxs-lookup"><span data-stu-id="617d4-209">The following examples demonstrate this using several different secret stores.</span></span>

### <a name="local-file"></a><span data-ttu-id="617d4-210">Archivo local</span><span class="sxs-lookup"><span data-stu-id="617d4-210">Local file</span></span>

<span data-ttu-id="617d4-211">El componente de archivo local está diseñado para escenarios de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="617d4-211">The local file component is designed for development scenarios.</span></span> <span data-ttu-id="617d4-212">Almacena secretos en el sistema de archivos local dentro de un archivo JSON.</span><span class="sxs-lookup"><span data-stu-id="617d4-212">It stores secrets on the local filesystem inside a JSON file.</span></span> <span data-ttu-id="617d4-213">A continuación se muestra un ejemplo denominado `eshop-secrets.json` .</span><span class="sxs-lookup"><span data-stu-id="617d4-213">Here's an example named `eshop-secrets.json`.</span></span> <span data-ttu-id="617d4-214">Contiene una contraseña de un solo secreto para Redis:</span><span class="sxs-lookup"><span data-stu-id="617d4-214">It contains a single secret - a password for Redis:</span></span>

```json
{
  "eShopRedisPassword": "e$h0p0nD@pr"
}
```

<span data-ttu-id="617d4-215">Este archivo se coloca en una `components` carpeta que se especifica al ejecutar la aplicación DAPR.</span><span class="sxs-lookup"><span data-stu-id="617d4-215">You place this file in a `components` folder that you specify when running the Dapr application.</span></span>

<span data-ttu-id="617d4-216">El siguiente archivo de configuración del almacén secreto utiliza el archivo JSON como almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-216">The following secret store configuration file consumes the JSON file as a secret store.</span></span> <span data-ttu-id="617d4-217">También se coloca en la `components` carpeta:</span><span class="sxs-lookup"><span data-stu-id="617d4-217">It's also placed in the `components` folder:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-local-secret-store
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secrets.json
  - name: nestedSeparator
    value: ":"
```

<span data-ttu-id="617d4-218">El tipo de componente es `secretstore.local.file` .</span><span class="sxs-lookup"><span data-stu-id="617d4-218">The component type is `secretstore.local.file`.</span></span> <span data-ttu-id="617d4-219">El `secretsFile` elemento de metadatos especifica la ruta de acceso al archivo de secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-219">The `secretsFile` metadata element specifies the path to the secrets file.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="617d4-220">La ruta de acceso a un archivo de secretos puede ser una ruta de acceso absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="617d4-220">The path to a secrets file can be a absolute or relative path.</span></span> <span data-ttu-id="617d4-221">La ruta de acceso relativa se basa en la carpeta en la que se inicia la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-221">The relative path is based on the folder in which the application starts.</span></span> <span data-ttu-id="617d4-222">En el ejemplo, la `components` carpeta es una subcarpeta del directorio que contiene la aplicación .net.</span><span class="sxs-lookup"><span data-stu-id="617d4-222">In the example, the `components` folder is a sub-folder of the directory that contains the .NET application.</span></span>

<span data-ttu-id="617d4-223">En la carpeta de la aplicación, inicie la aplicación DAPR especificando la `components` ruta de acceso como un argumento de línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="617d4-223">From the application folder, start the Dapr application specifying the `components` path as a command-line argument:</span></span>

```console
dapr run --app-id basket-api --components-path ./components dotnet run
```

> [!NOTE]
> <span data-ttu-id="617d4-224">Este ejemplo anterior se aplica a la ejecución de DAPR en modo autohospedado.</span><span class="sxs-lookup"><span data-stu-id="617d4-224">This above example applies to running Dapr in self-hosted mode.</span></span> <span data-ttu-id="617d4-225">Para el hospedaje de Kubernetes, considere la posibilidad de usar montajes de volumen.</span><span class="sxs-lookup"><span data-stu-id="617d4-225">For Kubernetes hosting, consider using volume mounts.</span></span>

<span data-ttu-id="617d4-226">`nestedSeparator`En un archivo de configuración de DAPR se especifica un carácter para *aplanar* una jerarquía JSON.</span><span class="sxs-lookup"><span data-stu-id="617d4-226">The `nestedSeparator` in a Dapr configuration file specifies a character to *flatten* a JSON hierarchy.</span></span> <span data-ttu-id="617d4-227">Considere el siguiente fragmento de código:</span><span class="sxs-lookup"><span data-stu-id="617d4-227">Consider the following snippet:</span></span>

```json
{
    "redisPassword": "some password",
    "connectionStrings": {
        "customerdb": "some connection string",
        "productdb": "some connection string"
    }
}
```

<span data-ttu-id="617d4-228">Si usa un signo de dos puntos como separador, puede recuperar la `customerdb` cadena de conexión mediante la clave `connectionStrings:customerdb` .</span><span class="sxs-lookup"><span data-stu-id="617d4-228">Using a colon as a separator, you can retrieve the `customerdb` connection-string using the key `connectionStrings:customerdb`.</span></span>

> [!NOTE]
> <span data-ttu-id="617d4-229">El signo de dos puntos `:` es el valor del separador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="617d4-229">The colon `:` is the default separator value.</span></span>

<span data-ttu-id="617d4-230">En el ejemplo siguiente, un archivo de configuración de administración de estado hace referencia al componente de almacén secreto local para obtener la contraseña para conectarse al servidor de Redis:</span><span class="sxs-lookup"><span data-stu-id="617d4-230">In the next example, a state management configuration file references the local secret store component to obtain the password for connecting to the Redis server:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: localhost:6379
  - name: redisPassword
    secretKeyRef:
      name: eShopRedisPassword
      key: eShopRedisPassword
auth:
  secretStore: eshop-local-secret-store
```

<span data-ttu-id="617d4-231">El `secretKeyRef` elemento hace referencia al secreto que contiene la contraseña.</span><span class="sxs-lookup"><span data-stu-id="617d4-231">The `secretKeyRef` element references the secret containing the password.</span></span> <span data-ttu-id="617d4-232">Reemplaza el valor *de texto no cifrado* anterior.</span><span class="sxs-lookup"><span data-stu-id="617d4-232">It replaces the earlier *clear-text* value.</span></span> <span data-ttu-id="617d4-233">El nombre del secreto y el nombre de la clave, `eShopRedisPassword` , hacen referencia al secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-233">The secret name and the key name, `eShopRedisPassword`, reference the secret.</span></span> <span data-ttu-id="617d4-234">El nombre del componente de administración de secretos `eshop-local-secret-store` se encuentra en el `auth` elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="617d4-234">The name of the secret management component `eshop-local-secret-store` is found in the `auth` metadata element.</span></span>

<span data-ttu-id="617d4-235">Es posible que se pregunte por qué `eShopRedisPassword` es idéntico para el nombre y la clave en la referencia secreta.</span><span class="sxs-lookup"><span data-stu-id="617d4-235">You might wonder why `eShopRedisPassword` is identical for both the name and key in the secret reference.</span></span> <span data-ttu-id="617d4-236">En el almacén secreto de archivo local, los secretos no se identifican con un nombre independiente.</span><span class="sxs-lookup"><span data-stu-id="617d4-236">In the local file secret store, secrets aren't identified with a separate name.</span></span> <span data-ttu-id="617d4-237">El escenario será diferente en el ejemplo siguiente con secretos de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="617d4-237">The scenario will be different in the next example using Kubernetes secrets.</span></span>

### <a name="kubernetes-secret"></a><span data-ttu-id="617d4-238">Kubernetes secreto</span><span class="sxs-lookup"><span data-stu-id="617d4-238">Kubernetes secret</span></span>

<span data-ttu-id="617d4-239">Este segundo ejemplo se centra en una aplicación DAPR que se ejecuta en Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="617d4-239">This second example focuses on a Dapr application running in Kubernetes.</span></span> <span data-ttu-id="617d4-240">Utiliza el mecanismo de secretos estándar que proporciona Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="617d4-240">It uses the standard secrets mechanism that Kubernetes offers.</span></span> <span data-ttu-id="617d4-241">Use la CLI de Kubernetes ( `kubectl` ) para crear un secreto denominado `eshop-redis-secret` que contenga la contraseña:</span><span class="sxs-lookup"><span data-stu-id="617d4-241">Use the Kubernetes CLI (`kubectl`) to create a secret named `eshop-redis-secret` that contains the password:</span></span>

```console
kubectl create secret generic eshopsecrets --from-literal=redisPassword=e$h0p0nD@pr -n eshop
```

<span data-ttu-id="617d4-242">Una vez creado, puede hacer referencia al secreto en el archivo de configuración de componentes para la administración de Estados:</span><span class="sxs-lookup"><span data-stu-id="617d4-242">Once created, you can reference the secret in the component configuration file for state management:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-basket-statestore
  namespace: eshop
spec:
  type: state.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: eshopsecrets
      key: redisPassword
auth:
  secretStore: kubernetes
```

<span data-ttu-id="617d4-243">El `secretKeyRef` elemento especifica el nombre del secreto de Kubernetes y la clave del secreto, `eshopsecrets` y, `redisPassword` respectivamente.</span><span class="sxs-lookup"><span data-stu-id="617d4-243">The `secretKeyRef` element specifies the name of the Kubernetes secret and the secret's key, `eshopsecrets`, and `redisPassword` respectively.</span></span> <span data-ttu-id="617d4-244">La `auth` sección de metadatos indica a DAPR que use el componente de administración de secretos de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="617d4-244">The `auth` metadata section instructs Dapr to use the Kubernetes secrets management component.</span></span>

> [!NOTE]
> <span data-ttu-id="617d4-245">Auth es el valor predeterminado cuando se usan secretos de Kubernetes y se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="617d4-245">Auth is the default value when using Kubernetes secrets and can be omitted.</span></span>

<span data-ttu-id="617d4-246">En una configuración de producción, los secretos se crean normalmente como parte de una canalización de CI/CD automatizada.</span><span class="sxs-lookup"><span data-stu-id="617d4-246">In a production setting, secrets are typically created as part of an automated CI/CD pipeline.</span></span> <span data-ttu-id="617d4-247">Esto garantiza que solo las personas con permisos suficientes puedan tener acceso a los secretos y cambiarlos.</span><span class="sxs-lookup"><span data-stu-id="617d4-247">Doing so ensures only people with sufficient permissions can access and change the secrets.</span></span> <span data-ttu-id="617d4-248">Los desarrolladores crean archivos de configuración sin conocer el valor real de los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-248">Developers create configuration files without knowing the actual value of the secrets.</span></span>

### <a name="azure-key-vault"></a><span data-ttu-id="617d4-249">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="617d4-249">Azure Key Vault</span></span>

<span data-ttu-id="617d4-250">El ejemplo siguiente está orientado hacia un escenario de producción real.</span><span class="sxs-lookup"><span data-stu-id="617d4-250">The next example is geared toward a real-world production scenario.</span></span> <span data-ttu-id="617d4-251">Usa **Azure Key Vault** como almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-251">It uses **Azure Key Vault** as the secret store.</span></span> <span data-ttu-id="617d4-252">Azure Key Vault es un servicio administrado de Azure que permite almacenar secretos de forma segura en la nube.</span><span class="sxs-lookup"><span data-stu-id="617d4-252">Azure Key Vault is a managed Azure service that enables secrets to be stored securely in the cloud.</span></span>

<span data-ttu-id="617d4-253">Para que este ejemplo funcione, deben cumplirse los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="617d4-253">For this example to work, the following prerequisites must be satisfied:</span></span>

- <span data-ttu-id="617d4-254">Ha protegido el acceso administrativo a una suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="617d4-254">You've secured administrative access to an Azure subscription.</span></span>
- <span data-ttu-id="617d4-255">Ha aprovisionado una Azure Key Vault denominada que contiene `eshopkv` un secreto denominado `redisPassword` que contiene la contraseña para conectarse al servidor de Redis.</span><span class="sxs-lookup"><span data-stu-id="617d4-255">You've provisioned an Azure Key Vault named `eshopkv` that holds a secret named `redisPassword` that contains the password for connecting to the Redis server.</span></span>
- <span data-ttu-id="617d4-256">Ha creado una [entidad de servicio](/azure/active-directory/develop/howto-create-service-principal-portal) en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="617d4-256">You've created [service principal](/azure/active-directory/develop/howto-create-service-principal-portal) in Azure Active Directory.</span></span>
- <span data-ttu-id="617d4-257">Ha instalado un certificado X509 para esta entidad de servicio (que contiene la clave pública y la clave privada) en el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="617d4-257">You've installed an X509 certificate for this service principal (containing both the public and private key) on the local filesystem.</span></span>

> [!NOTE]
> <span data-ttu-id="617d4-258">Una entidad de servicio es una identidad que una aplicación puede usar para autenticar un servicio de Azure.</span><span class="sxs-lookup"><span data-stu-id="617d4-258">A service principal is an identity that can be used by an application to authenticate an Azure service.</span></span> <span data-ttu-id="617d4-259">La entidad de servicio utiliza un certificado X509.</span><span class="sxs-lookup"><span data-stu-id="617d4-259">The service principal uses a X509 certificate.</span></span> <span data-ttu-id="617d4-260">La aplicación utiliza este certificado como credencial para autenticarse.</span><span class="sxs-lookup"><span data-stu-id="617d4-260">The application uses this certificate as a credential to authenticate itself.</span></span>

<span data-ttu-id="617d4-261">La [documentación de Dapr Azure Key Vault Secret Store](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) proporciona instrucciones paso a paso para crear y configurar un entorno de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-261">The [Dapr Azure Key Vault secret store documentation](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault/) provides step-by-step instructions to create and configure a Key Vault environment.</span></span>

#### <a name="use-key-vault-when-running-in-self-hosted-mode"></a><span data-ttu-id="617d4-262">Usar Key Vault cuando se ejecuta en modo autohospedado</span><span class="sxs-lookup"><span data-stu-id="617d4-262">Use Key Vault when running in self-hosted mode</span></span>

<span data-ttu-id="617d4-263">El consumo de Azure Key Vault en el modo autohospedado de DAPR requiere el siguiente archivo de configuración:</span><span class="sxs-lookup"><span data-stu-id="617d4-263">Consuming Azure Key Vault in Dapr self-hosted mode requires the following configuration file:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: eshopkv
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificateFile
    value : "azurekv-spn-cert.pfx"
```

<span data-ttu-id="617d4-264">El tipo de almacén secreto es `secretstores.azure.keyvault` .</span><span class="sxs-lookup"><span data-stu-id="617d4-264">The secret store type is `secretstores.azure.keyvault`.</span></span> <span data-ttu-id="617d4-265">El `metadata` elemento para configurar el acceso a Key Vault requiere las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="617d4-265">The `metadata` element to configure access to Key Vault requires the following properties:</span></span>

- <span data-ttu-id="617d4-266">El `vaultName` contiene el nombre del Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-266">The `vaultName` contains the name of the Azure Key Vault.</span></span>
- <span data-ttu-id="617d4-267">`spnTenantId`Contiene el *identificador de inquilino* de la entidad de servicio utilizada para autenticarse en el Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-267">The `spnTenantId` contains the *tenant ID* of the service principal used to authenticate against the Key Vault.</span></span>
- <span data-ttu-id="617d4-268">El `spnClientId` contiene el *identificador* de la aplicación de la entidad de servicio que se usa para autenticarse en el Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-268">The `spnClientId` contains the *app ID* of the service principal used to authenticate against the Key Vault.</span></span>
- <span data-ttu-id="617d4-269">`spnCertificateFile`Contiene la ruta de acceso al archivo de certificado de la entidad de servicio para autenticarse en el Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-269">The `spnCertificateFile` contains the path to the certificate file for the service principal to authenticate against the Key Vault.</span></span>

> [!TIP]
> <span data-ttu-id="617d4-270">Puede copiar la información de la entidad de servicio desde el Azure Portal o CLI de Azure.</span><span class="sxs-lookup"><span data-stu-id="617d4-270">You can copy the service principal information from the Azure portal or Azure CLI .</span></span>

<span data-ttu-id="617d4-271">Ahora la aplicación puede recuperar la contraseña de Redis desde el Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-271">Now the application can retrieve the Redis password from the Azure Key Vault.</span></span>

#### <a name="use-key-vault-when-running-on-kubernetes"></a><span data-ttu-id="617d4-272">Usar Key Vault cuando se ejecuta en Kubernetes</span><span class="sxs-lookup"><span data-stu-id="617d4-272">Use Key Vault when running on Kubernetes</span></span>

<span data-ttu-id="617d4-273">El consumo de Azure Key Vault con DAPR y Kubernetes también requiere una entidad de servicio para autenticarse en el Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-273">Consuming Azure Key Vault with Dapr and Kubernetes also requires a service principal to authenticate against the Azure Key Vault.</span></span>

<span data-ttu-id="617d4-274">En primer lugar, cree un *secreto de Kubernetes* que contenga un archivo de certificado mediante la herramienta de la CLI de kubectl:</span><span class="sxs-lookup"><span data-stu-id="617d4-274">First, create a *Kubernetes secret* that contains a certificate file using the kubectl CLI tool:</span></span>

```console
kubectl create secret generic [k8s_spn_secret_name] --from-file=[pfx_certificate_file_local_path] -n eshop
```

<span data-ttu-id="617d4-275">El comando requiere dos argumentos de la línea de comandos:</span><span class="sxs-lookup"><span data-stu-id="617d4-275">The command requires two command-line arguments:</span></span>

- <span data-ttu-id="617d4-276">`[k8s_spn_secret_name]` es el nombre del secreto en el almacén de secretos de Kubernetes.</span><span class="sxs-lookup"><span data-stu-id="617d4-276">`[k8s_spn_secret_name]` is the secret name in Kubernetes secret store.</span></span>
- <span data-ttu-id="617d4-277">`[pfx_certificate_file_local_path]` es la ruta de acceso del archivo de certificado X509.</span><span class="sxs-lookup"><span data-stu-id="617d4-277">`[pfx_certificate_file_local_path]` is the path of X509 certificate file.</span></span>

<span data-ttu-id="617d4-278">Una vez creado, puede hacer referencia al secreto de Kubernetes en el archivo de configuración del componente de almacén de secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-278">Once created, you can reference the Kubernetes secret in the secret store component configuration file:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-azurekv-secret-store
  namespace: eshop
spec:
  type: secretstores.azure.keyvault
  version: v1
  metadata:
  - name: vaultName
    value: [your_keyvault_name]
  - name: spnTenantId
    value: "619926af-a7c3-4e95-93ed-4ecc4e3e652b"
  - name: spnClientId
    value: "6cf48032-6c38-43be-9d6f-2a43ce736b09"
  - name: spnCertificate
    secretKeyRef:
      name: [k8s_spn_secret_name]
      key: [pfx_certificate_file_local_name]
auth:
    secretStore: kubernetes
```

<span data-ttu-id="617d4-279">En este momento, una aplicación que se ejecuta en Kubernetes puede recuperar la contraseña de Redis desde el Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-279">At this point, an application running in Kubernetes can retrieve the Redis password from the Azure Key Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="617d4-280">Es fundamental mantener el archivo de certificado X509 de la entidad de servicio en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="617d4-280">It's critical to keep the X509 certificate file for the service principal in a safe place.</span></span> <span data-ttu-id="617d4-281">Es mejor colocarlo en una carpeta conocida fuera del repositorio de código fuente.</span><span class="sxs-lookup"><span data-stu-id="617d4-281">It's best to place it in a well-known folder outside the source-code repository.</span></span> <span data-ttu-id="617d4-282">El archivo de configuración puede hacer referencia al archivo de certificado desde esta carpeta conocida.</span><span class="sxs-lookup"><span data-stu-id="617d4-282">The configuration file can then reference the certificate file from this well-known folder.</span></span> <span data-ttu-id="617d4-283">En una máquina de desarrollo local, es responsable de copiar el certificado en la carpeta.</span><span class="sxs-lookup"><span data-stu-id="617d4-283">On a local development machine, you're responsible for copying the certificate to the folder.</span></span> <span data-ttu-id="617d4-284">En el caso de las implementaciones automatizadas, la canalización copiará el certificado en el equipo donde se implementa la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-284">For automated deployments, the pipeline will copy the certificate to the machine where the application is deployed.</span></span> <span data-ttu-id="617d4-285">Se recomienda usar una entidad de servicio diferente por entorno.</span><span class="sxs-lookup"><span data-stu-id="617d4-285">It's a best practice to use a different service principal per environment.</span></span> <span data-ttu-id="617d4-286">Al hacerlo, se evita que la entidad de servicio de un entorno de desarrollo tenga acceso a los secretos en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="617d4-286">Doing so prevents the service principal from a DEVELOPMENT environment to access secrets in a PRODUCTION environment.</span></span>

<span data-ttu-id="617d4-287">Cuando se ejecuta en Azure Kubernetes Service (AKS), es preferible usar una [identidad administrada de Azure](/azure/active-directory/managed-identities-azure-resources/overview) para autenticarse en Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="617d4-287">When running in  Azure Kubernetes Service (AKS), it's preferable to use an [Azure Managed Identity](/azure/active-directory/managed-identities-azure-resources/overview) for authenticating against Azure Key Vault.</span></span> <span data-ttu-id="617d4-288">Las identidades administradas están fuera del ámbito de este libro, pero se explican en la documentación de [Azure Key Vault con identidades administradas](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) .</span><span class="sxs-lookup"><span data-stu-id="617d4-288">Managed identities are outside of the scope of this book, but explained in the [Azure Key Vault with managed identities](https://docs.dapr.io/operations/components/setup-secret-store/supported-secret-stores/azure-keyvault-managed-identity/) documentation.</span></span>

### <a name="scope-secrets"></a><span data-ttu-id="617d4-289">Secretos de ámbito</span><span class="sxs-lookup"><span data-stu-id="617d4-289">Scope secrets</span></span>

<span data-ttu-id="617d4-290">Los ámbitos secretos permiten controlar los secretos a los que puede tener acceso la aplicación.</span><span class="sxs-lookup"><span data-stu-id="617d4-290">Secret scopes allow you to control which secrets your application can access.</span></span> <span data-ttu-id="617d4-291">Los ámbitos se configuran en un archivo de configuración de DAPR sidecar.</span><span class="sxs-lookup"><span data-stu-id="617d4-291">You configure scopes in a Dapr sidecar configuration file.</span></span> <span data-ttu-id="617d4-292">La [documentación de configuración de DAPR](https://docs.dapr.io/operations/configuration/configuration-overview/) proporciona instrucciones para el ámbito de los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-292">The [Dapr configuration documentation](https://docs.dapr.io/operations/configuration/configuration-overview/) provides instructions for scoping secrets.</span></span>

<span data-ttu-id="617d4-293">A continuación se muestra un ejemplo de un archivo de configuración de DAPR sidecar que contiene ámbitos secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-293">Here's an example of a Dapr sidecar configuration file that contains secret scopes:</span></span>

```yml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  secrets:
    scopes:
      - storeName: eshop-azurekv-secret-store
        defaultAccess: allow
        deniedSecrets: ["redisPassword", "apiKey"]
```

<span data-ttu-id="617d4-294">Especifique los ámbitos por almacén secreto.</span><span class="sxs-lookup"><span data-stu-id="617d4-294">You specify scopes per secret store.</span></span> <span data-ttu-id="617d4-295">En el ejemplo anterior, el almacén de secretos se denomina `eshop-azurekv-secret-store` .</span><span class="sxs-lookup"><span data-stu-id="617d4-295">In the above example, the secret store is named `eshop-azurekv-secret-store`.</span></span> <span data-ttu-id="617d4-296">Configure el acceso a los secretos con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="617d4-296">You configure access to secrets using the following properties:</span></span>

| <span data-ttu-id="617d4-297">Propiedad</span><span class="sxs-lookup"><span data-stu-id="617d4-297">Property</span></span>         | <span data-ttu-id="617d4-298">Valor</span><span class="sxs-lookup"><span data-stu-id="617d4-298">Value</span></span>               | <span data-ttu-id="617d4-299">Descripción</span><span class="sxs-lookup"><span data-stu-id="617d4-299">Description</span></span>                                                                                                                       |
|------------------|---------------------|-----------------------------------------------------------------------------------------------------------------------------------|
| `defaultAccess`  | <span data-ttu-id="617d4-300">`allow` o `deny`</span><span class="sxs-lookup"><span data-stu-id="617d4-300">`allow` or `deny`</span></span>   | <span data-ttu-id="617d4-301">Permite o deniega el acceso a *todos los* secretos del almacén secreto especificado.</span><span class="sxs-lookup"><span data-stu-id="617d4-301">Allows or denies access to *all* secrets in the specified secret store.</span></span> <span data-ttu-id="617d4-302">Esta propiedad es opcional y su valor predeterminado es `allow` .</span><span class="sxs-lookup"><span data-stu-id="617d4-302">This property is optional with a default value of `allow`.</span></span> |
| `allowedSecrets` | <span data-ttu-id="617d4-303">Lista de claves secretas</span><span class="sxs-lookup"><span data-stu-id="617d4-303">List of secret keys</span></span> | <span data-ttu-id="617d4-304">Se podrá acceder a los secretos especificados en la matriz.</span><span class="sxs-lookup"><span data-stu-id="617d4-304">Secrets specified in the array will be accessible.</span></span> <span data-ttu-id="617d4-305">Esta propiedad es opcional.</span><span class="sxs-lookup"><span data-stu-id="617d4-305">This property is optional.</span></span>                                                     |
| `deniedSecrets`  | <span data-ttu-id="617d4-306">Lista de claves secretas</span><span class="sxs-lookup"><span data-stu-id="617d4-306">List of secret keys</span></span> | <span data-ttu-id="617d4-307">NO se podrá acceder a los secretos especificados en la matriz.</span><span class="sxs-lookup"><span data-stu-id="617d4-307">Secrets specified in the array will NOT be accessible.</span></span> <span data-ttu-id="617d4-308">Esta propiedad es opcional.</span><span class="sxs-lookup"><span data-stu-id="617d4-308">This property is optional.</span></span>                                                 |

<span data-ttu-id="617d4-309">Las `allowedSecrets` `deniedSecrets` propiedades y tienen prioridad sobre la `defaultAccess` propiedad.</span><span class="sxs-lookup"><span data-stu-id="617d4-309">The `allowedSecrets` and `deniedSecrets` properties take precedence over the `defaultAccess` property.</span></span> <span data-ttu-id="617d4-310">Imagine que especifica `defaultAccess: allowed` y una `allowedSecrets` lista.</span><span class="sxs-lookup"><span data-stu-id="617d4-310">Imagine specifying `defaultAccess: allowed` and an `allowedSecrets` list.</span></span> <span data-ttu-id="617d4-311">En este caso, `allowedSecrets` la aplicación solo podrá tener acceso a los secretos de la lista.</span><span class="sxs-lookup"><span data-stu-id="617d4-311">In this case, only the secrets in the `allowedSecrets` list would be accessible by the application.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="617d4-312">Aplicación de referencia: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="617d4-312">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="617d4-313">La aplicación de referencia eShopOnDapr usa el bloque de creación de secretos para dos secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-313">The eShopOnDapr reference application uses the secrets building block for two secrets:</span></span>

- <span data-ttu-id="617d4-314">La contraseña para conectarse a la caché en Redis.</span><span class="sxs-lookup"><span data-stu-id="617d4-314">The password for connecting to the Redis cache.</span></span>
- <span data-ttu-id="617d4-315">La clave de API para usar la API de Twilio Sendgrid.</span><span class="sxs-lookup"><span data-stu-id="617d4-315">The API-key for using the Twilio Sendgrid API.</span></span> <span data-ttu-id="617d4-316">La aplicación usa Twillio para enviar correos electrónicos mediante un enlace de salida de DAPR (como se describe en el capítulo sobre los [enlaces de bloques de creación](bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="617d4-316">The application uses Twillio to send emails using a Dapr output binding (as described in the [bindings building block chapter](bindings.md)).</span></span>

<span data-ttu-id="617d4-317">Al ejecutar la aplicación mediante Docker Compose, se usa el almacén de secreto de **archivo local** .</span><span class="sxs-lookup"><span data-stu-id="617d4-317">When running the application using Docker Compose, the **local file** secret store is used.</span></span> <span data-ttu-id="617d4-318">El archivo de configuración de componentes `eshop-secretstore.yaml` se encuentra en la `dapr/components` carpeta del repositorio eShopOnDapr:</span><span class="sxs-lookup"><span data-stu-id="617d4-318">The component configuration file `eshop-secretstore.yaml` is found in the `dapr/components` folder of the eShopOnDapr repository:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: eshop-secretstore
  namespace: eshop
spec:
  type: secretstores.local.file
  version: v1
  metadata:
  - name: secretsFile
    value: ./components/eshop-secretstore.json
```

<span data-ttu-id="617d4-319">El archivo de configuración hace referencia al archivo de almacenamiento local que se `eshop-secretstore.json` encuentra en la misma carpeta:</span><span class="sxs-lookup"><span data-stu-id="617d4-319">The configuration file references the local store file `eshop-secretstore.json` located in the same folder:</span></span>

```json
{
    "redisPassword": "**********",
    "sendgridAPIKey": "**********"
}
```

<span data-ttu-id="617d4-320">La `components` carpeta se especifica en la línea de comandos y se monta como una carpeta local dentro del contenedor de DAPR sidecar.</span><span class="sxs-lookup"><span data-stu-id="617d4-320">The `components` folder is specified in the command-line and mounted as a local folder inside the Dapr sidecar container.</span></span> <span data-ttu-id="617d4-321">A continuación se muestra un fragmento de código del `docker-compose.override.yml` archivo en la raíz del repositorio que especifica el montaje del volumen:</span><span class="sxs-lookup"><span data-stu-id="617d4-321">Here's a snippet from the `docker-compose.override.yml` file in the repository root that specifies the volume mount:</span></span>

```yaml
  ordering-backgroundtasks-dapr:
    command: ["./daprd",
      "-app-id", "ordering-backgroundtasks",
      "-app-port", "80",
      "-dapr-grpc-port", "50004",
      "-components-path", "/components",
      "-config", "/configuration/eshop-config.yaml"
      ]
    volumes:
      - "./dapr/components/:/components"
      - "./dapr/configuration/:/configuration"
```

> [!NOTE]
> <span data-ttu-id="617d4-322">El archivo de invalidación de Docker Compose contiene valores de configuración específicos del entorno.</span><span class="sxs-lookup"><span data-stu-id="617d4-322">The Docker Compose override file contains environmental specific configuration values.</span></span>

<span data-ttu-id="617d4-323">El `/components` montaje del volumen y el `--components-path` argumento de la línea de comandos se pasan al `daprd` comando de inicio.</span><span class="sxs-lookup"><span data-stu-id="617d4-323">The `/components` volume mount and `--components-path` command-line argument are passed into the `daprd` startup command.</span></span>

<span data-ttu-id="617d4-324">Una vez configurado, otros archivos de configuración de componentes también pueden hacer referencia a los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-324">Once configured, other component configuration files can also reference the secrets.</span></span> <span data-ttu-id="617d4-325">A continuación se muestra un ejemplo de la configuración del componente de publicación/suscripción que consume secretos:</span><span class="sxs-lookup"><span data-stu-id="617d4-325">Here's an example of the Publish/Subscribe component configuration consuming secrets:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Component
metadata:
  name: pubsub
  namespace: eshop
spec:
  type: pubsub.redis
  version: v1
  metadata:
  - name: redisHost
    value: redis:6379
  - name: redisPassword
    secretKeyRef:
      name: redisPassword
auth:
  secretStore: eshop-secretstore
```

<span data-ttu-id="617d4-326">En el ejemplo anterior, el almacén de Redis local se usa para hacer referencia a los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-326">In the preceding example, the local Redis store is used to reference secrets.</span></span>

## <a name="summary"></a><span data-ttu-id="617d4-327">Resumen</span><span class="sxs-lookup"><span data-stu-id="617d4-327">Summary</span></span>

<span data-ttu-id="617d4-328">El bloque de creación de secretos de DAPR proporciona funciones para almacenar y recuperar valores de configuración confidenciales como contraseñas y cadenas de conexión.</span><span class="sxs-lookup"><span data-stu-id="617d4-328">The Dapr secrets building block provides capabilities for storing and retrieving sensitive configuration settings like passwords and connection-strings.</span></span> <span data-ttu-id="617d4-329">Mantiene secretos privados y evita que se revelen accidentalmente.</span><span class="sxs-lookup"><span data-stu-id="617d4-329">It keeps secrets private and prevents them from being accidentally disclosed.</span></span>

<span data-ttu-id="617d4-330">El bloque de creación admite varios almacenes secretos diferentes y oculta su complejidad con la API DAPR Secrets.</span><span class="sxs-lookup"><span data-stu-id="617d4-330">The building block supports several different secret stores and hides their complexity with the Dapr secrets API.</span></span>

<span data-ttu-id="617d4-331">El SDK de .NET para DAPR proporciona un `DaprClient` objeto para recuperar los secretos.</span><span class="sxs-lookup"><span data-stu-id="617d4-331">The Dapr .NET SDK provides a `DaprClient` object to retrieve secrets.</span></span> <span data-ttu-id="617d4-332">También incluye un proveedor de configuración de .NET que agrega secretos al sistema de configuración de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="617d4-332">It also includes a .NET configuration provider that adds secrets to the .NET Core configuration system.</span></span> <span data-ttu-id="617d4-333">Una vez cargados, puede consumir estos secretos en el código .NET.</span><span class="sxs-lookup"><span data-stu-id="617d4-333">Once loaded, you can consume these secrets in your .NET code.</span></span>

<span data-ttu-id="617d4-334">Puede usar ámbitos secretos para controlar el acceso a secretos específicos.</span><span class="sxs-lookup"><span data-stu-id="617d4-334">You can use secret scopes to control access to specific secrets.</span></span>

## <a name="references"></a><span data-ttu-id="617d4-335">Referencias</span><span class="sxs-lookup"><span data-stu-id="617d4-335">References</span></span>

- [<span data-ttu-id="617d4-336">Más allá de la aplicación Twelve-Factor</span><span class="sxs-lookup"><span data-stu-id="617d4-336">Beyond the Twelve-Factor Application</span></span>](https://tanzu.vmware.com/content/blog/beyond-the-twelve-factor-app)

>[!div class="step-by-step"]
><span data-ttu-id="617d4-337">[Anterior](observability.md)
>[Siguiente](summary.md)</span><span class="sxs-lookup"><span data-stu-id="617d4-337">[Previous](observability.md)
[Next](summary.md)</span></span>
