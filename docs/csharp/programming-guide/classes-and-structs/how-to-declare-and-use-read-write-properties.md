---
title: Procedimiento para declarar y usar propiedades de lectura y escritura - Guía de programación de C#
description: Obtenga información sobre cómo usar propiedades de lectura y escritura en C#. Este ejemplo incluye dos propiedades, cada una con descriptores de acceso get y set, por lo que son de lectura y escritura.
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 75f3b4d6fa8595734cf1310c08281c26c829fd84
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899027"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="4a033-104">Procedimiento para declarar y usar propiedades de lectura y escritura (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="4a033-104">How to declare and use read write properties (C# Programming Guide)</span></span>

<span data-ttu-id="4a033-105">Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="4a033-105">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="4a033-106">Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="4a033-106">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="4a033-107">El descriptor de acceso [set](../../language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../language-reference/keywords/get.md) recupera los valores de los miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="4a033-107">The [set](../../language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="4a033-108">En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="4a033-108">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="4a033-109">Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="4a033-109">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a033-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a033-110">Example</span></span>  

 [!code-csharp[properties#1](snippets/how-to-declare-and-use-read-write-properties/Program.cs#1)]
  
## <a name="robust-programming"></a><span data-ttu-id="4a033-111">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="4a033-111">Robust Programming</span></span>  

 <span data-ttu-id="4a033-112">En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="4a033-112">In the previous example, the `Name` and `Age` properties are [public](../../language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="4a033-113">Esto permite que cualquier objeto lea y escriba estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="4a033-113">This allows any object to read and write these properties.</span></span> <span data-ttu-id="4a033-114">En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso.</span><span class="sxs-lookup"><span data-stu-id="4a033-114">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="4a033-115">Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="4a033-115">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[properties#2](snippets/how-to-declare-and-use-read-write-properties/Program.cs#2)]
  
 <span data-ttu-id="4a033-116">De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido.</span><span class="sxs-lookup"><span data-stu-id="4a033-116">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="4a033-117">Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](./restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="4a033-117">For more information, see [Asymmetric Accessor Accessibility](./restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="4a033-118">Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="4a033-118">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="4a033-119">Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a033-119">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[properties#3](snippets/how-to-declare-and-use-read-write-properties/Program.cs#3)]
  
 <span data-ttu-id="4a033-120">Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial.</span><span class="sxs-lookup"><span data-stu-id="4a033-120">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="4a033-121">Esta variable contiene el valor que el usuario ha especificado, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a033-121">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[properties#4](snippets/how-to-declare-and-use-read-write-properties/Program.cs#4)]
  
 <span data-ttu-id="4a033-122">Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:</span><span class="sxs-lookup"><span data-stu-id="4a033-122">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[properties#5](snippets/how-to-declare-and-use-read-write-properties/Program.cs#5)]
  
 <span data-ttu-id="4a033-123">Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4a033-123">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);
```  
  
 <span data-ttu-id="4a033-124">El método `ToString` se invalida en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4a033-124">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[properties#6](snippets/how-to-declare-and-use-read-write-properties/Program.cs#6)]
  
 <span data-ttu-id="4a033-125">Tenga en cuenta que `ToString` no se usa explícitamente en el programa.</span><span class="sxs-lookup"><span data-stu-id="4a033-125">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="4a033-126">Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="4a033-126">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a033-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a033-127">See also</span></span>

- [<span data-ttu-id="4a033-128">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="4a033-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4a033-129">Propiedades</span><span class="sxs-lookup"><span data-stu-id="4a033-129">Properties</span></span>](./properties.md)
- [<span data-ttu-id="4a033-130">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="4a033-130">Classes and Structs</span></span>](./index.md)
