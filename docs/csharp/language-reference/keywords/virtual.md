---
title: virtual (Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
dev_langs:
- CSharp
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 26
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
ms.openlocfilehash: 24ca77a0a645a17c0223437e73539bc04ba80f23
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="virtual-c-reference"></a><span data-ttu-id="6d6eb-102">virtual (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6d6eb-102">virtual (C# Reference)</span></span>
<span data-ttu-id="6d6eb-103">La palabra clave `virtual` se usa para modificar una declaración de método, propiedad, indizador o evento y permitir que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="6d6eb-104">Por ejemplo, cualquier clase que herede este método puede reemplazarlo:</span><span class="sxs-lookup"><span data-stu-id="6d6eb-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="6d6eb-105">Un [miembro de reemplazo](../../../csharp/language-reference/keywords/override.md) de una clase derivada puede modificar la implementación de un miembro virtual.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="6d6eb-106">Para obtener más información sobre cómo usar la palabra clave `virtual`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="6d6eb-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d6eb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6d6eb-107">Remarks</span></span>  
 <span data-ttu-id="6d6eb-108">Cuando se invoca a un método virtual, se busca un miembro de reemplazo en el tipo en tiempo de ejecución del objeto.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="6d6eb-109">Se llama al miembro de reemplazo en la clase más derivada, que podría ser el miembro original si ninguna clase derivada ha invalidado al miembro.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="6d6eb-110">De forma predeterminada, los métodos son no virtuales.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="6d6eb-111">No se puede invalidar un método no virtual.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="6d6eb-112">No se puede usar el modificador `virtual` con los modificadores `static`, `abstract, private` o `override`.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-112">You cannot use the `virtual` modifier with the `static`, `abstract, private`, or `override` modifiers.</span></span> <span data-ttu-id="6d6eb-113">En el siguiente ejemplo se muestra una propiedad virtual:</span><span class="sxs-lookup"><span data-stu-id="6d6eb-113">The following example shows a virtual property:</span></span>  
  
 <span data-ttu-id="6d6eb-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d6eb-114">[!code-cs[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]</span></span>  
  
 <span data-ttu-id="6d6eb-115">Las propiedades virtuales se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-115">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="6d6eb-116">Es un error usar el modificador `virtual` en una propiedad estática.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-116">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="6d6eb-117">Una propiedad virtual heredada se puede invalidar en una clase derivada al incluir una declaración de propiedad que use el modificador `override`.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d6eb-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6d6eb-118">Example</span></span>  
 <span data-ttu-id="6d6eb-119">En este ejemplo, la clase `Shape` contiene las dos coordenadas `x`, `y` y el método virtual `Area()`.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="6d6eb-120">Las distintas clases de formas como `Circle`, `Cylinder` y `Sphere` heredan la clase `Shape` y se calcula el área de cada figura.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="6d6eb-121">Cada clase derivada tiene su propia implementación de invalidación de `Area()`.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-121">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="6d6eb-122">Observe que las clases heredadas `Circle`, `Sphere` y `Cylinder` usan constructores que inicializan la clase base, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="6d6eb-123">El programa siguiente calcula y muestra el área apropiada de cada figura al invocar a la implementación adecuada del método `Area()`, según el objeto asociado al método.</span><span class="sxs-lookup"><span data-stu-id="6d6eb-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 <span data-ttu-id="6d6eb-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6d6eb-124">[!code-cs[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="6d6eb-125">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6d6eb-125">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d6eb-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="6d6eb-126">See Also</span></span>  
 <span data-ttu-id="6d6eb-127">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-127">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6d6eb-128">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-128">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6d6eb-129">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-129">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="6d6eb-130">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-130">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="6d6eb-131">[Polimorfismo](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-131">[Polymorphism](../../../csharp/programming-guide/classes-and-structs/polymorphism.md) </span></span>  
 <span data-ttu-id="6d6eb-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-132">[abstract](../../../csharp/language-reference/keywords/abstract.md) </span></span>  
 <span data-ttu-id="6d6eb-133">[override](../../../csharp/language-reference/keywords/override.md) </span><span class="sxs-lookup"><span data-stu-id="6d6eb-133">[override](../../../csharp/language-reference/keywords/override.md) </span></span>  
 [<span data-ttu-id="6d6eb-134">new</span><span class="sxs-lookup"><span data-stu-id="6d6eb-134">new</span></span>](../../../csharp/language-reference/keywords/new.md)

