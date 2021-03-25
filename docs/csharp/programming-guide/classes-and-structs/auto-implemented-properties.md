---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
description: En el caso de una propiedad implementada automáticamente en C#, el compilador crea un campo de respaldo privado y anónimo al que solo se accede a través de los descriptores de acceso get y set de la propiedad.
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: ef3e2d6dd5851801ea06d65b87c2274d8e44b4f1
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190286"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="eb077-103">Propiedades autoimplementadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="eb077-103">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="eb077-104">En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="eb077-104">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="eb077-105">También permite que el código de cliente cree objetos.</span><span class="sxs-lookup"><span data-stu-id="eb077-105">They also enable client code to create objects.</span></span> <span data-ttu-id="eb077-106">Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="eb077-106">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span> <span data-ttu-id="eb077-107">En C# 9 y versiones posteriores, los descriptores de acceso `init` también se pueden declarar como propiedades implementadas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="eb077-107">In C# 9 and later, `init` accessors can also be declared as auto-implemented properties.</span></span>
  
## <a name="example"></a><span data-ttu-id="eb077-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb077-108">Example</span></span>

<span data-ttu-id="eb077-109">En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:</span><span class="sxs-lookup"><span data-stu-id="eb077-109">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="eb077-110">No se pueden declarar propiedades implementadas automáticamente en interfaces.</span><span class="sxs-lookup"><span data-stu-id="eb077-110">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="eb077-111">Las propiedades implementadas automáticamente declaran un campo de respaldo de instancia privada y las interfaces no pueden declarar campos de instancia.</span><span class="sxs-lookup"><span data-stu-id="eb077-111">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="eb077-112">Al declarar una propiedad en una interfaz sin definir un cuerpo, se declara una propiedad con descriptores de acceso que debe ser implementada por cada tipo que implemente esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="eb077-112">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="eb077-113">En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:</span><span class="sxs-lookup"><span data-stu-id="eb077-113">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  

```csharp  
public string FirstName { get; set; } = "Jane";  
```  

<span data-ttu-id="eb077-114">La clase que se muestra en el ejemplo anterior es mutable.</span><span class="sxs-lookup"><span data-stu-id="eb077-114">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="eb077-115">El código de cliente puede cambiar los valores de los objetos una vez creados.</span><span class="sxs-lookup"><span data-stu-id="eb077-115">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="eb077-116">En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="eb077-116">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="eb077-117">Pero para las clases pequeñas o estructuras que solo encapsulan un conjunto de valores (datos) y tienen poco o ningún comportamiento, debe usar una de las opciones siguientes para hacer que los objetos sean inmutables:</span><span class="sxs-lookup"><span data-stu-id="eb077-117">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should use one of the following options for making the objects immutable:</span></span>

* <span data-ttu-id="eb077-118">Declare solo un descriptor de acceso `get` (inmutable en cualquier lugar excepto el constructor).</span><span class="sxs-lookup"><span data-stu-id="eb077-118">Declare only a `get` accessor (immutable everywhere except the constructor).</span></span>
* <span data-ttu-id="eb077-119">Declare un descriptor de acceso `get` y un descriptor de acceso `init` (inmutable en cualquier lugar excepto durante la construcción del objeto).</span><span class="sxs-lookup"><span data-stu-id="eb077-119">Declare a `get` accessor and an `init` accessor (immutable everywhere except during object construction).</span></span>
* <span data-ttu-id="eb077-120">Declare el descriptor de acceso `set` como [private](../../language-reference/keywords/private.md) (inmutable para los consumidores).</span><span class="sxs-lookup"><span data-stu-id="eb077-120">Declare the `set` accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers).</span></span>

<span data-ttu-id="eb077-121">Para obtener más información, vea [Procedimiento para implementar una clase ligera con propiedades autoimplementadas](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="eb077-121">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eb077-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb077-122">See also</span></span>

- [<span data-ttu-id="eb077-123">Propiedades</span><span class="sxs-lookup"><span data-stu-id="eb077-123">Properties</span></span>](./properties.md)
- [<span data-ttu-id="eb077-124">Modificadores</span><span class="sxs-lookup"><span data-stu-id="eb077-124">Modifiers</span></span>](../../language-reference/keywords/index.md)
