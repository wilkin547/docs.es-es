---
title: Almacenar secretos de aplicación de forma segura durante el desarrollo
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Almacenar secretos de aplicación de forma segura durante el desarrollo
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 6f5dfbb53b99fec4d7cc66c528fe866c71c2172f
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53143875"
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="5ec02-103">Almacenar secretos de aplicación de forma segura durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="5ec02-103">Storing application secrets safely during development</span></span>

<span data-ttu-id="5ec02-104">Para conectar con los recursos protegidos y otros servicios, las aplicaciones de ASP.NET Core normalmente necesitan usar cadenas de conexión, contraseñas u otras credenciales que contienen información confidencial.</span><span class="sxs-lookup"><span data-stu-id="5ec02-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="5ec02-105">Estos fragmentos de información confidenciales se denominan *secretos*.</span><span class="sxs-lookup"><span data-stu-id="5ec02-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="5ec02-106">Es un procedimiento recomendado no incluir secretos en el código fuente y, ciertamente, no almacenar secretos en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5ec02-106">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="5ec02-107">En su lugar, debe usar el modelo de configuración de ASP.NET Core para leer los secretos desde ubicaciones más seguras.</span><span class="sxs-lookup"><span data-stu-id="5ec02-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="5ec02-108">Debe separar los secretos usados para acceder a los recursos de desarrollo y almacenamiento provisional de los usados para acceder a los recursos de producción, ya que distintas personas deben tener acceso a los diferentes conjuntos de secretos.</span><span class="sxs-lookup"><span data-stu-id="5ec02-108">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="5ec02-109">Para almacenar secretos usados durante el desarrollo, los enfoques comunes son almacenar secretos en variables de entorno o usar la herramienta ASP.NET Core Secret Manager.</span><span class="sxs-lookup"><span data-stu-id="5ec02-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="5ec02-110">Para un almacenamiento más seguro en entornos de producción, los microservicios pueden almacenar secretos en un Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="5ec02-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="5ec02-111">Almacenamiento de secretos en variables de entorno</span><span class="sxs-lookup"><span data-stu-id="5ec02-111">Storing secrets in environment variables</span></span>

<span data-ttu-id="5ec02-112">Una manera de mantener secretos fuera del código fuente es que los desarrolladores establezcan secretos basados en cadena como [variables de entorno](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) en sus máquinas de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="5ec02-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="5ec02-113">Cuando use variables de entorno para almacenar secretos con nombres jerárquicos (aquellas anidadas en las secciones de configuración), cree un nombre para las variables de entorno que incluyen la jerarquía completa del nombre del secreto, delimitada por signos de dos puntos (:).</span><span class="sxs-lookup"><span data-stu-id="5ec02-113">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="5ec02-114">Por ejemplo, establecer una variable de entorno Logging:LogLevel:Default to Debug sería equivalente a un valor de configuración del archivo JSON siguiente:</span><span class="sxs-lookup"><span data-stu-id="5ec02-114">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="5ec02-115">Para acceder a estos valores de variables de entorno, la aplicación solo debe llamar a AddEnvironmentVariables en su ConfigurationBuilder al construir un objeto IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="5ec02-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="5ec02-116">Tenga en cuenta que las variables de entorno suelen almacenarse como texto sin formato, por lo que si se pone en peligro la máquina o el proceso con las variables de entorno, se verán los valores de las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="5ec02-116">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="5ec02-117">Almacenamiento de secretos mediante ASP.NET Core Secret Manager</span><span class="sxs-lookup"><span data-stu-id="5ec02-117">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="5ec02-118">La herramienta [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) de ASP.NET Core proporciona otro método para mantener secretos fuera del código fuente.</span><span class="sxs-lookup"><span data-stu-id="5ec02-118">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="5ec02-119">Para usar la herramienta Secret Manager, incluya una referencia de herramientas (DotNetCliToolReference) en el paquete Microsoft.Extensions.SecretManager.Tools del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="5ec02-119">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="5ec02-120">Una vez que esa dependencia está presente y se ha restaurado, se puede usar el comando dotnet user-secrets para establecer el valor de los secretos desde la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5ec02-120">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="5ec02-121">Estos secretos se almacenarán en un archivo JSON en el directorio del perfil del usuario (los detalles varían según el sistema operativo), lejos del código fuente.</span><span class="sxs-lookup"><span data-stu-id="5ec02-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="5ec02-122">La propiedad UserSecretsId del proyecto que está usando los secretos organiza los secretos que establece la herramienta Secret Manager.</span><span class="sxs-lookup"><span data-stu-id="5ec02-122">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="5ec02-123">Por tanto, debe asegurarse de establecer la propiedad UserSecretsId en el archivo del proyecto (como se muestra en el siguiente fragmento).</span><span class="sxs-lookup"><span data-stu-id="5ec02-123">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="5ec02-124">La cadena real que se usa como el identificador no es importante, siempre que sea única en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="5ec02-124">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="5ec02-125">Para usar los secretos almacenados con Secret Manager en una aplicación, debe llamar a AddUserSecrets&lt;T&gt; en la instancia de ConfigurationBuilder para incluir los secretos de la aplicación en su configuración.</span><span class="sxs-lookup"><span data-stu-id="5ec02-125">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="5ec02-126">El parámetro genérico T debe ser un tipo del ensamblado que se aplicó a UserSecretId.</span><span class="sxs-lookup"><span data-stu-id="5ec02-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="5ec02-127">Normalmente, usar AddUserSecrets&lt;Startup&gt; es correcto.</span><span class="sxs-lookup"><span data-stu-id="5ec02-127">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
><span data-ttu-id="5ec02-128">[Anterior](authorization-net-microservices-web-applications.md)
>[Siguiente](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="5ec02-128">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>