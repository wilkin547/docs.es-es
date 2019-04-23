---
title: Prueba de la salida publicada con vstest dotnet
description: Obtenga información sobre cómo ejecutar pruebas en bibliotecas publicadas en lugar de código fuente, con el comando dotnet vstest.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 660b966c6d02353b855e5728094083042a561558
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126092"
---
# <a name="test-published-output-with-dotnet-vstest"></a><span data-ttu-id="a38bd-103">Prueba de la salida publicada con vstest dotnet</span><span class="sxs-lookup"><span data-stu-id="a38bd-103">Test published output with dotnet vstest</span></span>

<span data-ttu-id="a38bd-104">Puede ejecutar pruebas en la salida ya publicada mediante el comando `dotnet vstest`.</span><span class="sxs-lookup"><span data-stu-id="a38bd-104">You can run tests on already published output by using the `dotnet vstest` command.</span></span> <span data-ttu-id="a38bd-105">Esto funcionará en pruebas de xUnit, MSTest y NUnit.</span><span class="sxs-lookup"><span data-stu-id="a38bd-105">This will work on xUnit, MSTest, and NUnit tests.</span></span> <span data-ttu-id="a38bd-106">Simplemente busque el archivo DLL que formaba parte de la salida publicada y ejecute:</span><span class="sxs-lookup"><span data-stu-id="a38bd-106">Simply locate the DLL file that was part of your published output and run:</span></span>

```
dotnet vstest <MyPublishedTests>.dll
```

<span data-ttu-id="a38bd-107">donde `<MyPublishedTests>` es el nombre del proyecto de prueba publicado.</span><span class="sxs-lookup"><span data-stu-id="a38bd-107">Where `<MyPublishedTests>` is the name of your published test project.</span></span>

## <a name="example"></a><span data-ttu-id="a38bd-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a38bd-108">Example</span></span>

<span data-ttu-id="a38bd-109">Los comandos siguientes muestran la ejecución de pruebas en un archivo DLL publicado.</span><span class="sxs-lookup"><span data-stu-id="a38bd-109">The commands below demonstrate running tests on a published DLL.</span></span>

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> <span data-ttu-id="a38bd-110">Nota: Si la aplicación tiene como destino un marco distinto de `netcoreapp` todavía puede ejecutar el comando `dotnet vstest` si pasa el marco de destino con una marca de marco.</span><span class="sxs-lookup"><span data-stu-id="a38bd-110">Note: If your app is targeting a framework other than `netcoreapp` you can still run the `dotnet vstest` command by passing in the targeted framework with a framework flag.</span></span> <span data-ttu-id="a38bd-111">Por ejemplo: `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span><span class="sxs-lookup"><span data-stu-id="a38bd-111">For example, `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`.</span></span> <span data-ttu-id="a38bd-112">En Visual Studio 2017 Update 5, se detecta automáticamente el marco deseado.</span><span class="sxs-lookup"><span data-stu-id="a38bd-112">In Visual Studio 2017 Update 5 the desired framework is automatically detected.</span></span>

## <a name="see-also"></a><span data-ttu-id="a38bd-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="a38bd-113">See also</span></span>

- [<span data-ttu-id="a38bd-114">Pruebas unitarias con pruebas de dotnet y xUnit</span><span class="sxs-lookup"><span data-stu-id="a38bd-114">Unit Testing with dotnet test and xUnit</span></span>](unit-testing-with-dotnet-test.md)
- [<span data-ttu-id="a38bd-115">Prueba unitaria de C# con NUnit y .NET Core</span><span class="sxs-lookup"><span data-stu-id="a38bd-115">Unit Testing with dotnet test and NUnit</span></span>](unit-testing-with-nunit.md)
- [<span data-ttu-id="a38bd-116">Pruebas unitarias con pruebas de dotnet y MSTest</span><span class="sxs-lookup"><span data-stu-id="a38bd-116">Unit Testing with dotnet test and MSTest</span></span>](unit-testing-with-mstest.md)
