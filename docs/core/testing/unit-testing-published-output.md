---
title: Prueba de la salida publicada con vstest dotnet
description: "Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando dotnet vstest."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.openlocfilehash: 6651d41d4d60194aec035107e3a65df6a5f70a51
ms.sourcegitcommit: 4a96a0fe9f87de70291245d71b76c7d1b15127ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2017
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
