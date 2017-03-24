---
title: "Operadores de comparaci&#243;n (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.<>"
  - "vb.>="
  - "vb.<="
  - "vb.>"
  - "vb.<"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "< (operador) [Visual Basic]"
  - "<= (operador) [Visual Basic]"
  - "<> (operador) [Visual Basic]"
  - "= (operador) [Visual Basic]"
  - "> (operador) [Visual Basic]"
  - ">= (operador) [Visual Basic]"
  - "comparar valores [Visual Basic]"
  - "operadores de comparación, Visual Basic"
  - "igual (operador) [Visual Basic]"
  - "mayor que (operador) [Visual Basic]"
  - "mayor o igual que (operador) [Visual Basic]"
  - "Is (operador) [Visual Basic]"
  - "menor que (operador) [Visual Basic]"
  - "menor o igual que (operador) [Visual Basic]"
  - "Like (operador) [Visual Basic]"
  - "distinto de (operador de comparación) [Visual Basic]"
  - "operadores [Visual Basic], comparación"
  - "operadores [Visual Basic], relacionales"
  - "operadores relacionales, sintaxis"
  - "comparación de cadenas [Visual Basic]"
  - "símbolos, operadores"
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Operadores de comparaci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

A continuación se recogen los operadores de comparación definidos en Visual Basic .NET.  
  
 `<` \(Operador\)  
  
 `<=` \(Operador\)  
  
 `>` \(Operador\)  
  
 `>=` \(Operador\)  
  
 `=` \(Operador\)  
  
 `<>` \(Operador\)  
  
 [Is \(Operador\)](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot \(Operador\)](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like \(Operador\)](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Estos operadores comparan dos expresiones para determinar si son iguales, y si no lo son, para determinar cuáles son sus diferencias.  `Is`, `IsNot` y `Like` se explican detalladamente en distintas páginas de la Ayuda.  Los operadores de comparación relacionales se explican detalladamente en esta página.  
  
## Sintaxis  
  
```  
  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## Elementos  
 `result`  
 Obligatorio.  Un valor `Boolean` que representa el resultado de la comparación.  
  
 `expression`  
 Obligatorio.  Cualquier expresión.  
  
 `comparisonoperator`  
 Obligatorio.  Cualquier operador de comparación relacional.  
  
 `object1`, `object2`  
 Obligatorio.  Cualquier nombre de objeto de referencia.  
  
 `string`  
 Obligatorio.  Cualquier expresión de tipo `String`.  
  
 `pattern`  
 Obligatorio.  Cualquier intervalo de caracteres o expresión `String`.  
  
## Comentarios  
 La siguiente tabla contiene una lista con los operadores de comparación relacionales y las condiciones que determinan si `result` es `True` o `False`.  
  
|Operador|`True` si|`False` si|  
|--------------|---------------|----------------|  
|`<` \(Menor que\)|`expression1` \< `expression2`|`expression1` \>\= `expression2`|  
|`<=` \(Menor o igual que\)|`expression1` \<\= `expression2`|`expression1` \> `expression2`|  
|`>` \(Mayor que\)|`expression1` \> `expression2`|`expression1` \<\= `expression2`|  
|`>=` \(Mayor o igual que\)|`expression1` \>\= `expression2`|`expression1` \< `expression2`|  
|`=` \(Igual a\)|`expression1` \= `expression2`|`expression1` \<\> `expression2`|  
|`<>` \(Distinto de\)|`expression1` \<\> `expression2`|`expression1` \= `expression2`|  
  
> [!NOTE]
>  [\= \(Operador\)](../../../visual-basic/language-reference/operators/assignment-operator.md) también se utiliza como un operador de asignación.  
  
 El operador `Is`, el operador `IsNot` y el operador `Like` tienen funcionalidades de comparación específicas que difieren de los operadores de la tabla anterior.  
  
## Comparar números  
 Cuando una expresión de tipo `Single` se compara con otra de tipo `Double`, la expresión `Single` se convierte a `Double`.  Este comportamiento es contrario al que se daba en Visual Basic 6.  
  
 De igual forma, cuando una expresión de tipo `Decimal` se compara con otra de tipo `Single` o `Double`, la expresión `Decimal` se convierte a `Single` o `Double`.  En las expresiones `Decimal`, cualquier valor fraccionario menor que 1E\-28 podría perderse.  Esta pérdida de valor fraccionario puede provocar que dos valores se consideren equivalentes sin serlo.  Por esta razón, deberán extremarse las precauciones cuando se utilice el signo de igualdad \(`=`\) para comparar dos variables de punto flotante.  Es más seguro comprobar si el valor absoluto de la diferencia entre dos números es inferior al mínimo aceptable.  
  
### Imprecisión de punto flotante  
 Cuando trabaje con números de punto flotante, tenga presente que no siempre tienen una representación precisa en memoria.  Esto podría producir que ciertas operaciones arrojaran resultados inesperados, como una comparación de valores y el operador [Mod \(Operador\)](../../../visual-basic/language-reference/operators/mod-operator.md).  Para obtener más información, vea [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Comparar cadenas  
 Cuando se comparan cadenas, las expresiones de cadena se evalúan en función del criterio de ordenación alfabética, que depende del valor de `Option Compare`.  
  
 `Option Compare Binary` efectúa comparaciones de cadenas en función de un criterio de ordenación que se deriva de las representaciones binarias internas de los caracteres.  El criterio de ordenación viene determinado por la página de códigos.  En el ejemplo siguiente se muestra un criterio de ordenación binario típico.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` efectúa comparaciones de cadenas en función de un criterio de ordenación textual que no distingue entre mayúsculas y minúsculas y que viene determinado por la configuración regional del sistema.  Al establecer `Option Compare Text` y ordenar los caracteres en el ejemplo anterior, se aplica el criterio de ordenación de texto siguiente:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### Dependencia de la configuración regional  
 Cuando establece `Option Compare Text`, el resultado de una comparación de cadenas puede depender de la configuración regional en la que se ejecuta la aplicación.  Dos caracteres podrían compararse como iguales en una configuración local, pero no en otra.  Si está utilizando una comparación de cadenas para tomar decisiones importantes, por ejemplo aceptar un intento de inicio de sesión, debería estar atento a la sensibilidad de la configuración regional.  Considere la posibilidad de definir `Option Compare Binary` o llamar a <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, que tiene en cuenta la configuración regional.  
  
## Programación sin tipos con operadores de comparación relacionales  
 No se permite utilizar operadores de comparación relacionales con expresiones `Object` bajo `Option Strict On`.  Cuando `Option Strict` es `Off`, y `expression1` o `expression2` es una expresión `Object`, los tipos en tiempo de ejecución determinan cómo se comparan.  En la siguiente tabla se muestra cómo se comparan las expresiones y el resultado que devuelve tal comparación en función del tiempo de ejecución de los operandos:  
  
|Si los operandos son...|La comparación es...|  
|-----------------------------|--------------------------|  
|Ambos `String`|Ordenar la comparación según las características de ordenación de las cadenas.|  
|Ambos numéricos|Objetos convertidos a `Double`, comparación numérica.|  
|Uno numérico y el otro `String`|`String` se convertirá en `Double` y se realizará una comparación numérica.  Si `String` no puede convertirse a `Double`, se producirá una excepción <xref:System.InvalidCastException>.|  
|Uno o ambos pertenecen a tipos de referencia distintos de `String`|Se produce una excepción <xref:System.InvalidCastException>.|  
  
 Las comparaciones numéricas tratan `Nothing` como 0.  Las comparaciones de cadenas tratan `Nothing` como `""` \(una cadena vacía\).  
  
## Sobrecarga  
 Los operadores de comparación relacionales \(`<`,  `<=`, `>`, `>=`, `=`, `<>`\) se pueden *sobrecargar*, lo que significa que una clase o una estructura pueden definir de nuevo su comportamiento cuando un operando tiene el tipo de dicha clase o estructura.  Si el código utiliza alguno de estos operadores en una clase o estructura de este tipo, asegúrese de conocer su comportamiento redefinido.  Para obtener más información, vea [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Observe que [\= \(Operador\)](../../../visual-basic/language-reference/operators/assignment-operator.md) sólo se puede sobrecargar como operador de comparación relacional, y no como operador de asignación.  
  
## Ejemplo  
 En este ejemplo se muestran varios usos distintos de los operadores de comparación, que se utilizan para comparar expresiones.  Los operadores de comparación relacionales devuelven un resultado de tipo `Boolean` para indicar si la expresión se evalúa o no como `True`.  Cuando los operadores `>` y `<` se apliquen a cadenas, la comparación se llevará a cabo utilizando el orden alfabético normal de las cadenas.  Este orden puede depender de la configuración regional.  Que el orden discrimine o no entre mayúsculas y minúsculas dependerá de la configuración de [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md).  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 En el ejemplo anterior, la primera comparación devuelve `False` y las comparaciones restantes devuelven `True`.  
  
## Vea también  
 <xref:System.InvalidCastException>   
 [\= \(Operador\)](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Prioridad de operador en Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operadores enumerados por funcionalidad](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Solucionar problemas de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Operadores de comparación en Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)