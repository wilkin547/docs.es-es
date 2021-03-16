---
title: Herramienta de instalación de .NET para autores de extensiones de VS Code
description: Información general de la herramienta de instalación de .NET para autores de extensiones, una extensión de Visual Studio Code para instalar el entorno de ejecución de .NET.
author: sfoslund
ms.date: 11/18/2020
ms.openlocfilehash: 4be931a254e4ce969f9eaf2efde7939cb54e1d5f
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102605157"
---
# <a name="net-install-tool-for-extension-authors"></a>Herramienta de instalación de .NET para autores de extensiones

La [herramienta de instalación de .NET para autores de extensiones](https://github.com/dotnet/vscode-dotnet-runtime) es una extensión de Visual Studio Code que permite la adquisición del entorno de ejecución de .NET específicamente para autores de extensiones de VS Code. Esta herramienta está diseñada para aprovecharse en extensiones escritas en .NET y requiere que .NET arranque partes de la extensión (por ejemplo, un servidor de lenguaje). La extensión no está pensada para que la usen directamente los usuarios con el fin de instalar .NET para el desarrollo.

## <a name="getting-started-extension-authors"></a>Introducción: autores de extensiones

Para asegurarse de que la herramienta de instalación de .NET para autores de extensiones es la opción adecuada en su escenario, empiece por revisar los [objetivos de esta extensión](https://github.com/dotnet/vscode-dotnet-runtime#goals-acquiring-net-core-for-extensions) en nuestra página de GitHub.

> [!NOTE]
> Esta herramienta solo se puede usar para instalar el entorno de ejecución de .NET, actualmente no tiene la capacidad de instalar el SDK de .NET.

Cuando haya comprobado que la herramienta de instalación de .NET para autores de extensiones se adapta a sus necesidades, puede aceptar una dependencia de ella en el [manifiesto de la extensión](https://code.visualstudio.com/api/references/extension-manifest) y empezar a usar los comandos que exponemos con la [API de VS Code](https://code.visualstudio.com/api/extension-guides/command#programmatically-executing-a-command). Puede encontrar la lista de comandos que expone esta extensión en nuestro [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/commands.md).

Consulte esta [extensión de ejemplo](https://github.com/dotnet/vscode-dotnet-runtime/tree/master/sample) para ver estos pasos en acción.

Para ver más ejemplos, consulte estas extensiones de código abierto que aprovechan actualmente esta herramienta:

- [Herramientas de Azure Resource Manager (ARM) para Visual Studio Code](https://github.com/microsoft/vscode-azurearmtools)

- [.NET Interactive Notebooks](https://github.com/dotnet/interactive/tree/main/src/dotnet-interactive-vscode)

## <a name="getting-started-end-users"></a>Introducción: usuarios finales

En general, no es necesario que el usuario final interactúe con la herramienta de instalación de .NET para autores extensiones. Si tiene problemas con la extensión, consulte nuestra [página de solución de problemas](https://github.com/dotnet/vscode-dotnet-runtime/blob/master/Documentation/troubleshooting-runtime.md) o presente una incidencia en nuestro [GitHub](https://github.com/dotnet/vscode-dotnet-runtime/issues).
