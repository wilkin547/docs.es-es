---
description: 'virtual: Referencia de C#'
title: 'virtual: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- virtual_CSharpKeyword
- virtual
helpviewer_keywords:
- virtual keyword [C#]
ms.assetid: 5da9abae-bc1e-434f-8bea-3601b8dcb3b2
ms.openlocfilehash: 67bdfcf27bb108ca85e94ba7fdce208e4cd83b80
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141730"
---
# <a name="virtual-c-reference"></a><span data-ttu-id="9157b-103">virtual (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9157b-103">virtual (C# Reference)</span></span>

<span data-ttu-id="9157b-104">La palabra clave `virtual` se usa para modificar una declaración de método, propiedad, indizador o evento y permitir que se invalide en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="9157b-104">The `virtual` keyword is used to modify a method, property, indexer, or event declaration and allow for it to be overridden in a derived class.</span></span> <span data-ttu-id="9157b-105">Por ejemplo, cualquier clase que herede este método puede reemplazarlo:</span><span class="sxs-lookup"><span data-stu-id="9157b-105">For example, this method can be overridden by any class that inherits it:</span></span>

```csharp
public virtual double Area()
{
    return x * y;
}
```

<span data-ttu-id="9157b-106">Un [miembro de reemplazo](override.md) de una clase derivada puede modificar la implementación de un miembro virtual.</span><span class="sxs-lookup"><span data-stu-id="9157b-106">The implementation of a virtual member can be changed by an [overriding member](override.md) in a derived class.</span></span> <span data-ttu-id="9157b-107">Para obtener más información sobre cómo usar la palabra clave `virtual`, vea [Control de versiones con las palabras clave Override y New](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) y [Saber cuándo usar las palabras clave Override y New (Guía de programación de C#)](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="9157b-107">For more information about how to use the `virtual` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing When to Use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="9157b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9157b-108">Remarks</span></span>

<span data-ttu-id="9157b-109">Cuando se invoca a un método virtual, se busca un miembro de reemplazo en el tipo en tiempo de ejecución del objeto.</span><span class="sxs-lookup"><span data-stu-id="9157b-109">When a virtual method is invoked, the run-time type of the object is checked for an overriding member.</span></span> <span data-ttu-id="9157b-110">Se llama al miembro de reemplazo en la clase más derivada, que podría ser el miembro original si ninguna clase derivada ha invalidado al miembro.</span><span class="sxs-lookup"><span data-stu-id="9157b-110">The overriding member in the most derived class is called, which might be the original member, if no derived class has overridden the member.</span></span>

<span data-ttu-id="9157b-111">De forma predeterminada, los métodos son no virtuales.</span><span class="sxs-lookup"><span data-stu-id="9157b-111">By default, methods are non-virtual.</span></span> <span data-ttu-id="9157b-112">No se puede invalidar un método no virtual.</span><span class="sxs-lookup"><span data-stu-id="9157b-112">You cannot override a non-virtual method.</span></span>

<span data-ttu-id="9157b-113">El modificador `virtual` no se puede usar con los modificadores `static`, `abstract`, `private` o `override`.</span><span class="sxs-lookup"><span data-stu-id="9157b-113">You cannot use the `virtual` modifier with the `static`, `abstract`, `private`, or `override` modifiers.</span></span> <span data-ttu-id="9157b-114">En el siguiente ejemplo se muestra una propiedad virtual:</span><span class="sxs-lookup"><span data-stu-id="9157b-114">The following example shows a virtual property:</span></span>

[!code-csharp[csrefKeywordsModifiers#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#26)]

<span data-ttu-id="9157b-115">Las propiedades virtuales se comportan como métodos virtuales, salvo por las diferencias en la sintaxis de declaración e invocación.</span><span class="sxs-lookup"><span data-stu-id="9157b-115">Virtual properties behave like virtual methods, except for the differences in declaration and invocation syntax.</span></span>

- <span data-ttu-id="9157b-116">Es un error usar el modificador `virtual` en una propiedad estática.</span><span class="sxs-lookup"><span data-stu-id="9157b-116">It is an error to use the `virtual` modifier on a static property.</span></span>

- <span data-ttu-id="9157b-117">Una propiedad virtual heredada se puede invalidar en una clase derivada al incluir una declaración de propiedad que use el modificador `override`.</span><span class="sxs-lookup"><span data-stu-id="9157b-117">A virtual inherited property can be overridden in a derived class by including a property declaration that uses the `override` modifier.</span></span>

## <a name="example"></a><span data-ttu-id="9157b-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9157b-118">Example</span></span>

<span data-ttu-id="9157b-119">En este ejemplo, la clase `Shape` contiene las dos coordenadas `x`, `y` y el método virtual `Area()`.</span><span class="sxs-lookup"><span data-stu-id="9157b-119">In this example, the `Shape` class contains the two coordinates `x`, `y`, and the `Area()` virtual method.</span></span> <span data-ttu-id="9157b-120">Las distintas clases de formas como `Circle`, `Cylinder` y `Sphere` heredan la clase `Shape` y se calcula el área de cada figura.</span><span class="sxs-lookup"><span data-stu-id="9157b-120">Different shape classes such as `Circle`, `Cylinder`, and `Sphere` inherit the `Shape` class, and the surface area is calculated for each figure.</span></span> <span data-ttu-id="9157b-121">Cada clase derivada tiene su propia implementación de invalidación de `Area()`.</span><span class="sxs-lookup"><span data-stu-id="9157b-121">Each derived class has its own override implementation of `Area()`.</span></span>

<span data-ttu-id="9157b-122">Observe que las clases heredadas `Circle`, `Sphere` y `Cylinder` usan constructores que inicializan la clase base, como se muestra en la siguiente declaración.</span><span class="sxs-lookup"><span data-stu-id="9157b-122">Notice that the inherited classes `Circle`, `Sphere`, and `Cylinder` all use constructors that initialize the base class, as shown in the following declaration.</span></span>

```csharp
public Cylinder(double r, double h): base(r, h) {}
```

<span data-ttu-id="9157b-123">El programa siguiente calcula y muestra el área apropiada de cada figura al invocar a la implementación adecuada del método `Area()`, según el objeto asociado al método.</span><span class="sxs-lookup"><span data-stu-id="9157b-123">The following program calculates and displays the appropriate area for each figure by invoking the appropriate implementation of the `Area()` method, according to the object that is associated with the method.</span></span>

[!code-csharp[csrefKeywordsModifiers#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#23)]

## <a name="c-language-specification"></a><span data-ttu-id="9157b-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9157b-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="9157b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9157b-125">See also</span></span>

- [<span data-ttu-id="9157b-126">Polimorfismo</span><span class="sxs-lookup"><span data-stu-id="9157b-126">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
- [<span data-ttu-id="9157b-127">abstract</span><span class="sxs-lookup"><span data-stu-id="9157b-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="9157b-128">override</span><span class="sxs-lookup"><span data-stu-id="9157b-128">override</span></span>](override.md)
- [<span data-ttu-id="9157b-129">new (modificador)</span><span class="sxs-lookup"><span data-stu-id="9157b-129">new (modifier)</span></span>](new-modifier.md)
