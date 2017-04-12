---
title: "Cómo: crear una unión de C ++ mediante atributos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 9352a7e4-c0da-4d07-aa14-55ed43736fcb
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3ff1686328630b233b25839c79d0009d48aab5ab
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-cc-union-by-using-attributes-visual-basic"></a>Cómo: crear una unión de C/c ++ mediante atributos (Visual Basic)
Mediante el uso de atributos puede personalizar cómo se organizan los structs en la memoria. Por ejemplo, puede crear lo que se conoce como una unión de C o C++ mediante el `StructLayout(LayoutKind.Explicit)` y `FieldOffset` atributos.  
  
## <a name="example"></a>Ejemplo  
 En este segmento de código, todos los campos de `TestUnion` iniciar en la misma ubicación en la memoria.  
  
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
 El siguiente es otro ejemplo que campos comienzan en diferentes establece explícitamente ubicaciones.  
  
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
  
 Los campos de dos enteros, `i1` y `i2`, comparten las mismas posiciones de memoria como `lg`. Este tipo de control sobre el diseño de la estructura es útil cuando se usa la invocación de plataforma.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Atributos](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Atributos (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Crear atributos personalizados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Acceso a atributos mediante reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
