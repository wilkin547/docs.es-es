---
title: In (modificador genérico)-Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceIn
helpviewer_keywords:
- contravariance, In keyword [Visual Basic]
- In keyword [Visual Basic]
ms.assetid: 59bb13c5-fe96-42b8-8286-86293d1661c5
ms.openlocfilehash: 9c0f7d454767112e1e309af81407b5fdef22eee9
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004872"
---
# <a name="in-generic-modifier-visual-basic"></a>In (Modificador genérico) (Visual Basic)

Para los parámetros de tipo genérico, la palabra clave `In` especifica que el parámetro de tipo es contravariante.

## <a name="remarks"></a>Comentarios

La contravarianza permite usar un tipo menos derivado que el que se especifica en el parámetro genérico. Esto permite la conversión implícita de las clases que implementan interfaces variantes y la conversión implícita de los tipos de delegado.

Para obtener más información, vea [Covarianza y contravarianza](../../programming-guide/concepts/covariance-contravariance/index.md).

## <a name="rules"></a>Reglas

Puede usar la palabra clave `In` en las interfaces y delegados genéricos.
  
Un parámetro de tipo puede declararse como contravariante en una interfaz o un delegado genérico si solo se usa como un tipo de argumentos de método y no se usa como tipo de valor devuelto de método. los parámetros `ByRef` no pueden ser covariantes o contravariante.

La covarianza y la contravarianza se admiten para los tipos de referencia y no se admiten para los tipos de valor.

En Visual Basic, no se pueden declarar eventos en interfaces contravariantes sin especificar el tipo de delegado. Además, las interfaces contravariantes no pueden tener clases anidadas, enumeraciones o estructuras, pero pueden tener interfaces anidadas.

## <a name="behavior"></a>Comportamiento

Una interfaz que tiene un parámetro de tipo contravariante permite que sus métodos acepten argumentos de tipos menos derivados que los que se especifican en el parámetro de tipo de interfaz. Por ejemplo, dado que en .NET Framework 4, en la interfaz <xref:System.Collections.Generic.IComparer%601>, el tipo T es contravariante, puede asignar un objeto del tipo `IComparer(Of Person)` a un objeto del tipo `IComparer(Of Employee)` sin usar ningún método de conversión especial si `Employee` hereda de `Person`.

A un delegado contravariante se le puede asignar otro delegado del mismo tipo, pero con un parámetro de tipo genérico menos derivado.

## <a name="example---contravariant-generic-interface"></a>Ejemplo: interfaz genérica contravariante

En el ejemplo siguiente se muestra cómo declarar, extender e implementar una interfaz genérica contravariante. También se muestra cómo puede usar la conversión implícita para las clases que implementan esta interfaz.

[!code-vb[vbVarianceKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#1)]

## <a name="example---contravariant-generic-delegate"></a>Ejemplo: delegado genérico contravariante

En el ejemplo siguiente se muestra cómo declarar e invocar un delegado genérico contravariante, y crear instancias de este. También se muestra cómo puede convertir implícitamente un tipo de delegado.

[!code-vb[vbVarianceKeywords#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#2)]

## <a name="see-also"></a>Vea también

- [Varianza en interfaces genéricas](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Out](out-generic-modifier.md)
