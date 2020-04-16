---
title: Autenticación con las bibliotecas de Azure para .NET
description: Autenticación en las bibliotecas de Azure para .NET
ms.date: 08/22/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: e562b60da0a2d34f716e80d3d5d0d0b5e55b0cdb
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433149"
---
# <a name="authenticate-with-the-azure-libraries-for-net"></a><span data-ttu-id="a84de-103">Autenticación con las bibliotecas de Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="a84de-103">Authenticate with the Azure Libraries for .NET</span></span>

## <a name="connect-to-services-with-connection-strings"></a><span data-ttu-id="a84de-104">Conexión a los servicios con cadenas de conexión</span><span class="sxs-lookup"><span data-stu-id="a84de-104">Connect to services with connection strings</span></span>

<span data-ttu-id="a84de-105">La mayoría de las bibliotecas de servicio de Azure necesitan claves o una cadena de conexión para la autenticación.</span><span class="sxs-lookup"><span data-stu-id="a84de-105">Most Azure service libraries require a connection string or keys for authentication.</span></span> <span data-ttu-id="a84de-106">Por ejemplo, SQL Database usa una cadena de conexión SQL estándar:</span><span class="sxs-lookup"><span data-stu-id="a84de-106">For example, SQL Database uses a standard SQL connection string:</span></span>

```csharp
var builder = new SqlConnectionStringBuilder();
builder.DataSource = "example.database.windows.net";
builder.InitialCatalog = "MyDatabase";
builder.UserID = "sampleuser@example"; // Format user ID as "user@server"
builder.Password = password;
builder.Encrypt = true;
builder.TrustServerCertificate = true;

using (var conn = new SqlConnection(builder.ConnectionString))
{
    conn.Open();
    // Do things with the connection...
    // ...
}
```

<span data-ttu-id="a84de-107">Azure Storage usa una clave de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="a84de-107">Azure Storage uses a storage key:</span></span>

```csharp
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storageName
        + ";AccountKey=" + storageKey
        + ";EndpointSuffix=core.windows.net";

var account = CloudStorageAccount.Parse(storageConnectionString);
// Do things with the account here...
```

<span data-ttu-id="a84de-108">Las cadenas de conexión de servicio se usan en otros servicios de Azure como [CosmosDB](/azure/documentdb/documentdb-dotnet-application#a-nametoc395637769astep-5-wiring-up-azure-cosmos-db), [Azure Cache para Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache)y [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) y puede obtener esas cadenas mediante Azure Portal, la CLI o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a84de-108">Service connection strings are used in other Azure services like [CosmosDB](/azure/documentdb/documentdb-dotnet-application#a-nametoc395637769astep-5-wiring-up-azure-cosmos-db), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache), and [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues) and you can get those strings using the Azure portal, CLI, or PowerShell.</span></span> <span data-ttu-id="a84de-109">También puede usar las bibliotecas de administración de Azure para .NET para consultar recursos para generar cadenas de conexión en el código.</span><span class="sxs-lookup"><span data-stu-id="a84de-109">You can also use the Azure management libraries for .NET to query resources to build connection strings in your code.</span></span>

<span data-ttu-id="a84de-110">Este fragmento de código usa las bibliotecas de administración para crear una cadena de conexión de la cuenta de almacenamiento:</span><span class="sxs-lookup"><span data-stu-id="a84de-110">This snippet uses the management libraries to create a storage account connection string:</span></span>

```csharp
// Get a storage account
var storage = azure.StorageAccounts.GetByResourceGroup("myResourceGroup", "myStorageAccount");

// Extract the keys
var storageKeys = storage.GetKeys();

// Build the connection string
string storageConnectionString = "DefaultEndpointsProtocol=https;"
        + "AccountName=" + storage.Name
        + ";AccountKey=" + storageKeys[0].Value
        + ";EndpointSuffix=core.windows.net";

// Connect
var account = CloudStorageAccount.Parse(storageConnectionString);

// Do things with the account here...
```

<span data-ttu-id="a84de-111">Otras bibliotecas requieren que la aplicación se ejecute con una [entidad de servicio](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) que autoriza la ejecución de la aplicación con las credenciales otorgadas.</span><span class="sxs-lookup"><span data-stu-id="a84de-111">Other libraries require your application to run with a [service principal](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) authorizing the application to run with granted credentials.</span></span> <span data-ttu-id="a84de-112">Esta configuración es similar a los pasos de la autenticación basada en objetos para la biblioteca de administración que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="a84de-112">This configuration is similar to the object-based authentication steps for the management library listed below.</span></span>

## <a name="azure-management-libraries-for-net-authentication"></a><a name="mgmt-auth"></a><span data-ttu-id="a84de-113">Bibliotecas de administración de Azure para .NET y Java</span><span class="sxs-lookup"><span data-stu-id="a84de-113">Azure management libraries for .NET authentication</span></span>

[!include[Create service principal](../includes/create-sp.md)]

<span data-ttu-id="a84de-114">Ahora que ya está creada la entidad de servicio, hay dos opciones disponibles para autenticarse en la entidad de servicio para crear y administrar los recursos.</span><span class="sxs-lookup"><span data-stu-id="a84de-114">Now that the service principal is created, two options are available to authenticate to the service principal to create and manage resources.</span></span>

<span data-ttu-id="a84de-115">Para ambas opciones, deberá agregar los siguientes paquetes NuGet al proyecto.</span><span class="sxs-lookup"><span data-stu-id="a84de-115">For both options you will need to add the following NuGet packages to your project.</span></span>

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a><span data-ttu-id="a84de-116">Autenticación con credenciales de token</span><span class="sxs-lookup"><span data-stu-id="a84de-116">Authenticate with token credentials</span></span>

<span data-ttu-id="a84de-117">El primer método consiste en generar el objeto de credencial de token en el código.</span><span class="sxs-lookup"><span data-stu-id="a84de-117">The first method is to build the token credential object in code.</span></span> <span data-ttu-id="a84de-118">Debe almacenar las credenciales de forma segura en un archivo de configuración, el Registro o Azure KeyVault.</span><span class="sxs-lookup"><span data-stu-id="a84de-118">You should store the credentials securely in a configuration file, the registry, or Azure KeyVault.</span></span>

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
    clientSecret,
    tenantId,
    AzureEnvironment.AzureGlobalCloud);
```

<span data-ttu-id="a84de-119">Use los valores de *clientId*, *clientSecret* y *tenantId* de la salida JSON de la creación de la entidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="a84de-119">Use the *clientId*, *clientSecret*, and *tenantId* values from the JSON output when you created the service principal.</span></span>

<span data-ttu-id="a84de-120">Después, cree el objeto `Azure` de punto de entrada para empezar a trabajar con la API:</span><span class="sxs-lookup"><span data-stu-id="a84de-120">Then create the entry point `Azure` object to start working with the API:</span></span>

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a><span data-ttu-id="a84de-121">Autenticación basada en archivo</span><span class="sxs-lookup"><span data-stu-id="a84de-121">File-based authentication</span></span>

<span data-ttu-id="a84de-122">La autenticación basada en archivo permite colocar las credenciales de la entidad de servicio en un archivo de texto sin formato y protegerlo en el sistema de archivos.</span><span class="sxs-lookup"><span data-stu-id="a84de-122">File-based authentication allows you to put the service principal credentials in a plain text file and secure it within the file system.</span></span>

[!include[File-based authentication](../includes/file-based-auth.md)]

<span data-ttu-id="a84de-123">Lea el contenido del archivo y cree el objeto `Azure` de punto de entrada para empezar a trabajar con la API:</span><span class="sxs-lookup"><span data-stu-id="a84de-123">Read the contents of the file and create the entry point `Azure` object to start working with the API:</span></span>

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
