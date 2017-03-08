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
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: c816bf4c93430a009e61ddf2a3673c43f49b8de9
ms.lasthandoff: 03/07/2017

---

# <a name="net-core-tools-telemetry"></a>Telemetría de herramientas de .NET Core

Las herramientas de .NET Core incluyen una [característica de telemetría](https://github.com/dotnet/cli/pull/2145) que recopila información de uso. Es importante que el equipo de .NET entienda cómo se usan las herramientas a fin de que podamos mejorarlas.

Los datos recopilados son anónimos y se publicarán de forma agregada para que los usen Microsoft y los ingenieros de la comunidad según la [licencia de atribución de Creative Commons](https://creativecommons.org/licenses/by/4.0/).

## <a name="scope"></a>Ámbito

El comando `dotnet` se usa para iniciar ambas aplicaciones y las herramientas de .NET Core. El comando `dotnet` mismo no recopila la telemetría. Son las herramientas de .NET Core que se ejecutan a través del comando `dotnet`las que recopilan la telemetría.

Comandos de .NET Core (telemetría no habilitada):

- `dotnet`
- `dotnet [path-to-app]`

[Comandos](index.md) de las herramientas de .NET Core (telemetría habilitada), como:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

##<a name="behavior"></a>Comportamiento

La característica de telemetría de las herramientas de .NET Core está habilitada de manera predeterminada. Puede optar por no tener la característica de telemetría; para ello, establezca una variable de entorno DOTNET_CLI_TELEMETRY_OPTOUT (por ejemplo, `export` en macOS/Linux, `set` en Windows) en true (por ejemplo, "true", 1).

##<a name="data-points"></a>Puntos de datos

La característica recopila los siguientes puntos de datos:

- El comando que se usa (por ejemplo, "build", "restore").
- El código ExitCode del comando.
- En el caso de los proyectos de prueba, el ejecutor de pruebas que se usa.
- La marca de tiempo de la invocación.
- El marco de trabajo que se usa.
- Si los identificadores de entorno de ejecución están presentes en el nodo "runtimes".
- La versión de la CLI que se usa.

La característica no recopilará información personal, como nombres de usuario o correos electrónicos. No examinará el código ni extraerá información a nivel de proyecto alguna que pueda tener un carácter confidencial, como nombre, repositorio o autor (si los definió en el archivo project.json). Queremos saber cómo se usan las herramientas y no lo que compila con ellas. Si ve que se recopila información confidencial, se trata de un error. [Informe de la existencia de un problema](https://github.com/dotnet/cli/issues) y se corregirá.

##<a name="license"></a>Licencia

La distribución de Microsoft de .NET Core cuenta con licencia en virtud del [CLUF DE LA BIBLIOTECA DE MICROSOFT .NET](https://aka.ms/dotnet-core-eula). Esto incluye la sección "DATOS" que se vuelven a mostrar a continuación, para habilitar la telemetría.

Los [paquetes NuGet de .NET](https://www.nuget.org/profiles/dotnetframework) usan esta misma licencia, pero no permiten la telemetría (consulte [Ámbito](#scope) arriba).

```text
2.      DATA.  The software may collect information about you and your use of
the software, and send that to Microsoft. Microsoft may use this information
to improve our products and services. You can learn more about data collection
and use in the help documentation and the privacy statement at
http://go.microsoft.com/fwlink/?LinkId=528096 . Your use of the software
operates as your consent to these practices.
```

## <a name="disclosure"></a>Divulgación

Las herramientas de .NET Core muestran el texto siguiente cuando ejecuta por primera vez uno de los comandos (por ejemplo, `dotnet restore`). Esta experiencia de "primera vista" es la forma en que Microsoft le notifica sobre la recopilación de datos. Esta misma experiencia rellena inicialmente la caché NuGet con las bibliotecas del SDK de .NET Core, lo que evita solicitar estas bibliotecas a NuGet.org (u otra fuente de NuGet).

```text
Welcome to .NET Core!
---------------------
Learn more about .NET Core @ https://aka.ms/dotnet-docs. Use dotnet --help to 
see available commands or go to https://aka.ms/dotnet-cli-docs.

Telemetry
--------------
The .NET Core tools collect usage data in order to improve your experience. 
The data is anonymous and does not include command-line arguments. The data is 
collected by Microsoft and shared with the community.
You can opt out of telemetry by setting a DOTNET_CLI_TELEMETRY_OPTOUT 
environment variable to 1 using your favorite shell.
You can read more about .NET Core tools telemetry @ https://aka.ms/dotnet-cli-telemetry.

Configuring...
-------------------
A command is running to initially populate your local package cache, to 
improve restore speed and enable offline access. This command will take up to 
a minute to complete and will only happen once. 
```
