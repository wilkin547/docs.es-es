---
title: "C&#243;mo: Cambiar el valor de un argumento de procedimiento (Visual Basic) | Microsoft Docs"
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
  - "procedimientos, parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# C&#243;mo: Cambiar el valor de un argumento de procedimiento (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Cuando llama a un procedimiento, cada argumento proporcionado se corresponde con uno de los parámetros definidos en el procedimiento.  En algunos casos, el código del procedimiento puede cambiar el valor subyacente a un argumento en el código de llamada.  En otros casos, el procedimiento sólo puede cambiar la copia local de un argumento.  
  
 Cuando llama al procedimiento, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] hace una copia local de cada argumento transferido [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  En cada argumento transferido [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] proporciona al código del procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.  
  
 Si el elemento subyacente del código de llamada es un elemento modificable y el argumento se transfiere `ByRef`, el código del procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## Cambiar el valor subyacente  
  
#### Para cambiar el valor subyacente de un argumento del procedimiento en el código de llamada  
  
1.  En la declaración del procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) en el parámetro que se corresponda con el argumento.  
  
2.  En el código de llamada, transfiera un elemento de programación modificable como argumento.  
  
3.  En el código de llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4.  En el código de procedimiento, utilice el nombre de parámetro para asignar un valor al elemento subyacente del código de llamada.  
  
 Vea el ejemplo siguiente para consultar una demostración.  
  
## Cambiar las copias locales  
 Si el elemento subyacente del código de llamada no es un elemento modificable o si el argumento se transfiere `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada.  Sin embargo, el procedimiento puede cambiar la copia local de este tipo de argumento.  
  
#### Para cambiar la copia de un argumento del procedimiento en el código del procedimiento  
  
1.  En la declaración del procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el parámetro que se corresponda con el argumento.  
  
     O bien  
  
     En el código de llamada, incluya el argumento entre paréntesis en la lista de argumentos.  Esto hace que [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] transfiera el argumento por valor, aun cuando el parámetro correspondiente especifique `ByRef`.  
  
2.  En el código del procedimiento, utilice el nombre de parámetro para asignar un valor a la copia local del argumento.  El valor subyacente del código de llamada no se modifica.  
  
## Ejemplo  
 En el siguiente ejemplo se muestran dos procedimientos que toman una variable de matriz y operan con sus elementos.  El procedimiento `increase` sencillamente suma una unidad a cada elemento.  El procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, suma una unidad a cada elemento.  
  
 [!code-vb[VbVbcnProcedures#35](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#36](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures#37](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 La primera llamada a `MsgBox` muestra "After increase\(n\): 11, 21, 31, 41".  Dado que la matriz  `n`  es un tipo de referencia,  `replace`  puede cambiar sus miembros, aunque el mecanismo para transferir argumentos es `ByVal`.  
  
 La segunda llamada a `MsgBox` muestra "After replace\(n\): 101, 201, 301".  Dado que `n` se transfiere `ByRef`,  `replace`  puede modificar la variable  `n`  en el código de llamada y asignarle una nueva matriz.  Como  `n`  es un tipo de referencia,  `replace`  también puede cambiar sus miembros.  
  
 Puede evitar que el procedimiento modifique la propia variable en el código de llamada.  Vea [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## Compilar el código  
 Cuando se pasa una variable por referencia, debe utilizarse la palabra clave `ByRef` para especificar este mecanismo.  
  
 En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], los argumentos se pasan por valor de forma predeterminada.  Sin embargo, es una práctica de programación recomendable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado.  De este modo, el código resulta más fácil de leer.  
  
## Seguridad de .NET Framework  
 Existe siempre el riesgo potencial de permitir que un procedimiento cambie el valor subyacente a un argumento en el código de llamada.  Asegúrese de que tiene previsto que este valor se modifique y prepárese para comprobar su validez antes de utilizarlo.  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Cómo: Pasar argumentos a un procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](../../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: Forzar un argumento para que pase como un valor](../../../../visual-basic/programming-guide/language-features/procedures/how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](../../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md)   
 [Tipos de valor y tipos de referencia](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)