---
title: "C&#243;mo: Interrumpir y combinar instrucciones en c&#243;digo (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb._"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "dos puntos (:)"
  - "continuación de línea"
  - "_ (carácter de continuación de línea)"
  - ": (carácter separador de línea)"
  - "código de Visual Basic, saltos de línea"
  - "código de Visual Basic, saltos de línea"
  - "código de Visual Basic, continuación de línea"
  - "líneas largas de código"
  - "terminador de línea"
  - "secuencia de continuación de línea"
  - "guiones bajos, en el código"
  - "instrucciones [Visual Basic], continuación de línea"
  - "saltos de línea, en el código"
  - "carácter de continuación de línea"
  - "código de Visual Basic, continuación de línea"
  - "instrucciones [Visual Basic], saltos de línea"
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Interrumpir y combinar instrucciones en c&#243;digo (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Cuando crea el código, a veces debe crear instrucciones largas que requieren un desplazamiento horizontal en el Editor de código.  Aunque esto no afecta al modo en que el código se ejecuta, dificulta que usted o nadie lee el código tal y como aparece en la pantalla.  En estos casos, debe considerar la posibilidad de segmentar la única instrucción larga en varias líneas.  
  
### Para segmentar una sola instrucción en varias líneas  
  
-   Utilice el carácter de continuación de línea, que es un subrayado \(`_`\), en el punto en el que desea que la línea se interrumpa.  El subrayado debe ir precedido inmediatamente de un espacio y seguir inmediatamente por un terminador de línea \(retorno de carro\).  
  
    > [!NOTE]
    >  En algunos casos, si se omite el carácter de la línea\- continuación, el compilador de Visual Basic continuará implícitamente la instrucción en la línea de código siguiente.  Para obtener una lista de elementos de sintaxis en los que se puede omitir el carácter de la línea\- continuación, vea “continuación de línea implícita” en [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md).  
  
     En el ejemplo siguiente, la instrucción se segmenta en cuatro líneas con caracteres de continuación de línea al final de todas las líneas excepto la última.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     La utilización de esta secuencia facilita la lectura del código, tanto en pantalla como al imprimirlo.  
  
     El carácter de la línea\- continuación debe ser el último carácter de una línea.  No puede seguirla con nada más en la misma línea.  
  
     Existen algunas restricciones respecto a donde puede utilizar el carácter de la línea\- continuación; por ejemplo, no puede utilizarlo en medio de un nombre de argumento.  Puede segmentar una lista de argumentos con el carácter de continuación de línea, pero los nombres individuales de los argumentos deben permanecer intactos.  
  
     No es posible continuar un comentario mediante el carácter de la línea\- continuación.  El compilador no examina los caracteres de un comentario para el significado especial.  Para insertar un comentario de múltiples líneas, repita el símbolo de comentario en cada línea \(`'`\).  
  
 Aunque colocar cada instrucción en una línea independiente es el método recomendado, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] también permite colocar varias instrucciones en la misma línea.  
  
### Para colocar varias instrucciones en la misma línea  
  
-   Separe las instrucciones con un signo de dos puntos \(`:`\), como en el ejemplo siguiente:  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## Vea también  
 [Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Instrucciones](../../../visual-basic/programming-guide/language-features/statements.md)