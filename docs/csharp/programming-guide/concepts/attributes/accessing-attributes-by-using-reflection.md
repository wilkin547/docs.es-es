---
title: Acceder a atributos mediante reflexión (C#)
description: Use la reflexión para obtener información definida con atributos personalizados en C# mediante el método GetCustomAttributes.
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 9425141d64fd061d0c1f628228693cce02f7bfa0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925103"
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="d719c-103">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="d719c-103">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="d719c-104">El hecho de que pueda definir atributos personalizados y colocarlos en el código fuente no serviría de mucho si no existiera ninguna forma de recuperar la información y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="d719c-104">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="d719c-105">Mediante la reflexión, puede recuperar la información que se ha definido con atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d719c-105">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="d719c-106">El método clave es `GetCustomAttributes`, que devuelve una matriz de objetos que son los equivalentes en tiempo de ejecución de los atributos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="d719c-106">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="d719c-107">Este método tiene varias versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="d719c-107">This method has several overloaded versions.</span></span> <span data-ttu-id="d719c-108">Para obtener más información, vea <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="d719c-108">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="d719c-109">Una especificación de atributo como:</span><span class="sxs-lookup"><span data-stu-id="d719c-109">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="d719c-110">es conceptualmente equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="d719c-110">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="d719c-111">En cambio, el código no se ejecuta hasta que se consulta a `SampleClass` sobre los atributos.</span><span class="sxs-lookup"><span data-stu-id="d719c-111">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="d719c-112">Llamar a `GetCustomAttributes` en `SampleClass` hace que se cree e inicialice un objeto `Author` como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d719c-112">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="d719c-113">Si la clase tiene otros atributos, se crean otros objetos de atributo de forma similar.</span><span class="sxs-lookup"><span data-stu-id="d719c-113">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="d719c-114">Luego, `GetCustomAttributes` devuelve el objeto `Author` y cualquier otro objeto de atributo en una matriz.</span><span class="sxs-lookup"><span data-stu-id="d719c-114">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="d719c-115">Después, puede recorrer en iteración esta matriz, determinar qué atributos se han aplicado según el tipo de cada elemento de la matriz y extraer información de los objetos de atributo.</span><span class="sxs-lookup"><span data-stu-id="d719c-115">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d719c-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d719c-116">Example</span></span>  
 <span data-ttu-id="d719c-117">Este es un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="d719c-117">Here is a complete example.</span></span> <span data-ttu-id="d719c-118">Se define un atributo personalizado, se aplica a varias entidades y se recupera mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="d719c-118">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="d719c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d719c-119">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="d719c-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="d719c-120">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="d719c-121">Recuperar información almacenada en atributos</span><span class="sxs-lookup"><span data-stu-id="d719c-121">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="d719c-122">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="d719c-122">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="d719c-123">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="d719c-123">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="d719c-124">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="d719c-124">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
