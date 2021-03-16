---
title: Comando dotnet nuget add source
description: El comando dotnet nuget add source agrega un nuevo origen de paquete a los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: df31a2eaba997d0e9fe4f4c2666052fd7c7c2f03
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105056"
---
# <a name="dotnet-nuget-add-source"></a>dotnet nuget add source

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet nuget add source`: agrega un origen de NuGet.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget add source <PACKAGE_SOURCE_PATH> [--name <SOURCE_NAME>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget add source -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet nuget add source` agrega un nuevo origen de paquete a los archivos de configuración de NuGet.

> [!WARNING]
> Al agregar varios orígenes de paquete, tenga cuidado de no introducir una [vulnerabilidad de confusión de dependencias](https://aka.ms/pkg-sec-wp).

## <a name="arguments"></a>Argumentos

- **`PACKAGE_SOURCE_PATH`**

  Ruta de acceso al origen del paquete.

## <a name="options"></a>Opciones

- **`--configfile <FILE>`**

  Archivo de configuración de NuGet. Si se especifica, solo se usará la configuración de este archivo. Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual. Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`-n|--name <SOURCE_NAME>`**

  Nombre del origen.

- **`-p|--password <PASSWORD>`**

  Contraseña que se debe usar al conectarse a un origen autenticado.

- **`--store-password-in-clear-text`**

  Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.

- **`-u|--username <USER>`**

  Nombre de usuario que se usará al conectarse a un origen autenticado.

- **`--valid-authentication-types <TYPES>`**

  Lista separada por comas de tipos de autenticación válidos para este origen. Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local. Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.

## <a name="examples"></a>Ejemplos

- Agregue `nuget.org` como origen:

  ```dotnetcli
  dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org
  ```

- Agregue `c:\packages` como origen local:

  ```dotnetcli
  dotnet nuget add source c:\packages
  ```

- Agregue un origen que necesite autenticación:

  ```dotnetcli
  dotnet nuget add source https://someServer/myTeam -n myTeam -u myUsername -p myPassword --store-password-in-clear-text
  ```

- Agregue un origen que necesite autenticación (luego, pase a la instalación del proveedor de credenciales):

  ```dotnetcli
  dotnet nuget add source https://azureartifacts.microsoft.com/myTeam -n myTeam
  ```

## <a name="see-also"></a>Vea también

- [Secciones de origen del paquete en archivos NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
