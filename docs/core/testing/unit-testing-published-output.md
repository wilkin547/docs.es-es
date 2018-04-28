---
title: Prueba de la salida publicada con vstest dotnet
description: Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.workload:
- dotnetcore
ms.openlocfilehash: 2f750a8bb0907069691c4a4491beeb4b1733df29
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="5db32-103">Prueba de la salida publicada con vstest dotnet</span><span class="sxs-lookup"><span data-stu-id="5db32-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="5db32-104">Puede ejecutar pruebas en la salida ya publicada mediante el comando `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="5db32-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="5db32-105">Esto funcionará en pruebas de xUnit, MSTest y NUnit.</span><span class="sxs-lookup"><span data-stu-id="5db32-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="5db32-106">Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:</span><span class="sxs-lookup"><span data-stu-id="5db32-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="5db32-107">donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicado.</span><span class="sxs-lookup"><span data-stu-id="5db32-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="5db32-108">Ejemplo de ejecución de pruebas en un archivo DLL publicado</span><span class="sxs-lookup"><span data-stu-id="5db32-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="5db32-109">Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el comando `dotnet vstest` pasando el marco de destino con un indicador de marco.</span><span class="sxs-lookup"><span data-stu-id="5db32-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="5db32-110">Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="5db32-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="5db32-111">En Visual Studio 2017 Update 5, se detecta automáticamente el marco deseado.</span><span class="sxs-lookup"><span data-stu-id="5db32-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="5db32-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5db32-112">See also</span></span>
 [<span data-ttu-id="5db32-113">Pruebas unitarias con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="5db32-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)  
 [<span data-ttu-id="5db32-114">Pruebas unitarias con pruebas de dotnet y MSTest</span><span class="sxs-lookup"><span data-stu-id="5db32-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)  
