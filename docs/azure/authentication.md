---
title: Descripción de la autenticación en las bibliotecas de Azure para .NET
description: Explica las distintas formas de autenticarse con el SDK de Azure para .NET.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 727842b34faa37558220a3035ac5228fae196201
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301624"
---
# <a name="authenticate-with-the-azure-sdk-for-net"></a>Autenticación con SDK de Azure para .NET

## <a name="recommended-azureidentity"></a>Se recomienda: Azure.Identity

Los paquetes más recientes de SDK de Azure para .NET usan un paquete de autenticación común para autenticarse, `Azure.Identity`. Se recomienda usar `Azure.Identity` sobre otros mecanismos de autenticación que se describen más adelante en este documento. Los paquetes que admiten las credenciales proporcionadas por `Azure.Identity` tienen identificadores de paquete que comienzan por *Azure*. [Para obtener más información, consulte las versiones más recientes de SDK de Azure para .NET](https://azure.github.io/azure-sdk/releases/latest/index.html#net).

Para obtener instrucciones completas sobre cómo usar `Azure.Identity` en el proyecto, consulte la documentación de [Azure Identity Client para .NET](/dotnet/api/overview/azure/identity-readme).

> [!TIP]
> Consulte la [muestra de Azure Identity, Resource Management y Storage](/samples/dotnet/samples/azure-identity-resource-management-storage/) para obtener ejemplos del uso de Azure Identity para administrar y acceder a los recursos de Azure.

Para autenticar con bibliotecas que no son compatibles con Azure.Identity, consulte el resto de este tema.

## <a name="access-azure-resources"></a>Acceso a recursos de Azure

Para interactuar con los recursos de Azure, como recuperar un secreto de Key Vault o almacenar un blob en Storage, muchas bibliotecas de servicios de Azure requieren una cadena de conexión o claves para la autenticación. Por ejemplo, SQL Database usa una [cadena de conexión SQL estándar](https://docs.microsoft.com/azure/azure-sql/database/connect-query-dotnet-core). Las cadenas de conexión de servicio se usan en otros servicios de Azure como [CosmosDB](/azure/cosmos-db/), [Azure Cache for Redis](/azure/azure-cache-for-redis/cache-dotnet-how-to-use-azure-redis-cache) y [Service Bus](/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues). Puede obtener esas cadenas mediante Azure Portal, la CLI o PowerShell. También puede usar las bibliotecas de administración de Azure para .NET para consultar recursos para generar cadenas de conexión en el código.

Los métodos para usar una cadena de conexión varían según el producto. [Consulte la documentación de su producto Azure](/azure/?product=featured).

## <a name="manage-azure-resources"></a>Administración de recursos de Azure

[!include[Create service principal](includes/create-sp.md)]

Ahora que ya está creada la entidad de servicio, hay dos opciones disponibles para autenticarse en la entidad de servicio para crear y administrar los recursos.

Para las dos opciones, tendrá que agregar los siguientes paquetes NuGet al proyecto.

```powershell
Install-Package Microsoft.Azure.Management.Fluent
Install-Package Microsoft.Azure.Management.ResourceManager.Fluent
```

### <a name="authenticate-with-token-credentials"></a>Autenticación con credenciales de token

El primer método consiste en generar el objeto de credencial de token en el código. Debe almacenar las credenciales de forma segura en un archivo de configuración, el Registro o Azure KeyVault.

```csharp
var credentials = SdkContext.AzureCredentialsFactory
    .FromServicePrincipal(clientId,
        clientSecret,
        tenantId,
        AzureEnvironment.AzureGlobalCloud);
```

Use los valores de *clientId*, *clientSecret* y *tenantId* de la salida JSON de la creación de la entidad de servicio.

Después, cree el objeto `Azure` de punto de entrada para empezar a trabajar con la API:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```

Se recomienda proporcionar explícitamente *subscriptionId* de la salida JSON al objeto `Azure`:

```csharp
var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithSubscription(subscriptionId);
```

### <a name="file-based-authentication"></a><a name="mgmt-file"></a>Autenticación basada en archivo

La autenticación basada en archivo permite colocar las credenciales de la entidad de servicio en un archivo de texto sin formato y protegerlo en el sistema de archivos.

[!include[File-based authentication](includes/file-based-auth.md)]

Lea el contenido del archivo y cree el objeto `Azure` de punto de entrada para empezar a trabajar con la API:

```csharp
// pull in the location of the authentication properties file from the environment
var credentials = SdkContext.AzureCredentialsFactory
    .FromFile(Environment.GetEnvironmentVariable("AZURE_AUTH_LOCATION"));

var azure = Microsoft.Azure.Management.Fluent.Azure
    .Configure()
    .Authenticate(credentials)
    .WithDefaultSubscription();
```
