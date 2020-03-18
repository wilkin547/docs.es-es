---
title: 'Modificador static: Referencia de C#'
ms.date: 01/22/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: e7671e9db488a7b50f4ed736864d6fa8d95eef1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "76744664"
---
# <a name="static-c-reference"></a><span data-ttu-id="98bbe-102">static (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="98bbe-102">static (C# Reference)</span></span>

<span data-ttu-id="98bbe-103">Use el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en lugar de a un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="98bbe-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="98bbe-104">El modificador `static` se puede usar para declarar clases `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-104">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="98bbe-105">En las clases, las interfaces y las estructuras, puede agregar el modificador `static` a los campos, los métodos, las propiedades, los operadores, los eventos y los constructores.</span><span class="sxs-lookup"><span data-stu-id="98bbe-105">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="98bbe-106">El modificador `static` no se puede usar con indizadores ni finalizadores.</span><span class="sxs-lookup"><span data-stu-id="98bbe-106">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="98bbe-107">Para obtener más información, consulte [Clases estáticas y sus miembros](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="98bbe-107">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="98bbe-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98bbe-108">Example</span></span>

<span data-ttu-id="98bbe-109">La siguiente clase se declara como `static` y contiene solo métodos `static`:</span><span class="sxs-lookup"><span data-stu-id="98bbe-109">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="98bbe-110">Una declaración de constantes o tipos es implícitamente un miembro `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-110">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="98bbe-111">No se puede hacer referencia a un miembro `static` mediante una instancia,</span><span class="sxs-lookup"><span data-stu-id="98bbe-111">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="98bbe-112">sino que se hace a través del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="98bbe-112">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="98bbe-113">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="98bbe-113">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="98bbe-114">Para hacer referencia al miembro `static` `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:</span><span class="sxs-lookup"><span data-stu-id="98bbe-114">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="98bbe-115">Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancia de la clase, solo hay una copia de cada campo `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-115">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="98bbe-116">No se puede usar [`this`](this.md) para hacer referencia a métodos `static` o descriptores de acceso de propiedades.</span><span class="sxs-lookup"><span data-stu-id="98bbe-116">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="98bbe-117">Si la palabra clave `static` se aplica a una clase, todos los miembros de esta deben ser `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-117">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="98bbe-118">Las clases, las interfaces y las clases `static` pueden tener constructores `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-118">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="98bbe-119">Se llama a un constructor `static` en algún momento entre el inicio del programa y la creación de una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="98bbe-119">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="98bbe-120">La palabra clave `static` tiene usos más limitados que en C++.</span><span class="sxs-lookup"><span data-stu-id="98bbe-120">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="98bbe-121">Para ver una comparación con la palabra clave de C++, vea [Clases de almacenamiento (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="98bbe-121">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="98bbe-122">Para mostrar miembros `static`, es recomendable una clase que represente al empleado de una empresa.</span><span class="sxs-lookup"><span data-stu-id="98bbe-122">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="98bbe-123">Supongamos que la clase contiene un método de recuento de empleados y un campo para almacenar el número de empleados.</span><span class="sxs-lookup"><span data-stu-id="98bbe-123">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="98bbe-124">El método y el campo no pertenecen a ninguna instancia de ningún empleado,</span><span class="sxs-lookup"><span data-stu-id="98bbe-124">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="98bbe-125">sino que pertenecen a la clase de empleados en su conjunto.</span><span class="sxs-lookup"><span data-stu-id="98bbe-125">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="98bbe-126">Se deben declarar como miembros `static` de la clase.</span><span class="sxs-lookup"><span data-stu-id="98bbe-126">They should be declared as `static` members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="98bbe-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98bbe-127">Example</span></span>

<span data-ttu-id="98bbe-128">En este ejemplo se lee el nombre y el identificador de un nuevo empleado, se incrementa en uno el recuento de empleados y se muestra la información del nuevo empleado, así como el nuevo número de empleados.</span><span class="sxs-lookup"><span data-stu-id="98bbe-128">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="98bbe-129">Este programa lee el número actual de empleados desde el teclado.</span><span class="sxs-lookup"><span data-stu-id="98bbe-129">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="98bbe-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98bbe-130">Example</span></span>

<span data-ttu-id="98bbe-131">En este ejemplo se muestra que se puede inicializar un campo `static` mediante otro campo `static` que aún no se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="98bbe-131">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="98bbe-132">Los resultados están sin definir hasta que se asigna explícitamente un valor al campo `static`.</span><span class="sxs-lookup"><span data-stu-id="98bbe-132">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="98bbe-133">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="98bbe-133">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="98bbe-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="98bbe-134">See also</span></span>

- [<span data-ttu-id="98bbe-135">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="98bbe-135">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="98bbe-136">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="98bbe-136">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="98bbe-137">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="98bbe-137">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="98bbe-138">Modificadores</span><span class="sxs-lookup"><span data-stu-id="98bbe-138">Modifiers</span></span>](index.md)
- [<span data-ttu-id="98bbe-139">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="98bbe-139">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
