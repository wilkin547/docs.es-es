---
title: Prueba de la salida publicada con vstest dotnet
description: Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: dbce1b6e616916e60e56318b773e8fcecbc55580
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33210258"
---
# <a name="test-published-output-with-dotnet-vstest"></a>Prueba de la salida publicada con vstest dotnet

Puede ejecutar pruebas en la salida ya publicada mediante el comando `dotnet vstest`. Esto funcionará en pruebas de xUnit, MSTest y NUnit. Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:

```
dotnet vstest <MyPublishedTests>.dll
```

donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicado.

## <a name="example-of-running-tests-on-a-published-dll"></a>Ejemplo de ejecución de pruebas en un archivo DLL publicado

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el comando `dotnet vstest` pasando el marco de destino con un indicador de marco. Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. En Visual Studio 2017 Update 5, se detecta automáticamente el marco deseado.

## <a name="see-also"></a>Vea también
 [Pruebas unitarias con pruebas de dotnet y xUnit](unit-testing-with-dotnet-test.md)  
 [Pruebas unitarias con pruebas de dotnet y MSTest](unit-testing-with-mstest.md)  
