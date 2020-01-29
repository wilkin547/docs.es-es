---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 04/24/2019
ms.openlocfilehash: e77a4d9f49f555ac847bb13380380599eef881b1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734379"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>NOMBRE

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
