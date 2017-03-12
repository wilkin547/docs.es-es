---
title: "Instrucci&#243;n While...End While (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.While"
  - "vb.While...EndWhile"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "While (instrucción)"
  - "While (instrucción), While...End While"
  - "While...End While (instrucciones)"
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Instrucci&#243;n While...End While (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Ejecuta una serie de instrucciones siempre que una condición dada sea `True`.  
  
## Sintaxis  
  
```  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`condition`|Requerido.  Expresión `Boolean`.  Si `condition` es `Nothing`, Visual Basic la trata como `False`.|  
|`statements`|Opcional.  Una o más instrucciones a continuación de `While`, que se ejecutan cada vez que `condition` es `True`.|  
|`Continue While`|Opcional.  Transfiere el control a la siguiente iteración del bloque de `While` .|  
|`Exit While`|Opcional.  Transfiere el control fuera del bloque `While`.|  
|`End While`|Requerido.  Termina la definición del bloque `While`.|  
  
## Comentarios  
 Utilice una estructura `While...End While` si desea repetir un conjunto de instrucciones un número indefinido de veces, siempre que una condición sea `True`.  Si desea más flexibilidad con respecto a la ubicación donde prueba la condición o al resultado para el que la prueba, quizá prefiera [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md).  Si desea repetir las instrucciones un número fijo de veces, [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md) suele ser mejor opción.  
  
> [!NOTE]
>  La palabra clave `While` también se utiliza en [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip While \(Cláusula\)](../../../visual-basic/language-reference/queries/skip-while-clause.md) y [Take While \(Cláusula\)](../../../visual-basic/language-reference/queries/take-while-clause.md).  
  
 Si `condition` es `True`, se ejecutan todas las `statements` hasta que se encuentra la instrucción `End While` El Control se devuelve a `While` el fragmento, y `condition` se comprueba de nuevo.  Si `condition` aún es `True`, se repite el proceso.  Si es `False`, el control que se va a extraer que sigue el fragmento de `End While` .  
  
 El fragmento de `While` comprueba siempre la condición antes de iniciar el bucle.  La ejecución en bucle continúa mientras el resultado de la condición sea `True`.  Si `condition` es `False` cuando primero entra en el bucle, no ejecuta incluso una vez.  
  
 `condition` resultados general de una comparación de dos valores, pero puede ser cualquier expresión que se evalúa como [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) un valor \(`True` o `False`\).  Esta expresión puede incluir un valor de otro tipo de datos, como un tipo numérico, convertido en `Boolean`.  
  
 Se pueden anidar bucles `While` colocando un bucle dentro de otro.  También puede anidar distintos tipos de estructuras de control dentro de otras.  Para obtener más información, vea [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## Salida mientras  
 El fragmento de [Salida mientras](../../../visual-basic/language-reference/statements/exit-statement.md) puede proporcionar otra forma de salir de un bucle de `While` .  De`Exit While` transfiere el control inmediatamente al extraer que sigue el fragmento de `End While` .  
  
 Normalmente se utiliza `Exit While` después de que se evalúe alguna condición \(por ejemplo, en una estructura de `If...Then...Else` \).  Por ejemplo, puede ser conveniente salir de un bucle si se detecta una condición que hace que sea innecesario o imposible continuar la iteración, como puede ser un valor erróneo o una solicitud de finalización.  Puede utilizar `Exit While` cuando se prueba para una condición que podría provocar *un bucle infinito*, que es un bucle que puede ejecutar un número muy grande o incluso infinito de veces.  Puede utilizar `Exit While` para que el bucle.  
  
 Puede poner cualquier número de instrucciones `Exit While` en cualquier lugar del bucle `While`.  
  
 Cuando se utiliza dentro de bucles `While` anidados, `Exit While` transfiere el control fuera del bucle más profundo y al siguiente nivel de anidamiento.  
  
 De `Continue While` de extraer transfiere el control inmediatamente a la siguiente iteración del bucle.  Para obtener más información, vea [Continue \(Instrucción\)](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
## Ejemplo  
 En el ejemplo siguiente, las instrucciones del bucle continúan ejecutándose hasta que la variable `index` es superior a 10.  
  
 [!code-vb[VbVbalrStatements#171](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_1.vb)]  
  
## Ejemplo  
 En el siguiente ejemplo se muestra el uso de las instrucciones `Continue While` y `Exit While`.  
  
 [!code-vb[VbVbalrStatements#172](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_2.vb)]  
  
## Ejemplo  
 En el ejemplo siguiente se leen todas las líneas de un archivo de texto.  El método <xref:System.IO.File.OpenText%2A> abre el archivo y devuelve un <xref:System.IO.StreamReader> que lee los caracteres.  En la condición de `While` , el método de <xref:System.IO.StreamReader.Peek%2A> de `StreamReader` determina si contiene caracteres adicionales.  
  
 [!code-vb[VbVbalrStatements#173](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/while-end-while-statement_3.vb)]  
  
## Vea también  
 [Estructuras de bucles](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Do...Loop \(Instrucción\)](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next \(Instrucción\)](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Estructuras de control anidadas](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [Continue \(Instrucción\)](../../../visual-basic/language-reference/statements/continue-statement.md)