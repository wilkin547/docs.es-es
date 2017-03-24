---
title: Solucionar problemas de procedimientos (Visual Basic) | Documentos de Microsoft
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
- troubleshooting Visual Basic, procedures
- procedures, troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures, about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: a5445d6da982e4eea5b1047505e4bee3380ed472
ms.lasthandoff: 03/13/2017

---
# <a name="troubleshooting-procedures-visual-basic"></a>Solucionar problemas de procedimientos (Visual Basic)
Esta página muestra algunos problemas comunes que pueden producirse al trabajar con procedimientos.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Devolver un tipo de matriz de un procedimiento de función  
 Si un `Function` procedimiento devuelve un tipo de datos de matriz, no puede utilizar el `Function` nombre para almacenar valores en los elementos de la matriz. Si intenta hacerlo, el compilador lo interpreta como una llamada a la `Function`. El ejemplo siguiente genera errores del compilador.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 La instrucción `allOnes(i) = 1` genera un error de compilador porque llama a `allOnes` con un argumento de tipo de datos incorrecto (un singleton `Integer` en lugar de un `Integer` matriz). La instrucción `Return allOnes()` genera un error de compilador porque llama a `allOnes` sin ningún argumento.  
  
 **El enfoque correcto:** para que pueda modificar los elementos de una matriz que se devuelve, definir una matriz interna como una variable local. En el ejemplo siguiente se compila sin errores.  
  
 [!code-vb[VbVbcnProcedures&#66;](./codesnippet/VisualBasic/troubleshooting-procedures_1.vb)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>Argumento no modificado por llamada a procedimiento  
 Si desea permitir a un procedimiento cambiar un elemento de programación subyacente a un argumento en el código de llamada, debe pasar por referencia. Pero un procedimiento puede tener acceso a los elementos de un argumento de tipo de referencia incluso si se pasa por valor.  
  
-   **Subyacente de la Variable**. Para permitir que el procedimiento reemplazar el valor de la variable subyacente propio, el procedimiento debe declarar el parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Además, el código de llamada no debe incluir tampoco el argumento entre paréntesis, porque eso reemplazaría el `ByRef` mecanismo para pasar argumentos.  
  
-   **Hacer referencia a elementos de tipo**. Si declara un parámetro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), el procedimiento no puede modificar el propio elemento variable subyacente. Sin embargo, si el argumento es un tipo de referencia, el procedimiento puede modificar los miembros del objeto al que señala, aunque no puede reemplazar el valor de la variable. Por ejemplo, si el argumento es una variable de matriz, el procedimiento no puede asignarle una nueva matriz, pero puede cambiar uno o más de sus elementos. Los elementos cambiados se reflejan en la variable de matriz subyacente al código de llamada.  
  
 El siguiente ejemplo define dos procedimientos que toman una variable de matriz por valor y operan con sus elementos. Procedimiento `increase` simplemente agrega una unidad a cada elemento. Procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una unidad a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente al código de llamada porque `a()` se declara `ByVal`.  
  
 [!code-vb[VbVbcnProcedures&#35;](./codesnippet/VisualBasic/troubleshooting-procedures_2.vb)]  
  
 [!code-vb[VbVbcnProcedures&#38;](./codesnippet/VisualBasic/troubleshooting-procedures_3.vb)]  
  
 En el ejemplo siguiente se realizan llamadas a `increase` y `replace`.  
  
 [!code-vb[VbVbcnProcedures&#37;](./codesnippet/VisualBasic/troubleshooting-procedures_4.vb)]  
  
 La primera `MsgBox` llamada a muestra "después Increase (n): 11, 21, 31, 41". Porque `n` es un tipo de referencia, `increase` puede cambiar sus miembros, aunque se pasa `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después Replace (n): 11, 21, 31, 41". Porque `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` asignándole una nueva matriz. Cuando `replace` crea la nueva instancia de la matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` pasados por el código de llamada. Cuando incrementa los miembros de `a`, solo la matriz local `k` se ve afectado.  
  
 **El enfoque correcto:** para poder modificar un elemento de variable subyacente propio, pasar por referencia. En el ejemplo siguiente se muestra el cambio en la declaración de `replace` que le permite reemplazar una matriz por otra en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures&#64;](./codesnippet/VisualBasic/troubleshooting-procedures_5.vb)]  
  
## <a name="unable-to-define-an-overload"></a>No se puede definir una sobrecarga  
 Si desea definir una versión sobrecargada de un procedimiento, debe usar el mismo nombre pero una firma diferente. Si el compilador no puede diferenciar su declaración de una sobrecarga con la misma firma, genera un error.  
  
 El *firma* de un procedimiento viene determinado por el nombre del procedimiento y la lista de parámetros. Cada sobrecarga debe tener el mismo nombre que todas las demás sobrecargas pero debe ser diferente de todas ellas en al menos uno de los demás componentes de la firma. Para obtener más información, consulte [sobrecarga de procedimientos](./procedure-overloading.md).  
  
 Los elementos siguientes, aunque pertenecen a la lista de parámetros, no forman parte de la firma de un procedimiento:  
  
-   Palabras clave de modificadores de procedimiento como `Public`, `Shared`, y`Static`  
  
-   Nombres de parámetro  
  
-   Palabras clave de modificador de parámetro, como `ByRef` y`Optional`  
  
-   El tipo de datos del valor devuelto (excepto para un operador de conversión)  
  
 No se puede sobrecargar un procedimiento cambiando únicamente uno o varios de los elementos anteriores.  
  
 **El enfoque correcto:** para poder definir una sobrecarga de procedimiento, debe variar la firma. Dado que debe utilizar el mismo nombre, debe variar el número, orden o tipos de datos de los parámetros. En un procedimiento genérico, puede variar el número de parámetros de tipo. En un operador de conversión ([CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md)), puede variar el tipo de valor devuelto.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con opcional y ParamArray (argumentos)  
 Si se sobrecarga un procedimiento con uno o varios [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetros o un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, debe evitar duplicarlas la *sobrecargas implícitas*. Para obtener información, consulte [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>Llamar a una versión incorrecta de un procedimiento sobrecargado  
 Si un procedimiento tiene varias versiones sobrecargadas, debe estar familiarizado con todas las listas de parámetros y comprender cómo [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resuelve las llamadas entre las sobrecargas. De lo contrario, podría llamar a una sobrecarga que no sea el deseado.  
  
 Cuando haya determinado qué sobrecarga desea llamar, asegúrese de observar las reglas siguientes:  
  
-   Proporcione el número correcto de argumentos y en el orden correcto.  
  
-   Idealmente, los argumentos deben tener los mismos tipos de datos exactos que los parámetros correspondientes. En cualquier caso, el tipo de datos de cada argumento debe ampliarse de su parámetro correspondiente. Esto es cierto incluso con la [Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establecido en `Off`. Si una sobrecarga requiere cualquier conversión de restricción de la lista de argumentos que sobrecargan no es apto para llamar.  
  
-   Si proporciona argumentos que requieren ampliación, asegúrese de sus tipos de datos lo más cerca posible de los tipos de datos de parámetro correspondiente. Si dos o más sobrecargas aceptan los tipos de datos del argumento, el compilador resuelve la llamada a la sobrecarga que requiere la menor cantidad de ampliación.  
  
 Puede reducir la posibilidad de tipo de datos mediante la [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) palabra clave de conversión cuando prepara los argumentos.  
  
### <a name="overload-resolution-failure"></a>Error de resolución de sobrecarga  
 Cuando se llama a un procedimiento sobrecargado, el compilador intenta eliminar todas menos una de las sobrecargas. Si lo consigue, resuelve la llamada a esa sobrecarga. Si elimina todas las sobrecargas, o si no puede reducir las sobrecargas seleccionables a un candidato único, genera un error.  
  
 En el ejemplo siguiente se muestra el proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures&#62;](./codesnippet/VisualBasic/troubleshooting-procedures_6.vb)]  
  
 [!code-vb[VbVbcnProcedures&#63;](./codesnippet/VisualBasic/troubleshooting-procedures_7.vb)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento (`Short`) se restringe al tipo del parámetro correspondiente (`Byte`). A continuación, elimina la tercera sobrecarga porque cada argumento de tipo en la segunda sobrecarga (`Short` y `Single`) se amplía al tipo correspondiente en la tercera sobrecarga (`Integer` y `Single`). La segunda sobrecarga requiere una ampliación menor, por lo que el compilador utiliza para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas sobre la base de restricción. Elimina la tercera sobrecarga por la misma razón que en la primera llamada, porque se puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y la segunda sobrecarga. Cada uno tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro (`Byte` a `Short`, pero `Single` a `Double`). Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
 **El enfoque correcto:** para poder llamar a un procedimiento sobrecargado sin ambigüedades, use [CType (función)](../../../../visual-basic/language-reference/functions/ctype-function.md) para que coincida con los tipos de datos de argumento con los tipos de parámetro. En el ejemplo siguiente se muestra una llamada a `z` que fuerza la resolución a la segunda sobrecarga.  
  
 [!code-vb[VbVbcnProcedures&#65;](./codesnippet/VisualBasic/troubleshooting-procedures_8.vb)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con opcional y ParamArray (argumentos)  
 Si dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que se declara el último parámetro [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) en uno y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en la otra, el compilador resuelve una llamada a ese procedimiento según la coincidencia más cercana. Para obtener más información, consulte [resolución de sobrecarga](./overload-resolution.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)   
 [Sub (procedimientos)](./sub-procedures.md)   
 [Function (procedimientos)](./function-procedures.md)   
 [Property (procedimientos)](./property-procedures.md)   
 [Procedimientos de operadores](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)   
 [Resolución de sobrecargas](./overload-resolution.md)
