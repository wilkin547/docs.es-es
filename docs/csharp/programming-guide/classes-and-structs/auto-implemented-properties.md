---
title: 'Propiedades autoimplementadas: Guía de programación de C#'
ms.date: 01/31/2020
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: aa55fa97-ccec-431f-b5e9-5ac789fd32b7
ms.openlocfilehash: 989266bfc2de9bd5ce2948f09a2b9f19dd2c782e
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628298"
---
# <a name="auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="0eb2b-102">Propiedades autoimplementadas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="0eb2b-102">Auto-Implemented Properties (C# Programming Guide)</span></span>

<span data-ttu-id="0eb2b-103">En C# 3.0 y versiones posteriores, las propiedades implementadas automáticamente hacen que la declaración de propiedades sea más concisa cuando no es necesaria ninguna lógica adicional en los descriptores de acceso de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-103">In C# 3.0 and later, auto-implemented properties make property-declaration more concise when no additional logic is required in the property accessors.</span></span> <span data-ttu-id="0eb2b-104">También permite que el código de cliente cree objetos.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-104">They also enable client code to create objects.</span></span> <span data-ttu-id="0eb2b-105">Cuando se declara una propiedad tal como se muestra en el ejemplo siguiente, el compilador crea un campo de respaldo privado y anónimo al que solo se puede acceder con los descriptores de acceso de propiedad `get` y `set`.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-105">When you declare a property as shown in the following example, the compiler creates a private, anonymous backing field that can only be accessed through the property's `get` and `set` accessors.</span></span>
  
## <a name="example"></a><span data-ttu-id="0eb2b-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0eb2b-106">Example</span></span>

<span data-ttu-id="0eb2b-107">En el ejemplo siguiente se muestra una clase simple que tiene algunas propiedades implementadas automáticamente:</span><span class="sxs-lookup"><span data-stu-id="0eb2b-107">The following example shows a simple class that has some auto-implemented properties:</span></span>  

[!code-csharp[csProgGuideLINQ#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#28)]  

<span data-ttu-id="0eb2b-108">No se pueden declarar propiedades implementadas automáticamente en interfaces.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-108">You can't declare auto-implemented properties in interfaces.</span></span> <span data-ttu-id="0eb2b-109">Las propiedades implementadas automáticamente declaran un campo de respaldo de instancia privada y las interfaces no pueden declarar campos de instancia.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-109">Auto-implemented properties declare a private instance backing field, and interfaces may not declare instance fields.</span></span> <span data-ttu-id="0eb2b-110">Al declarar una propiedad en una interfaz sin definir un cuerpo, se declara una propiedad con descriptores de acceso que debe ser implementada por cada tipo que implemente esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-110">Declaring a property in an interface without defining a body declares a property with accessors that must be implemented by each type that implements that interface.</span></span>

<span data-ttu-id="0eb2b-111">En C# 6 y versiones posteriores, puede inicializar las propiedades implementadas automáticamente de forma similar a los campos:</span><span class="sxs-lookup"><span data-stu-id="0eb2b-111">In C# 6 and later, you can initialize auto-implemented properties similarly to fields:</span></span>  
 
```csharp  
public string FirstName { get; set; } = "Jane";  
```  
 
<span data-ttu-id="0eb2b-112">La clase que se muestra en el ejemplo anterior es mutable.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-112">The class that is shown in the previous example is mutable.</span></span> <span data-ttu-id="0eb2b-113">El código de cliente puede cambiar los valores de los objetos una vez creados.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-113">Client code can change the values in objects after creation.</span></span> <span data-ttu-id="0eb2b-114">En clases complejas que contienen el comportamiento importante (métodos) y los datos, suele ser necesario tener propiedades públicas.</span><span class="sxs-lookup"><span data-stu-id="0eb2b-114">In complex classes that contain significant behavior (methods) as well as data, it's often necessary to have public properties.</span></span> <span data-ttu-id="0eb2b-115">Pero para clases pequeñas o structs que simplemente encapsulan un conjunto de valores (datos) y tienen pocos comportamientos o ninguno, debe establecer que los objetos sean inmutables ya sea declarando el descriptor de acceso set como [private](../../language-reference/keywords/private.md) (inmutable para los consumidores) o declarando solo un descriptor de acceso get (inmutable siempre excepto en el constructor).</span><span class="sxs-lookup"><span data-stu-id="0eb2b-115">However, for small classes or structs that just encapsulate a set of values (data) and have little or no behaviors, you should either make the objects immutable by declaring the set accessor as [private](../../language-reference/keywords/private.md) (immutable to consumers) or by declaring only a get accessor (immutable everywhere except the constructor).</span></span>  <span data-ttu-id="0eb2b-116">Para obtener más información, vea [Procedimiento para implementar una clase ligera con propiedades autoimplementadas](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0eb2b-116">For more information, see [How to implement a lightweight class with auto-implemented properties](./how-to-implement-a-lightweight-class-with-auto-implemented-properties.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0eb2b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0eb2b-117">See also</span></span>

- [<span data-ttu-id="0eb2b-118">Propiedades</span><span class="sxs-lookup"><span data-stu-id="0eb2b-118">Properties</span></span>](./properties.md)
- [<span data-ttu-id="0eb2b-119">Modificadores</span><span class="sxs-lookup"><span data-stu-id="0eb2b-119">Modifiers</span></span>](/dotnet/csharp/language-reference/keywords)
