---
title: Ejecución de pruebas unitarias selectivas
description: Muestra cómo usar una expresión de filtro para ejecutar pruebas unitarias selectivas con el comando de prueba de dotnet.
author: smadala
ms.author: mairaw
ms.date: 03/22/2017
ms.openlocfilehash: caea91e9884dba6bc07a7ef6a99699e43d23399c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33210839"
---
# <a name="running-selective-unit-tests"></a><span data-ttu-id="50389-103">Ejecución de pruebas unitarias selectivas</span><span class="sxs-lookup"><span data-stu-id="50389-103">Running selective unit tests</span></span>

<span data-ttu-id="50389-104">En los siguientes ejemplos, se utiliza `dotnet test`.</span><span class="sxs-lookup"><span data-stu-id="50389-104">The following examples use `dotnet test`.</span></span> <span data-ttu-id="50389-105">Si está usando `vstest.console.exe`, reemplace `--filter ` por `--testcasefilter:`.</span><span class="sxs-lookup"><span data-stu-id="50389-105">If you're using `vstest.console.exe`, replace `--filter ` with `--testcasefilter:`.</span></span>

## <a name="mstest"></a><span data-ttu-id="50389-106">MSTest</span><span class="sxs-lookup"><span data-stu-id="50389-106">MSTest</span></span>

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

| <span data-ttu-id="50389-107">Expresión</span><span class="sxs-lookup"><span data-stu-id="50389-107">Expression</span></span> | <span data-ttu-id="50389-108">Resultado</span><span class="sxs-lookup"><span data-stu-id="50389-108">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter Method` | <span data-ttu-id="50389-109">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `Method`.</span><span class="sxs-lookup"><span data-stu-id="50389-109">Runs tests whose `FullyQualifiedName` contains `Method`.</span></span> <span data-ttu-id="50389-110">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="50389-110">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Name~TestMethod1` | <span data-ttu-id="50389-111">Ejecuta pruebas cuyo nombre contenga `TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="50389-111">Runs tests whose name contains `TestMethod1`.</span></span> |
| `dotnet test --filter ClassName=MSTestNamespace.UnitTestClass1` | <span data-ttu-id="50389-112">Ejecuta pruebas que están en la clase `MSTestNamespace.UnitTestClass1`.</span><span class="sxs-lookup"><span data-stu-id="50389-112">Runs tests which are in class `MSTestNamespace.UnitTestClass1`.</span></span><br><span data-ttu-id="50389-113">**Nota:** El valor `ClassName` debe tener un espacio de nombres, por lo que `ClassName=UnitTestClass1` no funcionará.</span><span class="sxs-lookup"><span data-stu-id="50389-113">**Note:** The `ClassName` value should have a namespace, so `ClassName=UnitTestClass1` won't work.</span></span> |
| `dotnet test --filter FullyQualifiedName!=MSTestNamespace.UnitTestClass1.TestMethod1` | <span data-ttu-id="50389-114">Ejecuta todas las pruebas excepto `MSTestNamespace.UnitTestClass1.TestMethod1`.</span><span class="sxs-lookup"><span data-stu-id="50389-114">Runs all tests except `MSTestNamespace.UnitTestClass1.TestMethod1`.</span></span> |
| `dotnet test --filter TestCategory=CategoryA` | <span data-ttu-id="50389-115">Ejecuta pruebas anotadas con `[TestCategory("CategoryA")]`.</span><span class="sxs-lookup"><span data-stu-id="50389-115">Runs tests which are annotated with `[TestCategory("CategoryA")]`.</span></span> |
| `dotnet test --filter Priority=3` | <span data-ttu-id="50389-116">Ejecuta pruebas anotadas con `[Priority(3)]`.</span><span class="sxs-lookup"><span data-stu-id="50389-116">Runs tests which are annotated with `[Priority(3)]`.</span></span><br><span data-ttu-id="50389-117">**Nota:** `Priority~3` es un valor no válido, ya que no es una cadena.</span><span class="sxs-lookup"><span data-stu-id="50389-117">**Note:** `Priority~3` is an invalid value, as it isn't a string.</span></span> |

<span data-ttu-id="50389-118">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="50389-118">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="50389-119">Expresión</span><span class="sxs-lookup"><span data-stu-id="50389-119">Expression</span></span> | <span data-ttu-id="50389-120">Resultado</span><span class="sxs-lookup"><span data-stu-id="50389-120">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~UnitTestClass1&#124;TestCategory=CategoryA"</code> | <span data-ttu-id="50389-121">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **o** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="50389-121">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **or** `TestCategory` is `CategoryA`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA"` | <span data-ttu-id="50389-122">Ejecuta pruebas que tienen `UnitTestClass1` en `FullyQualifiedName` **y** en las que `TestCategory` es `CategoryA`.</span><span class="sxs-lookup"><span data-stu-id="50389-122">Runs tests which have `UnitTestClass1` in `FullyQualifiedName` **and** `TestCategory` is `CategoryA`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~UnitTestClass1&TestCategory=CategoryA)&#124;Priority=1"</code> | <span data-ttu-id="50389-123">Ejecuta pruebas que tienen `FullyQualifiedName` con `UnitTestClass1` **y** en las que `TestCategory` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="50389-123">Runs tests which have either `FullyQualifiedName` containing `UnitTestClass1` **and** `TestCategory` is `CategoryA` **or** `Priority` is 1.</span></span> |

## <a name="xunit"></a><span data-ttu-id="50389-124">xUnit</span><span class="sxs-lookup"><span data-stu-id="50389-124">xUnit</span></span>

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

| <span data-ttu-id="50389-125">Expresión</span><span class="sxs-lookup"><span data-stu-id="50389-125">Expression</span></span> | <span data-ttu-id="50389-126">Resultado</span><span class="sxs-lookup"><span data-stu-id="50389-126">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter DisplayName=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="50389-127">Ejecuta solo una prueba, `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="50389-127">Runs only one test, `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter FullyQualifiedName!=XUnitNamespace.TestClass1.Test1` | <span data-ttu-id="50389-128">Ejecuta todas las pruebas excepto `XUnitNamespace.TestClass1.Test1`.</span><span class="sxs-lookup"><span data-stu-id="50389-128">Runs all tests except `XUnitNamespace.TestClass1.Test1`.</span></span> |
| `dotnet test --filter DisplayName~TestClass1` | <span data-ttu-id="50389-129">Ejecuta pruebas cuyo nombre para mostrar contenga `TestClass1`.</span><span class="sxs-lookup"><span data-stu-id="50389-129">Runs tests whose display name contains `TestClass1`.</span></span> |

<span data-ttu-id="50389-130">En el ejemplo de código, los rasgos definidos con claves `Category` y `Priority` pueden usarse para filtrar.</span><span class="sxs-lookup"><span data-stu-id="50389-130">In the code example, the defined traits with keys `Category` and `Priority` can be used for filtering.</span></span>

| <span data-ttu-id="50389-131">Expresión</span><span class="sxs-lookup"><span data-stu-id="50389-131">Expression</span></span> | <span data-ttu-id="50389-132">Resultado</span><span class="sxs-lookup"><span data-stu-id="50389-132">Result</span></span> |
| ---------- | ------ |
| `dotnet test --filter XUnit` | <span data-ttu-id="50389-133">Ejecuta pruebas cuyo `FullyQualifiedName` contenga `XUnit`.</span><span class="sxs-lookup"><span data-stu-id="50389-133">Runs tests whose `FullyQualifiedName` contains `XUnit`.</span></span>  <span data-ttu-id="50389-134">Disponible en `vstest 15.1+`.</span><span class="sxs-lookup"><span data-stu-id="50389-134">Available in `vstest 15.1+`.</span></span> |
| `dotnet test --filter Category=bvt` | <span data-ttu-id="50389-135">Ejecuta las pruebas que tienen `[Trait("Category", "bvt")]`.</span><span class="sxs-lookup"><span data-stu-id="50389-135">Runs tests which have `[Trait("Category", "bvt")]`.</span></span> |

<span data-ttu-id="50389-136">**Usar operadores condicionales | y &amp;**</span><span class="sxs-lookup"><span data-stu-id="50389-136">**Using conditional operators | and &amp;**</span></span>

| <span data-ttu-id="50389-137">Expresión</span><span class="sxs-lookup"><span data-stu-id="50389-137">Expression</span></span> | <span data-ttu-id="50389-138">Resultado</span><span class="sxs-lookup"><span data-stu-id="50389-138">Result</span></span> |
| ---------- | ------ |
| <code>dotnet test --filter "FullyQualifiedName~TestClass1&#124;Category=Nightly"</code> | <span data-ttu-id="50389-139">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **o** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="50389-139">Runs tests which has `TestClass1` in `FullyQualifiedName` **or** `Category` is `Nightly`.</span></span> |
| `dotnet test --filter "FullyQualifiedName~TestClass1&Category=Nightly"` | <span data-ttu-id="50389-140">Ejecuta pruebas que tienen `TestClass1` en `FullyQualifiedName` **y** en las que `Category` es `Nightly`.</span><span class="sxs-lookup"><span data-stu-id="50389-140">Runs tests which has `TestClass1` in `FullyQualifiedName` **and** `Category` is `Nightly`.</span></span> |
| <code>dotnet test --filter "(FullyQualifiedName~TestClass1&Category=Nightly)&#124;Priority=1"</code> | <span data-ttu-id="50389-141">Ejecuta pruebas que tienen `FullyQualifiedName` con `TestClass1` **y** en las que `Category` es `CategoryA` **o** en las que `Priority` es 1.</span><span class="sxs-lookup"><span data-stu-id="50389-141">Runs tests which have either `FullyQualifiedName` containing `TestClass1` **and** `Category` is `CategoryA` **or** `Priority` is 1.</span></span> |
