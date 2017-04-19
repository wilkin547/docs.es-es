---
title: "Cómo: proteger un argumento de procedimiento y cambia el valor (Visual Basic) | Documentos de Microsoft"
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
- procedures, calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 6e18f7ceefeec9c1f422d0eae4e727700ebd8b6e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a>Cómo: Proteger un argumento de procedimiento para que no se realicen cambios de valor (Visual Basic)
Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] proporciona el código del procedimiento una referencia directa al elemento de programación subyacente al argumento en el código de llamada. Esto permite que el procedimiento para cambiar el valor subyacente al argumento en el código de llamada. En algunos casos el código de llamada puede protegerse contra este tipo de cambio.  
  
 Siempre puede proteger un argumento de cambio al declarar el parámetro correspondiente [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) en el procedimiento. Si desea poder cambiar un determinado argumento en algunos casos, pero no otras, puede declarar `ByRef` y dejar que el código de llamada determine el mecanismo para pasar argumentos en cada llamada. Para hacerlo, incluyendo el argumento correspondiente entre paréntesis para pasar por valor o déjelo sin paréntesis para pasar por referencia. Para obtener más información, consulte [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra dos procedimientos que toman una variable de matriz y operan con sus elementos. El `increase` procedimiento simplemente agrega una unidad a cada elemento. El `replace` procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente al código de llamada.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/how-to-protect-a-procedure-argument-against-value-changes_3.vb)]  
  
 La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41". Dado que la matriz `n` es un tipo de referencia, `replace` puede cambiar sus miembros, aunque es el mecanismo para pasar argumentos `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después Replace (n): 11, 21, 31, 41". Porque `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` en el código de llamada asignándole una nueva matriz. Cuando `replace` crea la nueva instancia de la matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` pasados por el código de llamada. Cuando cambia los miembros de `a`, solo la matriz local `k` se ve afectado. Por lo tanto, `replace` no incrementa los valores de matriz `n` en el código de llamada.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El valor predeterminado de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es pasar argumentos por valor. Sin embargo, es una buena práctica incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que su código más fácil de leer.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: forzar un argumento para pasar por valor](./how-to-force-an-argument-to-be-passed-by-value.md)   
 [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)   
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
