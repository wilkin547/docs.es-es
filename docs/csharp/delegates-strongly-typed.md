---
title: Delegados fuertemente tipados
description: Obtenga información sobre cómo usar tipos de delegado genéricos para declarar tipos personalizados al crear una característica que necesita delegados.
ms.date: 06/20/2016
ms.assetid: 564a683d-352b-4e57-8bac-b466529daf6b
ms.openlocfilehash: 2e4cc1c7bfa0aaa90f3aaefa0da64c5486a9d10f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="strongly-typed-delegates"></a><span data-ttu-id="05506-103">Delegados fuertemente tipados</span><span class="sxs-lookup"><span data-stu-id="05506-103">Strongly Typed Delegates</span></span>

[<span data-ttu-id="05506-104">Anterior</span><span class="sxs-lookup"><span data-stu-id="05506-104">Previous</span></span>](delegate-class.md)

<span data-ttu-id="05506-105">En el artículo anterior pudo ver que con la palabra clave `delegate` se crean tipos de delegados concretos.</span><span class="sxs-lookup"><span data-stu-id="05506-105">In the previous article, you saw that you create specific delegate types using the `delegate` keyword.</span></span> 

<span data-ttu-id="05506-106">La clase abstracta Delegate proporciona la infraestructura para el acoplamiento débil y la invocación.</span><span class="sxs-lookup"><span data-stu-id="05506-106">The abstract Delegate class provide the infrastructure for loose coupling and invocation.</span></span> <span data-ttu-id="05506-107">Los tipos de delegado concretos se hacen mucho más útiles al adoptar y aplicar la seguridad de tipos para los métodos agregados a la lista de invocación de un objeto de delegado.</span><span class="sxs-lookup"><span data-stu-id="05506-107">Concrete Delegate types become much more useful by embracing and enforcing type safety for the methods that are added to the invocation list for a delegate object.</span></span> <span data-ttu-id="05506-108">Cuando se usa palabra clave `delegate` y se define un tipo de delegado concreto, el compilador genera esos métodos.</span><span class="sxs-lookup"><span data-stu-id="05506-108">When you use the `delegate` keyword and define a concrete delegate type, the compiler generates those methods.</span></span>

<span data-ttu-id="05506-109">En la práctica, esto daría lugar a la creación de nuevos tipos de delegado siempre que necesitara otra firma de método.</span><span class="sxs-lookup"><span data-stu-id="05506-109">In practice, this would lead to creating new delegate types whenever you need a different method signature.</span></span> <span data-ttu-id="05506-110">Este trabajo podría resultar tedioso pasado un tiempo.</span><span class="sxs-lookup"><span data-stu-id="05506-110">This work could get tedious after a time.</span></span> <span data-ttu-id="05506-111">Cada nueva característica exige nuevos tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="05506-111">Every new feature requires new delegate types.</span></span>

<span data-ttu-id="05506-112">Afortunadamente, esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="05506-112">Thankfully, this isn't necessary.</span></span> <span data-ttu-id="05506-113">.NET Core Framework contiene varios tipos que puede volver a usar siempre que necesite tipos de delegado.</span><span class="sxs-lookup"><span data-stu-id="05506-113">The .NET Core framework contains several types that you can reuse whenever you need delegate types.</span></span> <span data-ttu-id="05506-114">Son definiciones [genéricas](programming-guide/generics/index.md), por lo que puede declarar personalizaciones cuando necesite nuevas declaraciones de método.</span><span class="sxs-lookup"><span data-stu-id="05506-114">These are [generic](programming-guide/generics/index.md) definitions so you can declare customizations when you need new method declarations.</span></span> 

<span data-ttu-id="05506-115">El primero de estos tipos es el tipo <xref:System.Action> y distintas variaciones:</span><span class="sxs-lookup"><span data-stu-id="05506-115">The first of these types is the <xref:System.Action> type, and several variations:</span></span>

```csharp
public delegate void Action();
public delegate void Action<in T>(T arg);
public delegate void Action<in T1, in T2>(T1 arg1, T2 arg2);
// Other variations removed for brevity.
```

<span data-ttu-id="05506-116">El modificador `in` del argumento de tipo genérico se trata en el artículo sobre la covarianza.</span><span class="sxs-lookup"><span data-stu-id="05506-116">The `in` modifier on the generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="05506-117">Hay variaciones del delegado `Action` que contienen hasta 16 argumentos, como <xref:System.Action%6016>.</span><span class="sxs-lookup"><span data-stu-id="05506-117">There are variations of the `Action` delegate that contain up to 16 arguments such as <xref:System.Action%6016>.</span></span>
<span data-ttu-id="05506-118">Es importante que estas definiciones usen argumentos genéricos distintos para cada uno de los argumentos del delegado: eso proporciona la máxima flexibilidad.</span><span class="sxs-lookup"><span data-stu-id="05506-118">It's important that these definitions use different generic arguments for each of the delegate arguments: That gives you maximum flexibility.</span></span> <span data-ttu-id="05506-119">Los argumentos de método no tienen que ser, aunque pueden ser, del mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="05506-119">The method arguments need not be, but may be, the same type.</span></span>

<span data-ttu-id="05506-120">Use uno de los tipos `Action` para cualquier tipo de delegado que tenga un tipo de valor devuelto void.</span><span class="sxs-lookup"><span data-stu-id="05506-120">Use one of the `Action` types for any delegate type that has a void return type.</span></span>

<span data-ttu-id="05506-121">.NET Framework también incluye varios tipos de delegado genéricos que se pueden usar para los tipos de delegado que devuelven valores:</span><span class="sxs-lookup"><span data-stu-id="05506-121">The framework also includes several generic delegate types that you can use for delegate types that return values:</span></span>

```csharp
public delegate TResult Func<out TResult>();
public delegate TResult Func<in T1, out TResult>(T1 arg);
public delegate TResult Func<in T1, in T2, out TResult>(T1 arg1, T2 arg2);
// Other variations removed for brevity
```

<span data-ttu-id="05506-122">El modificador `out` del argumento de tipo genérico result se trata en el artículo sobre la covarianza.</span><span class="sxs-lookup"><span data-stu-id="05506-122">The `out` modifier on the result generic type argument is covered in the article on covariance.</span></span>

<span data-ttu-id="05506-123">Hay variaciones del delegado `Func` con hasta 16 argumentos de entrada, como <xref:System.Func%6017>.</span><span class="sxs-lookup"><span data-stu-id="05506-123">There are variations of the `Func` delegate with up to 16 input arguments such as <xref:System.Func%6017>.</span></span>
<span data-ttu-id="05506-124">Por convención, el tipo del resultado siempre es el último parámetro de tipo de todas las declaraciones `Func`.</span><span class="sxs-lookup"><span data-stu-id="05506-124">The type of the result is always the last type parameter in all the `Func` declarations, by convention.</span></span>

<span data-ttu-id="05506-125">Use uno de los tipos `Func` para cualquier tipo de delegado que devuelva un valor.</span><span class="sxs-lookup"><span data-stu-id="05506-125">Use one of the `Func` types for any delegate type that returns a value.</span></span>

<span data-ttu-id="05506-126">También hay un tipo <xref:System.Predicate%601> especializado para un delegado que devuelva una prueba en un valor único:</span><span class="sxs-lookup"><span data-stu-id="05506-126">There's also a specialized <xref:System.Predicate%601> type for a delegate that returns a test on a single value:</span></span>

```csharp
public delegate bool Predicate<in T>(T obj);
```

<span data-ttu-id="05506-127">Es posible que observe que para cualquier tipo `Predicate` existe un tipo `Func` estructuralmente equivalente, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="05506-127">You may notice that for any `Predicate` type, a structurally equivalent `Func` type exists For example:</span></span>

```csharp
Func<string, bool> TestForString;
Predicate<string> AnotherTestForString;
```

<span data-ttu-id="05506-128">Podría llegar a pensar que estos dos tipos son equivalentes,</span><span class="sxs-lookup"><span data-stu-id="05506-128">You might think these two types are equivalent.</span></span> <span data-ttu-id="05506-129">pero no lo son.</span><span class="sxs-lookup"><span data-stu-id="05506-129">They are not.</span></span>
<span data-ttu-id="05506-130">Estas dos variables no se pueden usar indistintamente.</span><span class="sxs-lookup"><span data-stu-id="05506-130">These two variables cannot be used interchangeably.</span></span> <span data-ttu-id="05506-131">A una variable de un tipo no se le puede asignar el otro tipo.</span><span class="sxs-lookup"><span data-stu-id="05506-131">A variable of one type cannot be assigned the other type.</span></span> <span data-ttu-id="05506-132">El sistema de tipos de C# usa los nombres de los tipos definidos, no la estructura.</span><span class="sxs-lookup"><span data-stu-id="05506-132">The C# type system uses the names of the defined types, not the structure.</span></span>

<span data-ttu-id="05506-133">Todas estas definiciones de tipos de delegado de la biblioteca de .NET Core deberían significar que no es necesario definir ningún tipo de delegado nuevo para cualquier característica nueva creada que exija delegados.</span><span class="sxs-lookup"><span data-stu-id="05506-133">All these delegate type definitions in the .NET Core Library should mean that you do not need to define a new delegate type for any new feature you create that requires delegates.</span></span> <span data-ttu-id="05506-134">Estas definiciones genéricas deberían proporcionar todos los tipos de delegado necesarios para la mayoría de las situaciones.</span><span class="sxs-lookup"><span data-stu-id="05506-134">These generic definitions should provide all the delegate types you need under most situations.</span></span> <span data-ttu-id="05506-135">Puede simplemente crear instancias de uno de estos tipos con los parámetros de tipo necesarios.</span><span class="sxs-lookup"><span data-stu-id="05506-135">You can simply instantiate one of these types with the required type parameters.</span></span> <span data-ttu-id="05506-136">En el caso de los algoritmos que se pueden convertir en genéricos, estos delegados se pueden usar como tipos genéricos.</span><span class="sxs-lookup"><span data-stu-id="05506-136">In the case of algorithms that can be made generic, these delegates can be used as generic types.</span></span> 

<span data-ttu-id="05506-137">Esto debería ahorrar tiempo y minimizar el número de nuevos tipos que es necesario crear para poder trabajar con delegados.</span><span class="sxs-lookup"><span data-stu-id="05506-137">This should save time, and minimize the number of new types that you need to create in order to work with delegates.</span></span>

<span data-ttu-id="05506-138">En el siguiente artículo se verán varios patrones comunes para trabajar con delegados en la práctica.</span><span class="sxs-lookup"><span data-stu-id="05506-138">In the next article, you'll see several common patterns for working with delegates in practice.</span></span>

[<span data-ttu-id="05506-139">Siguiente</span><span class="sxs-lookup"><span data-stu-id="05506-139">Next</span></span>](delegates-patterns.md)
