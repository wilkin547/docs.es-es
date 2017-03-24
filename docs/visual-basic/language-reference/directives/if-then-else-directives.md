---
title: "#If...Then...#Else (Directivas) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.#EndIf"
  - "#End If"
  - "#Then"
  - "#ElseIf"
  - "vb.#ElseIf"
  - "vb.#Else"
  - "vb.#If"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "#Else (directiva) [Visual Basic]"
  - "#End if (directiva) [Visual Basic]"
  - "#If (directiva) [Visual Basic]"
  - "compilación condicional, directivas"
  - "else: directiva (#else)"
  - "compilación selectiva"
  - "código de Visual Basic, compilar"
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# #If...Then...#Else (Directivas)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Compila de forma condicional bloques de código seleccionados de Visual Basic.  
  
## Sintaxis  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## Elementos  
 `expression`  
 Requerida para las instrucciones `#If` y `#ElseIf`; en caso contrario, opcional.  Cualquier expresión formada exclusivamente por una o más constantes de compilación condicional, literales y operadores, que se evalúa como `True` o `False`.  
  
 `statements`  
 Requerida para el bloque de instrucción `#If`; en caso contrario, opcional.  Líneas de programa de Visual Basic o directivas de compilación que se compilan si la expresión asociada se evalúa como `True`.  
  
 `#End If`  
 Termina el bloque de instrucción `#If`.  
  
## Comentarios  
 Aparentemente, el comportamiento de las directivas `#If...Then...#Else` es el mismo que el de las instrucciones `If...Then...Else`.  Sin embargo, las directivas `#If...Then...#Else` evalúan lo compilado por el compilador, mientras que las instrucciones `If...Then...Else` evalúan las condiciones en tiempo de ejecución.  
  
 La compilación condicional se utiliza habitualmente para compilar el mismo programa para plataformas distintas.  También se utiliza para evitar que el código de depuración aparezca en los archivos ejecutables.  El código excluido durante una compilación condicional se omite completamente en el archivo ejecutable final, de modo que no tiene ningún efecto en el tamaño ni en el rendimiento.  
  
 Independientemente del resultado de la evaluación, todas las expresiones se evalúan utilizando `Option Compare Binary`.  La instrucción `Option Compare` no afecta a las expresiones de las instrucciones `#If` y `#ElseIf`.  
  
> [!NOTE]
>  No existe ningún formulario de línea única de las directivas `#If`, `#Else`, `#ElseIf` y `#End If`.  No puede aparecer otro código en la misma línea que cualquiera de las directivas.  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza el constructor `#If...Then...#Else` para determinar si se compilan ciertas instrucciones.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## Vea también  
 [\#Const \(Directiva\)](../../../visual-basic/language-reference/directives/const-directive.md)   
 [If...Then...Else \(Instrucción\)](../../../visual-basic/language-reference/statements/if-then-else-statement.md)   
 [Compilación condicional](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)