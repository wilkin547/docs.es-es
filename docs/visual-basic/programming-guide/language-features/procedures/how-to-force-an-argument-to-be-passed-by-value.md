---
title: "Cómo: forzar un argumento para pasar por valor (Visual Basic) | Documentos de Microsoft"
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
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures, calling
- arguments [Visual Basic], in parentheses
- procedure arguments, in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
caps.latest.revision: 16
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
ms.openlocfilehash: eea3466534f1797170ae4bc72afbcba899929911
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Cómo: Forzar un argumento para que pase como un valor (Visual Basic)
La declaración del procedimiento determina el mecanismo de paso. Si se declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] espera transferir el argumento correspondiente por referencia. Esto permite que el procedimiento cambiar el valor del elemento de programación subyacente al argumento en el código de llamada. Si desea proteger el elemento subyacente frente a estos cambios, puede invalidar el `ByRef` mecanismo para pasar argumentos en el procedimiento de llamada incluyendo el nombre del argumento entre paréntesis. Estos paréntesis son distintos de los paréntesis que encierran la lista de argumentos en la llamada.  
  
 El código de llamada no puede reemplazar un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mecanismo.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Para forzar un argumento para pasar por valor  
  
-   Si el parámetro correspondiente se declara `ByVal` en el procedimiento, no es necesario realizar pasos adicionales. [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]ya tiene previsto pasar el argumento por valor.  
  
-   Si el parámetro correspondiente se declara `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada al procedimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se invalida un `ByRef` declaración de parámetro. En la llamada que obliga a `ByVal`, tenga en cuenta los dos niveles de paréntesis.  
  
 [!code-vb[VbVbcnProcedures&#39;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_1.vb)]  
  
 [!code-vb[VbVbcnProcedures Nº&40;](./codesnippet/VisualBasic/how-to-force-an-argument-to-be-passed-by-value_2.vb)]  
  
 Cuando `str` se encierra entre paréntesis adicionales dentro de la lista de argumentos, la `setNewString` procedimiento no puede cambiar su valor en el código de llamada, y `MsgBox` muestra "Cannot be replaced if passed ByVal". Cuando `str` no está encerrada entre paréntesis adicionales, el procedimiento puede cambiar, y `MsgBox` muestra "Es un nuevo valor para el argumento inString."  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cuando se pasa una variable por referencia, debe utilizar el `ByRef` (palabra clave) para especificar este mecanismo.  
  
 El valor predeterminado de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] es pasar argumentos por valor. Sin embargo, es una buena práctica incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que su código más fácil de leer.  
  
## <a name="robust-programming"></a>Programación sólida  
 Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la ejecución correcta del código dependieran de poder cambiar el elemento subyacente en el código de llamada. Si el código de llamada reemplaza este mecanismo de llamada encerrando el argumento entre paréntesis, o si pasa un argumento, el procedimiento no puede cambiar el elemento subyacente. Esto podría producir resultados inesperados en el código de llamada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre hay un riesgo potencial de permitir que un procedimiento cambiar el valor subyacente a un argumento en el código de llamada. Asegúrese de que espera este valor puede cambiar y estar preparado para comprobar su validez antes de utilizarlo.  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Cómo: pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)   
 [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)   
 [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)   
 [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)   
 [Cómo: cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)   
 [Cómo: proteger un argumento de procedimiento realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)   
 [Pasar argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)   
 [Tipos de valores y tipos de referencias](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
