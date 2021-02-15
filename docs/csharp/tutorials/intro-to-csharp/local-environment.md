---
title: 'Introducción a C#: familiarización con las herramientas de desarrollo'
description: En este artículo se proporciona una introducción básica a las herramientas que usará para desarrollar de C# y .NET en el equipo.
ms.date: 02/02/2021
ms.openlocfilehash: d5fbd23679fc11f4e4c207c59858a71ab753c038
ms.sourcegitcommit: 65af0f0ad316858882845391d60ef7e303b756e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "99585330"
---
# <a name="set-up-your-local-environment"></a>Configuración de un entorno local

El primer paso en la ejecución de un tutorial en el equipo es configurar un entorno de desarrollo. Pruebe una de las siguientes alternativas:

* Para usar la CLI de .NET y su elección de texto o editor de código, consulte el tutorial de .NET [Hola mundo en 10 minutos](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro). En este tutorial se incluyen instrucciones para configurar un entorno de desarrollo en Windows, Linux o macOS.
* Para usar la CLI de .NET y Visual Studio Code, instale el SDK de [.NET](https://dotnet.microsoft.com/download) y [Visual Studio Code](https://code.visualstudio.com/).
* Para usar Visual Studio 2019 en Windows, consulte [Tutorial: Cree una aplicación de consola de C# sencilla en Visual Studio](/visualstudio/get-started/csharp/tutorial-console).

## <a name="basic-application-development-flow"></a>Flujo de desarrollo de aplicaciones básico

Las instrucciones de estos tutoriales asumen que está usando la CLI de .NET para crear, compilar y ejecutar aplicaciones. Usará los comandos siguientes:

* [`dotnet new`](../../../core/tools/dotnet-new.md) crea una aplicación. Este comando genera los archivos y los recursos necesarios para la aplicación. Los tutoriales de introducción a C# usan el tipo de aplicación `console`. Cuando conozca los conceptos básicos, puede expandirlo a otros tipos de aplicaciones.
* [`dotnet build`](../../../core/tools/dotnet-build.md) compila el archivo ejecutable.
* [`dotnet run`](../../../core/tools/dotnet-run.md) ejecuta el archivo ejecutable.

Si usa Visual Studio 2019 para estos tutoriales, elegirá una selección de menú de Visual Studio cuando un tutorial le indique que ejecute uno de estos comandos de la CLI:

* **Archivo** > **Nuevo** > **Proyecto** crea una aplicación.
* **Compilar** >  **Compilar solución** crea el arcivo ejecutable.
* **Depurar** > **Iniciar sin depurar** ejecuta el archivo ejecutable.

## <a name="pick-your-tutorial"></a>Elección del tutorial

Puede empezar con cualquiera de los siguientes tutoriales:

## <a name="numbers-in-c"></a>Números en C\#

En el tutorial [Números en C#](numbers-in-csharp-local.md), obtendrá información sobre cómo se almacenan los números en los equipos y cómo realizar cálculos con distintos tipos numéricos. Conocerá los datos básicos sobre cómo realizar redondeos y cálculos matemáticos con C#.

En este tutorial se asume que ha completado la lección [Hola mundo](hello-world.yml).

## <a name="branches-and-loops"></a>Bifurcaciones y bucles

En el tutorial [Ramas y bucles](branches-and-loops-local.md) se explican los datos básicos sobre la selección de diferentes rutas de acceso de la ejecución del código en función de los valores almacenados en variables. Aprenderá los datos básicos del flujo de control, es decir, cómo los programas toman decisiones y eligen distintas acciones.

En este tutorial se supone que ha completado las lecciones [Hola mundo](hello-world.yml) y [Números en C#](numbers-in-csharp-local.md).

## <a name="list-collection"></a>Colección de listas

En la lección [Colección de listas](arrays-and-collections.md) se ofrece información general sobre el tipo de colección de listas que almacena secuencias de datos. Se explica cómo agregar y quitar elementos, buscarlos y ordenar las listas. Explorará los diferentes tipos de listas.

En este tutorial se presupone que ha completado las lecciones que se muestran anteriormente.

## <a name="introduction-to-classes"></a>Introducción a las clases

En [Introducción a las clases](introduction-to-classes.md), creará una aplicación de consola y conocerá las características básicas orientadas a objetos que forman parte del lenguaje C#. Esta es la introducción final al tutorial de C#. Solo se encuentra disponible para ejecutarse en la máquina con un entorno de desarrollo local propio y .NET.
