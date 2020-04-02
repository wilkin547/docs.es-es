---
title: Comando dotnet nuget list source
description: El comando dotnet nuget list source muestra todos los orígenes existentes de los archivos de configuración de NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: 4d7bc3dbd3ab5eb14c1ebf592044b685d28355cd
ms.sourcegitcommit: 07123a475af89b6da5bb6cc51ea40ab1e8a488f0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "80148499"
---
# <a name="dotnet-nuget-list-source"></a>dotnet nuget list source

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1.200 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet nuget list source`: enumera todos los orígenes de NuGet configurados.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet nuget list source [--format] [--configfile]
dotnet nuget list source [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet nuget list source` muestra todos los orígenes existentes de los archivos de configuración de NuGet.

## <a name="options"></a>Opciones

- **`--configfile`**

  Archivo de configuración de NuGet. Si se especifica, solo se usará la configuración de este archivo. Si no se especifica, se utilizará la jerarquía de archivos de configuración del directorio actual. Para más información, consulte [Configuraciones comunes de NuGet](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior).

- **`--format`**

  Formato de la salida del comando de lista: `Detailed` (valor predeterminado) y `Short`.

## <a name="examples"></a>Ejemplos

- Enumeración de los orígenes configurados del directorio actual:

  ```dotnetcli
  dotnet nuget list source
  ```

## <a name="see-also"></a>Vea también

- [Secciones de origen del paquete en archivos NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Comando sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
