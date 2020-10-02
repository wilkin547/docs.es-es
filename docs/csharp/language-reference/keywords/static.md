---
description: 'Modificador static: Referencia de C#'
title: 'Modificador static: Referencia de C#'
ms.date: 09/25/2020
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: ccd575748c2286fa7348e2880acbfadd036d9ccd
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "91247727"
---
# <a name="static-c-reference"></a><span data-ttu-id="f248d-103">static (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f248d-103">static (C# Reference)</span></span>

<span data-ttu-id="f248d-104">En esta página se trata la palabra clave del modificador `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-104">This page covers the `static` modifier keyword.</span></span> <span data-ttu-id="f248d-105">La palabra clave `static` también forma parte de la directiva [`using static`](using-static.md).</span><span class="sxs-lookup"><span data-stu-id="f248d-105">The `static` keyword is also part of the [`using static`](using-static.md) directive.</span></span>

<span data-ttu-id="f248d-106">Use el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en lugar de a un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="f248d-106">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="f248d-107">El modificador `static` se puede usar para declarar clases `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-107">The `static` modifier can be used to declare `static` classes.</span></span> <span data-ttu-id="f248d-108">En las clases, las interfaces y las estructuras, puede agregar el modificador `static` a los campos, los métodos, las propiedades, los operadores, los eventos y los constructores.</span><span class="sxs-lookup"><span data-stu-id="f248d-108">In classes, interfaces, and structs, you may add the `static` modifier to fields, methods, properties, operators, events, and constructors.</span></span> <span data-ttu-id="f248d-109">El modificador `static` no se puede usar con indizadores ni finalizadores.</span><span class="sxs-lookup"><span data-stu-id="f248d-109">The `static` modifier can't be used with indexers or finalizers.</span></span> <span data-ttu-id="f248d-110">Para más información, vea [Clases estáticas y sus miembros](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="f248d-110">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

<span data-ttu-id="f248d-111">A partir de C# 9.0, puede agregar el modificador `static` a una [expresión lambda](../operators/lambda-expressions.md) o un [método anónimo](../operators/delegate-operator.md).</span><span class="sxs-lookup"><span data-stu-id="f248d-111">Beginning with C# 9.0, you can add the `static` modifier to a [lambda expression](../operators/lambda-expressions.md) or [anonymous method](../operators/delegate-operator.md).</span></span> <span data-ttu-id="f248d-112">Una expresión lambda o un método anónimo estático no pueden capturar variables locales o el estado de la instancia.</span><span class="sxs-lookup"><span data-stu-id="f248d-112">A static lambda or anonymous method can't capture local variables or instance state.</span></span>

## <a name="example---static-class"></a><span data-ttu-id="f248d-113">Ejemplo: clase estática</span><span class="sxs-lookup"><span data-stu-id="f248d-113">Example - static class</span></span>

<span data-ttu-id="f248d-114">La siguiente clase se declara como `static` y contiene solo métodos `static`:</span><span class="sxs-lookup"><span data-stu-id="f248d-114">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="f248d-115">Una declaración de constantes o tipos es implícitamente un miembro `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-115">A constant or type declaration is implicitly a `static` member.</span></span> <span data-ttu-id="f248d-116">No se puede hacer referencia a un miembro `static` mediante una instancia,</span><span class="sxs-lookup"><span data-stu-id="f248d-116">A `static` member can't be referenced through an instance.</span></span> <span data-ttu-id="f248d-117">sino que se hace a través del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="f248d-117">Instead, it's referenced through the type name.</span></span> <span data-ttu-id="f248d-118">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="f248d-118">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="f248d-119">Para hacer referencia al miembro `static` `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:</span><span class="sxs-lookup"><span data-stu-id="f248d-119">To refer to the `static` member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="f248d-120">Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancia de la clase, solo hay una copia de cada campo `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-120">While an instance of a class contains a separate copy of all instance fields of the class, there's only one copy of each `static` field.</span></span>

<span data-ttu-id="f248d-121">No se puede usar [`this`](this.md) para hacer referencia a métodos `static` o descriptores de acceso de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f248d-121">It isn't possible to use [`this`](this.md) to reference `static` methods or property accessors.</span></span>

<span data-ttu-id="f248d-122">Si la palabra clave `static` se aplica a una clase, todos los miembros de esta deben ser `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-122">If the `static` keyword is applied to a class, all the members of the class must be `static`.</span></span>

<span data-ttu-id="f248d-123">Las clases, las interfaces y las clases `static` pueden tener constructores `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-123">Classes, interfaces, and `static` classes may have `static` constructors.</span></span> <span data-ttu-id="f248d-124">Se llama a un constructor `static` en algún momento entre el inicio del programa y la creación de una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="f248d-124">A `static` constructor is called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="f248d-125">La palabra clave `static` tiene usos más limitados que en C++.</span><span class="sxs-lookup"><span data-stu-id="f248d-125">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="f248d-126">Para ver una comparación con la palabra clave de C++, vea [Clases de almacenamiento (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="f248d-126">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="f248d-127">Para mostrar miembros `static`, es recomendable una clase que represente al empleado de una empresa.</span><span class="sxs-lookup"><span data-stu-id="f248d-127">To demonstrate `static` members, consider a class that represents a company employee.</span></span> <span data-ttu-id="f248d-128">Supongamos que la clase contiene un método de recuento de empleados y un campo para almacenar el número de empleados.</span><span class="sxs-lookup"><span data-stu-id="f248d-128">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="f248d-129">El método y el campo no pertenecen a ninguna instancia de ningún empleado,</span><span class="sxs-lookup"><span data-stu-id="f248d-129">Both the method and the field don't belong to any one employee instance.</span></span> <span data-ttu-id="f248d-130">sino que pertenecen a la clase de empleados en su conjunto.</span><span class="sxs-lookup"><span data-stu-id="f248d-130">Instead, they belong to the class of employees as a whole.</span></span> <span data-ttu-id="f248d-131">Se deben declarar como miembros `static` de la clase.</span><span class="sxs-lookup"><span data-stu-id="f248d-131">They should be declared as `static` members of the class.</span></span>

## <a name="example---static-field-and-method"></a><span data-ttu-id="f248d-132">Ejemplo: campo estático y método</span><span class="sxs-lookup"><span data-stu-id="f248d-132">Example - static field and method</span></span>

<span data-ttu-id="f248d-133">En este ejemplo se lee el nombre y el identificador de un nuevo empleado, se incrementa en uno el recuento de empleados y se muestra la información del nuevo empleado, así como el nuevo número de empleados.</span><span class="sxs-lookup"><span data-stu-id="f248d-133">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="f248d-134">Este programa lee el número actual de empleados desde el teclado.</span><span class="sxs-lookup"><span data-stu-id="f248d-134">This program reads the current number of employees from the keyboard.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example---static-initialization"></a><span data-ttu-id="f248d-135">Ejemplo: inicialización estática</span><span class="sxs-lookup"><span data-stu-id="f248d-135">Example - static initialization</span></span>

<span data-ttu-id="f248d-136">En este ejemplo se muestra que se puede inicializar un campo `static` mediante otro campo `static` que aún no se ha declarado.</span><span class="sxs-lookup"><span data-stu-id="f248d-136">This example shows that you can initialize a `static` field by using another `static` field that is not yet declared.</span></span> <span data-ttu-id="f248d-137">Los resultados están sin definir hasta que se asigna explícitamente un valor al campo `static`.</span><span class="sxs-lookup"><span data-stu-id="f248d-137">The results will be undefined until you explicitly assign a value to the `static` field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="f248d-138">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f248d-138">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f248d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f248d-139">See also</span></span>

- [<span data-ttu-id="f248d-140">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f248d-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f248d-141">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="f248d-141">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f248d-142">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="f248d-142">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f248d-143">Modificadores</span><span class="sxs-lookup"><span data-stu-id="f248d-143">Modifiers</span></span>](index.md)
- [<span data-ttu-id="f248d-144">using static (directiva)</span><span class="sxs-lookup"><span data-stu-id="f248d-144">using static directive</span></span>](using-static.md)
- [<span data-ttu-id="f248d-145">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="f248d-145">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
