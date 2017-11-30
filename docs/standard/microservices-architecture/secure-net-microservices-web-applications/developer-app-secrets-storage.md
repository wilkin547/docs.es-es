---
title: "Almacenar secretos de aplicación de forma segura durante el desarrollo"
description: "Arquitectura de Microservicios de .NET para aplicaciones .NET en contenedores | Almacenar secretos de aplicación de forma segura durante el desarrollo"
keywords: Docker, microservicios, ASP.NET, contenedor
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="f6c71-104">Almacenar secretos de aplicación de forma segura durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="f6c71-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="f6c71-105">Para conectar con los recursos protegidos y otros servicios, aplicaciones de ASP.NET Core normalmente necesitan utilizar cadenas de conexión, contraseñas u otras credenciales que contienen información confidencial.</span><span class="sxs-lookup"><span data-stu-id="f6c71-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="f6c71-106">Estos fragmentos de información confidenciales se denominan *secretos*.</span><span class="sxs-lookup"><span data-stu-id="f6c71-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="f6c71-107">Es una práctica recomendada para que no incluya secretos en el código fuente y ciertamente no almacenar secretos en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="f6c71-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="f6c71-108">En su lugar, debe utilizar el modelo de configuración de ASP.NET Core para leer los secretos de ubicaciones más seguras.</span><span class="sxs-lookup"><span data-stu-id="f6c71-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="f6c71-109">Debería separar los secretos para poder acceder a desarrollo de recursos de las usadas para tener acceso a recursos de producción, ya que distintas personas deben tener acceso a los diferentes conjuntos de secretos de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="f6c71-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="f6c71-110">Para almacenar secretos usados durante el desarrollo, los enfoques comunes son bien almacenar secretos en variables de entorno o mediante la herramienta Administrador de secreto principal de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f6c71-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="f6c71-111">Para un almacenamiento más seguro en entornos de producción, microservicios pueden almacenar secretos en un almacén de claves de Azure.</span><span class="sxs-lookup"><span data-stu-id="f6c71-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="f6c71-112">Almacenamiento de secretos en variables de entorno</span><span class="sxs-lookup"><span data-stu-id="f6c71-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="f6c71-113">Una manera de mantener secretos fuera del código fuente es para que los desarrolladores establecer basada en cadena secretos como [variables de entorno](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) en sus equipos de desarrollo.</span><span class="sxs-lookup"><span data-stu-id="f6c71-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="f6c71-114">Cuando se usan variables de entorno para almacenar secretos con nombres jerárquicos (aquellas anidados en las secciones de configuración), cree un nombre para las variables de entorno que incluye la jerarquía completa del nombre del secreto, delimitados por signos de dos puntos (:).</span><span class="sxs-lookup"><span data-stu-id="f6c71-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="f6c71-115">Por ejemplo, si se establece una variable de entorno del registro: LogLevel:Default en depuración sería equivalente a un valor de configuración desde el archivo JSON siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6c71-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="f6c71-116">Para obtener acceso a estos valores de variables de entorno, la aplicación solo necesita llamar a AddEnvironmentVariables en su ConfigurationBuilder al construir un objeto IConfigurationRoot.</span><span class="sxs-lookup"><span data-stu-id="f6c71-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="f6c71-117">Tenga en cuenta que las variables de entorno se suelen almacenar como texto sin formato, por lo que si se pone en peligro el equipo o el proceso con las variables de entorno, se verán los valores de variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="f6c71-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="f6c71-118">Almacenamiento de secretos mediante el Administrador de secreto principal de ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f6c71-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="f6c71-119">El núcleo de ASP.NET [Manager secreto](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) herramienta proporciona otro método para mantener secretos fuera del código fuente.</span><span class="sxs-lookup"><span data-stu-id="f6c71-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="f6c71-120">Para usar la herramienta Administrador de secreto, incluir una referencia de herramientas (DotNetCliToolReference) del paquete Microsoft.Extensions.SecretManager.Tools en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="f6c71-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="f6c71-121">Una vez que esa dependencia está presente y se ha restaurado, el comando de dotnet secretos del usuario se puede utilizar para establecer el valor de secretos de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f6c71-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="f6c71-122">Estos secretos se almacenarán en un archivo JSON en el directorio del usuario perfil (detalles varían según el sistema operativo), fuera de código fuente.</span><span class="sxs-lookup"><span data-stu-id="f6c71-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="f6c71-123">Establecido por la herramienta Administrador de secreto de secretos están organizados por la propiedad UserSecretsId del proyecto que está usando los secretos.</span><span class="sxs-lookup"><span data-stu-id="f6c71-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="f6c71-124">Por lo tanto, debe asegurarse de establecer la propiedad UserSecretsId en el archivo de proyecto (como se muestra en el siguiente fragmento).</span><span class="sxs-lookup"><span data-stu-id="f6c71-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="f6c71-125">La cadena real que se usa como el identificador no es importante, siempre que sea único en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="f6c71-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="f6c71-126">Uso de secretos almacenados con el Administrador de secreto en una aplicación se lleva a cabo mediante una llamada a AddUserSecrets&lt;T&gt; en la instancia de ConfigurationBuilder para incluir los secretos de la aplicación en su configuración.</span><span class="sxs-lookup"><span data-stu-id="f6c71-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="f6c71-127">El parámetro genérico T debe ser un tipo de ensamblado que se aplicó la UserSecretId a.</span><span class="sxs-lookup"><span data-stu-id="f6c71-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="f6c71-128">Normalmente utilizando AddUserSecrets&lt;inicio&gt; es correcto.</span><span class="sxs-lookup"><span data-stu-id="f6c71-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="f6c71-129">[Anterior] (autorización-net-microservicios-web-applications.md) [siguiente] (azure-key-almacén-protege-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="f6c71-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
