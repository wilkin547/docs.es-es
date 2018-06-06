---
title: Procedimientos de operador (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 5b4641ce8509e3111a11ed803d36194d5a301bce
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805716"
---
# <a name="operator-procedures-visual-basic"></a>Procedimientos de operador (Visual Basic)
Un procedimiento de operador es una serie de instrucciones de Visual Basic que definen el comportamiento de un operador estándar (como `*`, `<>`, o `And`) en una clase o estructura que ha definido. También se denomina *sobrecarga de operadores*.  
  
## <a name="when-to-define-operator-procedures"></a>Cuándo se debe definir procedimientos de operadores  
 Una vez haya definido una clase o estructura, puede declarar variables del tipo de esa clase o estructura. A veces, estas variables deben participar en una operación como parte de una expresión. Para ello, debe ser un operando de un operador.  
  
 Visual Basic sólo define operadores en sus tipos de datos fundamentales. Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de dicha clase o estructura.  
  
 Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Tipos de procedimientos de operador  
 Un procedimiento de operador puede ser uno de los siguientes tipos:  
  
-   Definición de un operador unario donde el argumento es del tipo de la clase o estructura.  
  
-   Definición de un operador binario donde al menos uno de los argumentos es del tipo de la clase o estructura.  
  
-   Definición de un operador de conversión donde el argumento es del tipo de la clase o estructura.  
  
-   Definición de un operador de conversión que devuelve el tipo de dicha clase o estructura.  
  
 Operadores de conversión siempre son unarios y siempre utilizan `CType` como el operador que se va a definir.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un procedimiento de operador es como sigue:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol* `(` *operand1*`[,`*operand2* `]) As` *tipo de datos*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Usa el `Widening` o `Narrowing` palabra clave solo en un operador de conversión de tipos. El símbolo del operador siempre es [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) para un operador de conversión de tipos.  
  
 Declare dos operandos para definir un operador binario y declare un operando para definir un operador unario, incluido un operador de conversión de tipos. Todos los operandos deben declararse `ByVal`.  
  
 Declare cada operando de la misma manera que se pueden declarar parámetros para [Sub (procedimientos)](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Dado que va a definir un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura. Para un operador de conversión de tipo, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.  
  
 Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Invocar un procedimiento de operador implícitamente mediante el símbolo del operador en una expresión. Proporcione los operandos de la misma manera que lo hace para los operadores predefinidos.  
  
 La sintaxis de una llamada implícita a un procedimiento de operador es como sigue:  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol*  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Ilustración de declaración y llamada  
 La siguiente estructura almacena un valor entero con signo de 128 bits como las partes constituyentes de orden superior y de orden inferior. Define la `+` operador que se va a agregar dos `veryLong` valores y generar una resultante `veryLong` valor.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a la `+` operador definido en `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Para obtener más información y ejemplos, vea [Operator Overloading in Visual Basic 2005](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx) (Sobrecarga de operadores en Visual Basic 2005).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)  
 [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Definir un operador](./how-to-define-an-operator.md)  
 [Definir un operador de conversión](./how-to-define-a-conversion-operator.md)  
 [Llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)  
 [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
