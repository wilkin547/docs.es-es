---
title: Valores devueltos de Referencia
ms.date: 04/28/2017
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
ms.openlocfilehash: f2a92c584dbb12a322e28435d797fa4d7c2f6dbb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186938"
---
# <a name="support-for-reference-return-values-visual-basic"></a>Compatibilidad con valores devueltos de referencia (Visual Basic)

Comenzando con c- 7.0, el lenguaje C- admite *valores devueltos*de referencia. Una manera de entender los valores devueltos de referencia es que son lo opuesto a los argumentos que se pasan por referencia a un método. Cuando se modifica un argumento pasado por referencia, los cambios se reflejan en el valor de la variable en el llamador. Cuando un método proporciona un valor devuelto de referencia a un llamador, las modificaciones realizadas en el valor devuelto de referencia por el llamador se reflejan en los datos del método llamado.

Visual Basic no permite crear métodos con valores devueltos de referencia, pero sí permite consumir valores devueltos de referencia. En otras palabras, puede llamar a un método con un valor devuelto de referencia y modificar ese valor devuelto, y los cambios en el valor devuelto de referencia se reflejan en los datos del método llamado.

## <a name="modifying-the-ref-return-value-directly"></a>Modificación directa del valor devuelto ref

Para los métodos que `ByRef` siempre se realizan correctamente y no tienen parámetros, puede modificar el valor devuelto de referencia directamente. Para ello, asigne el nuevo valor a las expresiones que devuelven el valor devuelto de referencia.

En el siguiente ejemplo `NumericValue.IncrementValue` de C- se define un método que incrementa un valor interno y lo devuelve como un valor devuelto de referencia.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

A continuación, el autor de la llamada modifica el valor devuelto de referencia en el siguiente ejemplo de Visual Basic. Tenga en cuenta `NumericValue.IncrementValue` que la línea con la llamada al método no asigna un valor al método. En su lugar, asigna un valor al valor devuelto de referencia devuelto por el método.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Uso de un método auxiliar

En otros casos, modificar el valor devuelto de referencia de una llamada al método directamente no siempre puede ser deseable. Por ejemplo, un método de búsqueda que devuelve una cadena puede no encontrar siempre una coincidencia. En ese caso, desea modificar el valor devuelto de referencia solo si la búsqueda se realiza correctamente.

En el siguiente ejemplo de C- se muestra este escenario. Define una `Sentence` clase escrita en `FindNext` C- incluye un método que busca la siguiente palabra en una oración que comienza con una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. El valor devuelto de referencia indica que, además de leer el valor devuelto, el llamador también `Sentence` puede modificarlo y que la modificación se refleja en los datos contenidos internamente en la clase.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Modificar directamente el valor devuelto de referencia en este caso no es confiable, ya que la llamada al método puede no encontrar una coincidencia y devolver la primera palabra de la oración. En ese caso, el autor de la llamada modificará inadvertidamente la primera palabra de la oración. Esto podría ser impedido por `null` el `Nothing` llamador que devuelve un (o en Visual Basic). Pero en ese caso, al intentar modificar `Nothing` una <xref:System.NullReferenceException>cadena cuyo valor es se produce un archivo . Si también podría ser impedido <xref:System.String.Empty?displayProperty=nameWithType>por el llamador que devuelve , pero <xref:System.String.Empty?displayProperty=nameWithType>esto requiere que el llamador defina una variable de cadena cuyo valor es . Aunque el autor de la llamada puede modificar esa cadena, la modificación en sí `Sentence` no sirve para nada, ya que la cadena modificada no tiene ninguna relación con las palabras de la oración almacenada por la clase.

La mejor manera de controlar este escenario es pasar el valor devuelto de referencia por referencia a un método auxiliar. A continuación, el método auxiliar contiene la lógica para determinar si la llamada al método se realizó correctamente y, si lo hizo, para modificar el valor devuelto de referencia. En el ejemplo siguiente se proporciona una posible implementación.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Consulte también

- [Pasar argumentos por valor y por referencia](passing-arguments-by-value-and-by-reference.md)
- [Procedimientos en Visual Basic](index.md)
