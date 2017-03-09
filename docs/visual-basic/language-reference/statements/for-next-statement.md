---
title: "Instrucci&#243;n For...Next (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Step"
  - "vb.Next"
  - "vb.To"
  - "vb.for"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bucles infinitos"
  - "Palabra clave Next, instrucciones For...Next"
  - "palabra clave For [Visual Basic], instrucciones For...Next"
  - "Palabra clave Step, instrucciones For...Next"
  - "sobrecarga de operadores, instrucción For...Next"
  - "Palabra clave To, instrucciones For...Next"
  - "bucles sin fin"
  - "bucles, sin fin"
  - "instrucciones, repetición"
  - "instrucción Next, For...Next"
  - "For...Next (instrucciones)"
  - "estructuras de bucle, For...Next"
  - "bucles, infinitos"
  - "Instrucción Exit, instrucciones For...Next"
  - "For (instrucción)"
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: 64
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 64
---
# Instrucci&#243;n For...Next (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Repite un grupo de instrucciones un número de veces especificado.  
  
## Sintaxis  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## Elementos  
  
|Parte|Descripción|  
|-----------|-----------------|  
|`counter`|Se requiere en la instrucción `For`.  Variable numérica.  Variable de control para el bucle.  Para obtener más información, vea [Argumento de contador](#BKMK_Counter) más adelante en este tema.|  
|`datatype`|Opcional.  Tipo de datos de `counter`.  Para obtener más información, vea [Argumento de contador](#BKMK_Counter) más adelante en este tema.|  
|`start`|Requerido.  Expresión numérica.  Valor inicial de `counter`.|  
|`end`|Requerido.  Expresión numérica.  Valor final de `counter`.|  
|`step`|Opcional.  Expresión numérica.  Cantidad en la que se incrementa `counter` cada vez que se recorre el bucle.|  
|`statements`|Opcional.  Una o más instrucciones entre `For` y `Next` que se ejecutan un número especificado de veces.|  
|`Continue For`|Opcional.  Transfiere el control a la siguiente iteración del bucle.|  
|`Exit For`|Opcional.  Transfiere el control fuera del bucle `For`.|  
|`Next`|Requerido.  Termina la definición del bucle `For`.|  
  
> [!NOTE]
>  La palabra clave de `To` se utiliza en esta instrucción para especificar el intervalo del contador.  También puede utilizar esta palabra clave en [Select...Case \(Instrucción\)](../../../visual-basic/language-reference/statements/select-case-statement.md) y en declaraciones de matriz.  Para obtener más información sobre las declaraciones de matriz, vea [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md).  
  
## Ejemplos simples  
 Utiliza una estructura de `For`…`Next` cuando desea repetir un conjunto de instrucciones un número fijo de veces.  
  
 En el ejemplo siguiente, la variable de `index` comienza con un valor de 1 y se incrementa con cada iteración del bucle, finalizando después de que el valor de `index` cobertura 5.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_1.vb)]  
  
 En el ejemplo siguiente, la variable de `number` comienza en 2 y es baja por 0,25 en cada iteración del bucle, finalizando después de que el valor de `number` cobertura 0.  El argumento de `Step` de `-.25` reduce el valor en 0,25 en cada iteración del bucle.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md) o [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md) funciona bien cuando no se sabe de antemano cuántas veces para ejecutar las instrucciones del bucle.  Sin embargo, cuando espere ejecutar el bucle un número concreto de veces, `For`...`Next` es una mejor elección.  Determina el número de iteraciones cuando se entra en el bucle por primera vez.  
  
## Bucles anidados  
 Se pueden anidar bucles `For` colocando un bucle dentro de otro.  En el ejemplo siguiente se muestran estructuras `For`...`Next` anidadas con valores de incremento diferentes.  El bucle externo crea una cadena para cada iteración del bucle.  El bucle interior disminuye una variable de contador de bucle por cada iteración del bucle.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_3.vb)]  
  
 Cuando los bucles de anidamiento, cada bucle deben tener una variable única de `counter`.  
  
 También puede anidar distintos tipos de estructuras de control unos dentro de otros.  Para obtener más información, vea [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Exit For y Continue For  
 La instrucción de `Exit For` inmediatamente sale del bucle de `For`…`Next` y transfiere el control a la instrucción que sigue a la instrucción de `Next`.  
  
 la instrucción `Continue For` transfiere el control inmediatamente a la siguiente iteración del bucle.  Para obtener más información, vea [Continue \(Instrucción\)](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 En el siguiente ejemplo se muestra el uso de las instrucciones `Continue For` y `Exit For`.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_4.vb)]  
  
 Puede incluir cualquier número de instrucciones `Exit For` en un bucle `For`...`Next`.  Cuando se utiliza dentro de bucles `For`…`Next` anidados, `Exit For` sale del bucle más profundo y transfiere el control al siguiente nivel de anidamiento.  
  
 `Exit For` suele usarse después de que se evalúe alguna condición \(por ejemplo, en una estructura de `If`…`Then`…`Else` \).  Puede que desee utilizar `Exit For` para las siguientes condiciones:  
  
-   Continuar la iteración es innecesario o imposible.  Un valor de error o una solicitud de finalización podría crear esta condición.  
  
-   Una instrucción de `Try`…`Catch`…`Finally` detecta una excepción.  Puede utilizar `Exit For` al final del bloque `Finally` .  
  
-   Tiene un bucle infinito, que es un bucle que puede ejecutar un número grande o incluso infinito de veces.  Si se detecta este tipo de condición, se puede utilizar `Exit For` para escapar del bucle.  Para obtener más información, vea [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## Implementación técnica  
 Cuando comienza un bucle `For`...`Next`, Visual Basic evalúa `start` `end` y `step`.  Visual Basic evalúa estos valores únicamente en este momento y después asignará `start` a `counter`.  Antes de que el bloque de la instrucción se ejecuta, Visual Basic compara `counter` a `end`.  Si `counter` ya es mayor que el valor de `end` \(o más pequeño si `step` es negativo\), el bucle de `For` y el control pasa a la instrucción que sigue a la instrucción de `Next`.  Si no, se ejecuta el bloque de instrucciones.  
  
 Cada vez que Visual Basic encuentra la instrucción `Next`, incrementa `counter` en el valor indicado en `step` y vuelve a la instrucción `For`.  Compara de nuevo `counter` con `end` y, otra vez, ejecuta el bloque o sale del bucle, según el resultado.  Este proceso continúa hasta que `counter` sobrepasa `end` o se encuentra una instrucción `Exit For`.  
  
 El bucle no detiene hasta que `counter` haya pasado `end`.  Si `counter` es igual a `end`, el bucle continúa.  La comparación que determina si se ejecuta el bloque es `counter` \<\= `end` si `step` es positivo y `counter` \>\= `end` si `step` es negativo.  
  
 Si cambia el valor de `counter` mientras dentro de un bucle, el código podría ser más difícil de leer y depuración.  Cambie el valor de `start`, `end`, o `step` no afecta a los valores de iteración que se determinados cuando el bucle primero se escribió.  
  
 Si se anida bucles, el compilador señala un error si encuentra la instrucción de `Next` de un nivel de anidamiento externo antes de la instrucción de `Next` de un nivel interno.  Sin embargo, el compilador sólo puede detectar este error superpuesto si se especifica `counter` en cada instrucción `Next`.  
  
### Step \(argumento\)  
 El valor de `step` puede ser positivo o negativo.  Este parámetro determina el procesamiento de bucles según la tabla siguiente:  
  
|**Valor de step**|**El bucle se ejecuta si**|  
|-----------------------|--------------------------------|  
|Positivo o cero|`counter` \<\= `end`|  
|Negativo|`counter` \>\= `end`|  
  
 El valor predeterminado de `step` es 1.  
  
###  <a name="BKMK_Counter"></a> Argumento de contador  
 La siguiente tabla se indica si `counter` define una nueva variable local cuyo ámbito al bucle completo de `For…Next`.  Esta determinación depende de si `datatype` está presente y si `counter` está definido.  
  
|¿ `datatype` presente?|¿ `counter` ya se ha definido?|Resultado \(si `counter` define una nueva variable local cuyo ámbito al bucle completo de `For...Next` \)|  
|----------------------------|------------------------------------|---------------------------------------------------------------------------------------------------------------|  
|No|Sí|No, porque `counter` ya está definido.  Si el ámbito de `counter` no es local al procedimiento, una advertencia en tiempo de compilación se produce.|  
|No|No|Sí.  Se deduce el tipo de datos de `start`, de `end`, y las expresiones de `step`.  Para obtener información sobre la inferencia de tipos, vea [Option Infer \(instrucción\)](../../../visual-basic/language-reference/statements/option-infer-statement.md) y [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|Sí|Sí|Sí, pero solo si la variable existente de `counter` se define fuera del procedimiento.  Esa variable sigue siendo independiente.  Si el ámbito de la variable existente de `counter` es local al procedimiento, se produce un error de compilación.|  
|Sí|No|Sí.|  
  
 El tipo de datos de `counter` determina el tipo de la iteración, que debe ser uno de los tipos siguientes:  
  
-   Un `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, o `Double`.  
  
-   Una enumeración que se declara utilizando una [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
-   Interfaz `Object`.  
  
-   Un tipo `T` que tiene los siguientes operadores, donde `B` es un tipo que puede utilizarse en una expresión `Boolean` .  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 Puede especificar opcionalmente la variable de `counter` en la instrucción de `Next`.  Esta sintaxis mejora la legibilidad del programa, especialmente si ha anidado bucles de `For`.  Debe especificar la variable que aparece en la instrucción correspondiente de `For`.  
  
 Las expresiones `start`, `end` y `step` pueden evaluarse como cualquier tipo de datos que se amplíe al tipo de `counter`.  Si utiliza un tipo definido por el usuario para `counter`, podría tener que definir el operador de conversión de `CType` para convertir tipos de `start`, de `end`, o de `step` al tipo de `counter`.  
  
## Ejemplo  
 El ejemplo siguiente elimina todos los elementos de una lista genérica.  En lugar de [For Each...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-each-next-statement.md), el ejemplo muestra una instrucción de `For`…`Next` que recorra en orden descendente.  El ejemplo utiliza esta técnica porque el método de `removeAt` hace elementos después del elemento quitado para tener un valor de índice mínimo.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_5.vb)]  
  
## Ejemplo  
 El ejemplo siguiente se recorre en iteración una enumeración que se declara mediante [Enum \(Instrucción\)](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_6.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo, los parámetros de la instrucción utilizan una clase que tiene sobrecargas de operador para los operadores `+`, `-`, `>=` y `<=`.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/for-next-statement_7.vb)]  
  
## Vea también  
 <xref:System.Collections.Generic.List%601>   
 [Estructuras de bucles](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Colecciones](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)