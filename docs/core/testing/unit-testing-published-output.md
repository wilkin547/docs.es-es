---
title: Prueba de la salida publicada con vstest dotnet
description: "Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando dotnet vstest."
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 373c557d3fc640ed9071a732bba9f082ca6a4d33
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="fd9b7-103">Prueba de la salida publicada con vstest dotnet</span><span class="sxs-lookup"><span data-stu-id="fd9b7-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="fd9b7-104">Puede ejecutar pruebas en la salida ya publicada mediante el comando `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="fd9b7-105">Esto funcionará en pruebas de xUnit, MSTest y NUnit.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="fd9b7-106">Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:</span><span class="sxs-lookup"><span data-stu-id="fd9b7-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="fd9b7-107">donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicado.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="fd9b7-108">Ejemplo de ejecución de pruebas en un archivo DLL publicado</span><span class="sxs-lookup"><span data-stu-id="fd9b7-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="fd9b7-109">Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el comando `dotnet vstest` pasando el marco de destino con un indicador de marco.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="fd9b7-110">Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="fd9b7-111">En Visual Studio 2017 Update 5, se detecta automáticamente el marco deseado.</span><span class="sxs-lookup"><span data-stu-id="fd9b7-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd9b7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd9b7-112">See also</span></span>
 [<span data-ttu-id="fd9b7-113">Pruebas unitarias con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="fd9b7-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)  
 [<span data-ttu-id="fd9b7-114">Pruebas unitarias con pruebas de dotnet y MSTest</span><span class="sxs-lookup"><span data-stu-id="fd9b7-114">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)  
