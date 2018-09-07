---
title: Propiedades de interfaces (Guía de programación de C#)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], on interfaces
- interfaces [C#], properties
ms.assetid: 6503e9ed-33d7-44ec-b4c1-cc16c084b795
ms.openlocfilehash: eea2bb524496a3db22146586df323437d9f84242
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43396736"
---
# <a name="interface-properties-c-programming-guide"></a><span data-ttu-id="3a39d-102">Propiedades de interfaces (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="3a39d-102">Interface Properties (C# Programming Guide)</span></span>
<span data-ttu-id="3a39d-103">Las propiedades se pueden declarar en una [interfaz](../../../csharp/language-reference/keywords/interface.md).</span><span class="sxs-lookup"><span data-stu-id="3a39d-103">Properties can be declared on an [interface](../../../csharp/language-reference/keywords/interface.md).</span></span> <span data-ttu-id="3a39d-104">A continuación se muestra un ejemplo de un descriptor de acceso de propiedad de interfaz:</span><span class="sxs-lookup"><span data-stu-id="3a39d-104">The following is an example of an interface property accessor:</span></span>  
  
 [!code-csharp[csProgGuideProperties#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_1.cs)]  
  
 <span data-ttu-id="3a39d-105">El descriptor de acceso de una propiedad de interfaz no tiene un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="3a39d-105">The accessor of an interface property does not have a body.</span></span> <span data-ttu-id="3a39d-106">Por tanto, el propósito de los descriptores de acceso es indicar si la propiedad es de lectura y escritura, de solo lectura o de solo escritura.</span><span class="sxs-lookup"><span data-stu-id="3a39d-106">Thus, the purpose of the accessors is to indicate whether the property is read-write, read-only, or write-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a39d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a39d-107">Example</span></span>  
 <span data-ttu-id="3a39d-108">En este ejemplo, la interfaz `IEmployee` tiene una propiedad de lectura y escritura, `Name`, y una propiedad de solo lectura, `Counter`.</span><span class="sxs-lookup"><span data-stu-id="3a39d-108">In this example, the interface `IEmployee` has a read-write property, `Name`, and a read-only property, `Counter`.</span></span> <span data-ttu-id="3a39d-109">La clase `Employee` implementa la interfaz `IEmployee` y usa estas dos propiedades.</span><span class="sxs-lookup"><span data-stu-id="3a39d-109">The class `Employee` implements the `IEmployee` interface and uses these two properties.</span></span> <span data-ttu-id="3a39d-110">El programa lee el nombre de un nuevo empleado y el número actual de empleados y muestra el nombre del empleado y el número de empleados calculado.</span><span class="sxs-lookup"><span data-stu-id="3a39d-110">The program reads the name of a new employee and the current number of employees and displays the employee name and the computed employee number.</span></span>  
  
 <span data-ttu-id="3a39d-111">Puede usar el nombre completo de la propiedad, que hace referencia a la interfaz en la que se declara el miembro.</span><span class="sxs-lookup"><span data-stu-id="3a39d-111">You could use the fully qualified name of the property, which references the interface in which the member is declared.</span></span> <span data-ttu-id="3a39d-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3a39d-112">For example:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="3a39d-113">Se denomina [implementación de interfaz explícita](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="3a39d-113">This is called [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span> <span data-ttu-id="3a39d-114">Por ejemplo, si la clase `Employee` implementa dos interfaces `ICitizen` y `IEmployee`, y ambas interfaces tienen la propiedad `Name`, la implementación del miembro de interfaz explícita será necesaria.</span><span class="sxs-lookup"><span data-stu-id="3a39d-114">For example, if the class `Employee` is implementing two interfaces `ICitizen` and `IEmployee` and both interfaces have the `Name` property, the explicit interface member implementation will be necessary.</span></span> <span data-ttu-id="3a39d-115">Es decir, la siguiente declaración de propiedad:</span><span class="sxs-lookup"><span data-stu-id="3a39d-115">That is, the following property declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_2.cs)]  
  
 <span data-ttu-id="3a39d-116">implementa la propiedad `Name` en la interfaz `IEmployee`, mientras que la siguiente declaración:</span><span class="sxs-lookup"><span data-stu-id="3a39d-116">implements the `Name` property on the `IEmployee` interface, while the following declaration:</span></span>  
  
 [!code-csharp[csProgGuideProperties#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_3.cs)]  
  
 <span data-ttu-id="3a39d-117">implementa la propiedad `Name` en la interfaz `ICitizen`.</span><span class="sxs-lookup"><span data-stu-id="3a39d-117">implements the `Name` property on the `ICitizen` interface.</span></span>  
  
 [!code-csharp[csProgGuideProperties#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/interface-properties_4.cs)]  
  
  **`210 Hazem Abolrous`**    
## <a name="sample-output"></a><span data-ttu-id="3a39d-118">Resultados del ejemplo</span><span class="sxs-lookup"><span data-stu-id="3a39d-118">Sample Output</span></span>  
 `Enter number of employees: 210`  
  
 `Enter the name of the new employee: Hazem Abolrous`  
  
 `The employee information:`  
  
 `Employee number: 211`  
  
 `Employee name: Hazem Abolrous`  
  
## <a name="see-also"></a><span data-ttu-id="3a39d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a39d-119">See Also</span></span>  
 [<span data-ttu-id="3a39d-120">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3a39d-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3a39d-121">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3a39d-121">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)  
 [<span data-ttu-id="3a39d-122">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="3a39d-122">Using Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
 [<span data-ttu-id="3a39d-123">Comparación entre propiedades e indizadores</span><span class="sxs-lookup"><span data-stu-id="3a39d-123">Comparison Between Properties and Indexers</span></span>](../../../csharp/programming-guide/indexers/comparison-between-properties-and-indexers.md)  
 [<span data-ttu-id="3a39d-124">Indizadores</span><span class="sxs-lookup"><span data-stu-id="3a39d-124">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)  
 [<span data-ttu-id="3a39d-125">Interfaces</span><span class="sxs-lookup"><span data-stu-id="3a39d-125">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)
