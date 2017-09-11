---
title: interface (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- interface_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
caps.latest.revision: 29
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 126e674a2c56f04f54f35a011c24ebf0f713ee8d
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="interface-c-reference"></a><span data-ttu-id="27e10-102">interface (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="27e10-102">interface (C# Reference)</span></span>
<span data-ttu-id="27e10-103">Una interfaz contiene solo las firmas de [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md), [eventos](../../../csharp/programming-guide/events/index.md) o [indizadores](../../../csharp/programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="27e10-103">An interface contains only the signatures of [methods](../../../csharp/programming-guide/classes-and-structs/methods.md), [properties](../../../csharp/programming-guide/classes-and-structs/properties.md), [events](../../../csharp/programming-guide/events/index.md) or [indexers](../../../csharp/programming-guide/indexers/index.md).</span></span> <span data-ttu-id="27e10-104">Una clase o struct que implemente la interfaz debe implementar los miembros de la interfaz que se especifican en la definición de interfaz.</span><span class="sxs-lookup"><span data-stu-id="27e10-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="27e10-105">En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="27e10-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>  
  
 <span data-ttu-id="27e10-106">Para obtener más información y ejemplos, vea [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="27e10-106">For more information and examples, see [Interfaces](../../../csharp/programming-guide/interfaces/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27e10-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27e10-107">Example</span></span>  
 <span data-ttu-id="27e10-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="27e10-108">[!code-cs[csrefKeywordsTypes#14](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_1.cs)]</span></span>  
  
 <span data-ttu-id="27e10-109">Una interfaz puede ser miembro de un espacio de nombres o de una clase, y puede contener signaturas de los siguientes miembros:</span><span class="sxs-lookup"><span data-stu-id="27e10-109">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>  
  
-   [<span data-ttu-id="27e10-110">Métodos</span><span class="sxs-lookup"><span data-stu-id="27e10-110">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
  
-   [<span data-ttu-id="27e10-111">Propiedades</span><span class="sxs-lookup"><span data-stu-id="27e10-111">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/using-properties.md)  
  
-   [<span data-ttu-id="27e10-112">Indizadores</span><span class="sxs-lookup"><span data-stu-id="27e10-112">Indexers</span></span>](../../../csharp/programming-guide/indexers/using-indexers.md)  
  
-   [<span data-ttu-id="27e10-113">Eventos</span><span class="sxs-lookup"><span data-stu-id="27e10-113">Events</span></span>](../../../csharp/language-reference/keywords/event.md)  
  
 <span data-ttu-id="27e10-114">Una interfaz puede heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="27e10-114">An interface can inherit from one or more base interfaces.</span></span>  
  
 <span data-ttu-id="27e10-115">Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.</span><span class="sxs-lookup"><span data-stu-id="27e10-115">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>  
  
 <span data-ttu-id="27e10-116">Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="27e10-116">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="27e10-117">A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="27e10-117">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>  
  
 <span data-ttu-id="27e10-118">Para obtener más información detallada y ejemplos de código de la implementación de interfaces explícita, vea [Implementación de interfaz explícita](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="27e10-118">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../../csharp/programming-guide/interfaces/explicit-interface-implementation.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="27e10-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="27e10-119">Example</span></span>  
 <span data-ttu-id="27e10-120">En el ejemplo siguiente se muestra la implementación de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="27e10-120">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="27e10-121">En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación.</span><span class="sxs-lookup"><span data-stu-id="27e10-121">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="27e10-122">Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="27e10-122">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>  
  
 <span data-ttu-id="27e10-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="27e10-123">[!code-cs[csrefKeywordsTypes#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/interface_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="27e10-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="27e10-124">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="27e10-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="27e10-125">See Also</span></span>  
 <span data-ttu-id="27e10-126">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-126">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="27e10-127">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-127">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="27e10-128">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-128">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="27e10-129">[Tipos de referencia](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-129">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="27e10-130">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-130">[Interfaces](../../../csharp/programming-guide/interfaces/index.md) </span></span>  
 <span data-ttu-id="27e10-131">[Utilizar propiedades](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-131">[Using Properties](../../../csharp/programming-guide/classes-and-structs/using-properties.md) </span></span>  
 <span data-ttu-id="27e10-132">[Utilizar indizadores](../../../csharp/programming-guide/indexers/using-indexers.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-132">[Using Indexers](../../../csharp/programming-guide/indexers/using-indexers.md) </span></span>  
 <span data-ttu-id="27e10-133">[class](../../../csharp/language-reference/keywords/class.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-133">[class](../../../csharp/language-reference/keywords/class.md) </span></span>  
 <span data-ttu-id="27e10-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span><span class="sxs-lookup"><span data-stu-id="27e10-134">[struct](../../../csharp/language-reference/keywords/struct.md) </span></span>  
 [<span data-ttu-id="27e10-135">Interfaces</span><span class="sxs-lookup"><span data-stu-id="27e10-135">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

