---
title: Configuración en .NET
description: Obtenga información sobre cómo usar la API de configuración para las aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.topic: overview
ms.openlocfilehash: 5955e46c2f5acb6776ada4e3fd6a65507d3faa1f
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402195"
---
# <a name="configuration-in-net"></a>Configuración en .NET

La configuración de .NET se realiza mediante uno o varios [proveedores de configuración](#configuration-providers). Los proveedores de configuración leen los datos sobre los ajustes de los pares clave-valor mediante distintos orígenes de configuración:

- Archivos de configuración, como *appsettings.json*
- Variables de entorno
- [Azure Key Vault](/azure/key-vault/general/overview)
- [Azure App Configuration](/azure/azure-app-configuration/overview)
- Argumentos de la línea de comandos
- Proveedores personalizados (instalados o creados)
- Archivos de directorio
- Objetos de .NET en memoria

## <a name="configure-console-apps"></a>Configuración de las aplicaciones de consola

De forma predeterminada, las nuevas aplicaciones de consola .NET creadas mediante [dotnet new](../tools/dotnet-new.md) o Visual Studio *no* exponen las capacidades de configuración. Para agregar la configuración en una nueva aplicación de consola de .NET, [agregue una referencia de paquete](../tools/dotnet-add-package.md) a `Microsoft.Extensions.Hosting`. Modifique el archivo *Program.cs* para que coincida con el código siguiente:

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

El método <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])?displayProperty=nameWithType> proporciona la configuración predeterminada para la aplicación en el orden siguiente:

1. [ChainedConfigurationProvider](xref:Microsoft.Extensions.Configuration.ChainedConfigurationSource): agrega un elemento `IConfiguration` existente como origen.
1. *appsettings.json* con el [proveedor de configuración JSON](configuration-providers.md#file-configuration-provider).
1. *appsettings.* `Environment` *.json* con el [proveedor de configuración JSON](configuration-providers.md#file-configuration-provider). Por ejemplo, *appsettings*.***Production**_._json* y *appsettings*.***Development** _._json*.
1. Secretos de la aplicación cuando la aplicación se ejecuta en el entorno `Development`.
1. Variables de entorno con el [proveedor de configuración de variables de entorno](configuration-providers.md#environment-variable-configuration-provider).
1. Argumentos de la línea de comandos con el [proveedor de configuración de línea de comandos](configuration-providers.md#command-line-configuration-provider).

Los proveedores de configuración que se agregan posteriormente invalidan los ajustes de configuración de la clave anteriores. Por ejemplo, si se establece `SomeKey` tanto en *appsettings.json* como en el entorno, se usa el valor del entorno. Con los proveedores de configuración predeterminados, el [proveedor de configuración de línea de comandos](configuration-providers.md#command-line-configuration-provider) reemplaza al resto de proveedores.

### <a name="binding"></a>Enlace

Una de las principales ventajas de la configuración en .NET es la capacidad de enlazar los valores de configuración a las instancias de objetos .NET. Por ejemplo, el proveedor de configuración de JSON se puede usar para asignar archivos *appsettings.json* a objetos .NET y se usa con la inserción de dependencias. Esto habilita el patrón de opciones, que usa clases para proporcionar acceso fuertemente tipado a grupos de configuraciones relacionadas.

## <a name="configuration-providers"></a>Proveedores de configuración

En la siguiente tabla se muestran los proveedores de configuración disponibles para las aplicaciones de .NET Core.

| Proveedor                                                                                                               | Proporciona la configuración de        |
|------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| [Proveedor de configuración de aplicaciones de Azure](/azure/azure-app-configuration/quickstart-aspnet-core-app)                          | Configuración de aplicaciones de Azure            |
| [Proveedor de configuración de Azure Key Vault](/azure/key-vault/general/tutorial-net-virtual-machine)                        | Azure Key Vault                    |
| [Proveedor de configuración de línea de comandos](configuration-providers.md#command-line-configuration-provider)                  | Parámetros de la línea de comandos            |
| [Proveedor de configuración personalizada](custom-configuration-provider.md)                                                      | Origen personalizado                      |
| [Proveedor de configuración de variables de entorno](configuration-providers.md#environment-variable-configuration-provider) | Variables de entorno              |
| [Proveedor de configuración de archivo](configuration-providers.md#file-configuration-provider)                                  | Archivos JSON, XML e INI           |
| [Proveedor de configuración de clave por archivo](configuration-providers.md#key-per-file-configuration-provider)                  | Archivos de directorio                    |
| [Proveedor de configuración de memoria](configuration-providers.md#memory-configuration-provider)                              | Colecciones en memoria              |
| [Secretos de aplicaciones (Administrador de secretos)](/aspnet/core/security/app-secrets)                                                      | Archivo en el directorio del perfil de usuario |

Para obtener más información sobre los distintos proveedores de configuración, consulte [Proveedores de configuración en .NET](configuration-providers.md).

## <a name="see-also"></a>Vea también

- [Proveedores de configuración en .NET](configuration-providers.md)
- [Implementación de un proveedor de configuración personalizado](custom-configuration-provider.md)
- Los errores de configuración deben crearse en el repositorio [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues).
