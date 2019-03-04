---
title: 'Procedimiento Declarar y usar propiedades de lectura y escritura: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: b4dc9364e64f7ebfd495671b852b98d8f56c80b5
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969046"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a><span data-ttu-id="0557a-102">Procedimiento Declarar y usar propiedades de lectura y escritura (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0557a-102">How to: Declare and Use Read Write Properties (C# Programming Guide)</span></span>
<span data-ttu-id="0557a-103">Las propiedades proporcionan la comodidad de los miembros de datos públicos sin los riesgos que provienen del acceso sin comprobar, sin controlar y sin proteger a los datos de un objeto.</span><span class="sxs-lookup"><span data-stu-id="0557a-103">Properties provide the convenience of public data members without the risks that come with unprotected, uncontrolled, and unverified access to an object's data.</span></span> <span data-ttu-id="0557a-104">Esto se consigue mediante los *descriptores de acceso*: métodos especiales que asignan y recuperan valores del miembro de datos subyacente.</span><span class="sxs-lookup"><span data-stu-id="0557a-104">This is accomplished through *accessors*: special methods that assign and retrieve values from the underlying data member.</span></span> <span data-ttu-id="0557a-105">El descriptor de acceso [set](../../../csharp/language-reference/keywords/set.md) permite que los miembros de datos se asignen, y el descriptor de acceso [get](../../../csharp/language-reference/keywords/get.md) recupera los valores de los miembros de datos.</span><span class="sxs-lookup"><span data-stu-id="0557a-105">The [set](../../../csharp/language-reference/keywords/set.md) accessor enables data members to be assigned, and the [get](../../../csharp/language-reference/keywords/get.md) accessor retrieves data member values.</span></span>  
  
 <span data-ttu-id="0557a-106">En este ejemplo se muestra una clase `Person` que tiene dos propiedades: `Name` (string) y `Age` (int).</span><span class="sxs-lookup"><span data-stu-id="0557a-106">This sample shows a `Person` class that has two properties: `Name` (string) and `Age` (int).</span></span> <span data-ttu-id="0557a-107">Ambas propiedades proporcionan descriptores de acceso `get` y `set`, de manera que se consideran propiedades de lectura y escritura.</span><span class="sxs-lookup"><span data-stu-id="0557a-107">Both properties provide `get` and `set` accessors, so they are considered read/write properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0557a-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0557a-108">Example</span></span>  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a><span data-ttu-id="0557a-109">Programación sólida</span><span class="sxs-lookup"><span data-stu-id="0557a-109">Robust Programming</span></span>  
 <span data-ttu-id="0557a-110">En el ejemplo anterior, las propiedades `Name` y `Age` son [públicas](../../../csharp/language-reference/keywords/public.md) e incluyen un descriptor de acceso `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="0557a-110">In the previous example, the `Name` and `Age` properties are [public](../../../csharp/language-reference/keywords/public.md) and include both a `get` and a `set` accessor.</span></span> <span data-ttu-id="0557a-111">Esto permite que cualquier objeto lea y escriba estas propiedades.</span><span class="sxs-lookup"><span data-stu-id="0557a-111">This allows any object to read and write these properties.</span></span> <span data-ttu-id="0557a-112">En cambio, a veces esto es conveniente para excluir uno de los descriptores de acceso.</span><span class="sxs-lookup"><span data-stu-id="0557a-112">It is sometimes desirable, however, to exclude one of the accessors.</span></span> <span data-ttu-id="0557a-113">Omitir el descriptor de acceso `set`, por ejemplo, hace que la propiedad sea de solo lectura:</span><span class="sxs-lookup"><span data-stu-id="0557a-113">Omitting the `set` accessor, for example, makes the property read-only:</span></span>  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 <span data-ttu-id="0557a-114">De manera alternativa, puede exponer un descriptor de acceso públicamente pero hacer que el otro sea privado o esté protegido.</span><span class="sxs-lookup"><span data-stu-id="0557a-114">Alternatively, you can expose one accessor publicly but make the other private or protected.</span></span> <span data-ttu-id="0557a-115">Para obtener más información, vea [Accesibilidad del descriptor de acceso asimétrico](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span><span class="sxs-lookup"><span data-stu-id="0557a-115">For more information, see [Asymmetric Accessor Accessibility](../../../csharp/programming-guide/classes-and-structs/restricting-accessor-accessibility.md).</span></span>  
  
 <span data-ttu-id="0557a-116">Una vez que se declaren las propiedades, pueden usarse como si fueran campos de la clase.</span><span class="sxs-lookup"><span data-stu-id="0557a-116">Once the properties are declared, they can be used as if they were fields of the class.</span></span> <span data-ttu-id="0557a-117">Esto permite una sintaxis muy natural cuando ambos obtienen y establecen el valor de una propiedad, como se muestra en las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="0557a-117">This allows for a very natural syntax when both getting and setting the value of a property, as in the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 <span data-ttu-id="0557a-118">Tenga en cuenta que en un método `set` de la propiedad está disponible una variable `value` especial.</span><span class="sxs-lookup"><span data-stu-id="0557a-118">Note that in a property `set` method a special `value` variable is available.</span></span> <span data-ttu-id="0557a-119">Esta variable contiene el valor que el usuario ha especificado, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0557a-119">This variable contains the value that the user specified, for example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 <span data-ttu-id="0557a-120">Tenga en cuenta la sintaxis pura para incrementar la propiedad `Age` en un objeto `Person`:</span><span class="sxs-lookup"><span data-stu-id="0557a-120">Notice the clean syntax for incrementing the `Age` property on a `Person` object:</span></span>  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 <span data-ttu-id="0557a-121">Si los métodos `set` y `get` independientes se han usado para modelar las propiedades, el código equivalente puede tener este aspecto:</span><span class="sxs-lookup"><span data-stu-id="0557a-121">If separate `set` and `get` methods were used to model properties, the equivalent code might look like this:</span></span>  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 <span data-ttu-id="0557a-122">El método `ToString` se invalida en este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0557a-122">The `ToString` method is overridden in this example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 <span data-ttu-id="0557a-123">Tenga en cuenta que `ToString` no se usa explícitamente en el programa.</span><span class="sxs-lookup"><span data-stu-id="0557a-123">Notice that `ToString` is not explicitly used in the program.</span></span> <span data-ttu-id="0557a-124">Se invoca de manera predeterminada mediante las llamadas a `WriteLine`.</span><span class="sxs-lookup"><span data-stu-id="0557a-124">It is invoked by default by the `WriteLine` calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0557a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0557a-125">See also</span></span>

- [<span data-ttu-id="0557a-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="0557a-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="0557a-127">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0557a-127">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="0557a-128">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="0557a-128">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
