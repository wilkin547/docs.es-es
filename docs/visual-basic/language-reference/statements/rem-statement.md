---
title: "REM (Instrucci&#243;n, Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.'"
  - "vb.Rem"
  - "Rem"
  - "'"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "' (carácter marcador de comentario) [Visual Basic]"
  - "comentarios en código, Visual Basic"
  - "comentarios, código de Visual Basic"
  - "REM (instrucción)"
  - "código de Visual Basic, comentarios"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# REM (Instrucci&#243;n, Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Se utiliza para incluir comentarios explicativos en el código fuente de un programa.  
  
## Sintaxis  
  
```  
REM comment  
' comment  
```  
  
## Elementos  
 `comment`  
 Opcional.  El texto de cualquier comentario que desee incluir.  Se requiere un espacio entre el `REM` palabra clave y `comment`.  
  
## Comentarios  
 Puede colocar una instrucción `REM` sola en una línea o puede ponerla en una línea a continuación de otra instrucción.  La instrucción `REM` debe ser la última instrucción de la línea.  Si sigue otra instrucción, la `REM` debe estar separada de esa instrucción por un espacio.  
  
 Puede utilizar una comilla simple \(`'`\) en vez de `REM`.  Esto es cierto si el comentario sigue a otra instrucción en la misma línea o se encuentra sola en una línea.  
  
> [!NOTE]
>  No es posible continuar una instrucción `REM` mediante la secuencia de continuación de línea \(`_`\).  Una vez que se inicia un comentario, el compilador no busca ningún significado especial en los caracteres.  Para un comentario de varias líneas, utilice otra instrucción `REM` o un símbolo de comentario \(`'`\) en cada línea.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra la instrucción `REM`, que se utilizará para incluir observaciones explicativas en un programa.  También se muestra la alternativa de utilización de un carácter de comilla simple \(`'`\) en lugar de `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## Vea también  
 [Comentarios en código](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)   
 [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)