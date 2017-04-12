---
title: AttributeUsage (Visual Basic) | Documentos de Microsoft
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
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
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
ms.openlocfilehash: bf56f40033f9d1547d63fccd25e3c0561bb62cb1
ms.lasthandoff: 03/13/2017

---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)
Determina cómo se puede usar una clase de atributo personalizado. `AttributeUsage`es un atributo que se puede aplicar a definiciones de atributo personalizado para controlar cómo se aplica el nuevo atributo. La configuración predeterminada este aspecto cuando se aplica explícitamente:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 En este ejemplo, el `NewAttribute` clase se puede aplicar a cualquier entidad de código con atributo, pero se puede aplicar una sola vez a cada entidad. Que es heredada por las clases derivadas, cuando se aplica a una clase base.  
  
 El `AllowMultiple` y `Inherited` los argumentos son opcionales, por lo que este código tiene el mismo efecto:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 La primera `AttributeUsage` el argumento debe ser uno o más elementos de la <xref:System.AttributeTargets>enumeración.</xref:System.AttributeTargets> Varios tipos de destino se pueden vincular junto con el operador OR, como esta:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 Si el `AllowMultiple` argumento se establece en `true`, a continuación, el atributo resultante se puede aplicar más de una vez en una única entidad, similar al siguiente:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 En este caso `MultiUseAttr` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`. Ambos formatos para aplicar varios atributos son válidos.  
  
 Si `Inherited` se establece en `false`, a continuación, el atributo no es heredado por las clases que se derivan de una clase que tiene el atributo. Por ejemplo:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 En este caso `Attr1` no se aplica a `DClass` a través de la herencia.  
  
## <a name="remarks"></a>Comentarios  
 El `AttributeUsage` es un atributo de uso único, no se puede aplicar más de una vez a la misma clase. `AttributeUsage`es un alias para <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute>  
  
 Para obtener más información, consulte [acceso a atributos mediante reflexión usando (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra el efecto de la `Inherited` y `AllowMultiple` argumentos para el `AttributeUsage` atributo y cómo se pueden enumerar los atributos personalizados aplicados a una clase.  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a>Resultados del ejemplo  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Attribute></xref:System.Attribute>   
 <xref:System.Reflection></xref:System.Reflection>   
 [Guía de programación de Visual Basic](../../../../visual-basic/programming-guide/index.md)   
 [Atributos](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Atributos (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Crear atributos personalizados (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Acceso a atributos mediante reflexión (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
