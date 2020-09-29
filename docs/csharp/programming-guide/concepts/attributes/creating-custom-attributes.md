---
title: Crear atributos personalizados (C#)
description: Aprenda a crear atributos personalizados en C# mediante la definición de una clase de atributo que se derive de la clase de atributos.
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 6946b707134b2bdbc245b8786f144517a5870440
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202610"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="4810f-103">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="4810f-103">Creating Custom Attributes (C#)</span></span>

<span data-ttu-id="4810f-104">Para crear sus propios atributos personalizados, defina una clase de atributo derivada directa o indirectamente de <xref:System.Attribute>, que agiliza y facilita la identificación de las definiciones de atributos en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="4810f-104">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="4810f-105">Imagínese que desea etiquetar tipos con el nombre del programador que los escribió.</span><span class="sxs-lookup"><span data-stu-id="4810f-105">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="4810f-106">Puede definir una clase de atributos `Author` personalizada:</span><span class="sxs-lookup"><span data-stu-id="4810f-106">You might define a custom `Author` attribute class:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 <span data-ttu-id="4810f-107">El nombre de la clase `AuthorAttribute` es el nombre del atributo, `Author`, al que se le agrega el sufijo `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="4810f-107">The class name `AuthorAttribute` is the attribute's name, `Author`, plus the `Attribute` suffix.</span></span> <span data-ttu-id="4810f-108">Se deriva de `System.Attribute`, por lo que es una clase de atributo personalizada.</span><span class="sxs-lookup"><span data-stu-id="4810f-108">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="4810f-109">Los parámetros del constructor son los parámetros posicionales del atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="4810f-109">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="4810f-110">En este ejemplo, `name` es un parámetro posicional.</span><span class="sxs-lookup"><span data-stu-id="4810f-110">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="4810f-111">Las propiedades o los campos públicos de lectura y escritura son parámetros con nombre.</span><span class="sxs-lookup"><span data-stu-id="4810f-111">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="4810f-112">En este caso, `version` es el único parámetro con nombre.</span><span class="sxs-lookup"><span data-stu-id="4810f-112">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="4810f-113">Observe el uso del atributo `AttributeUsage` para hacer que el atributo `Author` sea válido solo en las declaraciones de clase y de `struct`.</span><span class="sxs-lookup"><span data-stu-id="4810f-113">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="4810f-114">Puede usar este nuevo atributo de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4810f-114">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="4810f-115">`AttributeUsage` tiene un parámetro con nombre, `AllowMultiple`, con el que puede hacer que un atributo personalizado sea multiuso o de un solo uso.</span><span class="sxs-lookup"><span data-stu-id="4810f-115">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="4810f-116">En el ejemplo de código siguiente se crea un atributo multiuso.</span><span class="sxs-lookup"><span data-stu-id="4810f-116">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 <span data-ttu-id="4810f-117">En el ejemplo de código siguiente se aplican varios atributos del mismo tipo a una clase.</span><span class="sxs-lookup"><span data-stu-id="4810f-117">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="4810f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4810f-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="4810f-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4810f-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="4810f-120">Escribir atributos personalizados</span><span class="sxs-lookup"><span data-stu-id="4810f-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="4810f-121">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="4810f-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="4810f-122">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="4810f-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="4810f-123">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="4810f-123">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="4810f-124">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="4810f-124">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
