---
title: 'Restricciones en el uso de los niveles de accesibilidad: Referencia de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- access modifiers [C#], accessibility level restrictions
ms.assetid: 987e2f22-46bf-4fea-80ee-270b9cd01045
ms.openlocfilehash: 90c76e68ca526106f3a8be6e3db2640edbb2bc80
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715158"
---
# <a name="restrictions-on-using-accessibility-levels-c-reference"></a><span data-ttu-id="b9dfe-102">Restricciones en el uso de los niveles de accesibilidad (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="b9dfe-102">Restrictions on using accessibility levels (C# Reference)</span></span>

<span data-ttu-id="b9dfe-103">Cuando especifique un tipo en una declaración, compruebe si el nivel de accesibilidad de este depende del nivel de accesibilidad de un miembro o de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-103">When you specify a type in a declaration, check whether the accessibility level of the type is dependent on the accessibility level of a member or of another type.</span></span> <span data-ttu-id="b9dfe-104">Por ejemplo, la clase base directa debe ser al menos igual de accesible que la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-104">For example, the direct base class must be at least as accessible as the derived class.</span></span> <span data-ttu-id="b9dfe-105">Las siguientes declaraciones producen un error del compilador porque la clase base `BaseClass` es menos accesible que `MyClass`:</span><span class="sxs-lookup"><span data-stu-id="b9dfe-105">The following declarations cause a compiler error because the base class `BaseClass` is less accessible than `MyClass`:</span></span>

```csharp
class BaseClass {...}
public class MyClass: BaseClass {...} // Error
```

<span data-ttu-id="b9dfe-106">En la tabla siguiente se resumen las restricciones en los niveles de accesibilidad declarados.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-106">The following table summarizes the restrictions on declared accessibility levels.</span></span>

|<span data-ttu-id="b9dfe-107">Contexto</span><span class="sxs-lookup"><span data-stu-id="b9dfe-107">Context</span></span>|<span data-ttu-id="b9dfe-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b9dfe-108">Remarks</span></span>|
|-------------|-------------|
|[<span data-ttu-id="b9dfe-109">Clases</span><span class="sxs-lookup"><span data-stu-id="b9dfe-109">Classes</span></span>](../../programming-guide/classes-and-structs/classes.md)|<span data-ttu-id="b9dfe-110">La clase base directa de un tipo de clase debe ser al menos igual de accesible que el propio tipo de clase.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-110">The direct base class of a class type must be at least as accessible as the class type itself.</span></span>|
|[<span data-ttu-id="b9dfe-111">Interfaces</span><span class="sxs-lookup"><span data-stu-id="b9dfe-111">Interfaces</span></span>](../../programming-guide/interfaces/index.md)|<span data-ttu-id="b9dfe-112">Las interfaces base explícitas de un tipo de interfaz deben ser al menos igual de accesibles que el propio tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-112">The explicit base interfaces of an interface type must be at least as accessible as the interface type itself.</span></span>|
|[<span data-ttu-id="b9dfe-113">Delegados</span><span class="sxs-lookup"><span data-stu-id="b9dfe-113">Delegates</span></span>](../../programming-guide/delegates/index.md)|<span data-ttu-id="b9dfe-114">El tipo de valor devuelto y los tipos de parámetros de un tipo de delegado deben ser al menos igual de accesibles que el propio tipo de delegado.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-114">The return type and parameter types of a delegate type must be at least as accessible as the delegate type itself.</span></span>|
|[<span data-ttu-id="b9dfe-115">Constantes</span><span class="sxs-lookup"><span data-stu-id="b9dfe-115">Constants</span></span>](../../programming-guide/classes-and-structs/constants.md)|<span data-ttu-id="b9dfe-116">El tipo de una constante debe ser al menos igual de accesible que la propia constante.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-116">The type of a constant must be at least as accessible as the constant itself.</span></span>|
|[<span data-ttu-id="b9dfe-117">Campos</span><span class="sxs-lookup"><span data-stu-id="b9dfe-117">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)|<span data-ttu-id="b9dfe-118">El tipo de un campo debe ser al menos igual de accesible que el propio campo.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-118">The type of a field must be at least as accessible as the field itself.</span></span>|
|[<span data-ttu-id="b9dfe-119">Métodos</span><span class="sxs-lookup"><span data-stu-id="b9dfe-119">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)|<span data-ttu-id="b9dfe-120">El tipo de valor devuelto y los tipos de parámetros de un método deben ser al menos igual de accesibles que el propio método.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-120">The return type and parameter types of a method must be at least as accessible as the method itself.</span></span>|
|[<span data-ttu-id="b9dfe-121">Propiedades</span><span class="sxs-lookup"><span data-stu-id="b9dfe-121">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)|<span data-ttu-id="b9dfe-122">El tipo de una propiedad debe ser al menos igual de accesible que la misma propiedad.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-122">The type of a property must be at least as accessible as the property itself.</span></span>|
|[<span data-ttu-id="b9dfe-123">Eventos</span><span class="sxs-lookup"><span data-stu-id="b9dfe-123">Events</span></span>](../../programming-guide/events/index.md)|<span data-ttu-id="b9dfe-124">El tipo de un evento debe ser al menos igual de accesible que el propio evento.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-124">The type of an event must be at least as accessible as the event itself.</span></span>|
|[<span data-ttu-id="b9dfe-125">Indizadores</span><span class="sxs-lookup"><span data-stu-id="b9dfe-125">Indexers</span></span>](../../programming-guide/indexers/index.md)|<span data-ttu-id="b9dfe-126">Los tipos de parámetro y el tipo de un indexador deben ser al menos igual de accesibles que el propio indexador.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-126">The type and parameter types of an indexer must be at least as accessible as the indexer itself.</span></span>|
|[<span data-ttu-id="b9dfe-127">Operadores</span><span class="sxs-lookup"><span data-stu-id="b9dfe-127">Operators</span></span>](../operators/index.md)|<span data-ttu-id="b9dfe-128">El tipo de valor devuelto y los tipos de parámetro de un operador deben ser al menos igual de accesibles que el propio operador.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-128">The return type and parameter types of an operator must be at least as accessible as the operator itself.</span></span>|
|[<span data-ttu-id="b9dfe-129">Constructores</span><span class="sxs-lookup"><span data-stu-id="b9dfe-129">Constructors</span></span>](../../programming-guide/classes-and-structs/constructors.md)|<span data-ttu-id="b9dfe-130">Los tipos de parámetro de un constructor deben ser al menos igual de accesibles que el propio constructor.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-130">The parameter types of a constructor must be at least as accessible as the constructor itself.</span></span>|

## <a name="example"></a><span data-ttu-id="b9dfe-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9dfe-131">Example</span></span>

<span data-ttu-id="b9dfe-132">El siguiente ejemplo contiene declaraciones erróneas de diferentes tipos.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-132">The following example contains erroneous declarations of different types.</span></span> <span data-ttu-id="b9dfe-133">El comentario que sigue a cada declaración indica el error del compilador previsto.</span><span class="sxs-lookup"><span data-stu-id="b9dfe-133">The comment following each declaration indicates the expected compiler error.</span></span>

```csharp
// Restrictions on Using Accessibility Levels
// CS0052 expected as well as CS0053, CS0056, and CS0057
// To make the program work, change access level of both class B
// and MyPrivateMethod() to public.

using System;

// A delegate:
delegate int MyDelegate();

class B
{
    // A private method:
    static int MyPrivateMethod()
    {
        return 0;
    }
}

public class A
{
    // Error: The type B is less accessible than the field A.myField.
    public B myField = new B();

    // Error: The type B is less accessible
    // than the constant A.myConst.
    public readonly B myConst = new B();

    public B MyMethod()
    {
        // Error: The type B is less accessible 
        // than the method A.MyMethod.
        return new B();
    }

    // Error: The type B is less accessible than the property A.MyProp
    public B MyProp
    {
        set
        {
        }
    }

    MyDelegate d = new MyDelegate(B.MyPrivateMethod);
    // Even when B is declared public, you still get the error: 
    // "The parameter B.MyPrivateMethod is not accessible due to 
    // protection level."

    public static B operator +(A m1, B m2)
    {
        // Error: The type B is less accessible
        // than the operator A.operator +(A,B)
        return new B();
    }

    static void Main()
    {
        Console.Write("Compiled successfully");
    }
}
```

## <a name="c-language-specification"></a><span data-ttu-id="b9dfe-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="b9dfe-134">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="b9dfe-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9dfe-135">See also</span></span>

- [<span data-ttu-id="b9dfe-136">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="b9dfe-136">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="b9dfe-137">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="b9dfe-137">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b9dfe-138">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="b9dfe-138">C# Keywords</span></span>](../../language-reference/keywords/index.md)
- [<span data-ttu-id="b9dfe-139">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="b9dfe-139">Access Modifiers</span></span>](../../language-reference/keywords/access-modifiers.md)
- [<span data-ttu-id="b9dfe-140">Dominio de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="b9dfe-140">Accessibility Domain</span></span>](../../language-reference/keywords/accessibility-domain.md)
- [<span data-ttu-id="b9dfe-141">Niveles de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="b9dfe-141">Accessibility Levels</span></span>](../../language-reference/keywords/accessibility-levels.md)
- [<span data-ttu-id="b9dfe-142">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="b9dfe-142">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="b9dfe-143">public</span><span class="sxs-lookup"><span data-stu-id="b9dfe-143">public</span></span>](../../language-reference/keywords/public.md)
- [<span data-ttu-id="b9dfe-144">private</span><span class="sxs-lookup"><span data-stu-id="b9dfe-144">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="b9dfe-145">protected</span><span class="sxs-lookup"><span data-stu-id="b9dfe-145">protected</span></span>](../../language-reference/keywords/protected.md)
- [<span data-ttu-id="b9dfe-146">internal</span><span class="sxs-lookup"><span data-stu-id="b9dfe-146">internal</span></span>](../../language-reference/keywords/internal.md)
