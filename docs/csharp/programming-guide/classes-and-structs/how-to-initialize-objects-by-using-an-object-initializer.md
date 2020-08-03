---
title: Procedimiento para inicializar objetos usando un inicializador de objeto - Guía de programación de C#
description: Obtenga información sobre cómo usar inicializadores de objeto para inicializar objetos de tipo en C# sin llamar a un constructor. Use un inicializador de objeto para definir un tipo anónimo.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0781b168b0ae8b8383affe19d2721da67f662045
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865039"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="b1aca-104">Procedimiento para inicializar objetos usando un inicializador de objeto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b1aca-104">How to initialize objects by using an object initializer (C# Programming Guide)</span></span>

<span data-ttu-id="b1aca-105">Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.</span><span class="sxs-lookup"><span data-stu-id="b1aca-105">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="b1aca-106">En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre.</span><span class="sxs-lookup"><span data-stu-id="b1aca-106">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="b1aca-107">El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia predeterminado y después procesando las inicializaciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="b1aca-107">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="b1aca-108">Por lo tanto, si el constructor sin parámetros se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.</span><span class="sxs-lookup"><span data-stu-id="b1aca-108">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="b1aca-109">Debe usar un inicializador de objeto si va a definir un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="b1aca-109">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="b1aca-110">Para obtener más información, vea [Procedimiento para devolver subconjuntos de propiedades de elementos en una consulta](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1aca-110">For more information, see [How to return subsets of element properties in a query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b1aca-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b1aca-111">Example</span></span>  

<span data-ttu-id="b1aca-112">En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="b1aca-112">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="b1aca-113">Este ejemplo establece propiedades en el tipo `StudentName`:</span><span class="sxs-lookup"><span data-stu-id="b1aca-113">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="b1aca-114">Los inicializadores de objeto pueden usarse para establecer indizadores en un objeto.</span><span class="sxs-lookup"><span data-stu-id="b1aca-114">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="b1aca-115">En el ejemplo siguiente se define una clase `BaseballTeam` que usa un indizador para obtener y establecer jugadores en posiciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="b1aca-115">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="b1aca-116">El inicializador puede asignar jugadores en función de la abreviatura de la posición o del número usado para las puntuaciones de béisbol de cada posición:</span><span class="sxs-lookup"><span data-stu-id="b1aca-116">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="b1aca-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="b1aca-117">See also</span></span>

- [<span data-ttu-id="b1aca-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b1aca-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b1aca-119">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="b1aca-119">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
