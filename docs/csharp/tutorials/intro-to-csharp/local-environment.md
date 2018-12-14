---
title: 'Introducción a C#: familiarización con las herramientas de desarrollo'
description: En este artículo se proporciona una introducción básica a las herramientas que usará para desarrollar de C# y .NET en el equipo.
ms.date: 10/23/2018
ms.openlocfilehash: cf5bf68c1497bf62826656aa9cd2bd981128d3a2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53129992"
---
# <a name="become-familiar-with-the-net-development-tools"></a>Familiarización con las herramientas de desarrollo de .NET

El primer paso en la ejecución de un tutorial en el equipo es configurar un entorno de desarrollo.
El tema de .NET [Iniciar en 10 minutos](https://www.microsoft.com/net/core) cuenta con instrucciones para configurar el entorno de desarrollo local en Mac, PC o Linux.

Como alternativa, puede instalar el [SDK de .NET Core](https://www.microsoft.com/net/download) y [Visual Studio Code](https://code.visualstudio.com/).

## <a name="basic-application-development-flow"></a>Flujo de desarrollo de aplicaciones básico

Podrá crear aplicaciones mediante el comando [`dotnet new`](../../../core/tools/dotnet-new.md). Este comando genera los archivos y los recursos necesarios para la aplicación. Los tutoriales de introducción a C# usan el tipo de aplicación `console`. Cuando conozca los conceptos básicos, puede expandirlo a otros tipos de aplicaciones.

Los otros comandos que se van a utilizar son [`dotnet build`](../../../core/tools/dotnet-build.md) para compilar el archivo ejecutable, y [`dotnet run`](../../../core/tools/dotnet-run.md) para ejecutar el archivo ejecutable.

## <a name="pick-your-tutorial"></a>Elección del tutorial

Puede empezar con cualquiera de los siguientes tutoriales:

## <a name="numbers-in-cnumbers-in-csharp-localmd"></a>[Números en C#](numbers-in-csharp-local.md)

En el tutorial [Números en C#](numbers-in-csharp-local.md), obtendrá información sobre cómo se almacenan los números en los equipos y cómo realizar cálculos con distintos tipos numéricos. Conocerá los datos básicos sobre cómo realizar redondeos y cálculos matemáticos con C#.

En este tutorial se asume que ha completado la lección [Hola mundo](hello-world.yml).

## <a name="branches-and-loopsbranches-and-loops-localmd"></a>[Bifurcaciones y bucles](branches-and-loops-local.md)

En el tutorial [Ramas y bucles](branches-and-loops-local.md) se explican los datos básicos sobre la selección de diferentes rutas de acceso de la ejecución del código en función de los valores almacenados en variables. Aprenderá los datos básicos del flujo de control, es decir, cómo los programas toman decisiones y eligen distintas acciones.

En este tutorial se supone que ha completado las lecciones [Hola mundo](hello-world.yml) y [Números en C#](numbers-in-csharp-local.md).

## <a name="string-interpolationinterpolated-strings-localmd"></a>[Interpolación de cadenas](interpolated-strings-local.md)

En el tutorial [Interpolación de cadenas](interpolated-strings-local.md) se muestra cómo insertar valores en una cadena. Aprenderá a crear una cadena interpolada con expresiones C# insertadas y a controlar el formato de la cadena de resultado.

En este tutorial se supone que ha completado las lecciones [Hola mundo](hello-world.yml), [Números en C#](numbers-in-csharp-local.md) y [Ramas y bucles](branches-and-loops-local.md).

## <a name="list-collectionarrays-and-collectionsmd"></a>[Colección de listas](arrays-and-collections.md)

En la lección [Colección de listas](arrays-and-collections.md) se ofrece información general sobre el tipo de colección de listas que almacena secuencias de datos. Se explica cómo agregar y quitar elementos, buscarlos y ordenar las listas. Explorará los diferentes tipos de listas. 

En este tutorial se presupone que ha completado las lecciones que se muestran anteriormente.

## <a name="introduction-to-classesintroduction-to-classesmd"></a>[Introducción a las clases](introduction-to-classes.md)

Este tutorial final de introducción a C# solo se encuentra disponible para ejecutarse en el equipo con un entorno de desarrollo local propio y .NET Core.
Creará una aplicación de consola y conocerá las características básicas orientadas a objetos que forman parte del lenguaje C#.
