---
title: Procedimiento para inicializar objetos usando un inicializador de objeto - Guía de programación de C#
description: Obtenga información sobre cómo usar inicializadores de objeto para inicializar objetos de tipo en C# sin llamar a un constructor. Use un inicializador de objeto para definir un tipo anónimo.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0c2d38713a1fdefd922234a02e23518c0f00add5
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2020
ms.locfileid: "97512787"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="9c2ad-104">Procedimiento para inicializar objetos usando un inicializador de objeto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9c2ad-104">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="9c2ad-105">Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-105">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="9c2ad-106">En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-106">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="9c2ad-107">El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia sin parámetros y después procesando las inicializaciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-107">The compiler processes object initializers by first accessing the parameterless instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="9c2ad-108">Por lo tanto, si el constructor sin parámetros se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-108">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="9c2ad-109">Debe usar un inicializador de objeto si va a definir un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-109">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="9c2ad-110">Para obtener más información, vea [Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="9c2ad-110">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c2ad-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c2ad-111">Example</span></span>  

<span data-ttu-id="9c2ad-112">En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-112">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="9c2ad-113">Este ejemplo establece propiedades en el tipo `StudentName`:</span><span class="sxs-lookup"><span data-stu-id="9c2ad-113">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="9c2ad-114">Los inicializadores de objeto pueden usarse para establecer indizadores en un objeto.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-114">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="9c2ad-115">En el ejemplo siguiente se define una clase `BaseballTeam` que usa un indizador para obtener y establecer jugadores en posiciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="9c2ad-115">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="9c2ad-116">El inicializador puede asignar jugadores en función de la abreviatura de la posición o del número usado para las puntuaciones de béisbol de cada posición:</span><span class="sxs-lookup"><span data-stu-id="9c2ad-116">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="9c2ad-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c2ad-117">See also</span></span>

- [<span data-ttu-id="9c2ad-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9c2ad-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9c2ad-119">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="9c2ad-119">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
