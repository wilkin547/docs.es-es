---
title: 'Cómo: Inicializar objetos usando un inicializador de objeto (Guía de programación de C#)'
ms.date: 07/20/2015
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0b103513bdcdef42c61172d1cc0ee096264a9559
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43521560"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="9307c-102">Cómo: Inicializar objetos usando un inicializador de objeto (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9307c-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>
<span data-ttu-id="9307c-103">Puede usar inicializadores de objeto para inicializar objetos de tipo de una forma declarativa sin tener que invocar explícitamente un constructor para el tipo.</span><span class="sxs-lookup"><span data-stu-id="9307c-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
 <span data-ttu-id="9307c-104">En los siguientes ejemplos se muestra cómo usar los inicializadores de objeto con objetos con nombre.</span><span class="sxs-lookup"><span data-stu-id="9307c-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="9307c-105">El compilador procesa los inicializadores de objeto primero obteniendo acceso al constructor de instancia predeterminado y después procesando las inicializaciones de miembro.</span><span class="sxs-lookup"><span data-stu-id="9307c-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="9307c-106">Por lo tanto, si el constructor predeterminado se declara como `private` en la clase, se producirá un error en los inicializadores de objeto que requieren acceso público.</span><span class="sxs-lookup"><span data-stu-id="9307c-106">Therefore, if the default constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>  
  
 <span data-ttu-id="9307c-107">Debe usar un inicializador de objeto si va a definir un tipo anónimo.</span><span class="sxs-lookup"><span data-stu-id="9307c-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="9307c-108">Para obtener más información, vea [Cómo: Devolver subconjuntos de propiedades de elementos en una consulta](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="9307c-108">For more information, see [How to: Return Subsets of Element Properties in a Query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9307c-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9307c-109">Example</span></span>  
 <span data-ttu-id="9307c-110">En el siguiente ejemplo se muestra cómo inicializar un nuevo tipo `StudentName` usando inicializadores de objeto.</span><span class="sxs-lookup"><span data-stu-id="9307c-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="9307c-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9307c-111">Example</span></span>  
 <span data-ttu-id="9307c-112">En el siguiente ejemplo se muestra cómo inicializar una colección de tipos `StudentName` usando un inicializador de colección.</span><span class="sxs-lookup"><span data-stu-id="9307c-112">The following example shows how to initialize a collection of `StudentName` types by using a collection initializer.</span></span> <span data-ttu-id="9307c-113">Tenga en cuenta que un inicializador de colección es una serie de inicializadores de objeto separados por comas.</span><span class="sxs-lookup"><span data-stu-id="9307c-113">Note that a collection initializer is a series of comma-separated object initializers.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9307c-114">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9307c-114">Compiling the Code</span></span>  
 <span data-ttu-id="9307c-115">Para ejecutar este código, copie y pegue la clase en un proyecto de aplicación de consola de Visual C# creado en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9307c-115">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9307c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9307c-116">See Also</span></span>

- [<span data-ttu-id="9307c-117">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9307c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="9307c-118">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="9307c-118">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
