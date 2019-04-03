---
title: Filtrar Crear una unión de C/C ++ mediante atributos (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
ms.openlocfilehash: 0c3ebf248f5d2f20e2fff25fb8326a294b51d153
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829309"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Filtrar Crear una unión de C/c ++ mediante atributos (Visual Basic)
Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria. Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.  
  
## <a name="example"></a>Ejemplo  
 En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
<System.Runtime.InteropServices.StructLayout(   
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestUnion  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public i As Integer  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public d As Double  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public c As Char  
  
    <System.Runtime.InteropServices.FieldOffset(0)>   
    Public b As Byte  
End Structure  
```  
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.  
  
```vb  
' Add an Imports statement for System.Runtime.InteropServices.  
  
 <System.Runtime.InteropServices.StructLayout(  
      System.Runtime.InteropServices.LayoutKind.Explicit)>   
Structure TestExplicit  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public lg As Long  
  
     <System.Runtime.InteropServices.FieldOffset(0)>   
     Public i1 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(4)>   
     Public i2 As Integer  
  
     <System.Runtime.InteropServices.FieldOffset(8)>   
     Public d As Double  
  
     <System.Runtime.InteropServices.FieldOffset(12)>   
     Public c As Char  
  
     <System.Runtime.InteropServices.FieldOffset(14)>   
     Public b As Byte  
 End Structure  
```  
  
 Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`. Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guía de programación en Visual Basic](../../../../visual-basic/programming-guide/index.md)
- [Atributos](../../../../standard/attributes/index.md)
- [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Atributos (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])
