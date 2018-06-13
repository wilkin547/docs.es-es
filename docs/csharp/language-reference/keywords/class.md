---
title: class (Referencia de C#)
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 20968d2f72195db6d16de1b726c6e946b91ffcd5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216757"
---
# <a name="class-c-reference"></a><span data-ttu-id="ad4d2-102">class (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="ad4d2-102">class (C# Reference)</span></span>

<span data-ttu-id="ad4d2-103">Las clases se declaran mediante la palabra clave `class`, como se muestra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ad4d2-103">Classes are declared using the keyword `class`, as shown in the following example:</span></span>

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates 
    // and nested classes go here.
}
```

## <a name="remarks"></a><span data-ttu-id="ad4d2-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad4d2-104">Remarks</span></span>
<span data-ttu-id="ad4d2-105">Solo la herencia simple se permite en C#.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-105">Only single inheritance is allowed in C#.</span></span> <span data-ttu-id="ad4d2-106">En otras palabras, una clase puede heredar la implementación solo de una clase base.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-106">In other words, a class can inherit implementation from one base class only.</span></span> <span data-ttu-id="ad4d2-107">En cambio, una clase puede implementar más de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-107">However, a class can implement more than one interface.</span></span> <span data-ttu-id="ad4d2-108">En la tabla siguiente se muestran ejemplos de herencia de clases e implementación de interfaces:</span><span class="sxs-lookup"><span data-stu-id="ad4d2-108">The following table shows examples of class inheritance and interface implementation:</span></span>

|<span data-ttu-id="ad4d2-109">Herencia</span><span class="sxs-lookup"><span data-stu-id="ad4d2-109">Inheritance</span></span>|<span data-ttu-id="ad4d2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad4d2-110">Example</span></span>|
|-----------------|-------------|
|<span data-ttu-id="ad4d2-111">Ninguna</span><span class="sxs-lookup"><span data-stu-id="ad4d2-111">None</span></span>|`class ClassA { }`|
|<span data-ttu-id="ad4d2-112">Single</span><span class="sxs-lookup"><span data-stu-id="ad4d2-112">Single</span></span>|`class DerivedClass: BaseClass { }`|
|<span data-ttu-id="ad4d2-113">Ninguna, implementa dos interfaces</span><span class="sxs-lookup"><span data-stu-id="ad4d2-113">None, implements two interfaces</span></span>|`class ImplClass: IFace1, IFace2 { }`|
|<span data-ttu-id="ad4d2-114">Única, implementa una interfaz</span><span class="sxs-lookup"><span data-stu-id="ad4d2-114">Single, implements one interface</span></span>|`class ImplDerivedClass: BaseClass, IFace1 { }`|

<span data-ttu-id="ad4d2-115">Las clases que se declaran directamente dentro de un espacio de nombres, que no están anidadas dentro de otras clases, pueden ser de tipo [public](../../../csharp/language-reference/keywords/public.md) o [internal](../../../csharp/language-reference/keywords/internal.md).</span><span class="sxs-lookup"><span data-stu-id="ad4d2-115">Classes that you declare directly within a namespace, not nested within other classes, can be either [public](../../../csharp/language-reference/keywords/public.md) or [internal](../../../csharp/language-reference/keywords/internal.md).</span></span> <span data-ttu-id="ad4d2-116">De forma predeterminada, las clases son `internal`.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-116">Classes are `internal` by default.</span></span>

<span data-ttu-id="ad4d2-117">Los miembros de clase, incluidas las clases anidadas, pueden ser de tipo [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md) o `private protected`.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-117">Class members, including nested classes, can be [public](../../../csharp/language-reference/keywords/public.md), `protected internal`, [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [private](../../../csharp/language-reference/keywords/private.md), or `private protected`.</span></span> <span data-ttu-id="ad4d2-118">Los miembros son [private](../../../csharp/language-reference/keywords/private.md) de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-118">Members are [private](../../../csharp/language-reference/keywords/private.md) by default.</span></span>

<span data-ttu-id="ad4d2-119">Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="ad4d2-119">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>

<span data-ttu-id="ad4d2-120">Puede declarar clases genéricas que tengan parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-120">You can declare generic classes that have type parameters.</span></span> <span data-ttu-id="ad4d2-121">Para obtener más información, consulte [Clases genéricas](../../../csharp/programming-guide/generics/generic-classes.md).</span><span class="sxs-lookup"><span data-stu-id="ad4d2-121">For more information, see [Generic Classes](../../../csharp/programming-guide/generics/generic-classes.md).</span></span>

<span data-ttu-id="ad4d2-122">Una clase puede contener declaraciones de los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad4d2-122">A class can contain declarations of the following members:</span></span>

- [<span data-ttu-id="ad4d2-123">Constructores</span><span class="sxs-lookup"><span data-stu-id="ad4d2-123">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)

- [<span data-ttu-id="ad4d2-124">Constantes</span><span class="sxs-lookup"><span data-stu-id="ad4d2-124">Constants</span></span>](../../../csharp/programming-guide/classes-and-structs/constants.md)

- [<span data-ttu-id="ad4d2-125">Campos</span><span class="sxs-lookup"><span data-stu-id="ad4d2-125">Fields</span></span>](../../../csharp/programming-guide/classes-and-structs/fields.md)

- [<span data-ttu-id="ad4d2-126">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="ad4d2-126">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)

- [<span data-ttu-id="ad4d2-127">Métodos</span><span class="sxs-lookup"><span data-stu-id="ad4d2-127">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="ad4d2-128">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ad4d2-128">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)

- [<span data-ttu-id="ad4d2-129">Indizadores</span><span class="sxs-lookup"><span data-stu-id="ad4d2-129">Indexers</span></span>](../../../csharp/programming-guide/indexers/index.md)

- [<span data-ttu-id="ad4d2-130">Operadores</span><span class="sxs-lookup"><span data-stu-id="ad4d2-130">Operators</span></span>](../../../csharp/programming-guide/statements-expressions-operators/operators.md)

- [<span data-ttu-id="ad4d2-131">Eventos</span><span class="sxs-lookup"><span data-stu-id="ad4d2-131">Events</span></span>](../../../csharp/programming-guide/events/index.md)

- [<span data-ttu-id="ad4d2-132">Delegados</span><span class="sxs-lookup"><span data-stu-id="ad4d2-132">Delegates</span></span>](../../../csharp/programming-guide/delegates/index.md)

- [<span data-ttu-id="ad4d2-133">Clases</span><span class="sxs-lookup"><span data-stu-id="ad4d2-133">Classes</span></span>](../../../csharp/programming-guide/classes-and-structs/classes.md)

- [<span data-ttu-id="ad4d2-134">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ad4d2-134">Interfaces</span></span>](../../../csharp/programming-guide/interfaces/index.md)

- [<span data-ttu-id="ad4d2-135">Structs</span><span class="sxs-lookup"><span data-stu-id="ad4d2-135">Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/structs.md)

## <a name="example"></a><span data-ttu-id="ad4d2-136">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad4d2-136">Example</span></span>
<span data-ttu-id="ad4d2-137">En el ejemplo siguiente se muestra cómo declarar campos de clase, constructores y métodos.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-137">The following example demonstrates declaring class fields, constructors, and methods.</span></span> <span data-ttu-id="ad4d2-138">También se muestra la creación de instancias de objeto y la impresión de datos de instancias.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-138">It also demonstrates object instantiation and printing instance data.</span></span> <span data-ttu-id="ad4d2-139">En este ejemplo, se declaran dos clases.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-139">In this example, two classes are declared.</span></span> <span data-ttu-id="ad4d2-140">La primera clase, `Child`, contiene dos campos privados (`name` y `age`), dos constructores públicos y un método público.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-140">The first class, `Child`, contains two private fields (`name` and `age`), two public constructors and one public method.</span></span> <span data-ttu-id="ad4d2-141">La segunda clase, `StringTest`, se usa para contener `Main`.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-141">The second class, `StringTest`, is used to contain `Main`.</span></span>

[!code-csharp[csrefKeywordsTypes#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/class_1.cs)]

## <a name="comments"></a><span data-ttu-id="ad4d2-142">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad4d2-142">Comments</span></span>
<span data-ttu-id="ad4d2-143">Observe que en el ejemplo anterior solo se puede acceder a los campos privados (`name` y `age`) a través del método público de la clase `Child`.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-143">Notice that in the previous example the private fields (`name` and `age`) can only be accessed through the public method of the `Child` class.</span></span> <span data-ttu-id="ad4d2-144">Por ejemplo, no puede imprimir el nombre de la clase child, desde el método `Main`, mediante una instrucción como esta:</span><span class="sxs-lookup"><span data-stu-id="ad4d2-144">For example, you cannot print the child's name, from the `Main` method, using a statement like this:</span></span>

```csharp
Console.Write(child1.name);   // Error
```

<span data-ttu-id="ad4d2-145">El acceso a miembros privados de `Child` desde `Main` solo sería posible si `Main` fuera un miembro de la clase.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-145">Accessing private members of `Child` from `Main` would only be possible if `Main` were a member of the class.</span></span>

<span data-ttu-id="ad4d2-146">Los tipos declarados dentro de una clase sin un modificador de acceso adoptan el valor predeterminado de `private`, por lo que los miembros de datos de este ejemplo seguirían siendo `private` si se quitara la palabra clave.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-146">Types declared inside a class without an access modifier default to `private`, so the data members in this example would still be `private` if the keyword were removed.</span></span>

<span data-ttu-id="ad4d2-147">Por último, tenga en cuenta que, para el objeto creado mediante el constructor predeterminado (`child3`), el campo age se ha inicializado a cero de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ad4d2-147">Finally, notice that for the object created using the default constructor (`child3`), the age field was initialized to zero by default.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ad4d2-148">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="ad4d2-148">C# Language Specification</span></span>
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ad4d2-149">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad4d2-149">See Also</span></span>
 [<span data-ttu-id="ad4d2-150">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="ad4d2-150">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ad4d2-151">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="ad4d2-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="ad4d2-152">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="ad4d2-152">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="ad4d2-153">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="ad4d2-153">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)
