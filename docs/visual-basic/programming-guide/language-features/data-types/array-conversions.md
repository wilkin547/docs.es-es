---
title: Conversiones de matrices
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], converting type
- type conversion [Visual Basic], arrays
- conversions [Visual Basic], type
- arrays [Visual Basic], data types
- conversions [Visual Basic], data type
- object arrays [Visual Basic], converting type
- data type conversion [Visual Basic], array conversions
- conversions [Visual Basic], array types
- object arrays
ms.assetid: fceff7d2-a1b7-44c7-b9aa-8bd831d8a444
ms.openlocfilehash: 622ebe8a77f2dfbeb35e0408be48622d93d409c6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345857"
---
# <a name="array-conversions-visual-basic"></a>Conversión de matrices (Visual Basic)
Puede convertir un tipo de matriz en un tipo de matriz diferente siempre que se cumplan las siguientes condiciones:  
  
- **Rango igual.** Los rangos de las dos matrices deben ser iguales, es decir, deben tener el mismo número de dimensiones. Sin embargo, no es necesario que las longitudes de las dimensiones respectivas sean las mismas.  
  
- **Tipo de datos de elemento.** Los tipos de datos de los elementos de ambas matrices deben ser tipos de referencia. No se puede convertir una matriz de `Integer` en una matriz de `Long`, o incluso en una matriz de `Object`, ya que se implica al menos un tipo de valor. Para obtener más información, consulta [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).  
  
- **Convertibility.** Una conversión, ya sea de ampliación o de restricción, debe ser posible entre los tipos de elemento de las dos matrices. Un ejemplo en el que se produce un error en este requisito es un intento de conversión entre una matriz de `String` y una matriz de una clase derivada de <xref:System.Attribute?displayProperty=nameWithType>. Estos dos tipos no tienen nada en común y no existe ninguna conversión de ningún tipo entre ellos.  
  
 Una conversión de un tipo de matriz a otro es la ampliación o la restricción, dependiendo de si la conversión de los elementos respectivos es de ampliación o reducción. Para obtener más información, consulta [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).  
  
## <a name="conversion-to-an-object-array"></a>Conversión a una matriz de objetos  
 Cuando se declara una matriz de `Object` sin inicializarla, su tipo de elemento se `Object` siempre y cuando permanezca sin inicializar. Cuando se establece en una matriz de una clase específica, toma el tipo de esa clase. Sin embargo, su tipo subyacente sigue siendo `Object`y, posteriormente, puede establecerlo en otra matriz de una clase no relacionada. Dado que todas las clases se derivan de `Object`, puede cambiar el tipo de elemento de la matriz de cualquier clase a cualquier otra clase.  
  
 En el ejemplo siguiente, no existe ninguna conversión entre tipos `student` y `String`, pero ambos derivan de `Object`, por lo que todas las asignaciones son válidas.  
  
```vb  
' Assume student has already been defined as a class.  
Dim testArray() As Object  
' testArray is still an Object array at this point.  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
testArray = New student(3) {}  
' testArray is now of type student().  
testArray = names  
' testArray is now a String array.  
```  
  
### <a name="underlying-type-of-an-array"></a>Tipo subyacente de una matriz  
 Si declara originalmente una matriz con una clase concreta, su tipo de elemento subyacente es esa clase. Si posteriormente lo establece en una matriz de otra clase, debe haber una conversión entre las dos clases.  
  
 En el ejemplo siguiente, `students` es una matriz de `student`. Dado que no existe ninguna conversión entre `String` y `student`, se produce un error en la última instrucción.  
  
```vb  
Dim students() As student  
Dim names() As String = New String(3) {"Name0", "Name1", "Name2", "Name3"}  
students = New Student(3) {}  
' The following statement fails at compile time.  
students = names  
```  
  
## <a name="see-also"></a>Vea también

- [Tipos de datos](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Cómo: convertir un objeto en otro tipo en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Matrices](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
