---
title: 'interface: Referencia de C#'
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 869f1398ae0af3c7379655aa018a9f4aacb934d7
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85243976"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="14394-102">:::no-loc text="interface"::: (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="14394-102">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="14394-103">Una interfaz define un contrato.</span><span class="sxs-lookup"><span data-stu-id="14394-103">An interface defines a contract.</span></span> <span data-ttu-id="14394-104">Cualquier [`class`](class.md) o [`struct`](../builtin-types/struct.md) que implemente ese contrato debe proporcionar una implementación de los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="14394-104">Any [`class`](class.md) or [`struct`](../builtin-types/struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="14394-105">A partir de C# 8.0, una interfaz puede definir una implementación predeterminada de miembros.</span><span class="sxs-lookup"><span data-stu-id="14394-105">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="14394-106">También puede definir miembros [`static`](static.md) para proporcionar una única implementación de funcionalidad común.</span><span class="sxs-lookup"><span data-stu-id="14394-106">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="14394-107">En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="14394-107">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="14394-108">Para obtener más información y ejemplos, vea [Interfaces](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="14394-108">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="14394-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14394-109">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="14394-110">Una interfaz puede ser un miembro de un espacio de nombres o una clase.</span><span class="sxs-lookup"><span data-stu-id="14394-110">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="14394-111">Una declaración de interfaz puede contener declaraciones (firmas sin ninguna implementación) de los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="14394-111">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="14394-112">Métodos</span><span class="sxs-lookup"><span data-stu-id="14394-112">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="14394-113">Propiedades</span><span class="sxs-lookup"><span data-stu-id="14394-113">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="14394-114">Indizadores</span><span class="sxs-lookup"><span data-stu-id="14394-114">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="14394-115">Eventos</span><span class="sxs-lookup"><span data-stu-id="14394-115">Events</span></span>](event.md)

<span data-ttu-id="14394-116">Normalmente, estas declaraciones de miembros anteriores no contienen ningún cuerpo.</span><span class="sxs-lookup"><span data-stu-id="14394-116">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="14394-117">A partir de C# 8.0, un miembro de interfaz puede declarar un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="14394-117">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="14394-118">Esto se conoce como *implementación predeterminada*.</span><span class="sxs-lookup"><span data-stu-id="14394-118">This is called a *default implementation*.</span></span> <span data-ttu-id="14394-119">Los miembros con cuerpos permiten que la interfaz proporcione una implementación "predeterminada" de las clases y las estructuras que no proporcionan una implementación de invalidación.</span><span class="sxs-lookup"><span data-stu-id="14394-119">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="14394-120">Además, a partir de C# 8.0, una interfaz puede incluir:</span><span class="sxs-lookup"><span data-stu-id="14394-120">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="14394-121">Constantes</span><span class="sxs-lookup"><span data-stu-id="14394-121">Constants</span></span>](const.md)
- [<span data-ttu-id="14394-122">Operadores</span><span class="sxs-lookup"><span data-stu-id="14394-122">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="14394-123">[Constructor estático](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span><span class="sxs-lookup"><span data-stu-id="14394-123">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="14394-124">Tipos anidados</span><span class="sxs-lookup"><span data-stu-id="14394-124">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- <span data-ttu-id="14394-125">[Campos, métodos, propiedades, indizadores y eventos estáticos](static.md).</span><span class="sxs-lookup"><span data-stu-id="14394-125">[Static fields, methods, properties, indexers, and events](static.md)</span></span>
- <span data-ttu-id="14394-126">Declaraciones de miembros con la sintaxis de implementación de interfaz explícita.</span><span class="sxs-lookup"><span data-stu-id="14394-126">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="14394-127">Modificadores de acceso explícitos (el acceso predeterminado es [`public`](access-modifiers.md)).</span><span class="sxs-lookup"><span data-stu-id="14394-127">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="14394-128">Es posible que las interfaces no contengan estado de instancia.</span><span class="sxs-lookup"><span data-stu-id="14394-128">Interfaces may not contain instance state.</span></span> <span data-ttu-id="14394-129">Aunque los campos estáticos ahora están permitidos, los campos de instancia no se permiten en las interfaces.</span><span class="sxs-lookup"><span data-stu-id="14394-129">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="14394-130">Las [propiedades automáticas de instancia](../../programming-guide/classes-and-structs/auto-implemented-properties.md) no se admiten en las interfaces, ya que declararían de forma implícita un campo oculto.</span><span class="sxs-lookup"><span data-stu-id="14394-130">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="14394-131">Esta regla tiene un efecto sutil en las declaraciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="14394-131">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="14394-132">En una declaración de interfaz, el código siguiente no declara una propiedad implementada automáticamente como hace en una `class` o un `struct`.</span><span class="sxs-lookup"><span data-stu-id="14394-132">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="14394-133">En su lugar, declara una propiedad que no tiene una implementación predeterminada pero que se debe implementar en cualquier tipo que implemente la interfaz:</span><span class="sxs-lookup"><span data-stu-id="14394-133">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="14394-134">Una interfaz puede heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="14394-134">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="14394-135">Cuando una interfaz [invalida un método](override.md) implementado en una interfaz base, debe usar la sintaxis de [implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="14394-135">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="14394-136">Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.</span><span class="sxs-lookup"><span data-stu-id="14394-136">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="14394-137">Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="14394-137">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="14394-138">A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="14394-138">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="14394-139">Además, solo se puede acceder a los miembros de interfaz predeterminados a través de una instancia de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="14394-139">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="14394-140">Para obtener más información sobre la implementación de interfaz explícita, vea [Implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="14394-140">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="14394-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14394-141">Example</span></span>

<span data-ttu-id="14394-142">En el ejemplo siguiente se muestra la implementación de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="14394-142">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="14394-143">En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación.</span><span class="sxs-lookup"><span data-stu-id="14394-143">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="14394-144">Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="14394-144">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="14394-145">especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="14394-145">C# language specification</span></span>

<span data-ttu-id="14394-146">Para obtener más información, vea la sección [Interfaces](~/_csharplang/spec/interfaces.md) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la especificación de características de [Miembros de interfaz predeterminados (C# 8.0)](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span><span class="sxs-lookup"><span data-stu-id="14394-146">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="14394-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="14394-147">See also</span></span>

- [<span data-ttu-id="14394-148">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="14394-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="14394-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="14394-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="14394-150">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="14394-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="14394-151">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="14394-151">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="14394-152">Interfaces</span><span class="sxs-lookup"><span data-stu-id="14394-152">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="14394-153">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="14394-153">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="14394-154">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="14394-154">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
