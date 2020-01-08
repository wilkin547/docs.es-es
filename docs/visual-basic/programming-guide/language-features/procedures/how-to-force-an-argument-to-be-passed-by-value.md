---
title: 'Cómo: Forzar un argumento para que pase como un valor'
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
ms.openlocfilehash: 047738a2cbadc6b7d72f41aade22bbeff16d1bac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347587"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Cómo: Forzar un argumento para que pase como un valor (Visual Basic)
La declaración de procedimiento determina el mecanismo de paso. Si un parámetro se declara como [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic espera pasar el argumento correspondiente por referencia. Esto permite al procedimiento cambiar el valor del elemento de programación subyacente del argumento en el código de llamada. Si desea proteger el elemento subyacente contra este cambio, puede invalidar el mecanismo de paso de `ByRef` en la llamada al procedimiento incluyendo el nombre del argumento entre paréntesis. Estos paréntesis se suman a los paréntesis que rodean la lista de argumentos de la llamada.  
  
 El código de llamada no puede invalidar un mecanismo [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) .  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Para forzar que un argumento se pase por valor  
  
- Si el parámetro correspondiente se declara `ByVal` en el procedimiento, no es necesario realizar ningún paso adicional. Visual Basic ya espera pasar el argumento por valor.  
  
- Si el parámetro correspondiente se declara `ByRef` en el procedimiento, incluya el argumento entre paréntesis en la llamada al procedimiento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se reemplaza una declaración de parámetro `ByRef`. En la llamada que fuerza `ByVal`, tenga en cuenta los dos niveles de paréntesis.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Cuando `str` está incluido entre paréntesis en la lista de argumentos, el procedimiento `setNewString` no puede cambiar su valor en el código de llamada y `MsgBox` muestra "no se puede reemplazar si se pasa por ByVal". Cuando `str` no está entre paréntesis adicionales, el procedimiento puede cambiarlo y `MsgBox` muestra "este es un nuevo valor para el argumento instring".  
  
## <a name="compile-the-code"></a>Compilar el código  
 Al pasar una variable por referencia, debe usar la palabra clave `ByRef` para especificar este mecanismo.  
  
 De forma predeterminada, en Visual Basic es pasar argumentos por valor. Sin embargo, es aconsejable incluir la palabra clave [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) con cada parámetro declarado. Esto hace que el código sea más fácil de leer.  
  
## <a name="robust-programming"></a>Programación sólida  
 Si un procedimiento declara un parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), la ejecución correcta del código podría depender de poder cambiar el elemento subyacente en el código de llamada. Si el código de llamada invalida este mecanismo de llamada incluyendo el argumento entre paréntesis, o si pasa un argumento no modificable, el procedimiento no puede cambiar el elemento subyacente. Esto podría producir resultados inesperados en el código de llamada.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Siempre existe un riesgo potencial en permitir que un procedimiento cambie el valor subyacente de un argumento en el código de llamada. Asegúrese de que espera que se cambie este valor y prepárese para comprobar su validez antes de usarlo.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Diferencias entre argumentos modificables y no modificables](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Diferencias entre pasar un argumento por valor y por referencia](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Cambiar el valor de un argumento de procedimiento](./how-to-change-the-value-of-a-procedure-argument.md)
- [Proteger un argumento de procedimiento para que no se realicen cambios de valor](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
