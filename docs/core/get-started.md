---
title: Introducción a .NET Core
description: Encuentre recursos para aprender a crear aplicaciones .NET Core en Windows, Linux y macOS.
author: thraka
ms.author: adegeo
ms.date: 09/19/2019
ms.openlocfilehash: 89db6d79336c01315983133d9041904d88cba301
ms.sourcegitcommit: 68a4b28242da50e1d25aab597c632767713a6f81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "74884259"
---
# <a name="get-started-with-net-core"></a>Introducción a .NET Core

En este artículo se proporciona información sobre cómo comenzar con .NET Core. .NET Core se puede instalar en Windows, Linux y macOS. Puede programar en su editor de texto preferido y crear aplicaciones y bibliotecas multiplataforma. 

Si no está seguro de qué es .NET Core o cómo se relaciona con otras tecnologías .NET, comience con la información general [¿Qué es .NET?](https://dotnet.microsoft.com/learn/dotnet/what-is-dotnet). En resumen, .NET Core es una implementación multiplataforma de código abierto de .NET.

## <a name="create-an-application"></a>Crear una aplicación

En primer lugar, descargue e instale el [SDK de .NET Core](https://dotnet.microsoft.com/download) en el equipo.

A continuación, abra un terminal como **PowerShell**, **Símbolo del sistema** o **bash**. Escriba los comandos `dotnet` siguientes para crear y ejecutar una aplicación C#:

```dotnetcli
dotnet new console --output sample1
dotnet run --project sample1
```

Debería ver los siguientes resultados:

```console
Hello World!
```

¡Enhorabuena! Ha creado una sencilla aplicación .NET Core. También puede usar [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio ](tutorials/with-visual-studio.md) (solo Windows) o [Visual Studio para Mac](tutorials/using-on-mac-vs.md) (solo macOS), para crear una aplicación .NET Core.

## <a name="tutorials"></a>Tutoriales

Para comenzar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso.

<!-- markdownlint-disable MD025 -->

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

- [Compilación de una aplicación "Hola a todos" en C# con .NET Core en Visual Studio 2017.](./tutorials/with-visual-studio.md)
- [Creación de una biblioteca de clases de C# con .NET Core en Visual Studio 2017](./tutorials/library-with-visual-studio.md)
- [Compilación de una aplicación "Hola a todos" en Visual Basic con .NET Core en Visual Studio 2017.](./tutorials/vb-with-visual-studio.md)
- [Creación de una biblioteca de clases con Visual Basic y .NET Core en Visual Studio 2017.](./tutorials/vb-library-with-visual-studio.md)  
- Vea un vídeo sobre [cómo instalar y usar Visual Studio Code y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/).
- Vea un vídeo sobre [cómo instalar y usar Visual Studio 2017 y .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/).
- [Introducción a .NET Core con la línea de comandos.](tutorials/cli-create-console-app.md)

Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-windows) para obtener una lista de las versiones de Windows admitidas.

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

Para empezar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:

- [Introducción a .NET Core con la línea de comandos.](tutorials/cli-create-console-app.md)
- Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu).

Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-linux) para obtener una lista de las distribuciones y las versiones de Linux admitidas.

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Para empezar a desarrollar aplicaciones .NET Core, puede seguir estos tutoriales paso a paso:

- Vea un vídeo de [introducción a Visual Studio Code mediante C# y .NET Core en macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac).
- [Introducción a .NET Core en macOS con Visual Studio Code.](tutorials/using-on-macos.md)
- [Introducción a .NET Core con la línea de comandos.](tutorials/cli-create-console-app.md)
- [Introducción a .NET Core en macOS con Visual Studio para Mac.](tutorials/using-on-mac-vs.md)
- [Creación de una solución completa de .NET Core en macOS con Visual Studio para Mac.](tutorials/using-on-mac-vs-full-solution.md)

Vea el artículo [Dependencias y requisitos de .NET Core](install/dependencies.md?tabs=netcore30&pivots=os-macos) para obtener una lista de las versiones de OS X / macOS admitidas.

---
