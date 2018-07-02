---
title: Almacenar secretos de aplicación de forma segura durante el desarrollo
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedores | Almacenar secretos de aplicación de forma segura durante el desarrollo
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 560120db35ae190bdef1f95d72ac1e5de697124e
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105951"
---
# <a name="storing-application-secrets-safely-during-development"></a>Almacenar secretos de aplicación de forma segura durante el desarrollo

Para conectar con los recursos protegidos y otros servicios, las aplicaciones de ASP.NET Core normalmente necesitan usar cadenas de conexión, contraseñas u otras credenciales que contienen información confidencial. Estos fragmentos de información confidenciales se denominan *secretos*. Es un procedimiento recomendado no incluir secretos en el código fuente y, ciertamente, no almacenar secretos en el control de código fuente. En su lugar, debe usar el modelo de configuración de ASP.NET Core para leer los secretos desde ubicaciones más seguras.

Debe separar los secretos usados para acceder a los recursos de desarrollo y almacenamiento provisional de los usados para acceder a los recursos de producción, ya que distintas personas deben tener acceso a los diferentes conjuntos de secretos. Para almacenar secretos usados durante el desarrollo, los enfoques comunes son almacenar secretos en variables de entorno o usar la herramienta ASP.NET Core Secret Manager. Para un almacenamiento más seguro en entornos de producción, los microservicios pueden almacenar secretos en un Azure Key Vault.

## <a name="storing-secrets-in-environment-variables"></a>Almacenamiento de secretos en variables de entorno

Una manera de mantener secretos fuera del código fuente es que los desarrolladores establezcan secretos basados en cadena como [variables de entorno](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) en sus máquinas de desarrollo. Cuando use variables de entorno para almacenar secretos con nombres jerárquicos (aquellas anidadas en las secciones de configuración), cree un nombre para las variables de entorno que incluyen la jerarquía completa del nombre del secreto, delimitada por signos de dos puntos (:).

Por ejemplo, establecer una variable de entorno Logging:LogLevel:Default to Debug sería equivalente a un valor de configuración del archivo JSON siguiente:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Para acceder a estos valores de variables de entorno, la aplicación solo debe llamar a AddEnvironmentVariables en su ConfigurationBuilder al construir un objeto IConfigurationRoot.

Tenga en cuenta que las variables de entorno suelen almacenarse como texto sin formato, por lo que si se pone en peligro la máquina o el proceso con las variables de entorno, se verán los valores de las variables de entorno.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>Almacenamiento de secretos mediante ASP.NET Core Secret Manager

La herramienta [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) de ASP.NET Core proporciona otro método para mantener secretos fuera del código fuente. Para usar la herramienta Secret Manager, incluya una referencia de herramientas (DotNetCliToolReference) en el paquete Microsoft.Extensions.SecretManager.Tools del archivo del proyecto. Una vez que esa dependencia está presente y se ha restaurado, el comando dotnet user-secrets se puede usar para establecer el valor de secretos desde la línea de comandos. Estos secretos se almacenarán en un archivo JSON en el directorio del perfil del usuario (los detalles varían según el sistema operativo), lejos del código fuente.

La propiedad UserSecretsId del proyecto que está usando los secretos organiza los secretos que establece la herramienta Secret Manager. Por tanto, debe asegurarse de establecer la propiedad UserSecretsId en el archivo del proyecto (como se muestra en el siguiente fragmento). La cadena real que se usa como el identificador no es importante, siempre que sea única en el proyecto.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Para usar los secretos almacenados con Secret Manager en una aplicación, debe llamar a AddUserSecrets&lt;T&gt; en la instancia de ConfigurationBuilder para incluir los secretos de la aplicación en su configuración. El parámetro genérico T debe ser un tipo del ensamblado que se aplicó a UserSecretId. Normalmente, usar AddUserSecrets&lt;Startup&gt; es correcto.


>[!div class="step-by-step"]
[Anterior](authorization-net-microservices-web-applications.md)
[Siguiente](azure-key-vault-protects-secrets.md)
