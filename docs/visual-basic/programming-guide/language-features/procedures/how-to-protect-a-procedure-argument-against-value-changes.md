---
title: "C&#243;mo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "argumentos [Visual Basic], ByRef"
  - "argumentos [Visual Basic], ByVal"
  - "argumentos [Visual Basic], cambiar valor"
  - "argumentos [Visual Basic], pasar por referencia"
  - "argumentos [Visual Basic], pasar por valor"
  - "argumentos de procedimientos"
  - "parámetros de procedimientos"
  - "procedimientos, argumentos"
  - "procedimientos, llamar"
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# C&#243;mo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona al código del procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.  Esto permite al procedimiento cambiar el valor subyacente al argumento en el código de llamada.  En algunos casos, es probable que se desee proteger el código de llamada frente a este tipo de cambios.  
  
 Para proteger un argumento y que no se efectúen cambios, puede declarar el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento.  Si desea poder cambiar un determinado argumento en algunos casos pero no en otros, puede declararlo `ByRef` y permitir que el código de llamada determine el mecanismo para pasar argumentos en cada llamada.  Para ello, incluya el argumento correspondiente entre paréntesis para transferirlo por valor o déjelo sin paréntesis para transferirlo por referencia.  Para obtener más información, vea [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md).  
  
## Ejemplo  
 En el siguiente ejemplo se muestran dos procedimientos que toman una variable de matriz y operan con sus elementos.  El procedimiento `increase` sencillamente suma una unidad a cada elemento.  El procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, suma una unidad a cada elemento.  La reasignación, sin embargo, no afecta a la variable de matriz subyacente al código de llamada.  
  
 [!code-vb[VbVbcnProcedures#35](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-protect-a-procedu_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#38](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-protect-a-procedu_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-protect-a-procedu_3.vb)]  
  
 La primera llamada a `MsgBox` muestra "After increase\(n\): 11, 21, 31, 41".  Dado que la matriz  `n`  es un tipo de referencia,  `replace`  puede cambiar sus miembros, aunque el mecanismo para transferir argumentos es `ByVal`.  
  
 La segunda llamada a `MsgBox` muestra "After replace\(n\): 11, 21, 31, 41".  Dado que  `n`  se transfiere `ByVal`,  `replace`  no puede modificar la variable  `n`  en el código de llamada ni asignarle una nueva matriz.  Cuando  `replace`  crea la nueva instancia de la matriz  `k`  y la asigna a la variable local  `a`, pierde la referencia a  `n`  que se transfirió en el código de llamada.  Cuando cambia los miembros de  `a`, sólo resulta afectada la matriz local  `k` .  Por consiguiente, `replace`  no incrementa los valores de la matriz  `n`  en el código de llamada.  
  
## Compilar el código  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], los argumentos se pasan por valor de forma predeterminada.  Sin embargo, es una práctica de programación recomendable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado.  De este modo, el código resulta más fácil de leer.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: Cambiar el valor de un argumento de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)