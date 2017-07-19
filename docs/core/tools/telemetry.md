---
title: "Telemetría de herramientas de .NET Core | Microsoft Docs"
description: "Núcleo de .NET"
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 480df976-7568-4df4-9d26-9911357b5a31
ms.translationtype: Human Translation
ms.sourcegitcommit: 6f3dc4235c75d7438f019838cb22192f4dc7c41a
ms.openlocfilehash: b7de81f38c0d4fa259f1c9d8ada675197930e945
ms.contentlocale: es-es
ms.lasthandoff: 06/12/2017

---

# Telemetría de herramientas de .NET Core
<a id="net-core-tools-telemetry" class="xliff"></a>

Las herramientas de .NET Core incluyen una [característica de telemetría](https://github.com/dotnet/cli/pull/2145) que recopila información de uso. Es importante que el equipo de .NET entienda cómo se usan las herramientas a fin de que podamos mejorarlas.

Los datos recopilados son anónimos y se publicarán de forma agregada para que los usen Microsoft y los ingenieros de la comunidad según la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).

## Ámbito
<a id="scope" class="xliff"></a>

El comando `dotnet` se usa para iniciar ambas aplicaciones y las herramientas de .NET Core. El comando `dotnet` mismo no recopila la telemetría. Son las herramientas de .NET Core que se ejecutan a través del comando `dotnet`las que recopilan la telemetría.

Comandos de .NET Core (telemetría no habilitada):

- `dotnet`
- `dotnet [path-to-app]`

[Comandos](index.md) de las herramientas de .NET Core (telemetría habilitada), como:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## Comportamiento
<a id="behavior" class="xliff"></a>

La característica de telemetría de las herramientas de .NET Core está habilitada de manera predeterminada. Puede optar por no tener la característica de telemetría; para ello, establezca una variable de entorno DOTNET_CLI_TELEMETRY_OPTOUT (por ejemplo, `export` en macOS/Linux, `set` en Windows) en True (por ejemplo, "True", 1).

## Puntos de datos
<a id="data-points" class="xliff"></a>

La característica recopila los siguientes puntos de datos:

- El comando que se usa (por ejemplo, "build", "restore").
- El código ExitCode del comando.
- En el caso de los proyectos de prueba, el ejecutor de pruebas que se usa.
- La marca de tiempo de la invocación.
- El marco de trabajo que se usa.
- Si los identificadores de tiempo de ejecución están presentes en el nodo "runtimes".
- La versión de la CLI que se usa.

La característica no recopilará información personal, como nombres de usuario o correos electrónicos. No examinará el código ni extraerá información a nivel de proyecto alguna que pueda tener un carácter confidencial, como nombre, repositorio o autor (si los definió en el archivo project.json). Queremos saber cómo se usan las herramientas y no lo que compila con ellas. Si ve que se recopila información confidencial, se trata de un error. [Informe de la existencia de un problema](https://github.com/dotnet/cli/issues) y se corregirá.

## Licencia
<a id="license" class="xliff"></a>

La distribución de Microsoft de .NET Core cuenta con licencia en virtud del [CLUF DE LA BIBLIOTECA DE MICROSOFT .NET](https://aka.ms/dotnet-core-eula). Esto incluye la sección "DATOS" que se vuelve a mostrar a continuación, para habilitar la telemetría.

Los [paquetes NuGet de .NET](https://www.nuget.org/profiles/dotnetframework) usan esta misma licencia, pero no permiten la telemetría (consulte [Ámbito](#scope) arriba).

> 2. DATOS. El software puede recopilar información sobre el usuario y la utilización del software y, después, enviarla a Microsoft. Microsoft puede usarla para mejorar nuestros productos y servicios. Puede obtener más información sobre la recopilación y el uso de datos en la documentación de ayuda y la declaración de privacidad en http://go.microsoft.com/fwlink/?LinkId=528096. Al usar el software, se entiende que da su consentimiento para la realización de estas prácticas.

## Divulgación
<a id="disclosure" class="xliff"></a>

Las herramientas de .NET Core muestran el texto siguiente cuando ejecuta por primera vez uno de los comandos (por ejemplo, `dotnet restore`). Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos. Esta misma experiencia rellena inicialmente la caché NuGet con las bibliotecas del SDK de .NET Core, lo que evita solicitar estas bibliotecas a NuGet.org (u otra fuente de NuGet).

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience.
The data is anonymous and does not include command-line arguments. The data is collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to improve restore speed and enable offline access. This command will take up to a minute to complete and will only happen once.
```

