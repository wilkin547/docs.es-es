---
title: Procedimientos de operadores (Visual Basic) | Documentos de Microsoft
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
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
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
ms.openlocfilehash: a9e86c9c466ba236cc33153f2f341af35c622de6
ms.lasthandoff: 03/13/2017

---
# <a name="operator-procedures-visual-basic"></a>Procedimientos de operador (Visual Basic)
Un procedimiento de operador es una serie de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] instrucciones que definen el comportamiento de un operador estándar (como `*`, `<>`, o `And`) en una clase o estructura que ha definido. También se denomina *sobrecarga de operadores*.  
  
## <a name="when-to-define-operator-procedures"></a>Cuándo definir procedimientos de operador  
 Cuando haya definido una clase o estructura, puede declarar las variables del tipo de esa clase o estructura. A veces estas variables deben participar en una operación como parte de una expresión. Para ello, debe ser un operando de un operador.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]sólo define operadores en sus tipos de datos fundamentales. Puede definir el comportamiento de un operador cuando uno o ambos operandos son del tipo de la clase o estructura.  
  
 Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Tipos de procedimientos de operador  
 Un procedimiento de operador puede ser uno de los siguientes tipos:  
  
-   Definición de un operador unario donde el argumento es del tipo de la clase o estructura.  
  
-   Definición de un operador binario donde al menos uno de los argumentos es del tipo de la clase o estructura.  
  
-   Definición de un operador de conversión donde el argumento es del tipo de la clase o estructura.  
  
-   Definición de un operador de conversión que devuelve el tipo de la clase o estructura.  
  
 Operadores de conversión siempre son unarios y siempre utilizan `CType` como el operador que se va a definir.  
  
## <a name="declaration-syntax"></a>Sintaxis de la declaración  
 La sintaxis para declarar un procedimiento de operador es la siguiente:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Utiliza la `Widening` o `Narrowing` palabra clave sólo en un operador de conversión de tipos. El símbolo del operador siempre es [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) para un operador de conversión de tipos.  
  
 Declare dos operandos para definir un operador binario y declare un operando para definir un operador unario, incluido un operador de conversión de tipos. Todos los operandos deben declararse `ByVal`.  
  
 Declare cada operando del mismo modo que se pueden declarar parámetros para [procedimientos Sub](./sub-procedures.md).  
  
### <a name="data-type"></a>Tipo de datos  
 Dado que va a definir un operador en una clase o estructura que ha definido, al menos uno de los operandos debe ser del tipo de datos de esa clase o estructura. Para un operador de conversión de tipo, el operando o el tipo de valor devuelto debe ser del tipo de datos de la clase o estructura.  
  
 Para obtener más información, consulte [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Sintaxis de llamada  
 Invocar un procedimiento de operador implícitamente mediante el símbolo de operador en una expresión. Proporcione los operandos de la misma manera que lo hace para los operadores predefinidos.  
  
 La sintaxis de una llamada implícita a un procedimiento de operador es la siguiente:  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*`= testStruct`*operatorsymbol    *  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Ejemplo de declaración y llamada  
 La estructura siguiente almacena un valor entero de 128 bits como las partes constitutivas de orden superior y de orden inferior. Define la `+` operador para agregar dos `veryLong` valores y generar una resultante `veryLong` valor.  
  
 [!code-vb[23 de VbVbcnProcedures #](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica a la `+` operador definido en `veryLong`.  
  
 [!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Para obtener más información y ejemplos, vea [sobrecarga de operadores en Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Operator (instrucción)](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Cómo: definir un operador](./how-to-define-an-operator.md)   
 [Cómo: definir un operador de conversión](./how-to-define-a-conversion-operator.md)   
 [Cómo: llamar a un procedimiento de operador](./how-to-call-an-operator-procedure.md)   
 [Utilizar una clase que define operadores](./how-to-use-a-class-that-defines-operators.md)
