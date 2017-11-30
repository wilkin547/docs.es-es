---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81e7440279a2d7dfa801394ee0e9af6181da3c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="attributeusage-c"></a><span data-ttu-id="dd5d4-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="dd5d4-102">AttributeUsage (C#)</span></span>
<span data-ttu-id="dd5d4-103">Determina cómo se puede usar una clase de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="dd5d4-104">`AttributeUsage` es un atributo que se puede aplicar a definiciones de atributos personalizados para controlar cómo se aplica el nuevo atributo.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-104">`AttributeUsage` is an attribute that can be applied to custom attribute definitions to control how the new attribute can be applied.</span></span> <span data-ttu-id="dd5d4-105">La configuración predeterminada presenta este aspecto cuando se aplica explícitamente:</span><span class="sxs-lookup"><span data-stu-id="dd5d4-105">The default settings look like this when applied explicitly:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="dd5d4-106">En este ejemplo, la clase `NewAttribute` se puede aplicar a cualquier entidad de código atribuible, pero solo se puede aplicar una vez a cada entidad.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-106">In this example, the `NewAttribute` class can be applied to any attribute-able code entity, but can be applied only once to each entity.</span></span> <span data-ttu-id="dd5d4-107">Las clases derivadas la heredan cuando se aplica a una clase base.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-107">It is inherited by derived classes when applied to a base class.</span></span>  
  
 <span data-ttu-id="dd5d4-108">Los argumentos `AllowMultiple` y `Inherited` son opcionales, por lo que este código tiene el mismo efecto:</span><span class="sxs-lookup"><span data-stu-id="dd5d4-108">The `AllowMultiple` and `Inherited` arguments are optional, so this code has the same effect:</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 <span data-ttu-id="dd5d4-109">El primer argumento `AttributeUsage` debe ser uno o varios elementos de la enumeración <xref:System.AttributeTargets>.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-109">The first `AttributeUsage` argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="dd5d4-110">Se pueden vincular diversos tipos de destino con el operador OR, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="dd5d4-110">Multiple target types can be linked together with the OR operator, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 <span data-ttu-id="dd5d4-111">Si el argumento `AllowMultiple` se establece en `true`, el atributo resultante se puede aplicar más de una vez a cada una de las entidades, del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="dd5d4-111">If the `AllowMultiple` argument is set to `true`, then the resulting attribute can be applied more than once to a single entity, like this:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 <span data-ttu-id="dd5d4-112">En este caso, `MultiUseAttr` se puede aplicar varias veces porque `AllowMultiple` está establecido en `true`.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-112">In this case `MultiUseAttr` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="dd5d4-113">Los dos formatos mostrados para aplicar varios atributos son válidos.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-113">Both formats shown for applying multiple attributes are valid.</span></span>  
  
 <span data-ttu-id="dd5d4-114">Si `Inherited` se establece en `false`, las clases que se derivan de una clase con atributos no heredan el atributo.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-114">If `Inherited` is set to `false`, then the attribute is not inherited by classes that are derived from a class that is attributed.</span></span> <span data-ttu-id="dd5d4-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="dd5d4-115">For example:</span></span>  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 <span data-ttu-id="dd5d4-116">En este caso, `Attr1` no se aplica a `DClass` a través de la herencia.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-116">In this case `Attr1` is not applied to `DClass` via inheritance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd5d4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="dd5d4-117">Remarks</span></span>  
 <span data-ttu-id="dd5d4-118">`AttributeUsage` es un atributo de uso único; no se puede aplicar más de una vez a la misma clase.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-118">The `AttributeUsage` attribute is a single-use attribute--it cannot be applied more than once to the same class.</span></span> <span data-ttu-id="dd5d4-119">`AttributeUsage` es un alias de <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-119">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="dd5d4-120">Para obtener más información, consulte [Acceder a atributos mediante reflexión (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="dd5d4-120">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd5d4-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd5d4-121">Example</span></span>  
 <span data-ttu-id="dd5d4-122">En el ejemplo siguiente se muestra el efecto de los argumentos `Inherited` y `AllowMultiple` en el atributo `AttributeUsage` y cómo se pueden enumerar los atributos personalizados aplicados a una clase.</span><span class="sxs-lookup"><span data-stu-id="dd5d4-122">The following example demonstrates the effect of the `Inherited` and `AllowMultiple` arguments to the `AttributeUsage` attribute, and how the custom attributes applied to a class can be enumerated.</span></span>  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
```  
  
## <a name="sample-output"></a><span data-ttu-id="dd5d4-123">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="dd5d4-123">Sample Output</span></span>  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd5d4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dd5d4-124">See Also</span></span>  
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [<span data-ttu-id="dd5d4-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="dd5d4-125">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dd5d4-126">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd5d4-126">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)  
 [<span data-ttu-id="dd5d4-127">Reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="dd5d4-127">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
 [<span data-ttu-id="dd5d4-128">Atributos</span><span class="sxs-lookup"><span data-stu-id="dd5d4-128">Attributes</span></span>](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [<span data-ttu-id="dd5d4-129">Crear atributos personalizados (C#)</span><span class="sxs-lookup"><span data-stu-id="dd5d4-129">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [<span data-ttu-id="dd5d4-130">Acceder a atributos mediante reflexión (C#)</span><span class="sxs-lookup"><span data-stu-id="dd5d4-130">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
