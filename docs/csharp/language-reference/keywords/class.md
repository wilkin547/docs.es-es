---
title: 'Palabra clave class: Referencia de C#'
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77673100"
---
# <a name="class-c-reference"></a><span data-ttu-id="a7462-102">class (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a7462-102">class (C# Reference)</span></span>

<span data-ttu-id="a7462-103">Las clases se declaran mediante la palabra clave `class`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a7462-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="a7462-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7462-104">Remarks</span></span>

<span data-ttu-id="a7462-105">Solo la herencia simple se permite en C#.</span><span class="sxs-lookup"><span data-stu-id="a7462-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="a7462-106">En otras palabras, una clase puede heredar la implementación solo de una clase base.</span><span class="sxs-lookup"><span data-stu-id="a7462-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="a7462-107">En cambio, una clase puede implementar más de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="a7462-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="a7462-108">En la tabla siguiente se muestran ejemplos de herencia de clases e implementación de interfaces:</span><span class="sxs-lookup"><span data-stu-id="a7462-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="a7462-109">Herencia</span><span class="sxs-lookup"><span data-stu-id="a7462-109">Inheritance</span></span>|<span data-ttu-id="a7462-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7462-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="a7462-111">None</span><span class="sxs-lookup"><span data-stu-id="a7462-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="a7462-112">Single</span><span class="sxs-lookup"><span data-stu-id="a7462-112">Single</span></span>|`class DerivedClass : BaseClass { }`|
|<span data-ttu-id="a7462-113">Ninguna, implementa dos interfaces</span><span class="sxs-lookup"><span data-stu-id="a7462-113">None, implements two interfaces</span></span>|`class ImplClass : IFace1, IFace2 { }`|
|<span data-ttu-id="a7462-114">Única, implementa una interfaz</span><span class="sxs-lookup"><span data-stu-id="a7462-114">Single, implements one interface</span></span>|`class ImplDerivedClass : BaseClass, IFace1 { }`|

<span data-ttu-id="a7462-115">Las clases que se declaran directamente dentro de un espacio de nombres, que no están anidadas dentro de otras clases, pueden ser de tipo [public](./public.md) o [internal](./internal.md).</span><span class="sxs-lookup"><span data-stu-id="a7462-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](./public.md) or [internal](./internal.md).</span></span> <span data-ttu-id="a7462-116">De forma predeterminada, las clases son `internal`.</span><span class="sxs-lookup"><span data-stu-id="a7462-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="a7462-117">Los miembros de clase, incluidas las clases anidadas, pueden ser [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md) o [private protected](private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="a7462-117">Class members, including nested classes, can be [public](public.md), [protected internal](protected-internal.md), [protected](protected.md), [internal](internal.md), [private](private.md), or [private protected](private-protected.md).</span></span> <span data-ttu-id="a7462-118">De forma predeterminada, los miembros son `private`.</span><span class="sxs-lookup"><span data-stu-id="a7462-118">Members are `private` by default.</span></span>

<span data-ttu-id="a7462-119">Para obtener más información, consulte [Modificadores de acceso](../../programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="a7462-119">For more information, see [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="a7462-120">Puede declarar clases genéricas que tengan parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="a7462-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="a7462-121">Para obtener más información, consulte [Clases genéricas](../../programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="a7462-121">For more information, see [Generic Classes](../../programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="a7462-122">Una clase puede contener declaraciones de los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="a7462-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="a7462-123">Constructores</span><span class="sxs-lookup"><span data-stu-id="a7462-123">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="a7462-124">Constantes</span><span class="sxs-lookup"><span data-stu-id="a7462-124">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="a7462-125">Campos</span><span class="sxs-lookup"><span data-stu-id="a7462-125">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="a7462-126">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="a7462-126">Finalizers</span></span>](../../programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="a7462-127">Métodos</span><span class="sxs-lookup"><span data-stu-id="a7462-127">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="a7462-128">Propiedades</span><span class="sxs-lookup"><span data-stu-id="a7462-128">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="a7462-129">Indizadores</span><span class="sxs-lookup"><span data-stu-id="a7462-129">Indexers</span></span>](../../programming-guide/indexers/index.md)

- [<span data-ttu-id="a7462-130">Operadores</span><span class="sxs-lookup"><span data-stu-id="a7462-130">Operators</span></span>](../operators/index.md)

- [<span data-ttu-id="a7462-131">Eventos</span><span class="sxs-lookup"><span data-stu-id="a7462-131">Events</span></span>](../../programming-guide/events/index.md)

- [<span data-ttu-id="a7462-132">Delegados</span><span class="sxs-lookup"><span data-stu-id="a7462-132">Delegates</span></span>](../../programming-guide/delegates/index.md)

- [<span data-ttu-id="a7462-133">Clases</span><span class="sxs-lookup"><span data-stu-id="a7462-133">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="a7462-134">Interfaces</span><span class="sxs-lookup"><span data-stu-id="a7462-134">Interfaces</span></span>](../../programming-guide/interfaces/index.md)

- [<span data-ttu-id="a7462-135">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="a7462-135">Structure types</span></span>](../builtin-types/struct.md)

- [<span data-ttu-id="a7462-136">Tipos de enumeración</span><span class="sxs-lookup"><span data-stu-id="a7462-136">Enumeration types</span></span>](../builtin-types/enum.md)

## <a name="example"></a><span data-ttu-id="a7462-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a7462-137">Example</span></span>

<span data-ttu-id="a7462-138">En el ejemplo siguiente se muestra cómo declarar campos de clase, constructores y métodos.</span><span class="sxs-lookup"><span data-stu-id="a7462-138">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="a7462-139">También se muestra la creación de instancias de objeto y la impresión de datos de instancias.</span><span class="sxs-lookup"><span data-stu-id="a7462-139">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="a7462-140">En este ejemplo, se declaran dos clases.</span><span class="sxs-lookup"><span data-stu-id="a7462-140">In this example, two classes are declared.</span></span> <span data-ttu-id="a7462-141">La primera clase, `Child`, contiene dos campos privados (`name` y `age`), dos constructores públicos y un método público.</span><span class="sxs-lookup"><span data-stu-id="a7462-141">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="a7462-142">La segunda clase, `StringTest`, se usa para contener `Main`.</span><span class="sxs-lookup"><span data-stu-id="a7462-142">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a><span data-ttu-id="a7462-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a7462-143">Comments</span></span>

<span data-ttu-id="a7462-144">Observe que en el ejemplo anterior solo se puede acceder a los campos privados (`name` y `age`) a través del método público de la clase `Child`.</span><span class="sxs-lookup"><span data-stu-id="a7462-144">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="a7462-145">Por ejemplo, no puede imprimir el nombre de la clase child, desde el método `Main`, mediante una instrucción como esta:</span><span class="sxs-lookup"><span data-stu-id="a7462-145">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="a7462-146">El acceso a miembros privados de `Child` desde `Main` solo sería posible si `Main` fuera un miembro de la clase.</span><span class="sxs-lookup"><span data-stu-id="a7462-146">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="a7462-147">Los tipos declarados dentro de una clase sin un modificador de acceso adoptan el valor predeterminado de `private`, por lo que los miembros de datos de este ejemplo seguirían siendo `private` si se quitara la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="a7462-147">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="a7462-148">Por último, tenga en cuenta que, para el objeto creado mediante el constructor sin parámetros (`child3`), el campo `age` se ha inicializado en cero de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a7462-148">Finally, notice that for the object created using the parameterless constructor (`child3`), the `age` field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a7462-149">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a7462-149">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a7462-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7462-150">See also</span></span>

- [<span data-ttu-id="a7462-151">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a7462-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a7462-152">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="a7462-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a7462-153">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="a7462-153">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a7462-154">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="a7462-154">Reference Types</span></span>](./reference-types.md)
