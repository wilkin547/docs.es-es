---
title: Comando dotnet help
description: El comando dotnet help muestra documentación en línea más detallada para el comando especificado.
ms.date: 08/08/2019
ms.openlocfilehash: e76f858f2529afc50646473f1aab9d52730cff16
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70990459"
---
# <a name="dotnet-help-reference"></a>Referencia de dotnet help

**Este artículo se aplica a: ✓** SDK de .NET Core 2.0.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-2plus.md)]
-->

## <a name="name"></a>nombre

`dotnet help`: muestra documentación más detallada en línea para el comando especificado.

## <a name="synopsis"></a>Sinopsis

`dotnet help <COMMAND_NAME> [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet help` abre la página de referencia para obtener información más detallada sobre el comando especificado en docs.microsoft.com.

## <a name="arguments"></a>Argumentos

* **`COMMAND_NAME`**

  Nombre del comando de la CLI de .NET Core. Para obtener una lista de los comandos de la CLI válidos, vea [Comandos de la CLI](index.md#cli-commands).

## <a name="options"></a>Opciones

* **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

* Se abre la página de documentación del comando [dotnet new](dotnet-new.md):

  ```console
  dotnet help new
  ```
