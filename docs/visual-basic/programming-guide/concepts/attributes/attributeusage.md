---
title: AttributeUsage
ms.date: 07/20/2015
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
ms.openlocfilehash: 677d49aba38801f2adf42cc745983af30b3eddc5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400737"
---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)

Determina cómo se puede usar una clase de atributo personalizado. `AttributeUsage` es un atributo que se puede aplicar a definiciones de atributos personalizados para controlar cómo se aplica el nuevo atributo. La configuración predeterminada presenta este aspecto cuando se aplica explícitamente:

```vb
<System.AttributeUsage(System.AttributeTargets.All,
                   AllowMultiple:=False,
                   Inherited:=True)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier entidad de código atribuible, pero solo se puede aplicar una vez a cada entidad. Las clases derivadas la heredan cuando se aplica a una clase base.

Los argumentos `AllowMultiple` y `Inherited` son opcionales, por lo que este código tiene el mismo efecto:

```vb
<System.AttributeUsage(System.AttributeTargets.All)>
Class NewAttribute
    Inherits System.Attribute
End Class
```

El primer argumento `AttributeUsage` debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>. Se pueden vincular diversos tipos de destino con el operador OR, de esta forma:

```vb
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>
Class NewPropertyOrFieldAttribute
    Inherits Attribute
End Class
```

Si el argumento `AllowMultiple` se establece en `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, del siguiente modo:

```vb
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>
Class MultiUseAttr
    Inherits Attribute
End Class

<MultiUseAttr(), MultiUseAttr()>
Class Class1
End Class
```

En este caso, `MultiUseAttr` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`. Los dos formatos mostrados para aplicar varios atributos son válidos.

Si `Inherited` se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo. Por ejemplo:

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

En este caso, `Attr1` no se aplica a `DClass` a través de la herencia.

## <a name="remarks"></a>Observaciones

`AttributeUsage` es un atributo de uso único; no se puede aplicar más de una vez a la misma clase. `AttributeUsage` es un alias de <xref:System.AttributeUsageAttribute>.

Para más información, vea [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic]).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra el efecto de los argumentos `Inherited` y `AllowMultiple` en el atributo `AttributeUsage` y cómo se pueden enumerar los atributos personalizados aplicados a una clase.

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

## <a name="sample-output"></a>Salida de ejemplo

```console
Attributes on Base Class:
A1
A2
Attributes on Derived Class:
A3
A3
A2
```

## <a name="see-also"></a>Consulte también

- <xref:System.Attribute>
- <xref:System.Reflection>
- [Guía de programación en Visual Basic](../../index.md)
- [Atributos](../../../../standard/attributes/index.md)
- [Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])
- [Atributos (Visual Basic)](../../../language-reference/attributes.md)
- [Creating Custom Attributes (Visual Basic)](creating-custom-attributes.md) (Creación de atributos personalizados [Visual Basic])
- [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])
