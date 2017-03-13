---
title: "Lista de par&#225;metros (Visual Basic) | Microsoft Docs"
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
  - "argumentos [Visual Basic], Visual Basic"
  - "listas de parámetros"
  - "parámetros, listas"
  - "parámetros, Visual Basic"
  - "procedimientos, listas de parámetros"
  - "código de Visual Basic, listas de parámetros"
  - "código de Visual Basic, procedimientos"
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Lista de par&#225;metros (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica los parámetros que un procedimiento espera cuando se le llama.  Los parámetros múltiples se separan por comas.  A continuación, se muestra la sintaxis para un parámetro.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## Elementos  
 `attributelist`  
 Opcional.  Lista de atributos que se aplican a este parámetro.  Debe incluir [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md) entre corchetes angulares \("`<`" y "`>`"\).  
  
 `Optional`  
 Opcional.  Especifica que este parámetro no es necesario cuando se llama al procedimiento.  
  
 `ByVal`  
 Opcional.  Especifica que el procedimiento no puede reemplazar o reasignar el elemento de variable subyacente del argumento correspondiente en el código de llamada.  
  
 `ByRef`  
 Opcional.  Especifica que el procedimiento puede modificar el elemento de variable subyacente en el código de llamada de la misma forma que puede hacerlo el propio código de llamada.  
  
 `ParamArray`  
 Opcional.  Especifica que el último parámetro de la lista de parámetros es una matriz opcional de elementos del tipo de datos especificado.  Esto permite al código de llamada proporcionar un número arbitrario de argumentos al procedimiento.  
  
 `parametername`  
 Obligatorio.  Nombre de la variable local que representa el parámetro.  
  
 `parametertype`  
 Obligatorio si `Option Strict` es `On`.  Tipo de datos de la variable local que representa el parámetro.  
  
 `defaultvalue`  
 Obligatorio para los parámetros `Optional`.  Cualquier constante o expresión constante que se evalúa como tipo de datos del parámetro.  Si el tipo es `Object`, o una clase, interfaz, matriz o estructura, el valor predeterminado sólo puede ser `Nothing`.  
  
## Comentarios  
 Los parámetros están incluidos entre paréntesis y separados por comas.  Se puede declarar un parámetro con cualquier tipo de datos.  Si no especifica `parametertype`, el valor predeterminado es `Object`.  
  
 Cuando el código de llamada llama al procedimiento, pasa un *argumento* a cada parámetro necesario.  Para obtener más información, vea [Diferencias entre parámetros y argumentos](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 El argumento que el código de llamada pasa a cada parámetro es un puntero a un elemento subyacente en el código de llamada.  Si este elemento es *no modificable* \(una constante, literal, enumeración o expresión\), no lo podrá cambiar ningún código.  Si es un elemento *variable* \(una variable declarada, campo, propiedad, elemento de matriz o elemento de estructura\), el código de llamada puede cambiarlo.  Para obtener más información, vea [Diferencias entre argumentos modificables y no modificables](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Si se pasa un elemento variable `ByRef`, el procedimiento también puede cambiarlo.  Para obtener más información, vea [Diferencias entre pasar un argumento por valor y por referencia](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## Reglas  
  
-   **Paréntesis.** Si especifica una lista de parámetros, debe incluirla entre paréntesis.  Si no hay ningún parámetro, puede utilizar paréntesis para incluir una lista vacía.  Esto mejora la legibilidad de su código clarificando que el elemento es un procedimiento.  
  
-   **Parámetros opcionales.** Si utiliza el modificador `Optional` en un parámetro, todos los parámetros posteriores de la lista deben ser también opcionales y declararse mediante el modificador `Optional`.  
  
     Cada declaración de parámetro opcional debe proporcionar la cláusula `defaultvalue`.  
  
     Para obtener más información, vea [Parámetros opcionales](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Matrices de parámetros.** Debe especificar `ByVal` para un parámetro `ParamArray`.  
  
     No es posible utilizar `Optional` y `ParamArray` en la misma lista de parámetros.  
  
     Para obtener más información, vea [Matrices de parámetros](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Mecanismo para pasar argumentos.** El mecanismo predeterminado para cada argumento es `ByVal`, lo que quiere decir que el procedimiento no puede cambiar el elemento variable subyacente.  No obstante, si el elemento es un tipo de referencia, el procedimiento puede modificar el contenido o los miembros del objeto subyacente, incluso aunque no pueda reemplazar o reasignar el objeto en sí.  
  
-   **Nombres de parámetros.** Si el tipo de datos del parámetro es una matriz, deben ir unos paréntesis justo detrás de `parametername`.  Para obtener más información sobre nombres de parámetros, vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Ejemplo  
 En el ejemplo siguiente se muestra un procedimiento `Function` que define dos parámetros.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## Vea también  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare \(Instrucción\)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Cómo: Interrumpir y combinar instrucciones en código](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)