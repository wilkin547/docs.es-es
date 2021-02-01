---
title: 'Utilizar constructores: Guía de programación de C#'
description: En este ejemplo se muestra cómo crear una instancia de una clase mediante el operador new en C#. El constructor simple se invoca después de asignar memoria para el nuevo objeto.
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: 161c243f16f6705fa8fcf79360f92a74e4d0b27b
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899261"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="8ac67-104">Utilizar constructores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="8ac67-104">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="8ac67-105">Cuando se crea una [class](../../language-reference/keywords/class.md) o un [struct](../../language-reference/builtin-types/struct.md), se llama a su constructor.</span><span class="sxs-lookup"><span data-stu-id="8ac67-105">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="8ac67-106">Los constructores tienen el mismo nombre que la class o el struct y suelen inicializar los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="8ac67-106">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="8ac67-107">En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple.</span><span class="sxs-lookup"><span data-stu-id="8ac67-107">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="8ac67-108">Luego, se crea una instancia de la clase con el operador [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-108">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="8ac67-109">El constructor `Taxi` se invoca con el operador `new` inmediatamente después de asignar memoria para el nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="8ac67-109">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[TaxiExample#1](snippets/using-constructors/Program.cs#1)]
  
 <span data-ttu-id="8ac67-110">Un constructor que no toma ningún parámetro se denomina *constructor sin parámetros*.</span><span class="sxs-lookup"><span data-stu-id="8ac67-110">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="8ac67-111">Los constructores sin parámetros se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se especifica ningún argumento en `new`.</span><span class="sxs-lookup"><span data-stu-id="8ac67-111">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="8ac67-112">Para obtener más información, vea [Instance Constructors](./instance-constructors.md) (Constructores de instancias [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="8ac67-112">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="8ac67-113">A menos que la clase sea [static](../../language-reference/keywords/static.md), las clases sin constructores tienen un constructor público sin parámetros por el compilador de C# con el fin de habilitar la creación de instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="8ac67-113">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="8ac67-114">Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-114">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="8ac67-115">Puede impedir que se cree una instancia de una clase convirtiendo el constructor en privado, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ac67-115">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[PrivateConstructor#2](snippets/using-constructors/Program.cs#2)]
  
 <span data-ttu-id="8ac67-116">Para obtener más información, vea [Private Constructors](./private-constructors.md) (Constructores privados [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="8ac67-116">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="8ac67-117">Los constructores de tipos [struct](../../language-reference/builtin-types/struct.md) son similares a los constructores de clases, pero `structs` no puede contener un constructor sin parámetros explícito porque el compilador proporciona uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="8ac67-117">Constructors for [struct](../../language-reference/builtin-types/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="8ac67-118">Este constructor inicializa cada campo del `struct` en los [valores predeterminados](../../language-reference/builtin-types/default-values.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-118">This constructor initializes each field in the `struct` to the [default value](../../language-reference/builtin-types/default-values.md).</span></span> <span data-ttu-id="8ac67-119">Pero este constructor sin parámetros solo se invoca si las instancias de `struct` se crean con `new`.</span><span class="sxs-lookup"><span data-stu-id="8ac67-119">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="8ac67-120">Por ejemplo, este código usa el constructor sin parámetros para <xref:System.Int32>, por lo que se tiene la certeza de que el entero se inicializa:</span><span class="sxs-lookup"><span data-stu-id="8ac67-120">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="8ac67-121">Si bien, el siguiente código genera un error del compilador porque no usa `new` y porque intenta usar un objeto que no se ha inicializado:</span><span class="sxs-lookup"><span data-stu-id="8ac67-121">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="8ac67-122">También puede inicializar o asignar los objetos basados en `structs` (incluidos todos los tipos numéricos integrados) y luego usarlos como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8ac67-122">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="8ac67-123">Por lo que no es necesario llamar al constructor sin parámetros para un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="8ac67-123">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="8ac67-124">Tanto las clases como los `structs` pueden definir constructores que toman parámetros.</span><span class="sxs-lookup"><span data-stu-id="8ac67-124">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="8ac67-125">Los constructores que toman parámetros deben llamarse mediante una instrucción `new` o [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-125">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="8ac67-126">Las clases y `structs` también pueden definir varios constructores y no es necesario definir un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="8ac67-126">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="8ac67-127">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac67-127">For example:</span></span>  
  
 [!code-csharp[EmployeeExample#3](snippets/using-constructors/Program.cs#3)]
  
 <span data-ttu-id="8ac67-128">Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="8ac67-128">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[InstantiatingEmployeeConstructors#4](snippets/using-constructors/Program.cs#4)]
  
 <span data-ttu-id="8ac67-129">Un constructor puede usar la palabra clave `base` para llamar al constructor de una clase base.</span><span class="sxs-lookup"><span data-stu-id="8ac67-129">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="8ac67-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8ac67-130">For example:</span></span>  
  
 [!code-csharp[ManagerInheritingEmployee#5](snippets/using-constructors/Program.cs#5)]
  
 <span data-ttu-id="8ac67-131">En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor.</span><span class="sxs-lookup"><span data-stu-id="8ac67-131">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="8ac67-132">La palabra clave `base` puede usarse con o sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="8ac67-132">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="8ac67-133">Los parámetros del constructor se pueden usar como parámetros en `base` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="8ac67-133">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="8ac67-134">Para obtener más información, vea [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-134">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="8ac67-135">En una clase derivada, si un constructor de clase base no se llama explícitamente con la palabra clave `base`, se llama implícitamente al constructor sin parámetros, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="8ac67-135">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="8ac67-136">Esto significa que las siguientes declaraciones del constructor son en efecto iguales:</span><span class="sxs-lookup"><span data-stu-id="8ac67-136">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[ManagerImplicitlyCallingParameterlessBaseConstructor#6](snippets/using-constructors/Program.cs#6)]
  
 [!code-csharp[ManagerExplicitlyCallingParameterlessBaseConstructor#7](snippets/using-constructors/Program.cs#7)]
  
 <span data-ttu-id="8ac67-137">Si una clase base no proporciona un constructor sin parámetros, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.</span><span class="sxs-lookup"><span data-stu-id="8ac67-137">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="8ac67-138">Un constructor puede invocar otro constructor en el mismo objeto mediante la palabra clave [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-138">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="8ac67-139">Igual que `base`, `this` puede usarse con o sin parámetros. Además, los parámetros del constructor están disponibles como parámetros en `this` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="8ac67-139">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="8ac67-140">Por ejemplo, el segundo constructor del ejemplo anterior se puede reescribir con `this`:</span><span class="sxs-lookup"><span data-stu-id="8ac67-140">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[EmployeeCallingConstructorInSameClass#8](snippets/using-constructors/Program.cs#8)]
  
 <span data-ttu-id="8ac67-141">El uso de la palabra clave `this` en el ejemplo anterior llama a este constructor:</span><span class="sxs-lookup"><span data-stu-id="8ac67-141">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[ConstructorBeingCalledByThisKeyword#9](snippets/using-constructors/Program.cs#9)]
  
 <span data-ttu-id="8ac67-142">Los constructores se pueden marcar como [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-142">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="8ac67-143">Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase.</span><span class="sxs-lookup"><span data-stu-id="8ac67-143">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="8ac67-144">Para obtener más información, consulte [Modificadores de acceso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-144">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="8ac67-145">Un constructor puede declararse estático mediante la palabra clave [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="8ac67-145">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="8ac67-146">Los constructores estáticos se llaman automáticamente, inmediatamente antes de acceder a los campos estáticos y, por lo general, se usan para inicializar miembros de clase estática.</span><span class="sxs-lookup"><span data-stu-id="8ac67-146">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="8ac67-147">Para obtener más información, vea [Static Constructors](./static-constructors.md) (Constructores estáticos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="8ac67-147">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ac67-148">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8ac67-148">C# Language Specification</span></span>  

<span data-ttu-id="8ac67-149">Para obtener más información, vea las secciones [Constructores de instancia](~/_csharplang/spec/classes.md#instance-constructors) y [Constructores estáticos](~/_csharplang/spec/classes.md#static-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="8ac67-149">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="8ac67-150">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="8ac67-150">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ac67-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="8ac67-151">See also</span></span>

- [<span data-ttu-id="8ac67-152">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="8ac67-152">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="8ac67-153">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="8ac67-153">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="8ac67-154">Constructores</span><span class="sxs-lookup"><span data-stu-id="8ac67-154">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="8ac67-155">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="8ac67-155">Finalizers</span></span>](./destructors.md)
