---
title: Ordenación de pruebas unitarias
description: Obtenga información sobre cómo ordenar pruebas unitarias con .NET Core.
author: IEvangelist
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: ce0d01c924075ffcc9ad49ef8aca49222c10c921
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83704536"
---
# <a name="order-unit-tests"></a><span data-ttu-id="15186-103">Ordenación de pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="15186-103">Order unit tests</span></span>

<span data-ttu-id="15186-104">En ocasiones, puede que desee que las pruebas unitarias se ejecuten en un orden específico.</span><span class="sxs-lookup"><span data-stu-id="15186-104">Occasionally, you may want to have unit tests run in a specific order.</span></span> <span data-ttu-id="15186-105">Idealmente, el orden en que se ejecutan las pruebas unitarias _no_ importa, y el [procedimiento recomendado](unit-testing-best-practices.md) es evitar la ordenación de las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="15186-105">Ideally, the order in which unit tests run should _not_ matter, and it is [best practice](unit-testing-best-practices.md) to avoid ordering unit tests.</span></span> <span data-ttu-id="15186-106">En cualquier caso, puede que sea necesario hacerlo.</span><span class="sxs-lookup"><span data-stu-id="15186-106">Regardless, there may be a need to do so.</span></span> <span data-ttu-id="15186-107">En ese caso, en este artículo se muestra cómo ordenar las series de pruebas.</span><span class="sxs-lookup"><span data-stu-id="15186-107">In that case, this article demonstrates how to order test runs.</span></span>

<span data-ttu-id="15186-108">Si prefiere examinar el código fuente, consulte el repositorio de ejemplo de [ordenación de pruebas unitarias de .NET Core](/samples/dotnet/samples/order-unit-tests-cs).</span><span class="sxs-lookup"><span data-stu-id="15186-108">If you prefer to browse the source code, see the [order .NET Core unit tests](/samples/dotnet/samples/order-unit-tests-cs) sample repository.</span></span>

> [!TIP]
> <span data-ttu-id="15186-109">Además de las funcionalidades de ordenación descritas en este artículo, considere la posibilidad de [crear listas de reproducción personalizadas con Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) como alternativa.</span><span class="sxs-lookup"><span data-stu-id="15186-109">In addition to the ordering capabilities outlined in this article, consider [creating custom playlists with Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) as an alternative.</span></span>

:::zone pivot="mstest"

## <a name="order-alphabetically"></a><span data-ttu-id="15186-110">Orden alfabético</span><span class="sxs-lookup"><span data-stu-id="15186-110">Order alphabetically</span></span>

<span data-ttu-id="15186-111">Con MSTest, las pruebas se ordenan automáticamente por su nombre de prueba.</span><span class="sxs-lookup"><span data-stu-id="15186-111">With MSTest, tests are automatically ordered by their test name.</span></span>

> [!NOTE]
> <span data-ttu-id="15186-112">Una prueba denominada `Test14` se ejecutará antes de `Test2` aunque el número `2` sea inferior a `14`.</span><span class="sxs-lookup"><span data-stu-id="15186-112">A test named `Test14` will run before `Test2` even though the number  `2` is less than `14`.</span></span> <span data-ttu-id="15186-113">Esto se debe a que la ordenación de los nombres de las pruebas utiliza el nombre de texto de la prueba.</span><span class="sxs-lookup"><span data-stu-id="15186-113">This is because, test name ordering uses the text name of the test.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

<span data-ttu-id="15186-114">El marco de pruebas de xUnit permite más nivel de detalle y control del orden de la serie de pruebas.</span><span class="sxs-lookup"><span data-stu-id="15186-114">The xUnit test framework allows for more granularity and control of test run order.</span></span> <span data-ttu-id="15186-115">Implemente las interfaces `ITestCaseOrderer` y `ITestCollectionOrderer` para controlar el orden de los casos de prueba de una clase o colecciones de prueba.</span><span class="sxs-lookup"><span data-stu-id="15186-115">You implement the `ITestCaseOrderer` and `ITestCollectionOrderer` interfaces to control the order of test cases for a class, or test collections.</span></span>

## <a name="order-by-test-case-alphabetically"></a><span data-ttu-id="15186-116">Orden alfabético por caso de prueba</span><span class="sxs-lookup"><span data-stu-id="15186-116">Order by test case alphabetically</span></span>

<span data-ttu-id="15186-117">Para ordenar los casos de prueba por su nombre de método, implemente `ITestCaseOrderer` y proporcione un mecanismo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="15186-117">To order test cases by their method name, you implement the `ITestCaseOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

<span data-ttu-id="15186-118">Después, en una clase de prueba, establezca el orden de los casos de prueba con `TestCaseOrdererAttribute`.</span><span class="sxs-lookup"><span data-stu-id="15186-118">Then in a test class you set the test case order with the `TestCaseOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a><span data-ttu-id="15186-119">Orden alfabético de la colección</span><span class="sxs-lookup"><span data-stu-id="15186-119">Order by collection alphabetically</span></span>

<span data-ttu-id="15186-120">Para ordenar las colecciones de pruebas por su nombre para mostrar, implemente `ITestCollectionOrderer` y proporcione un mecanismo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="15186-120">To order test collections by their display name, you implement the `ITestCollectionOrderer` and provide an ordering mechanism.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

<span data-ttu-id="15186-121">Como las colecciones de pruebas se ejecutan en paralelo, debe deshabilitar explícitamente la ejecución de pruebas en paralelo de las colecciones con `CollectionBehaviorAttribute`.</span><span class="sxs-lookup"><span data-stu-id="15186-121">Since test collections potentially run in parallel, you must explicitly disable test parallelization of the collections with the `CollectionBehaviorAttribute`.</span></span> <span data-ttu-id="15186-122">A continuación, especifique la implementación en `TestCollectionOrdererAttribute`.</span><span class="sxs-lookup"><span data-stu-id="15186-122">Then specify the implementation to the `TestCollectionOrdererAttribute`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a><span data-ttu-id="15186-123">Orden por atributo personalizado</span><span class="sxs-lookup"><span data-stu-id="15186-123">Order by custom attribute</span></span>

<span data-ttu-id="15186-124">Para ordenar las pruebas de xUnit con atributos personalizados, primero necesita un atributo en el que confiar.</span><span class="sxs-lookup"><span data-stu-id="15186-124">To order xUnit tests with custom attributes, you first need an attribute to rely on.</span></span> <span data-ttu-id="15186-125">Defina `TestPriorityAttribute` como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="15186-125">Define a `TestPriorityAttribute` as follows:</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

<span data-ttu-id="15186-126">A continuación, tenga en cuenta la siguiente implementación `PriorityOrderer` de la interfaz de `ITestCaseOrderer`.</span><span class="sxs-lookup"><span data-stu-id="15186-126">Next, consider the following `PriorityOrderer` implementation of the `ITestCaseOrderer` interface.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

<span data-ttu-id="15186-127">Después, en una clase de prueba, establezca el orden de los casos de prueba con `TestCaseOrdererAttribute` en `PriorityOrderer`.</span><span class="sxs-lookup"><span data-stu-id="15186-127">Then in a test class you set the test case order with the `TestCaseOrdererAttribute` to the `PriorityOrderer`.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a><span data-ttu-id="15186-128">Orden por prioridad</span><span class="sxs-lookup"><span data-stu-id="15186-128">Order by priority</span></span>

<span data-ttu-id="15186-129">Para ordenar las pruebas de forma explícita, NUnit proporciona [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute).</span><span class="sxs-lookup"><span data-stu-id="15186-129">To order tests explicitly, NUnit provides an [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute).</span></span> <span data-ttu-id="15186-130">Las pruebas con este atributo se inician antes que las pruebas sin él.</span><span class="sxs-lookup"><span data-stu-id="15186-130">Tests with this attribute are started before tests without.</span></span> <span data-ttu-id="15186-131">El valor de orden se usa para determinar el orden de ejecución de las pruebas unitarias.</span><span class="sxs-lookup"><span data-stu-id="15186-131">The order value is used to determined the order to run the unit tests.</span></span>

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a><span data-ttu-id="15186-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="15186-132">Next Steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="15186-133">Procedimientos recomendados para las pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="15186-133">Unit testing best practices</span></span>](unit-testing-best-practices.md)
