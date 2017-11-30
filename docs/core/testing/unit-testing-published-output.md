---
title: Probar el resultado publicado con vstest dotnet.
description: "Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando de vstest dotnet."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 3965e4ca-75b8-4969-b3af-ca993c397a15
ms.openlocfilehash: 217787d41a9da6000941ded6caaa4f44d124644b
ms.sourcegitcommit: 8a4f8e6a7f1341764abcd188a332cc28d1e2d8ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a>Probar el resultado publicado con vstest dotnet.

Puede ejecutar pruebas en la salida ya publicado mediante el `dotnet vstest` comando. Esto funcionará en xUnit, MSTest y NUnit pruebas. Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:
```
dotnet vstest <MyPublishedTests>.dll
```
donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicados.

### <a name="example-of-running-tests-on-a-published-dll"></a>Ejemplo de ejecución de pruebas en un archivo DLL publicado

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el `dotnet vstest` comando pasando el .NET framework de destino con una marca de framework. Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`. En Visual Studio de 2017 actualización 5 se detecta automáticamente el marco deseado.

### <a name="related-topics"></a>Temas relacionados
- [Pruebas unitarias con pruebas de dotnet y xUnit](unit-testing-with-dotnet-test.md)
- [Pruebas unitarias y pruebas de dotnet MSTest](unit-testing-with-mstest.md)
