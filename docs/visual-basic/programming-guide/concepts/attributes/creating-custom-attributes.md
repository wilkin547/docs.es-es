---
title: Crear atributos personalizados
ms.date: 07/20/2015
ms.assetid: 5c9ef584-6c7c-496b-92a9-6e42f8d9ca28
ms.openlocfilehash: 84b400c2fa1b2d4019eec32092f954d680e64978
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400699"
---
# <a name="creating-custom-attributes-visual-basic"></a>Creating Custom Attributes (Visual Basic) (Creación de atributos personalizados [Visual Basic])

Para crear sus propios atributos personalizados, defina una clase de atributo derivada directa o indirectamente de <xref:System.Attribute>, que agiliza y facilita la identificación de las definiciones de atributos en los metadatos. Imagínese que desea etiquetar tipos con el nombre del programador que los escribió. Puede definir una clase de atributos `Author` personalizada:

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

El nombre de la clase es el nombre del atributo, `Author`. Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizada. Los parámetros del constructor son los parámetros posicionales del atributo personalizado. En este ejemplo, `name` es un parámetro posicional. Las propiedades o los campos públicos de lectura y escritura son parámetros con nombre. En este caso, `version` es el único parámetro con nombre. Observe el uso del atributo `AttributeUsage` para hacer que el atributo `Author` sea válido solo en las declaraciones de clase y de `Structure`.

Puede usar este nuevo atributo de la siguiente manera:

```vb
<Author("P. Ackerman", Version:=1.1)>
Class SampleClass
    ' P. Ackerman's code goes here...
End Class
```

`AttributeUsage` tiene un parámetro con nombre, `AllowMultiple`, con el que puede hacer que un atributo personalizado sea multiuso o de un solo uso. En el ejemplo de código siguiente se crea un atributo multiuso.

```vb
' multiuse attribute
<System.AttributeUsage(System.AttributeTargets.Class Or
                       System.AttributeTargets.Struct,
                       AllowMultiple:=True)>
Public Class Author
    Inherits System.Attribute
```

En el ejemplo de código siguiente se aplican varios atributos del mismo tipo a una clase.

```vb
<Author("P. Ackerman", Version:=1.1),
Author("R. Koch", Version:=1.2)>
Class SampleClass
    ' P. Ackerman's code goes here...
    ' R. Koch's code goes here...
End Class
```

> [!NOTE]
> Si la clase de atributo contiene una propiedad, dicha propiedad debe ser de lectura y escritura.

## <a name="see-also"></a>Consulte también

- <xref:System.Reflection>
- [Guía de programación en Visual Basic](../../index.md)
- [Escribir atributos personalizados](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflection (Visual Basic)](../reflection.md) (Reflexión [Visual Basic])
- [Atributos (Visual Basic)](../../../language-reference/attributes.md)
- [Accessing Attributes by Using Reflection (Visual Basic)](accessing-attributes-by-using-reflection.md) (Acceso a atributos mediante reflexión [Visual Basic])
- [AttributeUsage (Visual Basic)](attributeusage.md)
