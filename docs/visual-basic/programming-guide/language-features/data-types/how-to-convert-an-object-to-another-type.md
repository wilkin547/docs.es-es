---
description: 'Más información sobre: Cómo: convertir un objeto en otro tipo en Visual Basic'
title: Procedimiento Conversión de un objeto a otro tipo
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: d6840cfd440483720f8ca9a0fa0140c3727a8688
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100484033"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Cómo: Convertir un objeto en otro tipo en Visual Basic

Para convertir una `Object` variable en otro tipo de datos, use una palabra clave de conversión como la [función ctype](../../../language-reference/functions/ctype-function.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se convierte una `Object` variable en `Integer` y `String` .  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Si sabe que el contenido de una `Object` variable es de un tipo de datos determinado, es mejor convertir la variable a ese tipo de datos. Si continúa usando la `Object` variable, incurrirá en la *conversión boxing* y la conversión *unboxing* (para un tipo de valor) o en el *enlace en tiempo de ejecución* (para un tipo de referencia). Estas operaciones tienen un tiempo de ejecución adicional y hacen que el rendimiento sea más lento.  
  
## <a name="compile-the-code"></a>Compilar el código  

 Para este ejemplo se necesita:  
  
- Una referencia al espacio de nombres <xref:System?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Object>
- [Conversiones de tipos en Visual Basic](type-conversions.md)
- [Widening and Narrowing Conversions](widening-and-narrowing-conversions.md)
- [Conversiones implícitas y explícitas](implicit-and-explicit-conversions.md)
- [Conversiones entre cadenas y otros tipos](conversions-between-strings-and-other-types.md)
- [Conversiones de matriz](array-conversions.md)
- [Estructuras](structures.md)
- [Tipo de datos](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
