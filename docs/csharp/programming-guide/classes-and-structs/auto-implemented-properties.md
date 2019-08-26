---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 44f3beb9de8c9d339c42db26bb9c510998abc7d7
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597137"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="468b4-102">Propiedades autoimplementadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="468b4-102">Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="468b4-103">En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="468b4-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="468b4-104">También permite que el código de cliente cree objetos.</span><span class="sxs-lookup"><span data-stu-id="468b4-104">They also enable client code to create objects.</span></span> <span data-ttu-id="468b4-105">Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="468b4-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>  
  
## <a name="example"></a><span data-ttu-id="468b4-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="468b4-106">Example</span></span>  
 <span data-ttu-id="468b4-107">En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:</span><span class="sxs-lookup"><span data-stu-id="468b4-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  
  
 [!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  
  
 <span data-ttu-id="468b4-108">En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:</span><span class="sxs-lookup"><span data-stu-id="468b4-108">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
  
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
  
 <span data-ttu-id="468b4-109">La clase que se muestra en el ejemplo anterior es mutable.</span><span class="sxs-lookup"><span data-stu-id="468b4-109">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="468b4-110">El código de cliente puede cambiar los valores de los objetos una vez creados.</span><span class="sxs-lookup"><span data-stu-id="468b4-110">Client code can change the values in objects after they are created.</span></span> <span data-ttu-id="468b4-111">En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="468b4-111">In complex classes that contain significant behavior (methods) as well as data, it is often necessary to have public properties.</span></span> <span data-ttu-id="468b4-112">Pero para clases pequeñas o structs que simplemente encapsulan un conjunto de valores (datos) y tienen pocos comportamientos o ninguno, debe establecer que los objetos sean inmutables ya sea declarando el descriptor de acceso set como [private](../../language-reference/keywords/private.md) (inmutable para los consumidores) o declarando solo un descriptor de acceso get (inmutable siempre excepto en el constructor).</span><span class="sxs-lookup"><span data-stu-id="468b4-112">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="468b4-113">Para obtener más información, vea [Cómo: Implementar una clase ligera con propiedades autoimplementadas](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="468b4-113">For more information, see [How to: Implement a Lightweight Class with Auto-Implemented Properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="468b4-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="468b4-114">See also</span></span>

- [<span data-ttu-id="468b4-115">Propiedades</span><span class="sxs-lookup"><span data-stu-id="468b4-115">Properties</span></span>](./properties.md)
- [<span data-ttu-id="468b4-116">Modificadores</span><span class="sxs-lookup"><span data-stu-id="468b4-116">Modifiers</span></span>](../../language-reference/keywords/modifiers.md)
