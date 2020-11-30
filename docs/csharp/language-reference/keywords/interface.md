---
description: ':::no-loc text=interface::: (Referencia de C#)'
title: 'interface: Referencia de C#'
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 24f95e828522f467c519c0c8a7ba9410aa97af4e
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "89134593"
---
# <a name="no-loc-textinterface-c-reference"></a><span data-ttu-id="587de-103">:::no-loc text="interface"::: (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="587de-103">:::no-loc text="interface"::: (C# Reference)</span></span>

<span data-ttu-id="587de-104">Una interfaz define un contrato.</span><span class="sxs-lookup"><span data-stu-id="587de-104">An interface defines a contract.</span></span> <span data-ttu-id="587de-105">Cualquier [`class`](class.md) o [`struct`](../builtin-types/struct.md) que implemente ese contrato debe proporcionar una implementación de los miembros definidos en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="587de-105">Any [`class`](class.md) or [`struct`](../builtin-types/struct.md) that implements that contract must provide an implementation of the members defined in the interface.</span></span> <span data-ttu-id="587de-106">A partir de C# 8.0, una interfaz puede definir una implementación predeterminada de miembros.</span><span class="sxs-lookup"><span data-stu-id="587de-106">Beginning with C# 8.0, an interface may define a default implementation for members.</span></span> <span data-ttu-id="587de-107">También puede definir miembros [`static`](static.md) para proporcionar una única implementación de funcionalidad común.</span><span class="sxs-lookup"><span data-stu-id="587de-107">It may also define [`static`](static.md) members in order to provide a single implementation for common functionality.</span></span>

<span data-ttu-id="587de-108">En el ejemplo siguiente, la clase `ImplementationClass` debe implementar un método denominado `SampleMethod` que no tiene ningún parámetro y devuelve `void`.</span><span class="sxs-lookup"><span data-stu-id="587de-108">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="587de-109">Para obtener más información y ejemplos, vea [Interfaces](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="587de-109">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="587de-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="587de-110">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="587de-111">Una interfaz puede ser un miembro de un espacio de nombres o una clase.</span><span class="sxs-lookup"><span data-stu-id="587de-111">An interface can be a member of a namespace or a class.</span></span> <span data-ttu-id="587de-112">Una declaración de interfaz puede contener declaraciones (firmas sin ninguna implementación) de los miembros siguientes:</span><span class="sxs-lookup"><span data-stu-id="587de-112">An interface declaration can contain declarations (signatures without any implementation) of the following members:</span></span>

- [<span data-ttu-id="587de-113">Métodos</span><span class="sxs-lookup"><span data-stu-id="587de-113">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="587de-114">Propiedades</span><span class="sxs-lookup"><span data-stu-id="587de-114">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="587de-115">Indizadores</span><span class="sxs-lookup"><span data-stu-id="587de-115">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="587de-116">Eventos</span><span class="sxs-lookup"><span data-stu-id="587de-116">Events</span></span>](event.md)

<span data-ttu-id="587de-117">Normalmente, estas declaraciones de miembros anteriores no contienen ningún cuerpo.</span><span class="sxs-lookup"><span data-stu-id="587de-117">These preceding member declarations typically do not contain a body.</span></span> <span data-ttu-id="587de-118">A partir de C# 8.0, un miembro de interfaz puede declarar un cuerpo.</span><span class="sxs-lookup"><span data-stu-id="587de-118">Beginning with C# 8.0, an interface member may declare a body.</span></span> <span data-ttu-id="587de-119">Esto se conoce como *implementación predeterminada*.</span><span class="sxs-lookup"><span data-stu-id="587de-119">This is called a *default implementation*.</span></span> <span data-ttu-id="587de-120">Los miembros con cuerpos permiten que la interfaz proporcione una implementación "predeterminada" de las clases y las estructuras que no proporcionan una implementación de invalidación.</span><span class="sxs-lookup"><span data-stu-id="587de-120">Members with bodies permit the interface to provide a "default" implementation for classes and structs that don't provide an overriding implementation.</span></span> <span data-ttu-id="587de-121">Además, a partir de C# 8.0, una interfaz puede incluir:</span><span class="sxs-lookup"><span data-stu-id="587de-121">In addition, beginning with C# 8.0, an interface may include:</span></span>

- [<span data-ttu-id="587de-122">Constantes</span><span class="sxs-lookup"><span data-stu-id="587de-122">Constants</span></span>](const.md)
- [<span data-ttu-id="587de-123">Operadores</span><span class="sxs-lookup"><span data-stu-id="587de-123">Operators</span></span>](../operators/operator-overloading.md)
- <span data-ttu-id="587de-124">[Constructor estático](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span><span class="sxs-lookup"><span data-stu-id="587de-124">[Static constructor](../../programming-guide/classes-and-structs/constructors.md#static-constructors).</span></span>
- [<span data-ttu-id="587de-125">Tipos anidados</span><span class="sxs-lookup"><span data-stu-id="587de-125">Nested types</span></span>](../../programming-guide/classes-and-structs/nested-types.md)
- <span data-ttu-id="587de-126">[Campos, métodos, propiedades, indizadores y eventos estáticos](static.md).</span><span class="sxs-lookup"><span data-stu-id="587de-126">[Static fields, methods, properties, indexers, and events](static.md)</span></span>
- <span data-ttu-id="587de-127">Declaraciones de miembros con la sintaxis de implementación de interfaz explícita.</span><span class="sxs-lookup"><span data-stu-id="587de-127">Member declarations using the explicit interface implementation syntax.</span></span>
- <span data-ttu-id="587de-128">Modificadores de acceso explícitos (el acceso predeterminado es [`public`](access-modifiers.md)).</span><span class="sxs-lookup"><span data-stu-id="587de-128">Explicit access modifiers (the default access is [`public`](access-modifiers.md)).</span></span>

<span data-ttu-id="587de-129">Es posible que las interfaces no contengan estado de instancia.</span><span class="sxs-lookup"><span data-stu-id="587de-129">Interfaces may not contain instance state.</span></span> <span data-ttu-id="587de-130">Aunque los campos estáticos ahora están permitidos, los campos de instancia no se permiten en las interfaces.</span><span class="sxs-lookup"><span data-stu-id="587de-130">While static fields are now permitted, instance fields are not permitted in interfaces.</span></span> <span data-ttu-id="587de-131">Las [propiedades automáticas de instancia](../../programming-guide/classes-and-structs/auto-implemented-properties.md) no se admiten en las interfaces, ya que declararían de forma implícita un campo oculto.</span><span class="sxs-lookup"><span data-stu-id="587de-131">[Instance auto-properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) are not supported in interfaces, as they would implicitly declare a hidden field.</span></span> <span data-ttu-id="587de-132">Esta regla tiene un efecto sutil en las declaraciones de propiedad.</span><span class="sxs-lookup"><span data-stu-id="587de-132">This rule has a subtle effect on property declarations.</span></span> <span data-ttu-id="587de-133">En una declaración de interfaz, el código siguiente no declara una propiedad implementada automáticamente como hace en una `class` o un `struct`.</span><span class="sxs-lookup"><span data-stu-id="587de-133">In an interface declaration, the following code does not declare an auto-implemented property as it does in a `class` or `struct`.</span></span> <span data-ttu-id="587de-134">En su lugar, declara una propiedad que no tiene una implementación predeterminada pero que se debe implementar en cualquier tipo que implemente la interfaz:</span><span class="sxs-lookup"><span data-stu-id="587de-134">Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface:</span></span>

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

<span data-ttu-id="587de-135">Una interfaz puede heredar de una o varias interfaces base.</span><span class="sxs-lookup"><span data-stu-id="587de-135">An interface can inherit from one or more base interfaces.</span></span> <span data-ttu-id="587de-136">Cuando una interfaz [invalida un método](override.md) implementado en una interfaz base, debe usar la sintaxis de [implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="587de-136">When an interface [overrides a method](override.md) implemented in a base interface, it must use the [explicit interface implementation](../../programming-guide/interfaces/explicit-interface-implementation.md) syntax.</span></span>

<span data-ttu-id="587de-137">Cuando una lista de tipos base contiene una clase e interfaces base, la clase base debe aparecer primero en la lista.</span><span class="sxs-lookup"><span data-stu-id="587de-137">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="587de-138">Una clase que implementa una interfaz puede implementar explícitamente miembros de esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="587de-138">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="587de-139">A un miembro implementado explícitamente solo se puede tener acceso mediante una instancia de la interfaz, y no mediante una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="587de-139">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span> <span data-ttu-id="587de-140">Además, solo se puede acceder a los miembros de interfaz predeterminados a través de una instancia de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="587de-140">In addition, default interface members can only be accessed through an instance of the interface.</span></span>

<span data-ttu-id="587de-141">Para obtener más información sobre la implementación de interfaz explícita, vea [Implementación de interfaz explícita](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="587de-141">For more information about explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="587de-142">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="587de-142">Example</span></span>

<span data-ttu-id="587de-143">En el ejemplo siguiente se muestra la implementación de una interfaz.</span><span class="sxs-lookup"><span data-stu-id="587de-143">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="587de-144">En este ejemplo, la interfaz contiene la declaración de propiedad y la clase contiene la implementación.</span><span class="sxs-lookup"><span data-stu-id="587de-144">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="587de-145">Cualquier instancia de una clase que implemente `IPoint` tiene las propiedades de entero `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="587de-145">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="587de-146">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="587de-146">C# language specification</span></span>

<span data-ttu-id="587de-147">Para obtener más información, vea la sección [Interfaces](~/_csharplang/spec/interfaces.md) de [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md) y la especificación de características de [Miembros de interfaz predeterminados (C# 8.0)](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span><span class="sxs-lookup"><span data-stu-id="587de-147">For more information, see the [Interfaces](~/_csharplang/spec/interfaces.md) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the feature specification for [Default interface members - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="587de-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="587de-148">See also</span></span>

- [<span data-ttu-id="587de-149">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="587de-149">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="587de-150">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="587de-150">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="587de-151">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="587de-151">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="587de-152">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="587de-152">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="587de-153">Interfaces</span><span class="sxs-lookup"><span data-stu-id="587de-153">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="587de-154">Utilizar propiedades</span><span class="sxs-lookup"><span data-stu-id="587de-154">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="587de-155">Utilizar indizadores</span><span class="sxs-lookup"><span data-stu-id="587de-155">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
