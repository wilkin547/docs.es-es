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
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="cfda3-103">Probar el resultado publicado con vstest dotnet.</span><span class="sxs-lookup"><span data-stu-id="cfda3-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="cfda3-104">Puede ejecutar pruebas en la salida ya publicado mediante el `dotnet vstest` comando.</span><span class="sxs-lookup"><span data-stu-id="cfda3-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="cfda3-105">Esto funcionará en xUnit, MSTest y NUnit pruebas.</span><span class="sxs-lookup"><span data-stu-id="cfda3-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="cfda3-106">Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:</span><span class="sxs-lookup"><span data-stu-id="cfda3-106">Simply locate the DLL file that was part of your published output and run:</span></span>
```
dotnet vstest <MyPublishedTests>.dll
```
<span data-ttu-id="cfda3-107">donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicados.</span><span class="sxs-lookup"><span data-stu-id="cfda3-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

### <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="cfda3-108">Ejemplo de ejecución de pruebas en un archivo DLL publicado</span><span class="sxs-lookup"><span data-stu-id="cfda3-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE] <span data-ttu-id="cfda3-109">Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el `dotnet vstest` comando pasando el .NET framework de destino con una marca de framework.</span><span class="sxs-lookup"><span data-stu-id="cfda3-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="cfda3-110">Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="cfda3-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="cfda3-111">En Visual Studio de 2017 actualización 5 se detecta automáticamente el marco deseado.</span><span class="sxs-lookup"><span data-stu-id="cfda3-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

### <a name="related-topics"></a><span data-ttu-id="cfda3-112">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cfda3-112">Related topics</span></span>
- [<span data-ttu-id="cfda3-113">Pruebas unitarias con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="cfda3-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="cfda3-114">Pruebas unitarias y pruebas de dotnet MSTest</span><span class="sxs-lookup"><span data-stu-id="cfda3-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
