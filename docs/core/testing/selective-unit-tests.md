---
title: "Ejecución de pruebas unitarias selectivas"
description: "Muestra cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet."
keywords: .NET, .NET Core, prueba unitaria, prueba selectiva
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 13d01272-bbf8-456c-a97a-560001d1a7f2
ms.openlocfilehash: af832d04d2cba530a93710a90701ab119a66deef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="2a4b2-104">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="2a4b2-104">Running selective unit tests</span></span>

<span data-ttu-id="2a4b2-105">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-105">The following examples use `dotnet test`.</span></span> <span data-ttu-id="2a4b2-106">Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-106">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="2a4b2-107">MSTest</span><span class="sxs-lookup"><span data-stu-id="2a4b2-107">MSTest</span></span>

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

| <span data-ttu-id="2a4b2-108">Expresión</span><span class="sxs-lookup"><span data-stu-id="2a4b2-108">Expression</span></span> | <span data-ttu-id="2a4b2-109">Resultado</span><span class="sxs-lookup"><span data-stu-id="2a4b2-109">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="2a4b2-110">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-110">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="2a4b2-111">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-111">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="2a4b2-112">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-112">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="2a4b2-113">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-113">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="2a4b2-114">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTestClass1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-114">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="2a4b2-115">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-115">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="2a4b2-116">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-116">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="2a4b2-117">Ejecuta pruebas anotadas con `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-117">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="2a4b2-118">**Nota:** `Priority~3` es un valor no válido, ya que no es una cadena.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-118">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="2a4b2-119">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="2a4b2-119">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2a4b2-120">Expresión</span><span class="sxs-lookup"><span data-stu-id="2a4b2-120">Expression</span></span> | <span data-ttu-id="2a4b2-121">Resultado</span><span class="sxs-lookup"><span data-stu-id="2a4b2-121">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="2a4b2-122">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="2a4b2-123">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-123">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="2a4b2-124">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTestClass1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-124">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="2a4b2-125">xUnit</span><span class="sxs-lookup"><span data-stu-id="2a4b2-125">xUnit</span></span>

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

| <span data-ttu-id="2a4b2-126">Expresión</span><span class="sxs-lookup"><span data-stu-id="2a4b2-126">Expression</span></span> | <span data-ttu-id="2a4b2-127">Resultado</span><span class="sxs-lookup"><span data-stu-id="2a4b2-127">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2a4b2-128">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-128">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="2a4b2-129">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-129">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="2a4b2-130">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-130">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="2a4b2-131">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-131">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="2a4b2-132">Expresión</span><span class="sxs-lookup"><span data-stu-id="2a4b2-132">Expression</span></span> | <span data-ttu-id="2a4b2-133">Resultado</span><span class="sxs-lookup"><span data-stu-id="2a4b2-133">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="2a4b2-134">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-134">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="2a4b2-135">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-135">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="2a4b2-136">Ejecuta las pruebas que tienen `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-136">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="2a4b2-137">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="2a4b2-137">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="2a4b2-138">Expresión</span><span class="sxs-lookup"><span data-stu-id="2a4b2-138">Expression</span></span> | <span data-ttu-id="2a4b2-139">Resultado</span><span class="sxs-lookup"><span data-stu-id="2a4b2-139">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="2a4b2-140">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="2a4b2-141">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-141">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="2a4b2-142">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="2a4b2-142">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
