---
title: Filtrar Forzar un argumento para pasar por valor (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 7bd78772b35e3f336f49c1d39b5f56a3a2076c30
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970290"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Filtrar Forzar un argumento para pasar por valor (Visual Basic)
La declaración de procedimiento determina el mecanismo de paso. Si se declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), espera que Visual Basic pasar el argumento correspondiente por referencia. Esto permite que el procedimiento cambiar el valor del elemento de programación subyacente del argumento en el código de llamada. Si desea proteger el elemento subyacente frente a estos cambios, puede invalidar el `ByRef` llame al mecanismo de paso en el procedimiento, incluya entre paréntesis el nombre del argumento. Los paréntesis son además de los paréntesis para delimitar la lista de argumentos en la llamada.  
  
 El código de llamada no se puede invalidar un [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) mecanismo.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Para forzar un argumento para pasar por valor  
  
-   Si se declara el correspondiente parámetro `ByVal` en el procedimiento, es necesario realizar ningún paso adicional. Ya espera Visual Basic pasar el argumento por valor.  
  
-   Si se declara el correspondiente parámetro `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada a procedimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se invalida un `ByRef` declaración de parámetro. En la llamada que obliga a `ByVal`, tenga en cuenta los dos niveles de paréntesis.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Cuando `str` se encierra entre paréntesis adicionales dentro de la lista de argumentos, el `setNewString` procedimiento no puede cambiar su valor en el código que realiza la llamada, y `MsgBox` muestra "No se puede reemplazar si pasa ByVal". Cuando `str` no está entre paréntesis adicionales, puede cambiar el procedimiento, y `MsgBox` muestra "Es un nuevo valor para el argumento inString".  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Cuando se pasa una variable por referencia, debe usar el `ByRef` palabra clave para especificar este mecanismo.  
  
 El valor predeterminado en Visual Basic consiste en pasar argumentos por valor. Sin embargo, es buena práctica para incluir cualquiera de programación la [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) palabra clave con cada parámetro declarado. Esto hace que el código más fácil de leer.  
  
## <a name="robust-programming"></a>Programación sólida  
 Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la ejecución correcta del código podría depender poder cambiar el elemento subyacente en el código de llamada. Si el código de llamada reemplaza este mecanismo de llamada, incluya el argumento entre paréntesis, o si pasa un argumento, el procedimiento no puede cambiar el elemento subyacente. Esto podría producir resultados inesperados en el código de llamada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre hay un riesgo potencial de permitir que un procedimiento cambiar el valor subyacente a un argumento en el código de llamada. Asegúrese de que se espera que este valor se puede cambiar, y estar preparado para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también
- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Cómo: Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Cómo: Cambie el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Cómo: Proteger un argumento de procedimiento contra cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
