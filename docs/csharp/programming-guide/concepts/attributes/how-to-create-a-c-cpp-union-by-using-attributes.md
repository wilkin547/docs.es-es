---
title: Procedimiento para crear una unión de C-C++ mediante atributos (C#)
ms.date: 07/20/2015
ms.assetid: 85f35e56-26e0-4d31-9f3a-89bd4005e71a
ms.openlocfilehash: a8b902536cd09ac732bf2144536605a66b5bbc56
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54599041"
---
# <a name="how-to-create-a-cc-union-by-using-attributes-c"></a>Procedimiento para crear una unión de C o C++ mediante atributos (C#)
Mediante el uso de atributos, puede personalizar la manera en que los structs se disponen en la memoria. Por ejemplo, puede crear lo que se conoce como una unión en C/ C++ mediante los atributos `StructLayout(LayoutKind.Explicit)` y `FieldOffset`.  
  
## <a name="example"></a>Ejemplo  
 En este segmento de código, todos los campos de `TestUnion` empiezan en la misma ubicación en la memoria.  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestUnion  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public byte b;  
       }  
```  
  
## <a name="example"></a>Ejemplo  
 A continuación se muestra otro ejemplo en el que los campos empiezan en ubicaciones diferentes establecidas explícitamente.  
  
```csharp  
// Add a using directive for System.Runtime.InteropServices.  
  
       [System.Runtime.InteropServices.StructLayout(LayoutKind.Explicit)]  
       struct TestExplicit  
       {  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public long lg;  
  
           [System.Runtime.InteropServices.FieldOffset(0)]  
           public int i1;  
  
           [System.Runtime.InteropServices.FieldOffset(4)]  
           public int i2;  
  
           [System.Runtime.InteropServices.FieldOffset(8)]  
           public double d;  
  
           [System.Runtime.InteropServices.FieldOffset(12)]  
           public char c;  
  
           [System.Runtime.InteropServices.FieldOffset(14)]  
           public byte b;  
       }  
```  
  
 Los dos campos enteros, `i1` e `i2`, tiene las mismas ubicaciones en la memoria que `lg`. Este tipo de control sobre el diseño del struct es útil cuando se usa la invocación de plataforma.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Guía de programación de C#](../../../../csharp/programming-guide/index.md)
- [Atributos](../../../../../docs/standard/attributes/index.md)
- [Reflexión (C#)](../../../../csharp/programming-guide/concepts/reflection.md)
- [Atributos (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)
- [Crear atributos personalizados (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)
- [Acceder a atributos mediante reflexión (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
