---
title: Crear atributos personalizados (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1aa97a591fdbdfab931a8b5e4f70ec3c00762332
ms.lasthandoff: 03/13/2017

---
# <a name="creating-custom-attributes-visual-basic"></a>Crear atributos personalizados (Visual Basic)
Puede crear sus propios atributos personalizados definiendo una clase de atributo, una clase que deriva directa o indirectamente de <xref:System.Attribute>, que hace que las definiciones de atributos en metadatos rápido y fácil de identificar.</xref:System.Attribute> Suponga que desea etiquetar tipos con el nombre del programador que escribió el tipo. Puede definir una personalizada `Author` clase de atributos:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
        version = 1.0  
    End Sub  
End Class  
```  
  
 El nombre de clase es el nombre del atributo, `Author`. Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizado. Los parámetros del constructor son los parámetros posicionales del atributo personalizado. En este ejemplo, `name` es un parámetro posicional. Las propiedades o campos públicos de lectura y escritura son parámetros con nombre. En este caso, `version` es el único parámetro con nombre. Tenga en cuenta el uso de la `AttributeUsage` atributo para realizar la `Author` válido solamente en la clase de atributo y `Structure` declaraciones.  
  
 Puede utilizar este nuevo atributo de la siguiente manera:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 `AttributeUsage`tiene un parámetro con nombre, `AllowMultiple`, con lo que puede hacer un atributo personalizado solo uso o bien multiuso. En el ejemplo de código siguiente se crea un atributo multiuso.  
  
```vb  
' multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
```  
  
 En el ejemplo de código siguiente, se aplican varios atributos del mismo tipo a una clase.  
  
```vb  
<Author("P. Ackerman", Version:=1.1),   
Author("R. Koch", Version:=1.2)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
    ' R. Koch's code goes here...  
End Class  
```  
  
> [!NOTE]
>  Si la clase de atributo contiene una propiedad, dicha propiedad debe ser de lectura y escritura.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection></xref:System.Reflection>   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Escribir atributos personalizados](http://msdn.microsoft.com/library/97216f69-bde8-49fd-ac40-f18c500ef5dc)   
 [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Atributos (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Acceso a atributos mediante reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/attributeusage.md)
