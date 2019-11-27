---
title: Like (Operador)
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
ms.openlocfilehash: 5db9488bbec716156a3ab464042c0853241a82b1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350943"
---
# <a name="like-operator-visual-basic"></a>Like (operador, Visual Basic)
Compara una cadena con un patrón.  

> [!IMPORTANT]
> El operador `Like` no se admite actualmente en los proyectos de .NET Core y .NET Standard.

## <a name="syntax"></a>Sintaxis  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>Elementos  
 `result`  
 Obligatorio. Cualquier variable de `Boolean`. El resultado es un valor `Boolean` que indica si el `string` satisface o no el `pattern`.  
  
 `string`  
 Obligatorio. Cualquier expresión `String` .  
  
 `pattern`  
 Obligatorio. Cualquier `String` expresión que se ajuste a las convenciones de coincidencia de patrones descritas en "Comentarios".  
  
## <a name="remarks"></a>Comentarios  
 Si el valor de `string` satisface el patrón incluido en `pattern`, se `True``result`. Si la cadena no satisface el modelo, `result` se `False`. Si tanto `string` como `pattern` son cadenas vacías, el resultado es `True`.  
  
## <a name="comparison-method"></a>Método de comparación  
 El comportamiento del operador `Like` depende de la [instrucción Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md). El método predeterminado de comparación de cadenas para cada archivo de código fuente es `Option Compare Binary`.  
  
## <a name="pattern-options"></a>Opciones de patrón  
 La coincidencia de patrones integrada proporciona una herramienta versátil para comparaciones de cadenas. Las características de coincidencia de patrones permiten hacer coincidir cada carácter de `string` con un carácter específico, un carácter comodín, una lista de caracteres o un intervalo de caracteres. En la tabla siguiente se muestran los caracteres permitidos en `pattern` y en qué coinciden.  
  
|Caracteres en `pattern`|Coincidencias en `string`|  
|-----------------------------|-------------------------|  
|`?`|Cualquier carácter individual|  
|`*`|Cero o más caracteres|  
|`#`|Cualquier dígito individual (0 – 9)|  
|`[charlist]`|Cualquier carácter individual de `charlist`|  
|`[!charlist]`|Cualquier carácter individual que no esté en `charlist`|  
  
## <a name="character-lists"></a>Listas de caracteres  
 Se puede usar un grupo de uno o varios caracteres (`charlist`) entre corchetes (`[ ]`) para buscar coincidencias con cualquier carácter individual de `string` y puede incluir prácticamente cualquier código de carácter, incluidos los dígitos.  
  
 Un signo de exclamación (`!`) al principio de `charlist` significa que se realiza una coincidencia si se encuentra algún carácter excepto los caracteres de `charlist` en `string`. Cuando se usa fuera de corchetes, el signo de exclamación coincide con sí mismo.  
  
## <a name="special-characters"></a>Caracteres especiales  
 Para hacer coincidir los caracteres especiales entre corchetes (`[`), signos de interrogación (`?`), signo de número (`#`) y asterisco (`*`), escríbalos entre corchetes. El corchete de cierre (`]`) no se puede usar dentro de un grupo para que coincida, pero se puede usar fuera de un grupo como un carácter individual.  
  
 La `[]` de la secuencia de caracteres se considera una cadena de longitud cero (`""`). Sin embargo, no puede formar parte de una lista de caracteres entre corchetes. Si desea comprobar si una posición en `string` contiene uno de un grupo de caracteres o ningún carácter, puede usar `Like` dos veces. Para obtener un ejemplo, vea [Cómo: buscar coincidencias de una cadena con un patrón](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalos de caracteres  
 Mediante el uso de un guión (`–`) para separar los límites inferior y superior del intervalo, `charlist` puede especificar un intervalo de caracteres. Por ejemplo, `[A–Z]` da como resultado una coincidencia si la posición de carácter correspondiente en `string` contiene cualquier carácter dentro del intervalo `A`–`Z`y `[!H–L]` da como resultado una coincidencia si la posición del carácter correspondiente contiene algún carácter situado fuera del intervalo `H`-`L`.  
  
 Cuando se especifica un intervalo de caracteres, deben aparecer en orden ascendente, es decir, de menor a mayor. Por lo tanto, `[A–Z]` es un patrón válido, pero `[Z–A]` no.  
  
### <a name="multiple-character-ranges"></a>Varios intervalos de caracteres  
 Para especificar varios intervalos para la misma posición de carácter, colóquelos dentro de los mismos corchetes sin delimitadores. Por ejemplo, `[A–CX–Z]` da como resultado una coincidencia si la posición de carácter correspondiente en `string` contiene cualquier carácter dentro del intervalo `A`–`C` o el intervalo `X`-`Z`.  
  
### <a name="usage-of-the-hyphen"></a>Uso del guión  
 Un guión (`–`) puede aparecer al principio (después de un signo de exclamación, si existe) o al final de `charlist` para que coincida. En cualquier otra ubicación, el guión identifica un intervalo de caracteres delimitado por los caracteres situados a cada lado del guión.  
  
## <a name="collating-sequence"></a>Secuencia de intercalación  
 El significado de un intervalo especificado depende del orden de los caracteres en tiempo de ejecución, según determine `Option Compare` y la configuración regional del sistema en el que se está ejecutando el código. Con `Option Compare Binary`, el intervalo `[A–E]` coincide con `A`, `B`, `C`, `D`y `E`. Con `Option Compare Text`, `[A–E]` coincide con `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E`y `e`. El intervalo no coincide con `Ê` o `ê` porque los caracteres acentuados se intercalan después de los caracteres no acentuados en el criterio de ordenación.  
  
## <a name="digraph-characters"></a>Caracteres de dígrafo  
 En algunos idiomas, hay caracteres alfabéticos que representan dos caracteres independientes. Por ejemplo, varios lenguajes usan el `æ` de caracteres para representar los caracteres `a` y `e` cuando aparecen juntos. El operador `Like` reconoce que el carácter de un solo gráfico y los dos caracteres individuales son equivalentes.  
  
 Cuando se especifica un idioma que usa un carácter de dígrafo en la configuración regional del sistema, una aparición del carácter de un solo gráfico en `pattern` o `string` coincide con la secuencia de dos caracteres equivalentes de la otra cadena. De forma similar, un carácter de dígrafo en `pattern` entre corchetes (por sí solo, en una lista o en un intervalo) coincide con la secuencia de dos caracteres equivalentes en `string`.  
  
## <a name="overloading"></a>Sobrecarga  
 El operador de `Like` se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el operador `Like` para comparar cadenas con varios patrones. Los resultados van a una variable `Boolean` que indica si cada cadena satisface el patrón.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Option Compare (instrucción)](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Comprobar si una cadena coincide con un modelo](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
