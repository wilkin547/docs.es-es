---
title: virtual (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dce3333646bca6f558e3760849b6cffdb34a6c0b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="virtual-c-reference"></a><span data-ttu-id="6f6b3-102">virtual (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="6f6b3-102">virtual (C# Reference)</span></span>
<span data-ttu-id="6f6b3-103">La palabra clave `virtual` se usa para modificar una declaración de método, propiedad, indizador o evento y permitir que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-103">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="6f6b3-104">Por ejemplo, cualquier clase que herede este método puede reemplazarlo:</span><span class="sxs-lookup"><span data-stu-id="6f6b3-104">For example, this method can be overridden by any class that inherits it:</span></span>  
  
```  
public virtual double Area()   
{  
    return x * y;  
}  
```  
  
 <span data-ttu-id="6f6b3-105">Un [miembro de reemplazo](../../../csharp/language-reference/keywords/override.md) de una clase derivada puede modificar la implementación de un miembro virtual.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-105">The implementation of a virtual member can be changed by an [overriding member](../../../csharp/language-reference/keywords/override.md) in a derived class.</span></span> <span data-ttu-id="6f6b3-106">Para obtener más información sobre cómo usar la palabra clave `virtual`, vea [Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="6f6b3-106">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f6b3-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6f6b3-107">Remarks</span></span>  
 <span data-ttu-id="6f6b3-108">Cuando se invoca a un método virtual, se busca un miembro de reemplazo en el tipo en tiempo de ejecución del objeto.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-108">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="6f6b3-109">Se llama al miembro de reemplazo en la clase más derivada, que podría ser el miembro original si ninguna clase derivada ha invalidado al miembro.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-109">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>  
  
 <span data-ttu-id="6f6b3-110">De forma predeterminada, los métodos son no virtuales.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-110">By default, methods are non-virtual.</span></span> <span data-ttu-id="6f6b3-111">No se puede invalidar un método no virtual.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-111">You cannot override a non-virtual method.</span></span>  
  
 <span data-ttu-id="6f6b3-112">No se puede utilizar el `virtual` modificador con la `static`, `abstract`, `private`, o `override` modificadores.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-112">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="6f6b3-113">En el siguiente ejemplo se muestra una propiedad virtual:</span><span class="sxs-lookup"><span data-stu-id="6f6b3-113">The following example shows a virtual property:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_1.cs)]  
  
 <span data-ttu-id="6f6b3-114">Las propiedades virtuales se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-114">Virtual properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="6f6b3-115">Es un error usar el modificador `virtual` en una propiedad estática.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-115">It is an error to use the `virtual` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="6f6b3-116">Una propiedad virtual heredada se puede invalidar en una clase derivada al incluir una declaración de propiedad que use el modificador `override`.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-116">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f6b3-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f6b3-117">Example</span></span>  
 <span data-ttu-id="6f6b3-118">En este ejemplo, la clase `Shape` contiene las dos coordenadas `x`, `y` y el método virtual `Area()`.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-118">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="6f6b3-119">Las distintas clases de formas como `Circle`, `Cylinder` y `Sphere` heredan la clase `Shape` y se calcula el área de cada figura.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-119">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="6f6b3-120">Cada clase derivada tiene su propia implementación de invalidación de `Area()`.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-120">Each derived class has it own override implementation of `Area()`.</span></span>  
  
 <span data-ttu-id="6f6b3-121">Observe que las clases heredadas `Circle`, `Sphere` y `Cylinder` usan constructores que inicializan la clase base, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-121">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>  
  
```  
public Cylinder(double r, double h): base(r, h) {}  
```  
  
 <span data-ttu-id="6f6b3-122">El programa siguiente calcula y muestra el área apropiada de cada figura al invocar a la implementación adecuada del método `Area()`, según el objeto asociado al método.</span><span class="sxs-lookup"><span data-stu-id="6f6b3-122">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/virtual_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="6f6b3-123">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="6f6b3-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f6b3-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f6b3-124">See Also</span></span>  
 [<span data-ttu-id="6f6b3-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="6f6b3-125">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6f6b3-126">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="6f6b3-126">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6f6b3-127">Modificadores</span><span class="sxs-lookup"><span data-stu-id="6f6b3-127">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="6f6b3-128">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="6f6b3-128">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6f6b3-129">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="6f6b3-129">Polymorphism</span></span>](../../../csharp/programming-guide/classes-and-structs/polymorphism.md)  
 [<span data-ttu-id="6f6b3-130">abstract</span><span class="sxs-lookup"><span data-stu-id="6f6b3-130">abstract</span></span>](../../../csharp/language-reference/keywords/abstract.md)  
 [<span data-ttu-id="6f6b3-131">override</span><span class="sxs-lookup"><span data-stu-id="6f6b3-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="6f6b3-132">new</span><span class="sxs-lookup"><span data-stu-id="6f6b3-132">new</span></span>](../../../csharp/language-reference/keywords/new.md)
