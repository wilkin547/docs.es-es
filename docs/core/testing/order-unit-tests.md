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
# <a name="order-unit-tests"></a>Ordenación de pruebas unitarias

En ocasiones, puede que desee que las pruebas unitarias se ejecuten en un orden específico. Idealmente, el orden en que se ejecutan las pruebas unitarias _no_ importa, y el [procedimiento recomendado](unit-testing-best-practices.md) es evitar la ordenación de las pruebas unitarias. En cualquier caso, puede que sea necesario hacerlo. En ese caso, en este artículo se muestra cómo ordenar las series de pruebas.

Si prefiere examinar el código fuente, consulte el repositorio de ejemplo de [ordenación de pruebas unitarias de .NET Core](/samples/dotnet/samples/order-unit-tests-cs).

> [!TIP]
> Además de las funcionalidades de ordenación descritas en este artículo, considere la posibilidad de [crear listas de reproducción personalizadas con Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists) como alternativa.

:::zone pivot="mstest"

## <a name="order-alphabetically"></a>Orden alfabético

Con MSTest, las pruebas se ordenan automáticamente por su nombre de prueba.

> [!NOTE]
> Una prueba denominada `Test14` se ejecutará antes de `Test2` aunque el número `2` sea inferior a `14`. Esto se debe a que la ordenación de los nombres de las pruebas utiliza el nombre de texto de la prueba.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

El marco de pruebas de xUnit permite más nivel de detalle y control del orden de la serie de pruebas. Implemente las interfaces `ITestCaseOrderer` y `ITestCollectionOrderer` para controlar el orden de los casos de prueba de una clase o colecciones de prueba.

## <a name="order-by-test-case-alphabetically"></a>Orden alfabético por caso de prueba

Para ordenar los casos de prueba por su nombre de método, implemente `ITestCaseOrderer` y proporcione un mecanismo de ordenación.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

Después, en una clase de prueba, establezca el orden de los casos de prueba con `TestCaseOrdererAttribute`.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a>Orden alfabético de la colección

Para ordenar las colecciones de pruebas por su nombre para mostrar, implemente `ITestCollectionOrderer` y proporcione un mecanismo de ordenación.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

Como las colecciones de pruebas se ejecutan en paralelo, debe deshabilitar explícitamente la ejecución de pruebas en paralelo de las colecciones con `CollectionBehaviorAttribute`. A continuación, especifique la implementación en `TestCollectionOrdererAttribute`.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a>Orden por atributo personalizado

Para ordenar las pruebas de xUnit con atributos personalizados, primero necesita un atributo en el que confiar. Defina `TestPriorityAttribute` como se indica a continuación:

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

A continuación, tenga en cuenta la siguiente implementación `PriorityOrderer` de la interfaz de `ITestCaseOrderer`.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

Después, en una clase de prueba, establezca el orden de los casos de prueba con `TestCaseOrdererAttribute` en `PriorityOrderer`.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a>Orden por prioridad

Para ordenar las pruebas de forma explícita, NUnit proporciona [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute). Las pruebas con este atributo se inician antes que las pruebas sin él. El valor de orden se usa para determinar el orden de ejecución de las pruebas unitarias.

:::code language="csharp" source="~/dotnet-samples/csharp/unit-testing/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Procedimientos recomendados para las pruebas unitarias](unit-testing-best-practices.md)
