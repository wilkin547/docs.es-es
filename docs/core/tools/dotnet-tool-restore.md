---
title: Comando dotnet tool restore
description: El comando dotnet tool restore instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.
ms.date: 02/14/2020
ms.openlocfilehash: cb46f70afb58e482b6aedfddfbf5f3a0c40674f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146442"
---
# <a name="dotnet-tool-restore"></a>dotnet tool restore

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool restore`: instala en el equipo las herramientas locales de .NET Core que se encuentran en el ámbito del directorio actual.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool restore <PACKAGE_NAME>
    [--configfile] [--add-source] [tool-manifest]
    [--disable-parallel] [--ignore-failed-sources]
    [--no-cache] [-interactive] [-v|--verbosity]

dotnet tool restore <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool restore` busca el archivo de manifiesto de las herramientas que está en el ámbito del directorio actual e instala las herramientas que se indican en él. Para obtener información sobre los archivos de manifiesto, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool) e [Invocación de una herramienta local](global-tools.md#invoke-a-local-tool).

## <a name="arguments"></a>Argumentos

- **`PACKAGE_NAME`**

Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere instalar.

## <a name="options"></a>Opciones

- **`--configfile <FILE>`**

  El archivo de configuración de NuGet (*nuget.config*) que se usará.

- **`--add-source <SOURCE>`**

  Agrega un origen de paquete NuGet adicional que se usará durante la instalación.

- **`--tool-manifest <PATH>`**

  Ruta de acceso al archivo de manifiesto.

- **`--disable-parallel`**

  Impide que se restauren varios proyectos en paralelo.

- **`--ignore-failed-sources`**

  Indica que los errores de origen de paquete se traten como advertencias.

- **`--no-cache`**

  Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="example"></a>Ejemplo

- **`dotnet tool restore`**

  Restaura las herramientas locales del directorio actual.

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core](local-tools-how-to-use.md)
