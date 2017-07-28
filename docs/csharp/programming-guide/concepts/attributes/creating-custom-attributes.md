---
title: Crear atributos personalizados (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8ae5084501a2dd60ae23c93bbdb52dcd44f3f3f7
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

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
  
> [!NOTE]
>  Si la clase de atributo contiene una propiedad, dicha propiedad debe ser de lectura y escritura.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Reflection>   
 [Guía de programación de C#](../../../../csharp/programming-guide/index.md)   
 [Escribir atributos personalizados](../../../../standard/attributes/writing-custom-attributes.md)   
 [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md)  (Reflexión (C#))  
 [Atributos (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)   
 [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  (Acceso a atributos mediante reflexión (C#))  
 [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)

