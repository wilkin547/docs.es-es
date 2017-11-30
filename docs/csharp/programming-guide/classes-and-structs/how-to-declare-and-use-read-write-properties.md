---
title: "Cómo: Declarar y usar propiedades de lectura y escritura (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c17bdd05196f834b491c69f648bec0b7cb6e3cd9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="a09f8-102">Cómo: Declarar y usar propiedades de lectura y escritura (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a09f8-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="a09f8-103">Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="a09f8-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="a09f8-104">Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="a09f8-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="a09f8-105">El descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) recupera los valores de los miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="a09f8-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="a09f8-106">En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="a09f8-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="a09f8-107">Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="a09f8-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a09f8-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a09f8-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_1.cs)]  
  
## <a name="robust-programming"></a><span data-ttu-id="a09f8-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="a09f8-109">Robust Programming</span></span>  
 <span data-ttu-id="a09f8-110">En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../../csharp/language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="a09f8-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="a09f8-111">Esto permite que cualquier objeto lea y escriba estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="a09f8-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="a09f8-112">En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso.</span><span class="sxs-lookup"><span data-stu-id="a09f8-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="a09f8-113">Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="a09f8-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_2.cs)]  
  
 <span data-ttu-id="a09f8-114">De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido.</span><span class="sxs-lookup"><span data-stu-id="a09f8-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="a09f8-115">Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="a09f8-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="a09f8-116">Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="a09f8-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="a09f8-117">Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="a09f8-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_3.cs)]  
  
 <span data-ttu-id="a09f8-118">Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial.</span><span class="sxs-lookup"><span data-stu-id="a09f8-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="a09f8-119">Esta variable contiene el valor que el usuario ha especificado, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a09f8-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_4.cs)]  
  
 <span data-ttu-id="a09f8-120">Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:</span><span class="sxs-lookup"><span data-stu-id="a09f8-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_5.cs)]  
  
 <span data-ttu-id="a09f8-121">Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="a09f8-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="a09f8-122">El método `ToString` se invalida en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a09f8-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/how-to-declare-and-use-read-write-properties_6.cs)]  
  
 <span data-ttu-id="a09f8-123">Tenga en cuenta que `ToString` no se usa explícitamente en el programa.</span><span class="sxs-lookup"><span data-stu-id="a09f8-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="a09f8-124">Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="a09f8-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a09f8-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a09f8-125">See Also</span></span>  
 [<span data-ttu-id="a09f8-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a09f8-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a09f8-127">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a09f8-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="a09f8-128">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="a09f8-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
