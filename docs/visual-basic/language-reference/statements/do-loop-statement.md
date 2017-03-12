---
title: "Instrucci&#243;n Do...Loop (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Do"
  - "vb.Loop"
  - "vb.Until"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "instrucciones condicionales, Do...Loop"
  - "bucles Do"
  - "Do (instrucción)"
  - "Do...Loop (instrucción)"
  - "do-while (instrucciones)"
  - "ejecución, condicional"
  - "Exit (instrucción), en instrucciones Do...Loop"
  - "instrucciones, repetir"
  - "Loop (palabra clave), Do...Loop (instrucción)"
  - "estructuras de bucle, Do...Loop (instrucciones)"
  - "bucles, salir"
  - "Until (palabra clave), Do...Loop (instrucción)"
  - "while (instrucción), Do...Loop"
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 37
---
# Instrucci&#243;n Do...Loop (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Repite un bloque de instrucciones mientras una condición `Boolean` sea `True` o hasta que la condición se convierta en `True`.  
  
## Sintaxis  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`Do`|Requerido.  Inicia la definición del bucle `Do`.|  
|`While`|Obligatorio si se utiliza `Until`.  Repite el bucle hasta que `condition` sea `False`.|  
|`Until`|Obligatorio a menos que se utilice `While`.  Repite el bucle hasta que `condition` sea `True`.|  
|`condition`|Opcional.  Expresión `Boolean`.  Si `condition` es `Nothing`, Visual Basic la trata como `False`.|  
|`statements`|Opcional.  Una o más instrucciones que se repiten mientras o hasta que `condition` sea `True`.|  
|`Continue Do`|Opcional.  Transfiere el control a la siguiente iteración del bucle de `Do` .|  
|`Exit Do`|Opcional.  Transfiere el control fuera del bucle `Do`.|  
|`Loop`|Requerido.  Termina la definición del bucle `Do`.|  
  
## Comentarios  
 Utilice una estructura `Do...Loop` cuando desee repetir un conjunto de instrucciones un número indefinido de veces, hasta que se satisfaga una condición.  Si desea repetir las instrucciones un número fijo de veces, la [Instrucción For...Next](../../../visual-basic/language-reference/statements/for-next-statement.md) es normalmente una opción mejor.  
  
 Puede usar `While` o `Until` para especificar `condition`, pero no ambas.  
  
 Puede probar `condition` solo una vez, en el inicio o el final del bucle.  Si prueba `condition` al principio del bucle \(en la instrucción `Do`\), puede que el bucle no se ejecute ni siquiera una vez.  Si prueba al final del bucle \(en la instrucción `Loop`\), el bucle siempre se ejecuta al menos una vez.  
  
 Generalmente, la condición es el resultado de comparar dos valores, pero también puede ser cualquier expresión que da como resultado un valor [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) \(`True` o `False`\).  Esto incluye los valores de otros tipos de datos, como los numéricos, que han sido convertidos a valores de tipo `Boolean`.  
  
 Se pueden anidar bucles `Do` colocando un bucle dentro de otro.  También puede anidar distintos tipos de estructuras de control unos dentro de otros.  Para obtener más información, vea [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
> [!NOTE]
>  La estructura `Do...Loop` proporciona mayor flexibilidad que la [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md) porque permite decidir si se debe finalizar el bucle cuando `condition` deja de ser `True` o cuando es `True` por primera vez.  También le permite probar `condition` en el inicio o el final del bucle.  
  
## Exit Do  
 La instrucción [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar una alternativa para salir de `Do…Loop`.  `Exit Do` transfiere el control inmediatamente a la instrucción que sigue a la instrucción `Loop`.  
  
 `Exit Do` se utiliza a menudo después de evaluar alguna condición, por ejemplo en una estructura `If...Then...Else`.  Por ejemplo, puede ser conveniente salir de un bucle si se detecta una condición que hace que sea innecesario o imposible continuar la iteración, como puede ser un valor erróneo o una solicitud de finalización.  Un uso de `Exit Do` consiste en comprobar una condición que podría ocasionar un *bucle sin fin*; es decir, un bucle que pudiera ejecutarse un número elevado, o incluso infinito, de veces.  Puede utilizar `Exit Do` para escapar del bucle.  
  
 Puede incluir cualquier número de instrucciones `Exit Do` en cualquier lugar de `Do…Loop`.  
  
 Cuando se utiliza dentro de bucles `Do` anidados, `Exit Do` transfiere el control fuera del bucle más profundo y al siguiente nivel de anidamiento.  
  
## Ejemplo  
 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la variable `index` es superior a 10.  La cláusula `Until` está al final del bucle.  
  
 [!code-vb[VbVbalrStatements#131](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/do-loop-statement_1.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza una cláusula `While` en vez de una cláusula `Until`, y se prueba `condition` al inicio del bucle en lugar de al final.  
  
 [!code-vb[VbVbalrStatements#132](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/do-loop-statement_2.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo, `condition` detiene el bucle cuando la variable `index` es superior a 100.  La instrucción `If` del bucle, sin embargo, hace que la instrucción `Exit Do` detenga el bucle cuando la variable índice es mayor de 10.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/do-loop-statement_3.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se leen todas las líneas de un archivo de texto.  El método <xref:System.IO.File.OpenText%2A> abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.  En la condición `Do...Loop`, el método <xref:System.IO.StreamReader.Peek%2A> de `StreamReader` determina si hay caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#134](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/do-loop-statement_4.vb)]  
  
## Vea también  
 [Estructuras de bucles](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [While...End While \(Instrucción\)](../../../visual-basic/language-reference/statements/while-end-while-statement.md)