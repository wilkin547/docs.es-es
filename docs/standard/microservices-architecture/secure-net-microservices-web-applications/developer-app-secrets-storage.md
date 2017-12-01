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
# <a name="storing-application-secrets-safely-during-development"></a>Almacenar secretos de aplicación de forma segura durante el desarrollo

Para conectar con los recursos protegidos y otros servicios, aplicaciones de ASP.NET Core normalmente necesitan utilizar cadenas de conexión, contraseñas u otras credenciales que contienen información confidencial. Estos fragmentos de información confidenciales se denominan *secretos*. Es una práctica recomendada para que no incluya secretos en el código fuente y ciertamente no almacenar secretos en el control de código fuente. En su lugar, debe utilizar el modelo de configuración de ASP.NET Core para leer los secretos de ubicaciones más seguras.

Debería separar los secretos para poder acceder a desarrollo de recursos de las usadas para tener acceso a recursos de producción, ya que distintas personas deben tener acceso a los diferentes conjuntos de secretos de almacenamiento provisional. Para almacenar secretos usados durante el desarrollo, los enfoques comunes son bien almacenar secretos en variables de entorno o mediante la herramienta Administrador de secreto principal de ASP.NET. Para un almacenamiento más seguro en entornos de producción, microservicios pueden almacenar secretos en un almacén de claves de Azure.

## <a name="storing-secrets-in-environment-variables"></a>Almacenamiento de secretos en variables de entorno

Una manera de mantener secretos fuera del código fuente es para que los desarrolladores establecer basada en cadena secretos como [variables de entorno](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) en sus equipos de desarrollo. Cuando se usan variables de entorno para almacenar secretos con nombres jerárquicos (aquellas anidados en las secciones de configuración), cree un nombre para las variables de entorno que incluye la jerarquía completa del nombre del secreto, delimitados por signos de dos puntos (:).

Por ejemplo, si se establece una variable de entorno del registro: LogLevel:Default en depuración sería equivalente a un valor de configuración desde el archivo JSON siguiente:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

Para obtener acceso a estos valores de variables de entorno, la aplicación solo necesita llamar a AddEnvironmentVariables en su ConfigurationBuilder al construir un objeto IConfigurationRoot.

Tenga en cuenta que las variables de entorno se suelen almacenar como texto sin formato, por lo que si se pone en peligro el equipo o el proceso con las variables de entorno, se verán los valores de variables de entorno.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>Almacenamiento de secretos mediante el Administrador de secreto principal de ASP.NET

El núcleo de ASP.NET [Manager secreto](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) herramienta proporciona otro método para mantener secretos fuera del código fuente. Para usar la herramienta Administrador de secreto, incluir una referencia de herramientas (DotNetCliToolReference) del paquete Microsoft.Extensions.SecretManager.Tools en el archivo de proyecto. Una vez que esa dependencia está presente y se ha restaurado, el comando de dotnet secretos del usuario se puede utilizar para establecer el valor de secretos de la línea de comandos. Estos secretos se almacenarán en un archivo JSON en el directorio del usuario perfil (detalles varían según el sistema operativo), fuera de código fuente.

Establecido por la herramienta Administrador de secreto de secretos están organizados por la propiedad UserSecretsId del proyecto que está usando los secretos. Por lo tanto, debe asegurarse de establecer la propiedad UserSecretsId en el archivo de proyecto (como se muestra en el siguiente fragmento). La cadena real que se usa como el identificador no es importante, siempre que sea único en el proyecto.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

Uso de secretos almacenados con el Administrador de secreto en una aplicación se lleva a cabo mediante una llamada a AddUserSecrets&lt;T&gt; en la instancia de ConfigurationBuilder para incluir los secretos de la aplicación en su configuración. El parámetro genérico T debe ser un tipo de ensamblado que se aplicó la UserSecretId a. Normalmente utilizando AddUserSecrets&lt;inicio&gt; es correcto.


>[!div class="step-by-step"]
[Anterior] (autorización-net-microservicios-web-applications.md) [siguiente] (azure-key-almacén-protege-secrets.md)
