---
title: Prueba de la salida publicada con vstest dotnet
description: Obtenga información acerca de cómo ejecutar pruebas en la salida publicada con el comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.openlocfilehash: e99000996f5dfa9f9d4f9b823e36ecbe325da835
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43404720"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="d0dcd-103">Prueba de la salida publicada con vstest dotnet</span><span class="sxs-lookup"><span data-stu-id="d0dcd-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="d0dcd-104">Puede ejecutar pruebas en la salida ya publicada mediante el comando `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="d0dcd-105">Esto funcionará en pruebas de xUnit, MSTest y NUnit.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="d0dcd-106">Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:</span><span class="sxs-lookup"><span data-stu-id="d0dcd-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="d0dcd-107">donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicado.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-107">where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example-of-running-tests-on-a-published-dll"></a><span data-ttu-id="d0dcd-108">Ejemplo de ejecución de pruebas en un archivo DLL publicado</span><span class="sxs-lookup"><span data-stu-id="d0dcd-108">Example of running tests on a published DLL</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="d0dcd-109">Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el comando `dotnet vstest` pasando el marco de destino con un indicador de marco.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-109">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="d0dcd-110">Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-110">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="d0dcd-111">En Visual Studio 2017 Update 5, se detecta automáticamente el marco deseado.</span><span class="sxs-lookup"><span data-stu-id="d0dcd-111">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0dcd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0dcd-112">See also</span></span>
- [<span data-ttu-id="d0dcd-113">Pruebas unitarias con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="d0dcd-113">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="d0dcd-114">Prueba unitaria de C# con NUnit y .NET Core</span><span class="sxs-lookup"><span data-stu-id="d0dcd-114">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="d0dcd-115">Pruebas unitarias con pruebas de dotnet y MSTest</span><span class="sxs-lookup"><span data-stu-id="d0dcd-115">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
