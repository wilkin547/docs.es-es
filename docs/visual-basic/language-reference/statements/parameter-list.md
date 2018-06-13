---
title: Lista de parámetros (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic
- parameters [Visual Basic], lists
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures [Visual Basic], parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
ms.openlocfilehash: 147a2501219db9f1f1c10f9cf1a81aa395b5ec2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605061"
---
# <a name="parameter-list-visual-basic"></a>Lista de parámetros (Visual Basic)
Especifica los parámetros de que un procedimiento espera cuando se llama. Varios parámetros se separan mediante comas. A continuación se muestra la sintaxis para un parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Lista de atributos que se aplican a este parámetro. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) corchetes angulares ("`<`"y"`>`").  
  
 `Optional`  
 Opcional. Especifica que este parámetro no es necesario cuando se llama al procedimiento.  
  
 `ByVal`  
 Opcional. Especifica que el procedimiento no puede reemplazar o reasignar el elemento de variable subyacente del argumento correspondiente en el código de llamada.  
  
 `ByRef`  
 Opcional. Especifica que el procedimiento puede modificar la variable subyacente en el código de llamada del mismo modo que el propio código de llamada.  
  
 `ParamArray`  
 Opcional. Especifica que el último parámetro en la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado. Esto permite que el código que realiza la llamada pasar un número arbitrario de argumentos al procedimiento.  
  
 `parametername`  
 Requerido. Nombre de la variable local que representa el parámetro.  
  
 `parametertype`  
 Obligatorio si `Option Strict` es `On`. Tipo de datos de la variable local que representa el parámetro.  
  
 `defaultvalue`  
 Necesario para `Optional` parámetros. Cualquier constante o una expresión constante que se evalúa como el tipo de datos del parámetro. Si el tipo es `Object`, o una clase, interfaz, matriz o estructura, solo puede ser el valor predeterminado `Nothing`.  
  
## <a name="remarks"></a>Comentarios  
 Parámetros entre paréntesis y separados por comas. Un parámetro se puede declarar con cualquier tipo de datos. Si no se especifica `parametertype`, el valor predeterminado es `Object`.  
  
 Cuando el código de llamada llama al procedimiento, pasa una *argumento* para cada parámetro necesario. Para obtener más información, consulte [diferencias entre parámetros y argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 El argumento que el código que realiza la llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada. Si este elemento es *no modificable* (una constante, literal, enumeración o expresión), no es posible escribir código cambiarlo. Si es un *variable* elemento (una variable declarada, campo, propiedad, elemento de matriz o elemento de estructura), el código de llamada puede cambiarlo. Para obtener más información, consulte [diferencias entre modificables y no modificables argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Si se pasa un elemento variable `ByRef`, el procedimiento puede cambiar también. Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Paréntesis.** Si especifica una lista de parámetros, debe encerrarlo entre paréntesis. Si no hay ningún parámetro, todavía puede usar una lista vacía entre paréntesis. Esto mejora la legibilidad del código aclarar que el elemento es un procedimiento.  
  
-   **Parámetros opcionales.** Si usas el `Optional` modificador en un parámetro, todos los parámetros siguientes en la lista deben ser también opcionales y declarados mediante el `Optional` modificador.  
  
     Cada declaración de parámetro opcional debe proporcionar la `defaultvalue` cláusula.  
  
     Para obtener más información, consulte [parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Matrices de parámetros.** Debe especificar `ByVal` para un `ParamArray` parámetro.  
  
     No puede utilizar ambos `Optional` y `ParamArray` en la misma lista de parámetros.  
  
     Para obtener más información, consulte [matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Mecanismo para pasar argumentos.** El mecanismo predeterminado para cada argumento es `ByVal`, lo que significa que el procedimiento no puede cambiar el elemento variable subyacente. Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o reasignar el propio objeto.  
  
-   **Nombres de parámetro.** Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente con paréntesis. Para obtener más información sobre nombres de parámetros, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un `Function` procedimiento que define dos parámetros.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)  
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
