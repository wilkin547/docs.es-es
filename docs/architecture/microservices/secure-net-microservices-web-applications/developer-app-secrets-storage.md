---
title: Almacenar secretos de aplicación de forma segura durante el desarrollo
description: 'Seguridad en microservicios y aplicaciones web de .NET: no almacene sus secretos de aplicación (contraseñas, cadenas de conexión o claves de API) en el control de código fuente y aprenda las opciones que puede usar en ASP.NET Core (en particular, debe aprender a controlar los "secretos de usuario").'
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77501798"
---
# <a name="store-application-secrets-safely-during-development"></a>Almacenar secretos de aplicación de forma segura durante el desarrollo

Para conectar con los recursos protegidos y otros servicios, las aplicaciones de ASP.NET Core normalmente necesitan usar cadenas de conexión, contraseñas u otras credenciales que contienen información confidencial. Estos fragmentos de información confidenciales se denominan *secretos*. Es un procedimiento recomendado no incluir secretos en el código fuente y, ciertamente, no almacenar secretos en el control de código fuente. En su lugar, debe usar el modelo de configuración de ASP.NET Core para leer los secretos desde ubicaciones más seguras.

Debe separar los secretos usados para acceder a los recursos de desarrollo y almacenamiento provisional de los usados para acceder a los recursos de producción, ya que distintas personas deben tener acceso a los diferentes conjuntos de secretos. Para almacenar secretos usados durante el desarrollo, los enfoques comunes son almacenar secretos en variables de entorno o usar la herramienta ASP.NET Core Secret Manager. Para un almacenamiento más seguro en entornos de producción, los microservicios pueden almacenar secretos en un Azure Key Vault.

## <a name="store-secrets-in-environment-variables"></a>Almacenamiento de secretos en variables de entorno

Una manera de mantener secretos fuera del código fuente es que los desarrolladores establezcan secretos basados en cadena como [variables de entorno](/aspnet/core/security/app-secrets#environment-variables) en sus máquinas de desarrollo. Cuando use variables de entorno para almacenar secretos con nombres jerárquicos, como las anidadas en las secciones de configuración, debe asignar un nombre a las variables para incluir la jerarquía completa de sus secciones, delimitada por signos de dos puntos (:).

Por ejemplo, establecer una variable de entorno `Logging:LogLevel:Default` to `Debug` sería equivalente a un valor de configuración del archivo JSON siguiente:

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

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a>Almacenamiento de secretos mediante ASP.NET Core Secret Manager

La herramienta [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) de ASP.NET Core proporciona otro método para mantener los secretos fuera del código fuente **durante el desarrollo**. Para usar la herramienta Secret Manager, instale el paquete **Microsoft.Extensions.Configuration.SecretManager** en su archivo del proyecto. Una vez que esa dependencia está presente y se ha restaurado, se puede usar el comando `dotnet user-secrets` para establecer el valor de los secretos desde la línea de comandos. Estos secretos se almacenarán en un archivo JSON en el directorio del perfil del usuario (los detalles varían según el sistema operativo), lejos del código fuente.

La propiedad `UserSecretsId` del proyecto que está usando los secretos organiza los secretos que establece la herramienta Secret Manager. Por tanto, debe asegurarse de establecer la propiedad UserSecretsId en el archivo del proyecto, como se muestra en el siguiente fragmento. El valor predeterminado es un GUID asignado por Visual Studio, pero la cadena real no es importante mientras sea única en su equipo.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Para usar los secretos almacenados con Secret Manager en una aplicación, debe llamar a `AddUserSecrets<T>` en la instancia de ConfigurationBuilder para incluir los secretos de la aplicación en su configuración. El parámetro genérico T debe ser un tipo del ensamblado que se aplicó a UserSecretId. Normalmente, usar `AddUserSecrets<Startup>` está bien.

`AddUserSecrets<Startup>()` se incluye en las opciones predeterminadas del entorno de desarrollo al usar el método `CreateDefaultBuilder` en *Program.cs*.

>[!div class="step-by-step"]
>[Anterior](authorization-net-microservices-web-applications.md)
>[Siguiente](azure-key-vault-protects-secrets.md)
