---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 04/24/2019
ms.openlocfilehash: 1c6c6dcdb53d779426daf5daa470d2ad0470a7a1
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523015"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Este artículo se aplica a: ✓** SDK de .NET Core 2.1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>Name

`dotnet build-server`: interactúa con servidores iniciados por una compilación.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Comandos

- **`shutdown`**

  Cierra los servidores de la compilación que se inician desde dotnet. De forma predeterminada, se cierran todos los servidores.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--msbuild`**

  Cierra el servidor de compilación de MSBuild.

- **`--razor`**

  Cierra el servidor de compilación de Razor.

- **`--vbcscompiler`**

  Cierra el servidor de compilación del compilador de VB/C#.
