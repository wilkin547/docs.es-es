---
title: Ejecución de pruebas unitarias selectivas
description: Muestra cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: 77ac7ab5a46150bd3654d50e6686087c804b8440
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="f0004-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="f0004-103">Running selective unit tests</span></span>

<span data-ttu-id="f0004-104">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="f0004-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="f0004-105">Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="f0004-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="f0004-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="f0004-106">MSTest</span></span>

```csharp
namespace MSTestNamespace
{
    using Microsoft.VisualStudio.TestTools.UnitTesting;

    [TestClass]
    public class UnitTestClass1
    {
        [Priority(2)]
        [TestMethod]
        public void TestMethod1()
        {
        }

        [TestCategory("CategoryA")]
        [Priority(3)]
        [TestMethod]
        public void TestMethod2()
        {
        }
    }
}
```

| <span data-ttu-id="f0004-107">Expresión</span><span class="sxs-lookup"><span data-stu-id="f0004-107">Expression</span></span> | <span data-ttu-id="f0004-108">Resultado</span><span class="sxs-lookup"><span data-stu-id="f0004-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="f0004-109">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="f0004-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="f0004-110">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="f0004-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="f0004-111">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="f0004-112">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="f0004-113">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTestClass1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="f0004-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="f0004-114">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="f0004-115">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="f0004-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="f0004-116">Ejecuta pruebas anotadas con `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="f0004-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="f0004-117">**Nota:** `Priority~3` es un valor no válido, ya que no es una cadena.</span><span class="sxs-lookup"><span data-stu-id="f0004-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="f0004-118">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="f0004-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f0004-119">Expresión</span><span class="sxs-lookup"><span data-stu-id="f0004-119">Expression</span></span> | <span data-ttu-id="f0004-120">Resultado</span><span class="sxs-lookup"><span data-stu-id="f0004-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="f0004-121">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f0004-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="f0004-122">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="f0004-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="f0004-123">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTestClass1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="f0004-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="f0004-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="f0004-124">xUnit</span></span>

```csharp
namespace XUnitNamespace
{
    public class TestClass1
    {
        [Trait("Category", "bvt")]
        [Trait("Priority", "1")]
        [Fact]
        public void foo()
        {
        }

        [Trait("Category", "Nightly")]
        [Trait("Priority", "2")]
        [Fact]
        public void bar()
        {
        }
    }
}
```

| <span data-ttu-id="f0004-125">Expresión</span><span class="sxs-lookup"><span data-stu-id="f0004-125">Expression</span></span> | <span data-ttu-id="f0004-126">Resultado</span><span class="sxs-lookup"><span data-stu-id="f0004-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f0004-127">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="f0004-128">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="f0004-129">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="f0004-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="f0004-130">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="f0004-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="f0004-131">Expresión</span><span class="sxs-lookup"><span data-stu-id="f0004-131">Expression</span></span> | <span data-ttu-id="f0004-132">Resultado</span><span class="sxs-lookup"><span data-stu-id="f0004-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="f0004-133">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="f0004-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="f0004-134">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="f0004-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="f0004-135">Ejecuta las pruebas que tienen `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="f0004-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="f0004-136">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="f0004-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="f0004-137">Expresión</span><span class="sxs-lookup"><span data-stu-id="f0004-137">Expression</span></span> | <span data-ttu-id="f0004-138">Resultado</span><span class="sxs-lookup"><span data-stu-id="f0004-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="f0004-139">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="f0004-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="f0004-140">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="f0004-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="f0004-141">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="f0004-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
