---
title: Valores devueltos de ref (Visual Basic)
ms.custom: ''
ms.date: 04/28/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic]
- ref return values [Visual Basic]
- ref returns [Visual Basic]
ms.assetid: 5ef0cc69-eb3a-4a67-92a2-78585f223cb5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6055028ac92016cbc4b6f7bffa7f483e5ea76608
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="support-for-reference-return-values-visual-basic"></a>Soporte técnico para los valores devueltos de referencia (Visual Basic)

A partir de C# 7.0, el lenguaje C# admite *hacen referencia a valores devueltos*. Una manera de comprender los valores devueltos de referencia es que son el opuesto de argumentos que se pasan por referencia a un método. Cuando se modifica un argumento que se pasa por referencia, los cambios se reflejan en el valor de la variable en el llamador. Cuando un método proporciona un valor devuelto de referencia a un llamador, las modificaciones realizadas en el valor devuelto de referencia por el llamador se reflejan en los datos del método llamado.

Visual Basic no permite que a los métodos de autor con referencia de valores devueltos, pero permite utilizar los valores devueltos de referencia. En otras palabras, puede llamar a un método con un valor devuelto de referencia y modificar ese valor devuelto, y los cambios en el valor devuelto de referencia se reflejan en los datos del método llamado.

## <a name="modifying-the-ref-return-value-directly"></a>Modificar directamente el valor devuelto de referencia

Para los métodos que se realizará correctamente siempre y no tienen ningún `ByRef` parámetros, se puede modificar directamente el valor devuelto de referencia. Para ello, asignando el nuevo valor a las expresiones que devuelve el valor devuelto de referencia. 

En el ejemplo de C# siguiente se define un `NumericValue.IncrementValue` método que incrementa un valor interno y lo devuelve como una referencia de valor devuelto. 

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/ref-returns1.cs)]

La referencia se devuelve, a continuación, se modifica el valor por el llamador en el siguiente ejemplo de Visual Basic. Tenga en cuenta que la línea que contiene el `NumericValue.IncrementValue` llamada al método no asigna un valor al método. En su lugar, asigna un valor para el valor devuelto de referencia devuelto por el método.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/procedures/use-ref-returns1.vb)]

## <a name="using-a-helper-method"></a>Mediante un método auxiliar

En otros casos, modificar directamente el valor devuelto de referencia de una llamada al método puede no siempre sea deseable. Por ejemplo, un método de búsqueda que devuelve una cadena no puede encontrar siempre una coincidencia. En ese caso, desea modificar el valor devuelto de referencia sólo si la búsqueda se realiza correctamente.

En el ejemplo de C# siguiente se muestra este escenario. Define un `Sentence` clase escrita en C# incluye un `FindNext` método que busca la siguiente palabra en una frase que comienza con una subcadena especificada. La cadena se devuelve como un valor devuelto de referencia, y una variable `Boolean` que se ha pasado mediante referencia al método indica si la búsqueda se ha realizado correctamente. El valor devuelto de referencia indica que el llamador no solo puede leer el valor devuelto; que también puede modificar y dicha modificación se refleja en los datos contenidos internamente en la `Sentence` clase.

[!code-csharp[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-returns.cs)]

Modificar directamente la referencia de valor devuelto en este caso no es confiable, ya que puede producir un error de la llamada al método buscar una coincidencia y devolver la primera palabra en la frase. En ese caso, el llamador accidentalmente modificará la primera palabra de la frase. Esto podría evitarse por el llamador devolver un `null` (o `Nothing` en Visual Basic). Pero en ese caso, al intentar modificar una cadena cuyo valor es `Nothing` produce una <xref:System.NullReferenceException>. Si también podría evitarse por el llamador devolver <xref:System.String.Empty?displayProperty=nameWithType>, pero esto requiere que el llamador definir una variable de cadena cuyo valor es <xref:System.String.Empty?displayProperty=nameWithType>. Mientras que el llamador puede modificar esa cadena, la modificación de sí mismo no tiene ninguna finalidad, ya que la cadena modificada no tiene ninguna relación con las palabras de la frase almacenada por la `Sentence` clase.

La mejor manera de controlar este escenario es pasar el valor devuelto de referencia por referencia a un método auxiliar. El método auxiliar, a continuación, contiene la lógica para determinar si la llamada al método se realizó correctamente y, si lo hiciera, para modificar la referencia de valor devuelto. En el ejemplo siguiente se proporciona una implementación posible.

[!code-vb[Ref-Return](../../../../../samples/snippets/visualbasic/getting-started/ref-return-helper.vb#1)]

## <a name="see-also"></a>Vea también

[Pasar argumentos por valor y por referencia](passing-arguments-by-value-and-by-reference.md)   
[Procedimientos en Visual Basic](index.md)   


