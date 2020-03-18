---
title: Procedimiento para inicializar objetos usando un inicializador de objeto - Guía de programación de C#
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: a2ecc9df211d0082bd4b413653e374758c877abc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705592"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="a7feb-102">Procedimiento para inicializar objetos usando un inicializador de objeto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="a7feb-102">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="a7feb-103">Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.</span><span class="sxs-lookup"><span data-stu-id="a7feb-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="a7feb-104">En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre.</span><span class="sxs-lookup"><span data-stu-id="a7feb-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="a7feb-105">El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia predeterminado y después procesando las inicializaciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="a7feb-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="a7feb-106">Por lo tanto, si el constructor sin parámetros se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.</span><span class="sxs-lookup"><span data-stu-id="a7feb-106">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="a7feb-107">Debe usar un inicializador de objeto si va a definir un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="a7feb-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="a7feb-108">Para obtener más información, vea [Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="a7feb-108">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7feb-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7feb-109">Example</span></span>  

<span data-ttu-id="a7feb-110">En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="a7feb-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="a7feb-111">Este ejemplo establece propiedades en el tipo `StudentName`:</span><span class="sxs-lookup"><span data-stu-id="a7feb-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="a7feb-112">Los inicializadores de objeto pueden usarse para establecer indizadores en un objeto.</span><span class="sxs-lookup"><span data-stu-id="a7feb-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="a7feb-113">En el ejemplo siguiente se define una clase `BaseballTeam` que usa un indizador para obtener y establecer jugadores en posiciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="a7feb-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="a7feb-114">El inicializador puede asignar jugadores en función de la abreviatura de la posición o del número usado para las puntuaciones de béisbol de cada posición:</span><span class="sxs-lookup"><span data-stu-id="a7feb-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="a7feb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7feb-115">See also</span></span>

- [<span data-ttu-id="a7feb-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a7feb-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a7feb-117">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="a7feb-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
