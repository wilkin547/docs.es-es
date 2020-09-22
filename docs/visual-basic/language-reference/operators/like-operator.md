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
ms.openlocfilehash: 49dfe5cf5dbcf8dc6f79f569a92e36aa81806913
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866780"
---
# <a name="like-operator-visual-basic"></a>Like (operador, Visual Basic)

Compara una cadena con un patrón.  

> [!IMPORTANT]
> El `Like` operador no se admite actualmente en los proyectos de .net Core y .net Standard.

## <a name="syntax"></a>Sintaxis  
  
```vb  
result = string Like pattern  
```  
  
## <a name="parts"></a>Partes  

 `result`  
 Obligatorio. Cualquier `Boolean` variable. El resultado es un `Boolean` valor que indica si el satisface o no `string` el `pattern` .  
  
 `string`  
 Obligatorio. Cualquier expresión `String` .  
  
 `pattern`  
 Obligatorio. Cualquier `String` expresión que se ajuste a las convenciones de coincidencia de patrones descritas en "Comentarios".  
  
## <a name="remarks"></a>Comentarios  

 Si el valor de `string` satisface el modelo contenido en `pattern` , `result` es `True` . Si la cadena no satisface el modelo, `result` es `False` . Si `string` y `pattern` son cadenas vacías, el resultado es `True` .  
  
## <a name="comparison-method"></a>Método de comparación  

 El comportamiento del `Like` operador depende de la [instrucción Option Compare](../statements/option-compare-statement.md). El método predeterminado de comparación de cadenas para cada archivo de código fuente es `Option Compare Binary` .  
  
## <a name="pattern-options"></a>Opciones de patrón  

 La coincidencia de patrones integrada proporciona una herramienta versátil para comparaciones de cadenas. Las características de coincidencia de patrones permiten buscar coincidencias con cada carácter de `string` un carácter específico, un carácter comodín, una lista de caracteres o un intervalo de caracteres. En la tabla siguiente se muestran los caracteres `pattern` que se permiten en y en qué coinciden.  
  
|Caracteres en `pattern`|Coincidencias en `string`|  
|-----------------------------|-------------------------|  
|`?`|Un carácter cualquiera|  
|`*`|Cero o más caracteres|  
|`#`|Cualquier dígito individual (0 – 9)|  
|`[charlist]`|Cualquier carácter individual de `charlist`|  
|`[!charlist]`|Cualquier carácter individual que no esté en `charlist`|  
  
## <a name="character-lists"></a>Listas de caracteres  

 Un grupo de uno o más caracteres ( `charlist` ) encerrado entre corchetes ( `[ ]` ) se puede usar para buscar coincidencias con cualquier carácter individual de `string` y puede incluir prácticamente cualquier código de carácter, incluidos los dígitos.  
  
 Un signo de exclamación ( `!` ) al principio de `charlist` significa que se realiza una coincidencia si se encuentra algún carácter excepto los caracteres de en `charlist` `string` . Cuando se usa fuera de corchetes, el signo de exclamación coincide con sí mismo.  
  
## <a name="special-characters"></a>Caracteres especiales  

 Para que coincida con los caracteres especiales, corchete de apertura ( `[` ), signo de interrogación ( `?` ), signo de número ( `#` ) y asterisco ( `*` ), escríbalos entre corchetes. El corchete de cierre ( `]` ) no se puede usar dentro de un grupo para que coincida, pero se puede usar fuera de un grupo como un carácter individual.  
  
 La secuencia de caracteres `[]` se considera una cadena de longitud cero ( `""` ). Sin embargo, no puede formar parte de una lista de caracteres entre corchetes. Si desea comprobar si una posición en `string` contiene uno de un grupo de caracteres o ningún carácter, puede usar `Like` dos veces. Para obtener un ejemplo, vea [Cómo: buscar coincidencias de una cadena con un patrón](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## <a name="character-ranges"></a>Intervalos de caracteres  

 Si usa un guión ( `–` ) para separar los límites inferior y superior del intervalo, `charlist` puede especificar un intervalo de caracteres. Por ejemplo, `[A–Z]` da como resultado una coincidencia si la posición del carácter correspondiente en `string` contiene cualquier carácter dentro del intervalo `A` – `Z` , y `[!H–L]` da como resultado una coincidencia si la posición del carácter correspondiente contiene algún carácter fuera del intervalo `H` : `L` .  
  
 Cuando se especifica un intervalo de caracteres, deben aparecer en orden ascendente, es decir, de menor a mayor. Por lo tanto, `[A–Z]` es un patrón válido, pero `[Z–A]` no lo es.  
  
### <a name="multiple-character-ranges"></a>Varios intervalos de caracteres  

 Para especificar varios intervalos para la misma posición de carácter, colóquelos dentro de los mismos corchetes sin delimitadores. Por ejemplo, `[A–CX–Z]` da como resultado una coincidencia si la posición del carácter correspondiente en `string` contiene cualquier carácter dentro del intervalo `A` , `C` o del `X` intervalo `Z` .  
  
### <a name="usage-of-the-hyphen"></a>Uso del guión  

 Un guion ( `–` ) puede aparecer al principio (después de un signo de exclamación, si existe) o al final de `charlist` para que coincida. En cualquier otra ubicación, el guión identifica un intervalo de caracteres delimitado por los caracteres situados a cada lado del guión.  
  
## <a name="collating-sequence"></a>Secuencia de intercalación  

 El significado de un intervalo especificado depende del orden de los caracteres en tiempo de ejecución, según determina `Option Compare` y la configuración regional del sistema en el que se ejecuta el código. Con `Option Compare Binary` , el intervalo `[A–E]` coincide con `A` ,, `B` `C` , `D` y `E` . Con, coincide con,,,,,,,,,, `Option Compare Text` `[A–E]` `A` `a` `À` `à` `B` `b` `C` `c` `D` `d` `E` y `e` . El intervalo no coincide `Ê` o `ê` porque los caracteres acentuados se intercalan después de los caracteres no acentuados en el criterio de ordenación.  
  
## <a name="digraph-characters"></a>Caracteres de dígrafo  

 En algunos idiomas, hay caracteres alfabéticos que representan dos caracteres independientes. Por ejemplo, varios lenguajes utilizan el carácter `æ` para representar los caracteres `a` y `e` cuando aparecen juntos. El `Like` operador reconoce que el carácter de un solo gráfico y los dos caracteres individuales son equivalentes.  
  
 Cuando se especifica un idioma que usa un carácter de dígrafo en la configuración regional del sistema, una aparición del carácter de un solo gráfico en `pattern` o `string` coincide con la secuencia de dos caracteres equivalentes de la otra cadena. Del mismo modo, un carácter de dígrafo `pattern` entre corchetes (por sí solo, en una lista o en un intervalo) coincide con la secuencia de dos caracteres equivalente en `string` .  
  
## <a name="overloading"></a>Sobrecarga  

 El `Like` operador se puede *sobrecargar*, lo que significa que una clase o estructura puede volver a definir su comportamiento cuando un operando tiene el tipo de esa clase o estructura. Si el código usa este operador en una clase o estructura de este tipo, asegúrese de entender su comportamiento redefinido. Para obtener más información, consulta [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa el `Like` operador para comparar cadenas con varios patrones. Los resultados se incluyen en una `Boolean` variable que indica si cada cadena satisface el modelo.  
  
 [!code-vb[VbVbalrOperators#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#30)]  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [Operadores de comparación](comparison-operators.md)
- [Prioridad de operador en Visual Basic](operator-precedence.md)
- [Lista de operadores según funcionalidad](operators-listed-by-functionality.md)
- [Option Compare (instrucción)](../statements/option-compare-statement.md)
- [Operadores y expresiones](../../programming-guide/language-features/operators-and-expressions/index.md)
- [Procedimiento para comprobar si una cadena coincide con un patrón](../../programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)
