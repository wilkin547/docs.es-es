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
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="c3bb2-102">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="c3bb2-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="c3bb2-103">Para crear sus propios atributos personalizados, defina una clase de atributo derivada directa o indirectamente de <xref:System.Attribute>, que agiliza y facilita la identificación de las definiciones de atributos en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="c3bb2-104">Imagínese que desea etiquetar tipos con el nombre del programador que los escribió.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="c3bb2-105">Puede definir una clase de atributos `Author` personalizada:</span><span class="sxs-lookup"><span data-stu-id="c3bb2-105">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="c3bb2-106">El nombre de la clase es el nombre del atributo, `Author`.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="c3bb2-107">Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizada.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="c3bb2-108">Los parámetros del constructor son los parámetros posicionales del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="c3bb2-109">En este ejemplo, `name` es un parámetro posicional.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="c3bb2-110">Las propiedades o los campos públicos de lectura y escritura son parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="c3bb2-111">En este caso, `version` es el único parámetro con nombre.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="c3bb2-112">Observe el uso del atributo `AttributeUsage` para hacer que el atributo `Author` sea válido solo en las declaraciones de clase y de `struct`.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="c3bb2-113">Puede usar este nuevo atributo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="c3bb2-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="c3bb2-114">`AttributeUsage` tiene un parámetro con nombre, `AllowMultiple`, con el que puede hacer que un atributo personalizado sea multiuso o de un solo uso.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="c3bb2-115">En el ejemplo de código siguiente se crea un atributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="c3bb2-116">En el ejemplo de código siguiente se aplican varios atributos del mismo tipo a una clase.</span><span class="sxs-lookup"><span data-stu-id="c3bb2-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3bb2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3bb2-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="c3bb2-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c3bb2-118">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="c3bb2-119">Escribir atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="c3bb2-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="c3bb2-120">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="c3bb2-120">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="c3bb2-121">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="c3bb2-121">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="c3bb2-122">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="c3bb2-122">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="c3bb2-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="c3bb2-123">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
