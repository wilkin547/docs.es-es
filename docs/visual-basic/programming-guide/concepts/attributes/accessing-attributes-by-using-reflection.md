---
title: "Acceso a atributos mediante reflexión (Visual Basic) | Documentos de Microsoft"
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
ms.assetid: c56e41da-5433-464f-a7bf-2a722e78bc9f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4763eccc5d1a6bdf3e89c1c4d825d5ff5c6caa3e
ms.lasthandoff: 03/13/2017

---
# <a name="accessing-attributes-by-using-reflection-visual-basic"></a>Acceso a atributos mediante reflexión (Visual Basic)
El hecho de que puede definir atributos personalizados y colocarlos en el código fuente sería de poco valor sin alguna manera de recuperar la información y actuar sobre ella. Mediante reflexión, puede recuperar la información definida con atributos personalizados. El método clave es `GetCustomAttributes`, que devuelve una matriz de objetos que son los equivalentes en tiempo de ejecución de los atributos de código fuente. Este método tiene varias versiones sobrecargadas. Para obtener más información, consulte <xref:System.Attribute>.</xref:System.Attribute>  
  
 Una especificación de atributo como:  
  
```vb  
<Author("P. Ackerman", Version:=1.1)>   
Class SampleClass  
    ' P. Ackerman's code goes here...  
End Class  
```  
  
 es conceptualmente equivalente a esta:  
  
```vb  
Dim anonymousAuthorObject As Author = New Author("P. Ackerman")  
anonymousAuthorObject.version = 1.1  
```  
  
 Sin embargo, el código no se ejecuta hasta que `SampleClass` se consultan los atributos. Llamar a `GetCustomAttributes` en `SampleClass` hace un `Author` objeto se crea e inicializa como anteriormente. Si la clase tiene otros atributos, se crean de forma similar otros objetos de atributo. `GetCustomAttributes`a continuación, devuelve el `Author` objeto y cualquier otro objeto de atributo en una matriz. A continuación, puede recorrer en iteración esta matriz, determinar qué atributos se aplicaron según el tipo de cada elemento de matriz y extraer información de los objetos de atributo.  
  
## <a name="example"></a>Ejemplo  
 Este es un ejemplo completo. Un atributo personalizado se define, aplica a varias entidades y recuperan mediante reflexión.  
  
```vb  
' Multiuse attribute  
<System.AttributeUsage(System.AttributeTargets.Class Or   
                       System.AttributeTargets.Struct,   
                       AllowMultiple:=True)>   
Public Class Author  
    Inherits System.Attribute  
    Private name As String  
    Public version As Double  
    Sub New(ByVal authorName As String)  
        name = authorName  
  
        ' Default value  
        version = 1.0  
    End Sub  
  
    Function GetName() As String  
        Return name  
    End Function          
End Class  
  
' Class with the Author attribute  
<Author("P. Ackerman")>   
Public Class FirstClass  
End Class  
  
' Class without the Author attribute  
Public Class SecondClass  
End Class  
  
' Class with multiple Author attributes.  
<Author("P. Ackerman"), Author("R. Koch", Version:=2.0)>   
Public Class ThirdClass  
End Class  
  
Class TestAuthorAttribute  
    Sub Main()  
        PrintAuthorInfo(GetType(FirstClass))  
        PrintAuthorInfo(GetType(SecondClass))  
        PrintAuthorInfo(GetType(ThirdClass))  
    End Sub  
  
    Private Shared Sub PrintAuthorInfo(ByVal t As System.Type)  
        System.Console.WriteLine("Author information for {0}", t)  
  
        ' Using reflection  
        Dim attrs() As System.Attribute = System.Attribute.GetCustomAttributes(t)  
  
        ' Displaying output  
        For Each attr In attrs  
            Dim a As Author = CType(attr, Author)  
            System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version)  
        Next              
    End Sub  
  
    ' Output:  
    '   Author information for FirstClass  
    '     P. Ackerman, version 1.00  
    ' Author information for SecondClass  
    ' Author information for ThirdClass  
    '  R. Koch, version 2.00  
    '  P. Ackerman, version 1.00  
  
End Class  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection></xref:System.Reflection>   
 <xref:System.Attribute></xref:System.Attribute>   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Recuperar información almacenada en atributos](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)   
 [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Atributos (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Crear atributos personalizados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)
