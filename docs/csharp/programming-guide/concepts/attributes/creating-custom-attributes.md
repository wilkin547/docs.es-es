---
title: Crear atributos personalizados (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: ec959723c339a13a40fd62388421ceacb736dfca
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389555"
---
# <a name="creating-custom-attributes-c"></a>Crear atributos personalizados (C#)
Para crear sus propios atributos personalizados, defina una clase de atributo derivada directa o indirectamente de <xref:System.Attribute>, que agiliza y facilita la identificación de las definiciones de atributos en los metadatos. Imagínese que desea etiquetar tipos con el nombre del programador que los escribió. Puede definir una clase de atributos `Author` personalizada:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 El nombre de la clase es el nombre del atributo, `Author`. Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizada. Los parámetros del constructor son los parámetros posicionales del atributo personalizado. En este ejemplo, `name` es un parámetro posicional. Las propiedades o los campos públicos de lectura y escritura son parámetros con nombre. En este caso, `version` es el único parámetro con nombre. Observe el uso del atributo `AttributeUsage` para hacer que el atributo `Author` sea válido solo en las declaraciones de clase y de `struct`.  
  
 Puede usar este nuevo atributo de la siguiente manera:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 `AttributeUsage` tiene un parámetro con nombre, `AllowMultiple`, con el que puede hacer que un atributo personalizado sea multiuso o de un solo uso. En el ejemplo de código siguiente se crea un atributo multiuso.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 En el ejemplo de código siguiente se aplican varios atributos del mismo tipo a una clase.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Reflection>
- [Guía de programación de C#](../../index.md)
- [Escribir atributos personalizados](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflexión (C#)](../reflection.md)
- [Atributos (C#)](./index.md)
- [Acceder a atributos mediante reflexión (C#)](./accessing-attributes-by-using-reflection.md)
- [AttributeUsage (C#)](../../../language-reference/attributes/general.md)
