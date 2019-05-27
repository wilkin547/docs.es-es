---
title: Comando dotnet build-server
description: El comando dotnet build-server interactúa con los servidores que se han iniciado por una compilación.
ms.date: 04/24/2019
ms.openlocfilehash: 491ac37e7f75f930423b3c7e43e3c090ec1ed07d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754277"
---
# <a name="dotnet-build-server"></a>dotnet build-server

**Este artículo se aplica a: ✓** SDK de .NET Core 2.1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-21plus](../../../includes/topic-appliesto-net-core-21plus.md)]
-->

## <a name="name"></a>nombre

`dotnet build-server`: interactúa con servidores iniciados por una compilación.

## <a name="synopsis"></a>Sinopsis

```
dotnet build-server shutdown [--msbuild] [--razor] [--vbcscompiler]
dotnet build-server shutdown [-h|--help]
dotnet build-server [-h|--help]
```

## <a name="commands"></a>Comandos

* **`shutdown`**

  Cierra los servidores de la compilación que se inician desde dotnet. De forma predeterminada, se cierran todos los servidores.

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

* **`--msbuild`**

  Cierra el servidor de compilación de MSBuild.

* **`--razor`**

  Cierra el servidor de compilación de Razor.

* **`--vbcscompiler`**

  Cierra el servidor de compilación del compilador de VB/C#.