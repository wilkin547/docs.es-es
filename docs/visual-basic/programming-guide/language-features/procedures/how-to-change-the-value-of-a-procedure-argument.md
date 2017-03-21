---
title: "Cómo: cambiar el valor de un argumento de procedimiento (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, arguments
- procedures, parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
caps.latest.revision: 16
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6c42a50b75bcc70ae0a3f70771b9e1f85626004b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a>Cómo: Cambiar el valor de un argumento de procedimiento (Visual Basic)
Cuando se llama a un procedimiento, cada argumento proporcionado se corresponde a uno de los parámetros definidos en el procedimiento. En algunos casos, el código del procedimiento puede cambiar el valor subyacente a un argumento en el código de llamada. En otros casos, el procedimiento puede cambiar sólo su copia local de un argumento.  
  
 Cuando se llama al procedimiento [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] hace una copia local de cada argumento que se pasa [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md). En cada argumento transferido [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona el código del procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada.  
  
 Si el elemento subyacente en el código de llamada es un elemento modificable y el argumento se pasa `ByRef`, el código del procedimiento puede utilizar la referencia directa para cambiar el valor del elemento en el código de llamada.  
  
## <a name="changing-the-underlying-value"></a>Cambiar el valor subyacente  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a>Para cambiar el valor subyacente de un argumento de procedimiento en el código de llamada  
  
1.  En la declaración de procedimiento, especifique [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) para el parámetro correspondiente al argumento.  
  
2.  En el código de llamada pasar un elemento de programación modificable como argumento.  
  
3.  En el código de llamada, no incluya el argumento entre paréntesis en la lista de argumentos.  
  
4.  En el código de procedimiento, utilice el nombre de parámetro para asignar un valor al elemento subyacente en el código de llamada.  
  
 Vea el ejemplo más abajo para obtener una demostración.  
  
## <a name="changing-local-copies"></a>Cambiar las copias locales  
 Si el elemento subyacente en el código de llamada es un elemento no modificable, o si se pasa el argumento `ByVal`, el procedimiento no puede cambiar su valor en el código de llamada. Sin embargo, el procedimiento puede cambiar la copia local del argumento.  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a>Para cambiar la copia de un argumento de procedimiento en el código de procedimiento  
  
1.  En la declaración de procedimiento, especifique [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) para el parámetro correspondiente al argumento.  
  
     O bien  
  
     En el código de llamada, incluya el argumento entre paréntesis en la lista de argumentos. Esto obliga a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] para pasar el argumento por valor, incluso si se especifica el parámetro correspondiente `ByRef`.  
  
2.  En el código de procedimiento, utilice el nombre de parámetro para asignar un valor a la copia local del argumento. No se cambia el valor subyacente en el código de llamada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos. El `increase` procedimiento simplemente agrega una unidad a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#36;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-change-the-value-of-a-procedure-argument_3.vb)]  
  
 La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después Replace (n): 101, 201, 301". Porque `n` se pasa `ByRef`, `replace` puede modificar la variable `n` en el código de llamada y asignar una nueva matriz a él. Porque `n` es un tipo de referencia, `replace` también se puede cambiar sus miembros.  
  
 Puede impedir que el procedimiento modificar la variable en el código de llamada. Consulte [Cómo: proteger un argumento de procedimiento y cambia el valor](./how-to-protect-a-procedure-argument-against-value-changes.md).  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cuando se pasa una variable por referencia, debe utilizar el `ByRef` (palabra clave) para especificar este mecanismo.  
  
 El valor predeterminado de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es pasar argumentos por valor. Sin embargo, es una buena práctica incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que su código más fácil de leer.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre hay un riesgo potencial de permitir que un procedimiento cambiar el valor subyacente a un argumento en el código de llamada. Asegúrese de que espera este valor puede cambiar y estar preparado para comprobar su validez antes de utilizarlo.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: proteger un argumento de procedimiento realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)   
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
