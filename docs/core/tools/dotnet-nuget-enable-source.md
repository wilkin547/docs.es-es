---
title: Comando dotnet nuget enable source
description: El comando dotnet nuget enable source habilita un origen existente en los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 38fb5917361bd7952fef9c31ed897fb81f005155
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463557"
---
# <a name="dotnet-nuget-enable-source"></a>dotnet nuget enable source

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet nuget enable source`: habilita un origen de NuGet.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget enable source <NAME> [--configfile <FILE>]

dotnet nuget enable source -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet nuget enable source` habilita un origen existente en los archivos de configuración de NuGet.

## <a name="arguments"></a>Argumentos

- **`NAME`**

  Nombre del origen.

## <a name="options"></a>Opciones

- **`--configfile <FILE>`**

  Archivo de configuración de NuGet. Si se especifica, solo se usará la configuración de este archivo. Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual. Para más información, consulte [Configuraciones comunes de NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

## <a name="examples"></a>Ejemplos

- Habilite un origen con el nombre de `mySource`:

  ```dotnetcli
  dotnet nuget enable source mySource
  ```

## <a name="see-also"></a>Vea también

- [Secciones de origen del paquete en archivos NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
