---
title: "Procedimientos de operador (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "sobrecarga de operadores"
  - "procedimientos de operadores"
  - "operadores [Visual Basic], sobrecargar"
  - "operadores sobrecargados"
  - "procedimientos, operador"
  - "sintaxis, procedimientos de operadores"
  - "código de Visual Basic, operadores"
  - "código de Visual Basic, procedimientos"
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Procedimientos de operador (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un procedimiento de operador es una serie de instrucciones [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] que definen el comportamiento de un operador estándar \(como `*`, `<>` o `And`\) en una clase o estructura definida,  lo que también se conoce como *sobrecarga de operadores*.  
  
## Cuándo definir procedimientos de operador  
 Tras definir una clase o estructura, puede declarar las variables para que pertenezcan al tipo de dicha clase o estructura.  A veces estas variables deben participar en una operación como parte de una expresión.  Para ello, estas variables deben ser un operando de un operador.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] sólo define operadores en sus tipos de datos fundamentales.  Puede definir el comportamiento de un operador cuando uno o los dos operandos pertenecen al tipo de la clase o de la estructura.  
  
 Para obtener más información, vea [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Tipos de procedimientos de operador  
 Los procedimientos de operador pueden ser de uno de los siguientes tipos:  
  
-   Una definición de un operador unario donde el argumento pertenece al tipo de la clase o estructura.  
  
-   Una definición de un operador binario donde al menos uno de los argumentos pertenece al tipo de la clase o estructura.  
  
-   Una definición de un operador de conversión donde el argumento pertenece al tipo de la clase o estructura.  
  
-   Una definición de un operador de conversión que devuelve el tipo de la clase o estructura.  
  
 Los operadores de conversión siempre son unarios y siempre utilizan `CType` como el operador que se está definiendo.  
  
## Sintaxis de la declaración  
 La sintaxis para declarar un procedimiento de operador es la siguiente:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`   ``  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Utilice únicamente la palabra clave `Widening` o `Narrowing` en un operador de conversión de tipos.  El símbolo del operador siempre es [CType \(Función\)](../../../../visual-basic/language-reference/functions/ctype-function.md) en un operador de conversión de tipos.  
  
 Declare dos operandos para definir un operador binario y declare un operando para definir un operador unario, incluidos los operadores de conversión de tipos.  Todos los operandos deben declararse `ByVal`.  
  
 Declare cada operando del mismo modo que declara los parámetros de [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Tipo de datos  
 Como está definiendo un operador de una clase o estructura que ha definido, al menos uno de los operandos debe tener el mismo tipo de datos que la clase o la estructura.  En un operador de conversión de tipos, el operando o el tipo de valor devuelto debe pertenecer al tipo de datos de la clase o estructura.  
  
 Para obtener más detalles, consulte [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Sintaxis de llamada  
 Para invocar un procedimiento de operador de forma implícita, utilice el símbolo del operador en una expresión.  Proporcione los operandos de la misma manera que proporciona los operadores predefinidos.  
  
 La sintaxis de una llamada implícita a un procedimiento de operador es la siguiente:  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *structurename*  `= testStruct`  *operatorsymbol*  `10`  
  
### Ejemplo de declaración y llamada  
 La estructura siguiente almacena un valor entero con signo de 128 bits como las partes constitutivas de orden superior y de orden inferior.  Esta estructura define el operador `+` para agregar dos valores  `veryLong`  y generar un valor  `veryLong`  resultante.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 En el ejemplo siguiente se muestra una llamada típica al operador `+` establecido en  `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Para obtener más información y ejemplos, vea [Sobrecarga en Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703)  
  
## Vea también  
 [Procedimientos](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedimientos Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedimientos Function](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Procedimientos de propiedad](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Argumentos y parámetros de procedimiento](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Operator \(Instrucción\)](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Cómo: Definir un operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [Cómo: Definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [Cómo: Llamar a un procedimiento de operador](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [Cómo: Utilizar una clase que define operadores](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)