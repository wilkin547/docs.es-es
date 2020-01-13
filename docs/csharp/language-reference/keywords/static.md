---
title: 'Modificador static: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- static
- static_CSharpKeyword
helpviewer_keywords:
- static keyword [C#]
ms.assetid: 5509e215-2183-4da3-bab4-6b7e607a4fdf
ms.openlocfilehash: f4ca3fcf809e723d2144654f1da949eb4d6de1b4
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713071"
---
# <a name="static-c-reference"></a><span data-ttu-id="00124-102">static (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="00124-102">static (C# Reference)</span></span>

<span data-ttu-id="00124-103">Use el modificador `static` para declarar un miembro estático, que pertenece al propio tipo en lugar de a un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="00124-103">Use the `static` modifier to declare a static member, which belongs to the type itself rather than to a specific object.</span></span> <span data-ttu-id="00124-104">El modificador `static` se puede usar con clases, campos, métodos, propiedades, operadores, eventos y constructores, pero no con indexadores, finalizadores o tipos que no sean clases.</span><span class="sxs-lookup"><span data-stu-id="00124-104">The `static` modifier can be used with classes, fields, methods, properties, operators, events, and constructors, but it cannot be used with indexers, finalizers, or types other than classes.</span></span> <span data-ttu-id="00124-105">Para más información, vea [Clases estáticas y sus miembros](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="00124-105">For more information, see [Static Classes and Static Class Members](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>

## <a name="example"></a><span data-ttu-id="00124-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00124-106">Example</span></span>

<span data-ttu-id="00124-107">La siguiente clase se declara como `static` y contiene solo métodos `static`:</span><span class="sxs-lookup"><span data-stu-id="00124-107">The following class is declared as `static` and contains only `static` methods:</span></span>

[!code-csharp[csrefKeywordsModifiers#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#18)]

<span data-ttu-id="00124-108">Una declaración de constantes o tipos es implícitamente un miembro estático.</span><span class="sxs-lookup"><span data-stu-id="00124-108">A constant or type declaration is implicitly a static member.</span></span>

<span data-ttu-id="00124-109">No se puede hacer referencia a los miembros estáticos mediante una instancia.</span><span class="sxs-lookup"><span data-stu-id="00124-109">A static member cannot be referenced through an instance.</span></span> <span data-ttu-id="00124-110">En su lugar, se hace referencia a ellos a través del nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="00124-110">Instead, it is referenced through the type name.</span></span> <span data-ttu-id="00124-111">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="00124-111">For example, consider the following class:</span></span>

[!code-csharp[csrefKeywordsModifiers#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#19)]

<span data-ttu-id="00124-112">Para hacer referencia al miembro estático `x`, use el nombre completo, `MyBaseC.MyStruct.x`, a menos que el miembro sea accesible desde el mismo ámbito:</span><span class="sxs-lookup"><span data-stu-id="00124-112">To refer to the static member `x`, use the fully qualified name, `MyBaseC.MyStruct.x`, unless the member is accessible from the same scope:</span></span>

```csharp
Console.WriteLine(MyBaseC.MyStruct.x);
```

<span data-ttu-id="00124-113">Mientras que una instancia de una clase contiene una copia independiente de todos los campos de instancias de la clase, solo existe una copia de cada campo estático.</span><span class="sxs-lookup"><span data-stu-id="00124-113">While an instance of a class contains a separate copy of all instance fields of the class, there is only one copy of each static field.</span></span>

<span data-ttu-id="00124-114">No se puede usar [this](this.md) para hacer referencia a métodos estáticos o descriptores de acceso de propiedades.</span><span class="sxs-lookup"><span data-stu-id="00124-114">It is not possible to use [this](this.md) to reference static methods or property accessors.</span></span>

<span data-ttu-id="00124-115">Si la palabra clave `static` se aplica a una clase, todos los miembros de esta última deben ser estáticos.</span><span class="sxs-lookup"><span data-stu-id="00124-115">If the `static` keyword is applied to a class, all the members of the class must be static.</span></span>

<span data-ttu-id="00124-116">Las clases y las clases estáticas pueden tener constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="00124-116">Classes and static classes may have static constructors.</span></span> <span data-ttu-id="00124-117">Se llama a los constructores estáticos en algún momento entre el inicio del programa y la creación de una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="00124-117">Static constructors are called at some point between when the program starts and the class is instantiated.</span></span>

> [!NOTE]
> <span data-ttu-id="00124-118">La palabra clave `static` tiene usos más limitados que en C++.</span><span class="sxs-lookup"><span data-stu-id="00124-118">The `static` keyword has more limited uses than in C++.</span></span> <span data-ttu-id="00124-119">Para ver una comparación con la palabra clave de C++, vea [Clases de almacenamiento (C++)](/cpp/cpp/storage-classes-cpp#static).</span><span class="sxs-lookup"><span data-stu-id="00124-119">To compare with the C++ keyword, see [Storage classes (C++)](/cpp/cpp/storage-classes-cpp#static).</span></span>

<span data-ttu-id="00124-120">Para demostrar cómo funcionan los miembros estáticos, imagine una clase que represente el empleado de una empresa.</span><span class="sxs-lookup"><span data-stu-id="00124-120">To demonstrate static members, consider a class that represents a company employee.</span></span> <span data-ttu-id="00124-121">Supongamos que la clase contiene un método de recuento de empleados y un campo para almacenar el número de empleados.</span><span class="sxs-lookup"><span data-stu-id="00124-121">Assume that the class contains a method to count employees and a field to store the number of employees.</span></span> <span data-ttu-id="00124-122">El método y el campo no pertenecen a ninguna instancia de empleado.</span><span class="sxs-lookup"><span data-stu-id="00124-122">Both the method and the field do not belong to any instance employee.</span></span> <span data-ttu-id="00124-123">En su lugar, pertenecen a la clase de la empresa.</span><span class="sxs-lookup"><span data-stu-id="00124-123">Instead they belong to the company class.</span></span> <span data-ttu-id="00124-124">Por lo tanto, se deben declarar como miembros estáticos de la clase.</span><span class="sxs-lookup"><span data-stu-id="00124-124">Therefore, they should be declared as static members of the class.</span></span>

## <a name="example"></a><span data-ttu-id="00124-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00124-125">Example</span></span>

<span data-ttu-id="00124-126">En este ejemplo se lee el nombre y el identificador de un nuevo empleado, se incrementa en uno el recuento de empleados y se muestra la información del nuevo empleado, así como el nuevo número de empleados.</span><span class="sxs-lookup"><span data-stu-id="00124-126">This example reads the name and ID of a new employee, increments the employee counter by one, and displays the information for the new employee and the new number of employees.</span></span> <span data-ttu-id="00124-127">Para que resulte más sencillo, este programa lee el número actual de empleados desde el teclado.</span><span class="sxs-lookup"><span data-stu-id="00124-127">For simplicity, this program reads the current number of employees from the keyboard.</span></span> <span data-ttu-id="00124-128">En una aplicación real, esta información se debe leer desde un archivo.</span><span class="sxs-lookup"><span data-stu-id="00124-128">In a real application, this information should be read from a file.</span></span>

[!code-csharp[csrefKeywordsModifiers#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#20)]  

## <a name="example"></a><span data-ttu-id="00124-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="00124-129">Example</span></span>

<span data-ttu-id="00124-130">En este ejemplo se muestra que, aunque se puede inicializar un campo estático usando otro campo estático que aún no se haya declarado, los resultados serán indefinidos hasta que asigne explícitamente un valor al campo estático.</span><span class="sxs-lookup"><span data-stu-id="00124-130">This example shows that although you can initialize a static field by using another static field not yet declared, the results will be undefined until you explicitly assign a value to the static field.</span></span>

[!code-csharp[csrefKeywordsModifiers#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#21)]  

## <a name="c-language-specification"></a><span data-ttu-id="00124-131">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="00124-131">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="00124-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="00124-132">See also</span></span>

- [<span data-ttu-id="00124-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="00124-133">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="00124-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="00124-134">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="00124-135">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="00124-135">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="00124-136">Modificadores</span><span class="sxs-lookup"><span data-stu-id="00124-136">Modifiers</span></span>](index.md)
- [<span data-ttu-id="00124-137">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="00124-137">Static Classes and Static Class Members</span></span>](../../programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
