---
title: 'Miembros con cuerpo de expresión: Guía de programación de C#'
description: Conozca los miembros con forma de expresión. Vea ejemplos de código que usan la definición de cuerpo de expresiones para propiedades, constructores, finalizadores, etc.
ms.date: 02/06/2019
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
ms.openlocfilehash: e68e96e4aa3ff6a64590459a7197da1833e1a275
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381663"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="35d7e-104">Miembros con cuerpo de expresión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="35d7e-104">Expression-bodied members (C# programming guide)</span></span>

<span data-ttu-id="35d7e-105">Las definiciones de cuerpos de expresión permiten proporcionar la implementación de un miembro de una forma muy concisa y legible.</span><span class="sxs-lookup"><span data-stu-id="35d7e-105">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="35d7e-106">Se puede usar una definición de cuerpo de expresión siempre que la lógica de cualquier miembro compatible, como un método o propiedad, se componga de una expresión única.</span><span class="sxs-lookup"><span data-stu-id="35d7e-106">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="35d7e-107">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="35d7e-107">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="35d7e-108">donde *expresión* es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="35d7e-108">where *expression* is a valid expression.</span></span>

<span data-ttu-id="35d7e-109">La compatibilidad con las definiciones de cuerpos de expresión se introdujo para los métodos y las propiedades de solo lectura en C# 6 y se expandió en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="35d7e-109">Support for expression body definitions was introduced for methods and read-only properties in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="35d7e-110">Las definiciones de cuerpos de expresión se pueden usar con los miembros de tipo que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="35d7e-110">Expression body definitions can be used with the type members listed in the following table:</span></span>

|<span data-ttu-id="35d7e-111">Miembro</span><span class="sxs-lookup"><span data-stu-id="35d7e-111">Member</span></span>  |<span data-ttu-id="35d7e-112">Se admite desde...</span><span class="sxs-lookup"><span data-stu-id="35d7e-112">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="35d7e-113">Método</span><span class="sxs-lookup"><span data-stu-id="35d7e-113">Method</span></span>](#methods)  |<span data-ttu-id="35d7e-114">C# 6</span><span class="sxs-lookup"><span data-stu-id="35d7e-114">C# 6</span></span> |
|[<span data-ttu-id="35d7e-115">Propiedad de solo lectura</span><span class="sxs-lookup"><span data-stu-id="35d7e-115">Read-only property</span></span>](#read-only-properties)   |<span data-ttu-id="35d7e-116">C# 6</span><span class="sxs-lookup"><span data-stu-id="35d7e-116">C# 6</span></span>  |
|[<span data-ttu-id="35d7e-117">Property</span><span class="sxs-lookup"><span data-stu-id="35d7e-117">Property</span></span>](#properties)  |<span data-ttu-id="35d7e-118">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="35d7e-118">C# 7.0</span></span> |
|[<span data-ttu-id="35d7e-119">Constructor</span><span class="sxs-lookup"><span data-stu-id="35d7e-119">Constructor</span></span>](#constructors)   |<span data-ttu-id="35d7e-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="35d7e-120">C# 7.0</span></span> |
|[<span data-ttu-id="35d7e-121">Finalizador</span><span class="sxs-lookup"><span data-stu-id="35d7e-121">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="35d7e-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="35d7e-122">C# 7.0</span></span> |
|[<span data-ttu-id="35d7e-123">Indizador</span><span class="sxs-lookup"><span data-stu-id="35d7e-123">Indexer</span></span>](#indexers)       |<span data-ttu-id="35d7e-124">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="35d7e-124">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="35d7e-125">Métodos</span><span class="sxs-lookup"><span data-stu-id="35d7e-125">Methods</span></span>

<span data-ttu-id="35d7e-126">Un método con cuerpo de expresión consta de una sola expresión que devuelve un valor cuyo tipo coincide con el tipo de valor devuelto del método, o bien, para los métodos que devuelven `void`, que realiza alguna operación.</span><span class="sxs-lookup"><span data-stu-id="35d7e-126">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="35d7e-127">Por ejemplo, los tipos que reemplazan el método <xref:System.Object.ToString%2A> normalmente incluyen una sola expresión que devuelve la representación de cadena del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="35d7e-127">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span>

<span data-ttu-id="35d7e-128">En el ejemplo siguiente se define una clase `Person` que reemplaza el método <xref:System.Object.ToString%2A> con una definición de cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="35d7e-128">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="35d7e-129">También define un método `DisplayName` que muestra un nombre en la consola.</span><span class="sxs-lookup"><span data-stu-id="35d7e-129">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="35d7e-130">Tenga en cuenta que la palabra clave `return` no se usa en la definición de cuerpo de expresión de `ToString`.</span><span class="sxs-lookup"><span data-stu-id="35d7e-130">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="35d7e-131">Para más información, vea [Métodos (Guía de programación de C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-131">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>

## <a name="read-only-properties"></a><span data-ttu-id="35d7e-132">Propiedades de solo lectura</span><span class="sxs-lookup"><span data-stu-id="35d7e-132">Read-only properties</span></span>

<span data-ttu-id="35d7e-133">A partir de C# 6, puede usar la definición de cuerpo de expresión para implementar una propiedad de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="35d7e-133">Starting with C# 6, you can use expression body definition to implement a read-only property.</span></span> <span data-ttu-id="35d7e-134">Para ello, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="35d7e-134">To do that, use the following syntax:</span></span>

```csharp
PropertyType PropertyName => expression;
```

<span data-ttu-id="35d7e-135">En el ejemplo siguiente se define una clase `Location` cuya propiedad `Name` de solo lectura se implementa como una definición de cuerpo de expresión que devuelve el valor del campo privado `locationName`:</span><span class="sxs-lookup"><span data-stu-id="35d7e-135">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field:</span></span>

[!code-csharp[expression-bodied-read-only-property](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="35d7e-136">Para más información sobre las propiedades, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-136">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="properties"></a><span data-ttu-id="35d7e-137">Propiedades</span><span class="sxs-lookup"><span data-stu-id="35d7e-137">Properties</span></span>

<span data-ttu-id="35d7e-138">A partir de C# 7.0, puede usar las definiciones de cuerpo de expresión para implementar los descriptores de acceso `get` y `set` de propiedades.</span><span class="sxs-lookup"><span data-stu-id="35d7e-138">Starting with C# 7.0, you can use expression body definitions to implement property `get` and `set` accessors.</span></span> <span data-ttu-id="35d7e-139">En el ejemplo siguiente se muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="35d7e-139">The following example demonstrates how to do that:</span></span>

[!code-csharp[expression-bodied-property-get-set](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]

<span data-ttu-id="35d7e-140">Para más información sobre las propiedades, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-140">For more information about properties, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="constructors"></a><span data-ttu-id="35d7e-141">Constructores</span><span class="sxs-lookup"><span data-stu-id="35d7e-141">Constructors</span></span>

<span data-ttu-id="35d7e-142">Una definición de cuerpo de expresión para un constructor normalmente consta de una expresión de asignación única o una llamada de método que controla los argumentos del constructor o inicializa el estado de la instancia.</span><span class="sxs-lookup"><span data-stu-id="35d7e-142">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span>

<span data-ttu-id="35d7e-143">En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*.</span><span class="sxs-lookup"><span data-stu-id="35d7e-143">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="35d7e-144">La definición del cuerpo de expresión asigna el argumento a la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="35d7e-144">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="35d7e-145">Para más información, vea [Constructores (Guía de programación de C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-145">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="35d7e-146">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="35d7e-146">Finalizers</span></span>

<span data-ttu-id="35d7e-147">Una definición de cuerpo de expresión para un finalizador normalmente contiene instrucciones de limpieza, como las instrucciones que liberan recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="35d7e-147">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="35d7e-148">En el ejemplo siguiente se define un finalizador que usa una definición de cuerpo de expresión para indicar que el finalizador se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="35d7e-148">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="35d7e-149">Para más información, vea [Finalizadores (Guía de programación de C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-149">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="35d7e-150">Indizadores</span><span class="sxs-lookup"><span data-stu-id="35d7e-150">Indexers</span></span>

<span data-ttu-id="35d7e-151">Como las propiedades, los descriptores de acceso `get` y `set` del indizador constan de las definiciones de cuerpos de expresión si el descriptor de acceso `get` está formado por una sola expresión que devuelve un valor o el descriptor de acceso `set` realiza una asignación simple.</span><span class="sxs-lookup"><span data-stu-id="35d7e-151">Like with properties, indexer `get` and `set` accessors consist of expression body definitions if the `get` accessor consists of a single expression that returns a value or the `set` accessor performs a simple assignment.</span></span>

<span data-ttu-id="35d7e-152">En el ejemplo siguiente se define una clase denominada `Sports` que incluye una matriz <xref:System.String> interna que contiene los nombres de varios deportes.</span><span class="sxs-lookup"><span data-stu-id="35d7e-152">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="35d7e-153">Los descriptores de acceso `get` y `set` del indizador se implementan como definiciones de cuerpos de expresión.</span><span class="sxs-lookup"><span data-stu-id="35d7e-153">Both the indexer `get` and `set` accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)]

<span data-ttu-id="35d7e-154">Para más información, vea [Indizadores (Guía de programación de C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="35d7e-154">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>
