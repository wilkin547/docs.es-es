---
title: "Operator (Instrucci&#243;n) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.operator"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CType (función), Operator (instrucción)"
  - "Narrowing (palabra clave), operadores de conversión"
  - "sobrecarga de operadores"
  - "procedimientos de operadores"
  - "Operator (instrucción)"
  - "operadores [Visual Basic]"
  - "operadores [Visual Basic], sobrecargar"
  - "operadores sobrecargados"
  - "procedimientos, operador"
  - "sintaxis, procedimientos de operadores"
  - "código de Visual Basic, operadores"
  - "Widening (palabra clave), operadores de conversión"
ms.assetid: b12ec4af-1ad7-4a17-865b-c5ee96320ae5
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Operator (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Declara el símbolo de operador, los operandos y el código que definen un procedimiento de operador en una clase o estructura.  
  
## Sintaxis  
  
```  
[ <attrlist> ] Public [ Overloads ] Shared [ Shadows ] [ Widening | Narrowing ]   
Operator operatorsymbol ( operand1 [, operand2 ]) [ As [ <attrlist> ] type ]  
    [ statements ]  
    [ statements ]  
    Return returnvalue  
    [ statements ]  
End Operator  
```  
  
## Elementos  
 `attrlist`  
 Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `Public`  
 Obligatorio.  Indica que este procedimiento de operador tiene acceso de tipo [Public](../../../visual-basic/language-reference/modifiers/public.md).  
  
 `Overloads`  
 Opcional.  Vea [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).  
  
 `Shared`  
 Obligatorio.  Indica que este procedimiento de operador es de tipo [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  
  
 `Shadows`  
 Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
 `Widening`  
 Se requiere para un operador de conversión a menos que especifique `Narrowing`.  Indica que este procedimiento de operador define una conversión de tipo [Widening](../../../visual-basic/language-reference/modifiers/widening.md).  Vea "Conversiones de ampliación y restricción" en esta página de Ayuda.  
  
 `Narrowing`  
 Se requiere para un operador de conversión a menos que especifique `Widening`.  Indica que este procedimiento de operador define una conversión de tipo [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md).  Vea "Conversiones de ampliación y restricción" en esta página de Ayuda.  
  
 `operatorsymbol`  
 Obligatorio.  El símbolo o identificador del operador que define este procedimiento de operador.  
  
 `operand1`  
 Obligatorio.  El nombre y tipo del operando único de un operador unario \(incluido un operador de conversión\) o el operando izquierdo de un operador binario.  
  
 `operand2`  
 Obligatorio para los operadores binarios.  El nombre y tipo del operando derecho de un operador binario.  
  
 `operand1` y `operand2` tienen la sintaxis y las partes siguientes:  
  
 `[ ByVal ] operandname [ As operandtype ]`  
  
|Parte|Descripción|  
|-----------|-----------------|  
|`ByVal`|Opcional, pero el mecanismo para pasar argumentos debe ser [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).|  
|`operandname`|Obligatorio.  Nombre de la variable que representa este operando.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`operandtype`|Opcional a menos que `Option Strict` esté establecido en `On`.  Tipo de datos de este operando.|  
  
 `type`  
 Opcional a menos que `Option Strict` esté establecido en `On`.  Tipos de datos del valor que devuelve el procedimiento de operador.  
  
 `statements`  
 Opcional.  Bloquee de instrucciones que ejecuta el procedimiento de operador.  
  
 `returnvalue`  
 Obligatorio.  El valor que el procedimiento de operador devuelve al código de llamada.  
  
 `End` `Operator`  
 Obligatorio.  Termina la definición de este procedimiento de operador.  
  
## Comentarios  
 Sólo puede utilizar `Operator` en una clase o una estructura.  Esto significa que el *contexto de declaración* de un operador no puede ser un archivo de código fuente, espacio de nombres, módulo, interfaz, procedimiento o bloque.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Todos los operadores deben ser de tipo `Public Shared`.  No puede especificar `ByRef`, `Optional` o `ParamArray` en ningún operando.  
  
 No puede utilizar el símbolo o identificador de operador para incluir un valor devuelto.  Debe utilizar la instrucción `Return` y debe especificar un valor.  Puede aparecer cualquier número de instrucciones `Return` en cualquier lugar de un procedimiento.  
  
 La definición de un operador de esta manera se denomina *sobrecarga de operadores*, independientemente de si utiliza la palabra clave `Overloads`.  En la siguiente tabla se muestran los operadores que se pueden definir.  
  
|Tipo|Operadores|  
|----------|----------------|  
|Unario|`+`, `-`, `IsFalse`, `IsTrue`, `Not`|  
|Binary|`+`, `-`, `*`, `/`, `\`, `&`, `^`, `>>`, `<<`, `=`, `<>`, `>`, `>=`, `<`, `<=`, `And`, `Like`, `Mod`, `Or`, `Xor`|  
|Conversión \(unario\)|`CType`|  
  
 Observe que el operador `=` en la lista binaria es el operador de comparación, no el operador de asignación.  
  
 Cuando define `CType`, debe especificar `Widening` o `Narrowing`.  
  
## Pares correspondientes  
 Debe definir ciertos operadores como pares correspondientes.  Si define un operador de este tipo, también debe definir el otro.  Los pares correspondientes son los siguientes:  
  
-   `=` y `<>`  
  
-   `>` y `<`  
  
-   `>=` y `<=`  
  
-   `IsTrue` y `IsFalse`  
  
## Restricciones de tipos de datos  
 Cada operador que define debe implicar la clase o estructura donde lo define.  Esto significa que la clase o estructura debe aparecer como tipo de datos de los elementos siguientes:  
  
-   El operando de un operador unario.  
  
-   Al menos uno de los operandos de un operador binario.  
  
-   El operando o el tipo de valor devuelto de un operador de conversión.  
  
 Ciertos operadores tienen restricciones adicionales de tipo de datos, como las siguientes:  
  
-   Si define los operadores `IsTrue` y `IsFalse`, ambos deben devolver el tipo `Boolean`.  
  
-   Si define los operadores `<<` y `>>`, ambos deben especificar el tipo `Integer` en `operandtype` y `operand2`.  
  
 El tipo de valor devuelto no tiene que corresponder con el tipo de un operando.  Por ejemplo, un operador de comparación como `=` o `<>` puede devolver un valor de tipo `Boolean` aunque ninguno de los operandos sea de tipo `Boolean`.  
  
## Operadores lógicos y bit a bit  
 Los operadores `And`, `Or`, `Not` y `Xor` pueden realizar operaciones bit a bit o lógicas en Visual Basic.  Sin embargo, si define uno de estos operadores en una clase o estructura, sólo puede definir su operación bit a bit.  
  
 No puede definir directamente el operador `AndAlso` con una instrucción `Operator`.  Sin embargo, puede utilizar `AndAlso` si ha cumplido las condiciones siguientes:  
  
-   Ha definido `And` en los mismos tipos de operando que desea utilizar para `AndAlso`.  
  
-   Su definición de `And` devuelve el mismo tipo que la clase o estructura donde lo ha definido.  
  
-   Ha definido el operador `IsFalse` en la clase o estructura donde ha definido `And`.  
  
 De la misma forma, puede utilizar `OrElse` si ha definido `Or` en los mismos operandos, con el tipo de valor devuelto de la clase o estructura, y ha definido `IsTrue` en la clase o estructura.  
  
## Conversiones de ampliación y de restricción  
 Una *conversión de ampliación* siempre es correcta en tiempo de ejecución, mientras que una *conversión de restricción* puede generar un error en tiempo de ejecución.  Para obtener más información, vea [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
 Si declara un procedimiento de conversión de tipo `Widening`, su código de procedimiento no debe generar ningún error.  Esto significa lo siguiente:  
  
-   Siempre debe devolver un valor válido de tipo `type`.  
  
-   Debe controlar todas las excepciones posibles y otras condiciones de error.  
  
-   Debe controlar cualquier retorno del error de cualquier procedimiento al que llama.  
  
 Si existe alguna posibilidad de que un procedimiento de conversión genere un error o una excepción no controlada, debe declararlo de tipo `Narrowing`.  
  
## Ejemplo  
 En el ejemplo de código siguiente se usa la instrucción `Operator` para definir el esquema de una estructura que incluye procedimientos de los operadores `And`, `Or`, `IsTrue` e `IsFalse`.  `And` y `Or` toman cada uno dos operandos de tipo `abc` y devuelven un valor de tipo `abc`.  `IsFalse` e `IsTrue` toman cada uno un único operando de tipo `abc` y devuelven un valor de tipo `Boolean`.  Estas definiciones permiten al código de llamada utilizar `And`, `AndAlso`, `Or` y `OrElse` con operandos de tipo `abc`.  
  
 [!code-vb[VbVbalrStatements#44](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/operator-statement_1.vb)]  
  
## Vea también  
 [IsFalse \(Operador\)](../../../visual-basic/language-reference/operators/isfalse-operator.md)   
 [IsTrue \(Operador\)](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Conversiones de ampliación y de restricción](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Cómo: Llamar a un procedimiento de operador](../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Cómo: Utilizar una clase que define operadores](../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)