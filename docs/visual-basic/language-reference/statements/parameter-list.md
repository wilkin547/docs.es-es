---
title: "Lista de parámetros (Visual Basic) | Documentos de Microsoft"
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
- Visual Basic code, procedures
- parameters, Visual Basic
- parameters, lists
- parameter lists
- Visual Basic code, parameter lists
- arguments [Visual Basic], Visual Basic
- procedures, parameter lists
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
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
ms.openlocfilehash: abadaa8e035bfa4c92acc30ab633d6a7e958676c
ms.lasthandoff: 03/13/2017

---
# <a name="parameter-list-visual-basic"></a>Lista de parámetros (Visual Basic)
Especifica los parámetros de que un procedimiento espera cuando se llama. Varios parámetros se separan por comas. La siguiente es la sintaxis para un parámetro.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## <a name="parts"></a>Elementos  
 `attributelist`  
 Opcional. Lista de atributos que se aplican a este parámetro. Debe incluir el [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) en corchetes angulares ("`<`"y"`>`").  
  
 `Optional`  
 Opcional. Especifica que este parámetro no es necesario cuando se llama al procedimiento.  
  
 `ByVal`  
 Opcional. Especifica que el procedimiento no puede reemplazar o reasignar el elemento de variable subyacente del argumento correspondiente en el código de llamada.  
  
 `ByRef`  
 Opcional. Especifica que el procedimiento puede modificar la variable subyacente en el código de llamada del mismo modo que el propio código de llamada.  
  
 `ParamArray`  
 Opcional. Especifica que el último parámetro en la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado. Esto permite que el código de llamada pasar un número arbitrario de argumentos al procedimiento.  
  
 `parametername`  
 Obligatorio. Nombre de la variable local que representa el parámetro.  
  
 `parametertype`  
 Requerido si `Option Strict` es `On`. Tipo de datos de la variable local que representa el parámetro.  
  
 `defaultvalue`  
 Necesario para `Optional` parámetros. Cualquier constante o expresión constante que se evalúa como el tipo de datos del parámetro. Si el tipo es `Object`, o una clase, interfaz, matriz o estructura, el valor predeterminado sólo puede ser `Nothing`.  
  
## <a name="remarks"></a>Comentarios  
 Parámetros entre paréntesis y separados por comas. Puede declarar un parámetro con cualquier tipo de datos. Si no se especifica `parametertype`, el valor predeterminado es `Object`.  
  
 Cuando el código de llamada llama al procedimiento, pasa un *argumento* a cada parámetro necesario. Para obtener más información, consulte [diferencias entre parámetros y argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 El argumento que el código de llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada. Si este elemento es *no modificable* (una constante, literal, enumeración o expresión), es imposible escribir código cambiarlo. Si es un *variable* elemento (una variable declarada, campo, propiedad, elemento de matriz o elemento de estructura), el código de llamada puede cambiarlo. Para obtener más información, consulte [diferencias entre modificables y no modificables argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Si se pasa un elemento variable `ByRef`, el procedimiento puede cambiar también. Para obtener más información, consulte [las diferencias entre pasar un argumento por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Paréntesis.** Si especifica una lista de parámetros, debe encerrarlo entre paréntesis. Si no hay ningún parámetro, aún puede usar una lista vacía entre paréntesis. Esto mejora la legibilidad del código aclarar que el elemento es un procedimiento.  
  
-   **Parámetros opcionales.** Si utiliza la `Optional` modificador en un parámetro, todos los parámetros posteriores en la lista deben ser también opcionales y declarados mediante el `Optional` modificador.  
  
     Cada declaración de parámetro opcional debe proporcionar la `defaultvalue` cláusula.  
  
     Para obtener más información, consulte [parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Matrices de parámetros.** Debe especificar `ByVal` para un `ParamArray` parámetro.  
  
     No puede utilizar ambos `Optional` y `ParamArray` en la misma lista de parámetros.  
  
     Para obtener más información, consulte [matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Mecanismo para pasar argumentos.** El mecanismo predeterminado para cada argumento es `ByVal`, lo que significa que el procedimiento no puede cambiar el elemento variable subyacente. Sin embargo, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, aunque no puede reemplazar o reasignar el propio objeto.  
  
-   **Nombres de parámetro.** Si el tipo de datos del parámetro es una matriz, siga `parametername` inmediatamente mediante paréntesis. Para obtener más información sobre nombres de parámetros, vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra un `Function` procedimiento que define dos parámetros.  
  
 [!code-vb[VbVbalrStatements&#2;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute></xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure (instrucción)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict (instrucción)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Información general de atributos](../../../visual-basic/programming-guide/concepts/attributes/index.md)   
 [Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
