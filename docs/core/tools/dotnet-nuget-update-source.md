---
title: Comando dotnet nuget update source
description: El comando dotnet nuget update source actualiza un origen existente en los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: a8658c78c095ad4b9272d97200e1d6466cbe658b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537859"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet nuget update source`: actualiza un origen de NuGet.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet nuget update source` actualiza un origen existente en los archivos de configuración de NuGet.

## <a name="arguments"></a>Argumentos

- **`NAME`**

  Nombre del origen.

## <a name="options"></a>Opciones

- **`--configfile <FILE>`**

  Archivo de configuración de NuGet. Si se especifica, solo se usará la configuración de este archivo. Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual. Para más información, consulte [Configuraciones comunes de NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password <PASSWORD>`**

  Contraseña que se debe usar al conectarse a un origen autenticado.

- **`-s|--source <SOURCE>`**

  Ruta de acceso al origen del paquete.

- **`--store-password-in-clear-text`**

  Deshabilita el cifrado de la contraseña para permitir el almacenamiento de las credenciales de origen del paquete portátil.

- **`-u|--username <USER>`**

  Nombre de usuario que se usará al conectarse a un origen autenticado.

- **`--valid-authentication-types <TYPES>`**

  Lista separada por comas de tipos de autenticación válidos para este origen. Establézcalo en `basic` si el servidor anuncia NTLM o Negotiate y las credenciales deben enviarse mediante el mecanismo básico, por ejemplo, cuando se usa una instancia de PAT con Azure DevOps Server local. Otros valores válidos son `negotiate`, `kerberos`, `ntlm` y `digest`, pero es poco probable que estos valores sean útiles.

## <a name="examples"></a>Ejemplos

- Actualice un origen con el nombre de `mySource`:

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>Vea también

- [Secciones de origen del paquete en archivos NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
