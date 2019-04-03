---
title: Filtrar Convertir un objeto a otro tipo en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 1e515c0f4ce8e787754c61a9b53d247fa93c49f2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58814385"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Filtrar Convertir un objeto a otro tipo en Visual Basic
Convierte un `Object` variable a otro tipo de datos con una palabra clave de conversión como [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente se convierte un `Object` variable a un `Integer` y un `String`.  
  
```  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Si sabe que el contenido de un `Object` son variable de un tipo de datos determinado, es mejor convertir la variable a ese tipo de datos. Si se sigue usando el `Object` variable, se incurre en cualquiera *boxing* y *unboxing* (para un tipo de valor) o *enlace más tarde* (para un tipo de referencia). Estas operaciones toman tiempo de ejecución adicional y ralentizan el rendimiento.  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
-   Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Object>
- [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Conversiones de ampliación y de restricción](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Conversiones entre cadenas y otros tipos](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Conversiones de matriz](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Estructuras](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Tipos de datos](../../../../visual-basic/language-reference/data-types/index.md)
- [Funciones de conversión de tipos](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
