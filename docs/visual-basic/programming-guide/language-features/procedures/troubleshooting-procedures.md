---
title: Solucionar problemas de procedimientos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: 492a7474a38a7e41b7e3b3f59dfa118c30256ea4
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58830141"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Solucionar problemas de procedimientos (Visual Basic)
Esta página enumera algunos problemas comunes que pueden producirse al trabajar con procedimientos.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Devuelve un tipo de matriz de un procedimiento Function  
 Si un `Function` procedimiento devuelve un tipo de datos de matriz, no se puede usar el `Function` nombre para almacenar valores en los elementos de la matriz. Si intenta hacerlo, el compilador lo interpreta como una llamada a la `Function`. El ejemplo siguiente genera errores del compilador.  
  
 `Function allOnes(ByVal n As Integer) As Integer()`  
  
 `For i As Integer = 1 To n - 1`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `allOnes(i) = 1`  
  
 `Next i`  
  
 `' The following statement generates a`   `COMPILER ERROR`  `.`  
  
 `Return allOnes()`  
  
 `End Function`  
  
 La instrucción `allOnes(i) = 1` genera un error del compilador porque llama a `allOnes` con un argumento de tipo de datos erróneo (un singleton `Integer` en lugar de un `Integer` matriz). La instrucción `Return allOnes()` genera un error del compilador porque llama a `allOnes` sin ningún argumento.  
  
 **Enfoque correcto:** Para poder modificar los elementos de una matriz que se va a devolver, definir una matriz interna como una variable local. El ejemplo siguiente se compila sin errores.  
  
 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]  
  
## <a name="argument-not-being-modified-by-procedure-call"></a>No se está modificando el argumento por llamada a procedimiento  
 Si piensa permitir que un procedimiento cambiar un elemento de programación subyacente a un argumento en el código de llamada, debe pasar por referencia. Pero un procedimiento puede tener acceso a los elementos de un argumento de tipo de referencia, incluso si se pasa por valor.  
  
-   **Subyacente Variable**. Para permitir que el procedimiento reemplazar el valor de la variable subyacente propio, el procedimiento debe declarar el parámetro [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). Además, el código de llamada debe no incluya el argumento entre paréntesis, porque eso reemplazaría el `ByRef` mecanismo que pasa.  
  
-   **Hacer referencia a elementos de tipo**. Si declara un parámetro [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md), el procedimiento no puede modificar el propio elemento variable subyacente. Sin embargo, si el argumento es un tipo de referencia, el procedimiento puede modificar los miembros del objeto al que señala, aunque no puede reemplazar el valor de la variable. Por ejemplo, si el argumento es una variable de matriz, el procedimiento no puede asignar una nueva matriz a él, pero pueden cambiar uno o varios de sus elementos. Los elementos modificados se reflejan en la variable de matriz subyacente en el código de llamada.  
  
 El siguiente ejemplo define dos procedimientos que toman una variable de matriz por valor y operan en sus elementos. Procedimiento `increase` simplemente agrega uno a cada elemento. Procedimiento `replace` asigna una nueva matriz al parámetro `a()` y, a continuación, agrega uno a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada porque `a()` se declara `ByVal`.  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 El ejemplo siguiente realiza llamadas a `increase` y `replace`.  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 La primera `MsgBox` llamada a muestra "después de Increase (n): 11, 21, 31, 41". Dado que `n` es un tipo de referencia, `increase` puede cambiar sus miembros, incluso si se pasa `ByVal`.  
  
 El segundo `MsgBox` llamada a muestra "después de Replace (n): 11, 21, 31, 41". Dado que `n` se pasa `ByVal`, `replace` no se puede modificar la variable `n` asignándole una nueva matriz. Cuando `replace` crea la nueva instancia de matriz `k` y lo asigna a la variable local `a`, pierde la referencia a `n` pasada por el código de llamada. Cuando incrementa los miembros de `a`, solo la matriz local `k` se ve afectado.  
  
 **Enfoque correcto:** Para poder modificar un elemento de variable subyacente Sí, pasar por referencia. El ejemplo siguiente muestra el cambio en la declaración de `replace` que le permite reemplazar una matriz con otro en el código de llamada.  
  
 [!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]  
  
## <a name="unable-to-define-an-overload"></a>No se puede definir una sobrecarga  
 Si desea definir una versión sobrecargada de un procedimiento, debe usar el mismo nombre pero una firma diferente. Si el compilador no puede diferenciar su declaración de una sobrecarga con la misma firma, genera un error.  
  
 El *firma* de un procedimiento viene determinada por el nombre del procedimiento y la lista de parámetros. Cada sobrecarga debe tener el mismo nombre que todas las demás sobrecargas pero debe diferir de todas ellas en al menos uno de los demás componentes de la firma. Para obtener más información, consulta [Procedure Overloading](./procedure-overloading.md).  
  
 Los elementos siguientes, aunque pertenecen a la lista de parámetros, no forman parte de firma de un procedimiento:  
  
-   Palabras clave de modificador de procedimiento, como `Public`, `Shared`, y `Static`  
  
-   Nombres de parámetro  
  
-   Palabras clave de modificador de parámetro, como `ByRef` y `Optional`  
  
-   El tipo de datos del valor devuelto (excepto para un operador de conversión)  
  
 No se puede sobrecargar un procedimiento cambiando únicamente uno o varios de los elementos anteriores.  
  
 **Enfoque correcto:** Para poder definir una sobrecarga de procedimiento, debe variar la firma. Dado que debe usar el mismo nombre, debe variar el número, orden o tipos de datos de los parámetros. En un procedimiento genérico, puede cambiar el número de parámetros de tipo. En un operador de conversión ([CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md)), puede variar el tipo de valor devuelto.  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con opcional y ParamArray (argumentos)  
 Si se sobrecarga un procedimiento con uno o varios [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) parámetros o un [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parámetro, debe evitar la duplicación de cualquiera de los *sobrecargas implícitas*. Para obtener información, consulte [consideraciones en sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).  
  
## <a name="calling-a-wrong-version-of-an-overloaded-procedure"></a>Una llamada a una versión incorrecta de un procedimiento sobrecargado  
 Si un procedimiento tiene varias versiones sobrecargadas, debe estar familiarizado con todas las listas de parámetros y comprender cómo resuelve las llamadas entre las sobrecargas de Visual Basic. En caso contrario, podría llamar a una sobrecarga que no sea el deseado.  
  
 Cuando haya determinado qué sobrecarga que desea llamar, tenga cuidado para observar las reglas siguientes:  
  
-   Proporcione el número correcto de argumentos y en el orden correcto.  
  
-   Idealmente, los argumentos deben tener los mismos tipos de datos exactos que los parámetros correspondientes. En cualquier caso, el tipo de datos de cada argumento debe ampliarse del parámetro correspondiente. Esto es cierto incluso con la [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) establecido en `Off`. Si una sobrecarga requiere cualquier conversión de restricción de la lista de argumentos, que sobrecarga no es apto para llamarlo.  
  
-   Si se suministran argumentos que requieren la ampliación, asegúrese de sus tipos de datos más cerca posible de los tipos de datos del parámetro correspondiente. Si dos o más sobrecargas aceptan los tipos de datos de argumento, el compilador resuelve la llamada a la sobrecarga que requiere la menor cantidad de ampliación.  
  
 Puede reducir la posibilidad de errores de coincidencia de tipo de datos utilizando el [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) palabra clave de conversión cuando prepara los argumentos.  
  
### <a name="overload-resolution-failure"></a>Error de resolución de sobrecarga  
 Cuando se llama a un procedimiento sobrecargado, el compilador intenta eliminar todas menos una de las sobrecargas. Si se realiza correctamente, se resuelve como la llamada a esa sobrecarga. Si elimina todas las sobrecargas, o si no puede reducir las sobrecargas aptas para un único candidato, genera un error.  
  
 El ejemplo siguiente ilustra el proceso de resolución de sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]  
  
 [!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]  
  
 En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento (`Short`) se restringe al tipo del parámetro correspondiente (`Byte`). A continuación, elimina la tercera sobrecarga porque cada argumento de tipo en la segunda sobrecarga (`Short` y `Single`) se amplía al tipo correspondiente en la tercera sobrecarga (`Integer` y `Single`). La segunda sobrecarga requiere menos ampliación, por lo que el compilador lo usa para la llamada.  
  
 En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas en función de restricción. Elimina la tercera sobrecarga por la misma razón, como se muestra en la primera llamada, porque puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y segunda sobrecarga. Cada uno tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro (`Byte` a `Short`, pero `Single` a `Double`). Por lo tanto, el compilador genera un error de resolución de sobrecarga.  
  
 **Enfoque correcto:** Para poder llamar a un procedimiento sobrecargado sin ambigüedades, utilice [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) para que coincida con los tipos de datos de argumento para los tipos de parámetro. El ejemplo siguiente muestra una llamada a `z` que fuerza la resolución a la segunda sobrecarga.  
  
 [!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]  
  
### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con opcional y ParamArray (argumentos)  
 Si las dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que se declara el último parámetro [opcional](../../../../visual-basic/language-reference/modifiers/optional.md) en uno y [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) en el otro, el compilador resuelve una llamada a ese procedimiento. según la coincidencia más cercana. Para obtener más información, consulta [Overload Resolution](./overload-resolution.md).  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md)
- [Resolución de sobrecargas](./overload-resolution.md)
