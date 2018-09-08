---
title: Like (operador, Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Like
- vb.Like
helpviewer_keywords:
- similar to
- pattern matching
- Like operator [Visual Basic]
- '? symbol, wildcard character'
- string comparison [Visual Basic], Like operator
- strings [Visual Basic], comparing
- comparison operators [Visual Basic]
- symbols, wildcard
- wildcards, Like operator
- strings [Visual Basic], matching
- string comparison [Visual Basic], sorting data
- data [Visual Basic], sorting
- text [Visual Basic], comparing
- operators [Visual Basic], pattern-matching
- data [Visual Basic], string comparisons
- string comparison [Visual Basic], Like operators
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
ms.openlocfilehash: c5b26bd1d3ebae5136718833c124e3c6e575e9b7
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44198171"
---
# <a name="like-operator-visual-basic"></a>Like (operador, Visual Basic)
Compara una cadena con un patrón.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
result = string Like pattern  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Requerido. Cualquier `Boolean` variable. El resultado es un `Boolean` valor que indica si el `string` satisface el `pattern`.  
  
 `string`  
 Requerido. Cualquier expresión `String`.  
  
 `pattern`  
 Requerido. Cualquier `String` expresión que cumpla las convenciones de coincidencia de patrones que se describe en la sección "comentarios".  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `string` ajusta al modelo incluido en `pattern`, `result` es `True`. Si la cadena no cumple el patrón, `result` es `False`. Si ambos `string` y `pattern` son cadenas vacías, el resultado es `True`.  
  
## <a name="comparison-method"></a>Método de comparación  
 El comportamiento de la `Like` operador depende el [instrucción Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md). El método de comparación de cadenas predeterminado para cada archivo de origen es `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Opciones de patrón  
 Coincidencia de patrones integrados proporciona una herramienta versátil para comparaciones de cadenas. Las características de coincidencia de patrones permiten hacer coincidir cada carácter de `string` con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres. La tabla siguiente muestran los caracteres permitidos en `pattern` y qué coinciden.  
  
|Caracteres en `pattern`|Coincidencias de `string`|  
|-----------------------------|-------------------------|  
|`?`|Cualquier carácter individual|  
|`*`|Cero o más caracteres|  
|`#`|Cualquier dígito (0 – 9)|  
|`[charlist]`|Cualquier carácter individual `charlist`|  
|`[!charlist]`|Cualquier carácter individual que no está en `charlist`|  
  
## <a name="character-lists"></a>Listas de caracteres  
 Un grupo de uno o varios caracteres (`charlist`) entre corchetes (`[ ]`) puede usarse para coincidir con cualquier carácter individual en `string` y puede incluir prácticamente cualquier código de carácter, incluidos los dígitos.  
  
 Un signo de exclamación (`!`) al principio de `charlist` significa que se realiza una coincidencia si cualquier carácter excepto los caracteres en `charlist` se encuentra en `string`. Cuando se utiliza fuera de los corchetes, el signo de exclamación coincide consigo mismo.  
  
## <a name="special-characters"></a>Caracteres especiales  
 Para que coincida con los caracteres especiales corchete izquierdo (`[`), signo de interrogación (`?`), signo de número (`#`) y el asterisco (`*`), incluya entre corchetes. El corchete derecho (`]`) no se puede usar dentro de un grupo para que coincida con sí mismo, pero se puede usar fuera de un grupo como un carácter individual.  
  
 La secuencia de caracteres `[]` se considera una cadena de longitud cero (`""`). Sin embargo, no puede formar parte de una lista de caracteres entre corchetes. Si desea comprobar si una posición en `string` contiene uno de un grupo de caracteres o ningún carácter en absoluto, puede usar `Like` dos veces. Para obtener un ejemplo, vea [Cómo: hacer coincidir una cadena con un patrón](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalos de caracteres  
 Con un guión (`–`) para separar los límites inferior y superior del intervalo, `charlist` puede especificar un intervalo de caracteres. Por ejemplo, `[A–Z]` da como resultado una coincidencia si el carácter correspondiente se coloque en `string` contiene cualquier carácter dentro del intervalo `A`–`Z`, y `[!H–L]` da como resultado una coincidencia si coloca el carácter correspondiente contiene cualquier carácter fuera del intervalo `H`–`L`.  
  
 Al especificar un intervalo de caracteres, deben aparecer en orden ascendente, es decir, de menor a mayor. Por lo tanto, `[A–Z]` es un patrón válido, pero `[Z–A]` no es.  
  
### <a name="multiple-character-ranges"></a>Varios intervalos de caracteres  
 Para especificar varios intervalos para la misma posición de carácter, coloque corchetes sin delimitadores. Por ejemplo, `[A–CX–Z]` da como resultado una coincidencia si el carácter correspondiente se coloque en `string` contiene cualquier carácter en el intervalo `A`–`C` o en el intervalo `X`–`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Uso del guión  
 Un guión (`–`) puede aparecer al principio (después de un punto de exclamación, si existe) o al final de `charlist` para que coincida con sí mismo. En cualquier otra ubicación, el guión identifica un intervalo de caracteres delimitados por los caracteres a ambos lados del guión.  
  
## <a name="collating-sequence"></a>Secuencia de intercalación  
 El significado de un intervalo especificado depende de la ordenación en tiempo de ejecución, determinado por el carácter de `Option Compare` y la configuración regional del sistema se está ejecutando el código. Con `Option Compare Binary`, el intervalo `[A–E]` coincide con `A`, `B`, `C`, `D`, y `E`. Con `Option Compare Text`, `[A–E]` coincide con `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`, y `e`. No coincide con el intervalo `Ê` o `ê` porque los caracteres acentuados se intercalan después caracteres no acentuadas en el criterio de ordenación.  
  
## <a name="digraph-characters"></a>Digrama caracteres adicionales.  
 En algunos idiomas, existen caracteres alfabéticos que representan dos caracteres separados. Por ejemplo, varios idiomas utilizan el carácter `æ` para representar los caracteres `a` y `e` cuando aparecen conjuntamente. El `Like` operador reconoce que el carácter dígrafo único y los dos caracteres individuales son equivalentes.  
  
 Cuando se especifica un idioma que utiliza un carácter dígrafo en la configuración regional del sistema, una aparición del carácter único dígrafo en cualquiera `pattern` o `string` coincide con la secuencia de dos caracteres equivalente en la otra cadena. De forma similar, un carácter dígrafo en `pattern` entre corchetes (por sí mismo, en una lista o en un intervalo) coincide con la secuencia de dos caracteres equivalente en `string`.  
  
## <a name="overloading"></a>Sobrecarga  
 El `Like` operador puede ser *sobrecargado*, lo que significa que una clase o estructura puede redefinir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de que conocer su comportamiento redefinido. Para obtener más información, consulte [procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `Like` operador para comparar cadenas en varios modelos. Entre los resultados en un `Boolean` que indica si cada cadena ajusta al modelo de variable.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/like-operator_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>  
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>  
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Comprobar si una cadena coincide con un modelo](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
