---
description: 'Más información sobre: procedimientos de solución de problemas (Visual Basic)'
title: Procedimientos de solución de problemas
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: a36e2ef9442fc0e76c9a98e83007976393e7957b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471154"
---
# <a name="troubleshooting-procedures-visual-basic"></a>Procedimientos de solución de problemas (Visual Basic)

En esta página se enumeran algunos problemas comunes que pueden producirse al trabajar con procedimientos.  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a>Devolver un tipo de matriz a partir de un procedimiento de función

Si un `Function` procedimiento devuelve un tipo de datos de matriz, no se puede usar el `Function` nombre para almacenar valores en los elementos de la matriz. Si intenta hacerlo, el compilador lo interpreta como una llamada a `Function` . En el ejemplo siguiente se generan errores del compilador:
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

La instrucción `AllOnes(i) = 1` genera un error del compilador porque parece llamar a `AllOnes` con un argumento del tipo de datos incorrecto (un valor escalar `Integer` en lugar de una `Integer` matriz). La instrucción `Return AllOnes()` genera un error del compilador porque parece que llama a `AllOnes` sin ningún argumento.  
  
 **Enfoque correcto:** Para poder modificar los elementos de una matriz que se va a devolver, defina una matriz interna como variable local. En el ejemplo siguiente se compila sin errores:

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a>Argumento no modificado por la llamada a procedimiento

Si desea permitir que un procedimiento cambie un elemento de programación subyacente a un argumento en el código de llamada, debe pasarlo por referencia. Pero un procedimiento puede tener acceso a los elementos de un argumento de tipo de referencia, incluso si se pasa por valor.

- **Variable subyacente**. Para permitir que el procedimiento Reemplace el valor del elemento variable subyacente, el procedimiento debe declarar el parámetro [ByRef](../../../language-reference/modifiers/byref.md). Además, el código de llamada no debe incluir el argumento entre paréntesis, porque esto invalidaría el `ByRef` mecanismo de paso.

- **Elementos de tipo de referencia**. Si declara un parámetro [ByVal](../../../language-reference/modifiers/byval.md), el procedimiento no podrá modificar el propio elemento de variable subyacente. Sin embargo, si el argumento es un tipo de referencia, el procedimiento puede modificar los miembros del objeto al que señala, aunque no puede reemplazar el valor de la variable. Por ejemplo, si el argumento es una variable de matriz, el procedimiento no puede asignarle una nueva matriz, pero puede cambiar uno o varios de sus elementos. Los elementos modificados se reflejan en la variable de matriz subyacente en el código de llamada.

En el ejemplo siguiente se definen dos procedimientos que toman una variable de matriz por valor y operan en sus elementos. El procedimiento `increase` simplemente agrega uno a cada elemento. `replace`El procedimiento asigna una nueva matriz al parámetro `a()` y, a continuación, agrega una a cada elemento. Sin embargo, la reasignación no afecta a la variable de matriz subyacente en el código de llamada porque `a()` se declara `ByVal` .

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

En el ejemplo siguiente se realizan llamadas a `increase` y `replace` :

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
La primera `MsgBox` llamada muestra "después del aumento (n): 11, 21, 31, 41". Dado `n` que es un tipo de referencia, `increase` puede cambiar sus miembros, aunque se pase `ByVal` .

La segunda `MsgBox` llamada muestra "After Replace (n): 11, 21, 31, 41". Dado `n` que se pasa `ByVal` , `replace` no se puede modificar la variable `n` mediante la asignación de una nueva matriz a ella. Cuando `replace` crea la nueva instancia de la matriz `k` y la asigna a la variable local `a` , pierde la referencia a `n` pasada por el código de llamada. Cuando incrementa los miembros de `a` , solo `k` se ve afectada la matriz local.

**Enfoque correcto:** Para poder modificar un elemento variable subyacente, páselo por referencia. En el ejemplo siguiente se muestra el cambio en la declaración de `replace` que le permite reemplazar una matriz por otra en el código de llamada:

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a>No se puede definir una sobrecarga

Si desea definir una versión sobrecargada de un procedimiento, debe usar el mismo nombre pero una firma diferente. Si el compilador no puede diferenciar su declaración de una sobrecarga con la misma firma, genera un error.

La *firma* de un procedimiento viene determinada por el nombre del procedimiento y la lista de parámetros. Cada sobrecarga debe tener el mismo nombre que las demás sobrecargas, pero debe ser diferente de todas en al menos uno de los demás componentes de la firma. Para obtener más información, consulta [Procedure Overloading](./procedure-overloading.md).

Los elementos siguientes, aunque pertenezcan a la lista de parámetros, no son componentes de la firma de un procedimiento:

- Palabras clave de modificador de procedimientos, como `Public` , `Shared` y `Static` .
- Nombres de parámetro.
- Palabras clave de modificador de parámetro, como `ByRef` y `Optional` .
- El tipo de datos del valor devuelto (excepto para un operador de conversión).

No se puede sobrecargar un procedimiento cambiando solo uno o varios de los elementos anteriores.

**Enfoque correcto:** Para poder definir una sobrecarga de procedimiento, debe modificar la firma. Como debe utilizar el mismo nombre, debe variar el número, el orden o los tipos de datos de los parámetros. En un procedimiento genérico, puede variar el número de parámetros de tipo. En un operador de conversión ([función ctype](../../../language-reference/functions/ctype-function.md)), puede modificar el tipo de valor devuelto.

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con argumentos opcionales y ParamArray

Si va a sobrecargar un procedimiento con uno o varios parámetros [opcionales](../../../language-reference/modifiers/optional.md) o un parámetro [ParamArray](../../../language-reference/modifiers/paramarray.md) , debe evitar duplicar cualquiera de las *sobrecargas implícitas*. Para obtener más información, vea [consideraciones sobre la sobrecarga de procedimientos](./considerations-in-overloading-procedures.md).

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a>Llamar a la versión incorrecta de un procedimiento sobrecargado

Si un procedimiento tiene varias versiones sobrecargadas, debe estar familiarizado con todas sus listas de parámetros y comprender cómo resuelve Visual Basic las llamadas entre las sobrecargas. De lo contrario, podría llamar a una sobrecarga distinta de la deseada.

Cuando haya determinado qué sobrecarga desea llamar, tenga cuidado de observar las siguientes reglas:

- Proporcione el número correcto de argumentos y en el orden correcto.  
- Idealmente, los argumentos deben tener exactamente los mismos tipos de datos que los parámetros correspondientes. En cualquier caso, el tipo de datos de cada argumento debe ampliarse al de su parámetro correspondiente. Esto es así incluso con la [instrucción Option Strict](../../../language-reference/statements/option-strict-statement.md) establecida en `Off` . Si una sobrecarga requiere una conversión de restricción de la lista de argumentos, esa sobrecarga no es válida para llamarla.
- Si proporciona argumentos que requieren ampliación, realice sus tipos de datos lo más cerca posible de los tipos de datos de parámetro correspondientes. Si dos o más sobrecargas aceptan los tipos de datos de argumento, el compilador resuelve la llamada a la sobrecarga que llama a la menor cantidad de ampliación.

Puede reducir la posibilidad de que los tipos de datos no coincidan con la palabra clave de conversión de [funciones ctype](../../../language-reference/functions/ctype-function.md) al preparar los argumentos.

### <a name="overload-resolution-failure"></a>Error de resolución de sobrecarga

Cuando se llama a un procedimiento sobrecargado, el compilador intenta eliminar todas las sobrecargas excepto una. Si se realiza correctamente, resuelve la llamada a esa sobrecarga. Si elimina todas las sobrecargas, o si no puede reducir las sobrecargas válidas a un solo candidato, se genera un error.

En el ejemplo siguiente se muestra el proceso de resolución de sobrecarga:

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
En la primera llamada, el compilador elimina la primera sobrecarga porque el tipo del primer argumento ( `Short` ) se limita al tipo del parámetro correspondiente ( `Byte` ). A continuación, elimina la tercera sobrecarga porque cada tipo de argumento de la segunda sobrecarga ( `Short` y `Single` ) se amplía al tipo correspondiente en la tercera sobrecarga ( `Integer` y `Single` ). La segunda sobrecarga requiere menos ampliación, por lo que el compilador la usa para la llamada.

En la segunda llamada, el compilador no puede eliminar ninguna de las sobrecargas en función de la restricción. Elimina la tercera sobrecarga por la misma razón que en la primera llamada, porque puede llamar a la segunda sobrecarga con menos ampliación de los tipos de argumento. Sin embargo, el compilador no puede resolver entre la primera y la segunda sobrecarga. Cada tiene un tipo de parámetro definido que se amplía al tipo correspondiente en el otro ( `Byte` a `Short` , pero `Single` a `Double` ). Por tanto, el compilador genera un error de resolución de sobrecarga.

**Enfoque correcto:** Para poder llamar a un procedimiento sobrecargado sin ambigüedad, utilice la [función ctype](../../../language-reference/functions/ctype-function.md) para hacer coincidir los tipos de datos de argumento con los tipos de parámetro. En el ejemplo siguiente se muestra una llamada a `z` que fuerza la resolución a la segunda sobrecarga.

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a>Resolución de sobrecarga con argumentos opcionales y ParamArray

Si dos sobrecargas de un procedimiento tienen firmas idénticas, salvo que el último parámetro se declara [opcional](../../../language-reference/modifiers/optional.md) en One y [ParamArray](../../../language-reference/modifiers/paramarray.md) en el otro, el compilador resuelve una llamada a ese procedimiento según la coincidencia más cercana. Para obtener más información, consulta [Overload Resolution](./overload-resolution.md).

## <a name="see-also"></a>Consulte también

- [Procedimientos](index.md)
- [Procedimientos Sub](sub-procedures.md)
- [Procedimientos de función](function-procedures.md)
- [Procedimientos de propiedad](property-procedures.md)
- [Procedimientos de operador](operator-procedures.md)
- [Argumentos y parámetros de procedimiento](procedure-parameters-and-arguments.md)
- [Sobrecarga de procedimientos](procedure-overloading.md)
- [Consideraciones sobre la sobrecarga de procedimientos](considerations-in-overloading-procedures.md)
- [Overload Resolution](overload-resolution.md)
