---
title: Valores devueltos ref (Visual Basic)
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: d0600f7d9030324160343e800c37e0f5e68bff61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133983"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Compatibilidad con los valores devueltos de referencia (Visual Basic)

A partir de C# 7.0, el C# lenguaje admite *hacen referencia a los valores devueltos*. Una manera de comprender los valores devueltos de referencia es que son lo opuesto de argumentos que se pasan por referencia a un método. Cuando se modifica un argumento pasado por referencia, los cambios se reflejan en el valor de la variable en el llamador. Cuando un método proporciona un valor devuelto de referencia a un llamador, las modificaciones realizadas en el valor devuelto de referencia por el llamador se reflejan en los datos de un método llamado.

Visual Basic no permite a los métodos de autor con referencia devuelve valores, pero le permite utilizar valores devueltos de referencia. En otras palabras, puede llamar a un método con un valor devuelto de referencia y modificar ese valor devuelto y los cambios realizados en el valor devuelto de referencia se reflejan en los datos de un método llamado.

## <a name="modifying-the-ref-return-value-directly"></a>Modificar directamente el valor devuelto de referencia

Para los métodos que siempre se ejecuta correctamente y no tienen ningún `ByRef` parámetros, se puede modificar directamente el valor devuelto de referencia. Para ello, asigne el valor nuevo a las expresiones que devuelve el valor devuelto de referencia. 

La siguiente C# ejemplo define un `NumericValue.IncrementValue` método que incrementa un valor interno y lo devuelve como una referencia de valor devuelto. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

La referencia de devolver al llamador en el siguiente ejemplo de Visual Basic, a continuación, modifica el valor. Tenga en cuenta que la línea con el `NumericValue.IncrementValue` llamada al método no asigna un valor al método. En su lugar, asigna un valor para el valor devuelto de referencia devuelto por el método.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Mediante un método auxiliar

En otros casos, modificar directamente el valor devuelto de referencia de una llamada al método es posible que no siempre sea deseable. Por ejemplo, un método de búsqueda que devuelve una cadena no puede encontrar siempre una coincidencia. En ese caso, va a modificar el valor devuelto de referencia sólo si la búsqueda se realiza correctamente.

La siguiente C# en el ejemplo se muestra este escenario. Define un `Sentence` clase escrita en C# incluye un `FindNext` método que busca la siguiente palabra en una frase que comienza con una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. El valor devuelto de referencia indica que el llamador no solo puede leer el valor devuelto; él o ella también puede modificar, y esa modificación se refleja en los datos contenidos en internamente el `Sentence` clase.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Modificando directamente la referencia de valor devuelto en este caso no es confiable, puesto que puede producir un error de la llamada al método buscar una coincidencia y devolver la primera palabra en la frase. En ese caso, el llamador accidentalmente modificará la primera palabra de la oración. Esto se podría evitar el llamador devolver un `null` (o `Nothing` en Visual Basic). Pero en ese caso, se intenta modificar una cadena cuyo valor es `Nothing` produce una <xref:System.NullReferenceException>. Si también se podría evitar el llamador devolver <xref:System.String.Empty?displayProperty=nameWithType>, pero esto requiere que el llamador definir una variable de cadena cuyo valor es <xref:System.String.Empty?displayProperty=nameWithType>. Mientras que el llamador puede modificar esa cadena, la modificación en sí no tiene ninguna finalidad, puesto que la cadena modificada tiene ninguna relación con las palabras de la oración almacenada por la `Sentence` clase.

La mejor manera de controlar este escenario es pasar el valor devuelto de referencia por referencia a un método auxiliar. El método auxiliar, a continuación, contiene la lógica para determinar si la llamada al método se realizó correctamente y, si lo hiciera, para modificar el valor devuelto de referencia. El ejemplo siguiente proporciona una implementación posible.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vea también

- [Pasar argumentos por valor y por referencia](passing-arguments-by-value-and-by-reference.md)
- [Procedimientos en Visual Basic](index.md)
