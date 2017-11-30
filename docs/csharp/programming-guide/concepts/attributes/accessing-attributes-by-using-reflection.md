---
title: "Acceder a atributos mediante reflexión (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 162bdd6b968def391a2f3413596ee8c2a8b01cc3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="fb287-102">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="fb287-102">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="fb287-103">El hecho de que pueda definir atributos personalizados y colocarlos en el código fuente no serviría de mucho si no existiera ninguna forma de recuperar la información y actuar en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="fb287-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="fb287-104">Mediante la reflexión, puede recuperar la información que se ha definido con atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="fb287-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="fb287-105">El método clave es `GetCustomAttributes`, que devuelve una matriz de objetos que son los equivalentes en tiempo de ejecución de los atributos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="fb287-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="fb287-106">Este método tiene varias versiones sobrecargadas.</span><span class="sxs-lookup"><span data-stu-id="fb287-106">This method has several overloaded versions.</span></span> <span data-ttu-id="fb287-107">Para obtener más información, consulta <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="fb287-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="fb287-108">Una especificación de atributo como:</span><span class="sxs-lookup"><span data-stu-id="fb287-108">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="fb287-109">es conceptualmente equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="fb287-109">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="fb287-110">En cambio, el código no se ejecuta hasta que se consulta a `SampleClass` sobre los atributos.</span><span class="sxs-lookup"><span data-stu-id="fb287-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="fb287-111">Llamar a `GetCustomAttributes` en `SampleClass` hace que se cree e inicialice un objeto `Author` como se ha mostrado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fb287-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="fb287-112">Si la clase tiene otros atributos, se crean otros objetos de atributo de forma similar.</span><span class="sxs-lookup"><span data-stu-id="fb287-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="fb287-113">Luego, `GetCustomAttributes` devuelve el objeto `Author` y cualquier otro objeto de atributo en una matriz.</span><span class="sxs-lookup"><span data-stu-id="fb287-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="fb287-114">Después, puede recorrer en iteración esta matriz, determinar qué atributos se han aplicado según el tipo de cada elemento de la matriz y extraer información de los objetos de atributo.</span><span class="sxs-lookup"><span data-stu-id="fb287-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb287-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb287-115">Example</span></span>  
 <span data-ttu-id="fb287-116">Este es un ejemplo completo.</span><span class="sxs-lookup"><span data-stu-id="fb287-116">Here is a complete example.</span></span> <span data-ttu-id="fb287-117">Se define un atributo personalizado, se aplica a varias entidades y se recupera mediante reflexión.</span><span class="sxs-lookup"><span data-stu-id="fb287-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb287-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb287-118">See Also</span></span>  
 <xref:System.Reflection>  
 <xref:System.Attribute>  
 [<span data-ttu-id="fb287-119">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="fb287-119">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 <span data-ttu-id="fb287-120">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) (Recuperar la información almacenada en atributos)</span><span class="sxs-lookup"><span data-stu-id="fb287-120">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)</span></span>  
 [<span data-ttu-id="fb287-121">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="fb287-121">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="fb287-122">Atributos (C#)</span><span class="sxs-lookup"><span data-stu-id="fb287-122">Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="fb287-123">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="fb287-123">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)
