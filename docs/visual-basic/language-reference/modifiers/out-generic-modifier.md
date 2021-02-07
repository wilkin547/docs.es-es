---
description: 'Más información acerca de: out (modificador genérico) (Visual Basic)'
title: Modificador genérico Out
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: cdf80439fbae0d2411eecff1c7e8438534fcfdc1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730543"
---
# <a name="out-generic-modifier-visual-basic"></a>Out (Modificador genérico) (Visual Basic)

En el caso de los parámetros de tipo genérico, la `Out` palabra clave especifica que el tipo es covariante.

## <a name="remarks"></a>Observaciones

La covarianza le permite usar un tipo más derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.

Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Reglas

Puede usar la palabra clave `Out` en las interfaces y delegados genéricos.

En una interfaz genérica, un parámetro de tipo se puede declarar como covariante si cumple las siguientes condiciones:

- El parámetro de tipo se usa solamente como tipo de valor devuelto de los métodos de interfaz y no como tipo de los argumentos de método.

    > [!NOTE]
    > Hay una excepción para esta regla. Si en una interfaz covariante tiene un delegado genérico contravariante como parámetro de método, puede usar el tipo covariante como parámetro de tipo genérico para este delegado. Para obtener más información sobre los delegados genéricos covariantes y contravariantes, vea [Varianza en delegados](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) y [Usar la varianza para los delegados genéricos Func y Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).

- El parámetro de tipo no se usa como restricción genérica para los métodos de interfaz.

En un delegado genérico, un parámetro de tipo puede declararse como covariante si solo se usa como un tipo de valor devuelto de método y no se usa para los argumentos de método.

La covarianza y la contravarianza son compatibles con los tipos de referencia, pero no lo son con los tipos de valor.

En Visual Basic, no se pueden declarar eventos en interfaces covariantes sin especificar el tipo de delegado. Además, las interfaces covariantes no pueden tener clases, enumeraciones o estructuras anidadas, pero pueden tener interfaces anidadas.

## <a name="behavior"></a>Comportamiento

Una interfaz con un parámetro de tipo covariante permite que sus métodos devuelvan tipos más derivados que los especificados por el parámetro de tipo. Por ejemplo, dado que en .NET Framework 4, en <xref:System.Collections.Generic.IEnumerable%601>, el tipo T es covariante, puede asignar un objeto del tipo `IEnumerable(Of String)` a otro objeto del tipo `IEnumerable(Of Object)` sin usar ningún método de conversión especial.

A un delegado covariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico más derivado.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica covariante. También se muestra cómo usar la conversión implícita para las clases que implementan una interfaz covariante.

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo declarar, invocar y crear instancias de un delegado genérico covariante. También se muestra cómo puede usar la conversión implícita para los tipos de delegado.

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](in-generic-modifier.md)
