---
title: 'Miembros con cuerpo de expresión: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- expression-bodied members[C#]
- C# language, expresion-bodied members
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36f71352dca584c107af4f45850ce21bb016ba01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2018
ms.locfileid: "53238122"
---
# <a name="expression-bodied-members-c-programming-guide"></a><span data-ttu-id="6c78c-102">Miembros con cuerpo de expresión (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="6c78c-102">Expression-bodied members (C# programming guide)</span></span>
<span data-ttu-id="6c78c-103">Las definiciones de cuerpos de expresión permiten proporcionar la implementación de un miembro de una forma muy concisa y legible.</span><span class="sxs-lookup"><span data-stu-id="6c78c-103">Expression body definitions let you provide a member's implementation in a very concise, readable form.</span></span> <span data-ttu-id="6c78c-104">Se puede usar una definición de cuerpo de expresión siempre que la lógica de cualquier miembro compatible, como un método o propiedad, se componga de una expresión única.</span><span class="sxs-lookup"><span data-stu-id="6c78c-104">You can use an expression body definition whenever the logic for any supported member, such as a method or property, consists of a single expression.</span></span> <span data-ttu-id="6c78c-105">Una definición de cuerpo de expresión tiene la siguiente sintaxis general:</span><span class="sxs-lookup"><span data-stu-id="6c78c-105">An expression body definition has the following general syntax:</span></span>

```csharp
member => expression;
```

<span data-ttu-id="6c78c-106">donde *expresión* es una expresión válida.</span><span class="sxs-lookup"><span data-stu-id="6c78c-106">where *expression* is a valid expression.</span></span> 

<span data-ttu-id="6c78c-107">La compatibilidad con las definiciones de cuerpos de expresión se introdujo para los métodos y descriptores de acceso get de propiedad en C# 6 y se expandió en C# 7.0.</span><span class="sxs-lookup"><span data-stu-id="6c78c-107">Support for expression body definitions was introduced for methods and property get accessors in C# 6 and was expanded in C# 7.0.</span></span> <span data-ttu-id="6c78c-108">Las definiciones de cuerpos de expresión se pueden usar con los miembros de tipo que se muestran en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c78c-108">Expression body definitions can be used with the type members listed in the following table:</span></span> 

|<span data-ttu-id="6c78c-109">Miembro</span><span class="sxs-lookup"><span data-stu-id="6c78c-109">Member</span></span>  |<span data-ttu-id="6c78c-110">Se admite desde...</span><span class="sxs-lookup"><span data-stu-id="6c78c-110">Supported as of...</span></span> |
|---------|---------|
|[<span data-ttu-id="6c78c-111">Método</span><span class="sxs-lookup"><span data-stu-id="6c78c-111">Method</span></span>](#methods)  |<span data-ttu-id="6c78c-112">C# 6</span><span class="sxs-lookup"><span data-stu-id="6c78c-112">C# 6</span></span> |
|[<span data-ttu-id="6c78c-113">Constructor</span><span class="sxs-lookup"><span data-stu-id="6c78c-113">Constructor</span></span>](#constructors)   |<span data-ttu-id="6c78c-114">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="6c78c-114">C# 7.0</span></span> |
|[<span data-ttu-id="6c78c-115">Finalizador</span><span class="sxs-lookup"><span data-stu-id="6c78c-115">Finalizer</span></span>](#finalizers)     |<span data-ttu-id="6c78c-116">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="6c78c-116">C# 7.0</span></span> |
|[<span data-ttu-id="6c78c-117">Descriptor de acceso get de propiedad</span><span class="sxs-lookup"><span data-stu-id="6c78c-117">Property Get</span></span>](#property-get-statements)  |<span data-ttu-id="6c78c-118">C# 6</span><span class="sxs-lookup"><span data-stu-id="6c78c-118">C# 6</span></span> |
|[<span data-ttu-id="6c78c-119">Descriptor de acceso set de propiedad</span><span class="sxs-lookup"><span data-stu-id="6c78c-119">Property Set</span></span>](#property-set-statements)  |<span data-ttu-id="6c78c-120">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="6c78c-120">C# 7.0</span></span> |
|[<span data-ttu-id="6c78c-121">Indizador</span><span class="sxs-lookup"><span data-stu-id="6c78c-121">Indexer</span></span>](#indexers)       |<span data-ttu-id="6c78c-122">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="6c78c-122">C# 7.0</span></span> |

## <a name="methods"></a><span data-ttu-id="6c78c-123">Métodos</span><span class="sxs-lookup"><span data-stu-id="6c78c-123">Methods</span></span>

<span data-ttu-id="6c78c-124">Un método con cuerpo de expresión consta de una sola expresión que devuelve un valor cuyo tipo coincide con el tipo de valor devuelto del método, o bien, para los métodos que devuelven `void`, que realiza alguna operación.</span><span class="sxs-lookup"><span data-stu-id="6c78c-124">An expression-bodied method consists of a single expression that returns a value whose type matches the method's return type, or, for methods that return `void`, that performs some operation.</span></span> <span data-ttu-id="6c78c-125">Por ejemplo, los tipos que reemplazan el método <xref:System.Object.ToString%2A> normalmente incluyen una sola expresión que devuelve la representación de cadena del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="6c78c-125">For example, types that override the <xref:System.Object.ToString%2A> method typically include a single expression that returns the string representation of the current object.</span></span> 

<span data-ttu-id="6c78c-126">En el ejemplo siguiente se define una clase `Person` que reemplaza el método <xref:System.Object.ToString%2A> con una definición de cuerpo de expresión.</span><span class="sxs-lookup"><span data-stu-id="6c78c-126">The following example defines a `Person` class that overrides the <xref:System.Object.ToString%2A> method with an expression body definition.</span></span> <span data-ttu-id="6c78c-127">También define un método `DisplayName` que muestra un nombre en la consola.</span><span class="sxs-lookup"><span data-stu-id="6c78c-127">It also defines a `DisplayName` method that displays a name to the console.</span></span> <span data-ttu-id="6c78c-128">Tenga en cuenta que la palabra clave `return` no se usa en la definición de cuerpo de expresión de `ToString`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-128">Note that the `return` keyword is not used in the `ToString` expression body definition.</span></span>

[!code-csharp[expression-bodied-methods](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-methods.cs)]  

<span data-ttu-id="6c78c-129">Para más información, vea [Métodos (Guía de programación de C#)](../classes-and-structs/methods.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-129">For more information, see [Methods (C# Programming Guide)](../classes-and-structs/methods.md).</span></span>
 
## <a name="constructors"></a><span data-ttu-id="6c78c-130">Constructores</span><span class="sxs-lookup"><span data-stu-id="6c78c-130">Constructors</span></span>

<span data-ttu-id="6c78c-131">Una definición de cuerpo de expresión para un constructor normalmente consta de una expresión de asignación única o una llamada de método que controla los argumentos del constructor o inicializa el estado de la instancia.</span><span class="sxs-lookup"><span data-stu-id="6c78c-131">An expression body definition for a constructor typically consists of a single assignment expression or a method call that handles the constructor's arguments or initializes instance state.</span></span> 

<span data-ttu-id="6c78c-132">En el ejemplo siguiente se define una clase `Location` cuyo constructor tiene un único parámetro de cadena denominado *name*.</span><span class="sxs-lookup"><span data-stu-id="6c78c-132">The following example defines a `Location` class whose constructor has a single string parameter named *name*.</span></span> <span data-ttu-id="6c78c-133">La definición del cuerpo de expresión asigna el argumento a la propiedad `Name`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-133">The expression body definition assigns the argument to the `Name` property.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="6c78c-134">Para más información, vea [Constructores (Guía de programación de C#)](../classes-and-structs/constructors.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-134">For more information, see [Constructors (C# Programming Guide)](../classes-and-structs/constructors.md).</span></span>

## <a name="finalizers"></a><span data-ttu-id="6c78c-135">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="6c78c-135">Finalizers</span></span>

<span data-ttu-id="6c78c-136">Una definición de cuerpo de expresión para un finalizador normalmente contiene instrucciones de limpieza, como las instrucciones que liberan recursos no administrados.</span><span class="sxs-lookup"><span data-stu-id="6c78c-136">An expression body definition for a finalizer typically contains cleanup statements, such as statements that release unmanaged resources.</span></span>

<span data-ttu-id="6c78c-137">En el ejemplo siguiente se define un finalizador que usa una definición de cuerpo de expresión para indicar que el finalizador se ha llamado.</span><span class="sxs-lookup"><span data-stu-id="6c78c-137">The following example defines a finalizer that uses an expression body definition to indicate that the finalizer has been called.</span></span>

[!code-csharp[expression-bodied-finalizer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-destructor.cs#1)]  

<span data-ttu-id="6c78c-138">Para más información, vea [Finalizadores (Guía de programación de C#)](../classes-and-structs/destructors.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-138">For more information, see [Finalizers (C# Programming Guide)](../classes-and-structs/destructors.md).</span></span>

## <a name="property-get-statements"></a><span data-ttu-id="6c78c-139">Instrucciones get de propiedad</span><span class="sxs-lookup"><span data-stu-id="6c78c-139">Property get statements</span></span>

<span data-ttu-id="6c78c-140">Si decide implementar un descriptor de acceso get de la propiedad usted mismo, puede usar una definición de cuerpo de expresión para expresiones únicas que simplemente devuelven el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c78c-140">If you choose to implement a property get accessor yourself, you can use an expression body definition for single expressions that simply return the property value.</span></span> <span data-ttu-id="6c78c-141">Tenga en cuenta que se usa la instrucción `return`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-141">Note that the `return` statement isn't used.</span></span>

<span data-ttu-id="6c78c-142">En el ejemplo siguiente se define una propiedad `Location.Name` cuyo descriptor de acceso get de propiedad devuelve el valor del campo `locationName` privado que respalda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c78c-142">The following example defines a `Location.Name` property whose property get accessor returns the value of the private `locationName` field that backs the property.</span></span> 

[!code-csharp[expression-bodied-property-getter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="6c78c-143">Las propiedades de solo lectura que usan una definición de cuerpo de expresión se pueden implementar sin una instrucción `set` explícita.</span><span class="sxs-lookup"><span data-stu-id="6c78c-143">Read-only properties that use an expression body definition can be implemented without an explicit `set` statement.</span></span> <span data-ttu-id="6c78c-144">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6c78c-144">The syntax is:</span></span>

```csharp
PropertyName => returnValue;
```

<span data-ttu-id="6c78c-145">En el ejemplo siguiente se define una clase `Location` cuya propiedad `Name` de solo lectura se implementa como una definición de cuerpo de expresión que devuelve el valor del campo privado `locationName`.</span><span class="sxs-lookup"><span data-stu-id="6c78c-145">The following example defines a `Location` class whose read-only `Name` property is implemented as an expression body definition that returns the value of the private `locationName` field.</span></span>

[!code-csharp[expression-bodied-constructor](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-readonly.cs#1)]  

<span data-ttu-id="6c78c-146">Para más información, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-146">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="property-set-statements"></a><span data-ttu-id="6c78c-147">Instrucciones set de propiedad</span><span class="sxs-lookup"><span data-stu-id="6c78c-147">Property set statements</span></span>

<span data-ttu-id="6c78c-148">Si decide implementar un descriptor de acceso set de propiedad usted mismo, puede usar una definición de cuerpo de expresión para una expresión de una sola línea que asigne un valor al campo que respalda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c78c-148">If you choose to implement a property set accessor yourself, you can use an expression body definition for a single-line expression that assigns a value to the field that backs the property.</span></span>

<span data-ttu-id="6c78c-149">En el ejemplo siguiente se define una propiedad `Location.Name` cuya instrucción set de propiedad asigna su argumento de entrada al valor del campo `locationName` privado que respalda la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6c78c-149">The following example defines a `Location.Name` property whose property set statement assigns its input argument to the private `locationName` field that backs the property.</span></span>

[!code-csharp[expression-bodied-property-setter](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-ctor.cs#1)]  

<span data-ttu-id="6c78c-150">Para más información, vea [Propiedades (Guía de programación de C#)](../classes-and-structs/properties.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-150">For more information, see [Properties (C# Programming Guide)](../classes-and-structs/properties.md).</span></span>

## <a name="indexers"></a><span data-ttu-id="6c78c-151">Indizadores</span><span class="sxs-lookup"><span data-stu-id="6c78c-151">Indexers</span></span>

<span data-ttu-id="6c78c-152">Como las propiedades, los descriptores de acceso get y set de un indizador constan de las definiciones de cuerpos de expresión si el descriptor de acceso get está formado por una sola instrucción que devuelve un valor o el descriptor de acceso set realiza una asignación simple.</span><span class="sxs-lookup"><span data-stu-id="6c78c-152">Like properties, an indexer's get and set accessors consist of expression body definitions if the get accessor consists of a single statement that returns a value or the set accessor performs a simple assignment.</span></span>

<span data-ttu-id="6c78c-153">En el ejemplo siguiente se define una clase denominada `Sports` que incluye una matriz <xref:System.String> interna que contiene los nombres de varios deportes.</span><span class="sxs-lookup"><span data-stu-id="6c78c-153">The following example defines a class named `Sports` that includes an internal <xref:System.String> array that contains the names of a number of sports.</span></span> <span data-ttu-id="6c78c-154">Los descriptores de acceso get y set del indizador se implementan como definiciones de cuerpos de expresión.</span><span class="sxs-lookup"><span data-stu-id="6c78c-154">Both the indexer's get and set accessors are implemented as expression body definitions.</span></span>

[!code-csharp[expression-bodied-indexer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/expr-bodied-indexers.cs#1)] 

<span data-ttu-id="6c78c-155">Para más información, vea [Indizadores (Guía de programación de C#)](../indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6c78c-155">For more information, see [Indexers (C# Programming Guide)](../indexers/index.md).</span></span>

