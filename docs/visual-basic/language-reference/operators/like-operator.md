---
title: "Like (operador, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Like"
  - "vb.Like"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "? símbolo, carácter comodín"
  - "operadores de comparación"
  - "datos [Visual Basic], ordenar"
  - "datos [Visual Basic], comparaciones de cadenas"
  - "Like (operador) [Visual Basic]"
  - "operadores [Visual Basic], coincidencia de patrones"
  - "coincidencia de patrones"
  - "similar a"
  - "comparación de cadenas [Visual Basic], Like (operador)"
  - "comparación de cadenas [Visual Basic], Like (operadores)"
  - "comparación de cadenas [Visual Basic], ordenar datos"
  - "cadenas [Visual Basic], comparar"
  - "cadenas [Visual Basic], coincidencia"
  - "símbolos, carácter comodín"
  - "texto [Visual Basic], comparar"
  - "comodines, Like (operador)"
ms.assetid: 966283ec-80e2-4294-baa8-c75baff804f9
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Like (operador, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Compara una cadena respecto a un modelo.  
  
## Sintaxis  
  
```  
  
result = string Like pattern  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Cualquier variable de tipo `Boolean`.  El resultado será un valor de tipo `Boolean` que indicará si `string` satisface o no el modelo `pattern`.  
  
 `string`  
 Obligatorio.  Cualquier expresión de tipo `String`.  
  
 `pattern`  
 Obligatorio.  Cualquier expresión `String` que cumpla las convenciones de coincidencia de modelos que se describen en la sección "Comentarios".  
  
## Comentarios  
 Si el valor de `string` coincide con el modelo contenido en `pattern`, `result` es `True`.  Si la cadena no coincide con el modelo, `result` es `False`.  Si tanto `string` como `pattern` son cadenas vacías, el resultado es `True`.  
  
## Método de comparación  
 El comportamiento del operador `Like` depende de [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md).  El método de comparación de cadenas predeterminado para cada archivo de código fuente es `Option Compare Binary`.  
  
## Opciones de modelo  
 El modelo de coincidencias integrado es una flexible herramienta para establecer comparaciones entre cadenas.  Las características de coincidencia de modelos permiten comparar cada carácter de `string` con un carácter concreto, un carácter comodín, una lista de caracteres o un intervalo de caracteres.  En la siguiente tabla se muestran los caracteres permitidos en `pattern` y aquellos caracteres con los que coinciden.  
  
|Caracteres de `pattern`|Coincidencias en `string`|  
|-----------------------------|-------------------------------|  
|`?`|Cualquier carácter individual|  
|`*`|Cero o más caracteres|  
|`#`|Cualquier dígito individual \(0\-9\)|  
|`[` `charlist` `]`|Cualquier carácter individual de `charlist`|  
|`[!` `charlist` `]`|Cualquier carácter individual que no esté incluido en `charlist`|  
  
## Listas de caracteres  
 Se puede utilizar un grupo de uno o varios caracteres \(`charlist`\) entre corchetes \(`[ ]`\) para hacer coincidir cualquier carácter individual de `string`; este grupo podrá incluir prácticamente cualquier código de caracteres, dígitos incluidos.  
  
 Un signo de exclamación de cierre \(`!`\) situado al principio de `charlist` significa que se encontrará una coincidencia si `string` contiene cualquier carácter no incluido en `charlist`.  Cuando se use sin corchetes, el signo de cerrar exclamación coincidirá consigo mismo.  
  
## Caracteres especiales  
 Si desea buscar caracteres especiales: corchete de apertura \(`[`\), interrogación de cierre \(`?`\) signo de número \(`#`\) y asterisco \(`*`\), escríbalos entre corchetes.  No se puede usar el corchete de cierre \(`]`\) dentro de un grupo para identificar una autocoincidencia, pero sí fuera de un grupo, como carácter individual.  
  
 La secuencia `[]` se considera una cadena de longitud cero \(`""`\).  Sin embargo, no puede formar parte de una lista de caracteres encerrada entre corchetes.  Si desea comprobar si una posición en `string` contiene un carácter de un grupo de caracteres o no contiene ninguno, puede utilizar `Like` dos veces.  Para obtener un ejemplo, vea [Cómo: Comprobar si una cadena coincide con un modelo](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md).  
  
## Intervalos de caracteres  
 Si utiliza un guión \(`–`\) para separar los límites superior e inferior del intervalo, `charlist` puede especificar un intervalo de caracteres.  Por ejemplo, `[A–Z]` arroja una coincidencia si la posición de caracteres correspondiente en `string` contiene cualquier carácter comprendido en el intervalo `A`–`Z`, y `[!H–L]` arroja una coincidencia si la posición de caracteres correspondiente contiene cualquier carácter que no esté comprendido en el intervalo `H`–`L`.  
  
 Cuando se especifique un intervalo de caracteres, éstos deberán aparecer en orden ascendente, es decir, de menor a mayor.  Eso significa que `[A–Z]` es un modelo válido, pero `[Z–A]` no.  
  
### Varios intervalos de caracteres  
 Para especificar varios intervalos en la misma posición de caracteres, sitúelos entre los mismos corchetes sin delimitadores.  Por ejemplo, `[A–CX–Z]` arroja una coincidencia si la posición de caracteres correspondiente en `string` contiene cualquier carácter comprendido en el intervalo `A`–`C` o en el intervalo `X`–`Z`.  
  
### Uso del guión  
 Un guión \(`–`\) puede aparecer tanto al principio \(después de un signo de exclamación, si lo hay\) como al final de `charlist` para identificar una autocoincidencia.  En cualquier otra posición, el guión identifica un intervalo de caracteres delimitado por los caracteres a ambos lados de él.  
  
## Secuencia de ordenación  
 El significado de un intervalo específico dependerá del orden de los caracteres en tiempo de ejecución \(según venga determinado por `Option` `Compare` y la configuración regional del sistema en que se esté ejecutando el código\).  Con `Option` `Compare` `Binary`, el intervalo `[A–E]` coincide con `A`, `B`, `C`, `D` y `E`.  Con `Option` `Compare` `Text`, `[A–E]` coincide con `A`, `a`, `À`, `à`, `B`, `b`, `C`, `c`, `D`, `d`, `E` y `e`.  El intervalo no coincide con `Ê` o `ê` porque los caracteres acentuados se intercalan después de los caracteres sin acento en el criterio de ordenación.  
  
## Caracteres dígrafos  
 En algunos idiomas, existen caracteres alfabéticos que representan dos fonemas distintos.  Por ejemplo, existen algunos idiomas que utilizan el carácter `æ` para representar los sonidos `a` y `e` cuando aparecen juntos.  El operador `Like` reconoce que el carácter dígrafo unitario y los dos caracteres individuales son equivalentes.  
  
 Cuando en la configuración regional del sistema se especifica un idioma que utiliza un carácter dígrafo, la aparición de un carácter dígrafo unitario, ya sea en `pattern` o en `string`, coincidirá con la secuencia de dos caracteres de la otra cadena.  Del mismo modo, un carácter dígrafo que aparezca en `pattern` entre corchetes \(aislado, en una lista o en un intervalo\) coincidirá con la secuencia de dos caracteres equivalente en `string`.  
  
## Sobrecarga  
 El operador `Like` se puede *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza este operador en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Ejemplo  
 En este ejemplo se utiliza el operador `Like` para comparar cadenas en varios modelos.  Los resultados se introducen en una variable de tipo `Boolean` que indica si cada cadena satisface el modelo.  
  
 [!code-vb[VbVbalrOperators#30](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/like-operator_1.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Strings.InStr%2A>   
 <xref:Microsoft.VisualBasic.Strings.StrComp%2A>   
 [Operadores de comparación](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Option Compare \(Instrucción\)](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Operadores y expresiones](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Cómo: Comprobar si una cadena coincide con un modelo](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-match-a-string-against-a-pattern.md)