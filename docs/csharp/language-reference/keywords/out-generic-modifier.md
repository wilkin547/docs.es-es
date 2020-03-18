---
title: 'Palabra clave out (modificador genérico): Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, out keyword [C#]
- out keyword [C#]
ms.assetid: f8c20dec-a8bc-426a-9882-4076b1db1e00
ms.openlocfilehash: 97ddae2efe55be89840f7a483c18d61259020283
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713286"
---
# <a name="out-generic-modifier-c-reference"></a>out (Modificador genérico) (Referencia de C#)

Para los parámetros de tipo genérico, la palabra clave `out` especifica que el parámetro de tipo es covariante. Puede usar la palabra clave `out` en las interfaces y delegados genéricos.

La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces covariantes y la conversión implícita de los tipos de delegado. La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.

Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo. Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerable(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.

A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.

Para obtener más información, vea [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md) (Covarianza y contravarianza).

## <a name="example---covariant-generic-interface"></a>Ejemplo: interfaz genérica covariante

En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante. También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.

[!code-csharp[csVarianceKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#3)]

En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:

- El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.

    > [!NOTE]
    > Hay una excepción para esta regla. Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado. Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.

## <a name="example---covariant-generic-delegate"></a>Ejemplo: delegado genérico covariante

En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante. También se muestra cómo convertir implícitamente los tipos de delegado.

[!code-csharp[csVarianceKeywords#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csvariancekeywords/cs/program.cs#4)]

En un delegado genérico, un tipo se puede declarar como covariante si se usa solamente como tipo de valor devuelto por un método y no se usa para los argumentos de método.

## <a name="c-language-specification"></a>especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [in](in-generic-modifier.md)
- [Modificadores](index.md)
