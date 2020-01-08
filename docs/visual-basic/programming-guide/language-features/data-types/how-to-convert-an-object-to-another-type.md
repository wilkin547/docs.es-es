---
title: 'Cómo: convertir un objeto en otro tipo'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 6d16e0eafc3fa9233037abe0c92dcb1945ca8da9
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75341588"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Cómo: Convertir un objeto en otro tipo en Visual Basic
Para convertir una variable de `Object` en otro tipo de datos, use una palabra clave de conversión como [CType function](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se convierte una variable de `Object` en un `Integer` y un `String`.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Si sabe que el contenido de una variable `Object` es de un tipo de datos determinado, es mejor convertir la variable a ese tipo de datos. Si continúa usando la variable `Object`, incurrirá en la *conversión boxing* y la conversión *unboxing* (para un tipo de valor) o en el *enlace en tiempo de ejecución* (para un tipo de referencia). Estas operaciones tienen un tiempo de ejecución adicional y hacen que el rendimiento sea más lento.  
  
## <a name="compile-the-code"></a>Compilar el código  
 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.  
  
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
