---
title: 'Utilizar constructores: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
ms.openlocfilehash: cb6a0befb9e2e628f066061282532513019c1419
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "73418733"
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="27bbb-102">Utilizar constructores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="27bbb-102">Using Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="27bbb-103">Cuando se crea una [class](../../language-reference/keywords/class.md) o un [struct](../../language-reference/keywords/struct.md), se llama a su constructor.</span><span class="sxs-lookup"><span data-stu-id="27bbb-103">When a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="27bbb-104">Los constructores tienen el mismo nombre que la class o el struct y suelen inicializar los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="27bbb-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="27bbb-105">En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple.</span><span class="sxs-lookup"><span data-stu-id="27bbb-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="27bbb-106">Luego, se crea una instancia de la clase con el operador [new](../../language-reference/operators/new-operator.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-106">This class is then instantiated with the [new](../../language-reference/operators/new-operator.md) operator.</span></span> <span data-ttu-id="27bbb-107">El constructor `Taxi` se invoca con el operador `new` inmediatamente después de asignar memoria para el nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="27bbb-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#53)]  
  
 <span data-ttu-id="27bbb-108">Un constructor que no toma ningún parámetro se denomina *constructor sin parámetros*.</span><span class="sxs-lookup"><span data-stu-id="27bbb-108">A constructor that takes no parameters is called a *parameterless constructor*.</span></span> <span data-ttu-id="27bbb-109">Los constructores sin parámetros se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se especifica ningún argumento en `new`.</span><span class="sxs-lookup"><span data-stu-id="27bbb-109">Parameterless constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="27bbb-110">Para obtener más información, vea [Instance Constructors](./instance-constructors.md) (Constructores de instancias [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="27bbb-110">For more information, see [Instance Constructors](./instance-constructors.md).</span></span>  
  
 <span data-ttu-id="27bbb-111">A menos que la clase sea [static](../../language-reference/keywords/static.md), las clases sin constructores tienen un constructor público sin parámetros por el compilador de C# con el fin de habilitar la creación de instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="27bbb-111">Unless the class is [static](../../language-reference/keywords/static.md), classes without constructors are given a public parameterless constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="27bbb-112">Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-112">For more information, see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="27bbb-113">Puede impedir que se cree una instancia de una clase convirtiendo el constructor en privado, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="27bbb-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="27bbb-114">Para obtener más información, vea [Private Constructors](./private-constructors.md) (Constructores privados [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="27bbb-114">For more information, see [Private Constructors](./private-constructors.md).</span></span>  
  
 <span data-ttu-id="27bbb-115">Los constructores de tipos [struct](../../language-reference/keywords/struct.md) son similares a los constructores de clases, pero `structs` no puede contener un constructor sin parámetros explícito porque el compilador proporciona uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="27bbb-115">Constructors for [struct](../../language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit parameterless constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="27bbb-116">Este constructor inicializa cada campo del `struct` en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="27bbb-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="27bbb-117">Para obtener más información, vea [Default Values Table](../../language-reference/keywords/default-values-table.md) (Tabla de valores predeterminados [Referencia de C#]).</span><span class="sxs-lookup"><span data-stu-id="27bbb-117">For more information, see [Default Values Table](../../language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="27bbb-118">Pero este constructor sin parámetros solo se invoca si las instancias de `struct` se crean con `new`.</span><span class="sxs-lookup"><span data-stu-id="27bbb-118">However, this parameterless constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="27bbb-119">Por ejemplo, este código usa el constructor sin parámetros para <xref:System.Int32>, por lo que se tiene la certeza de que el entero se inicializa:</span><span class="sxs-lookup"><span data-stu-id="27bbb-119">For example, this code uses the parameterless constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```csharp  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="27bbb-120">Si bien, el siguiente código genera un error del compilador porque no usa `new` y porque intenta usar un objeto que no se ha inicializado:</span><span class="sxs-lookup"><span data-stu-id="27bbb-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```csharp  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="27bbb-121">También puede inicializar o asignar los objetos basados en `structs` (incluidos todos los tipos numéricos integrados) y luego usarlos como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27bbb-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```csharp  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="27bbb-122">Por lo que no es necesario llamar al constructor sin parámetros para un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="27bbb-122">So calling the parameterless constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="27bbb-123">Tanto las clases como los `structs` pueden definir constructores que toman parámetros.</span><span class="sxs-lookup"><span data-stu-id="27bbb-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="27bbb-124">Los constructores que toman parámetros deben llamarse mediante una instrucción `new` o [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-124">Constructors that take parameters must be called through a `new` statement or a [base](../../language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="27bbb-125">Las clases y `structs` también pueden definir varios constructores y no es necesario definir un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="27bbb-125">Classes and `structs` can also define multiple constructors, and neither is required to define a parameterless constructor.</span></span> <span data-ttu-id="27bbb-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27bbb-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#54)]  
  
 <span data-ttu-id="27bbb-127">Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="27bbb-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#55)]  
  
 <span data-ttu-id="27bbb-128">Un constructor puede usar la palabra clave `base` para llamar al constructor de una clase base.</span><span class="sxs-lookup"><span data-stu-id="27bbb-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="27bbb-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27bbb-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#56)]  
  
 <span data-ttu-id="27bbb-130">En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor.</span><span class="sxs-lookup"><span data-stu-id="27bbb-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="27bbb-131">La palabra clave `base` puede usarse con o sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="27bbb-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="27bbb-132">Los parámetros del constructor se pueden usar como parámetros en `base` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="27bbb-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="27bbb-133">Para obtener más información, vea [base](../../language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-133">For more information, see [base](../../language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="27bbb-134">En una clase derivada, si un constructor de clase base no se llama explícitamente con la palabra clave `base`, se llama implícitamente al constructor sin parámetros, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="27bbb-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the parameterless constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="27bbb-135">Esto significa que las siguientes declaraciones del constructor son en efecto iguales:</span><span class="sxs-lookup"><span data-stu-id="27bbb-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#58)]  
  
 [!code-csharp[csProgGuideObjects#57](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#57)]  
  
 <span data-ttu-id="27bbb-136">Si una clase base no proporciona un constructor sin parámetros, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.</span><span class="sxs-lookup"><span data-stu-id="27bbb-136">If a base class does not offer a parameterless constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="27bbb-137">Un constructor puede invocar otro constructor en el mismo objeto mediante la palabra clave [this](../../language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-137">A constructor can invoke another constructor in the same object by using the [this](../../language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="27bbb-138">Igual que `base`, `this` puede usarse con o sin parámetros. Además, los parámetros del constructor están disponibles como parámetros en `this` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="27bbb-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="27bbb-139">Por ejemplo, el segundo constructor del ejemplo anterior se puede reescribir con `this`:</span><span class="sxs-lookup"><span data-stu-id="27bbb-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#59)]  
  
 <span data-ttu-id="27bbb-140">El uso de la palabra clave `this` en el ejemplo anterior llama a este constructor:</span><span class="sxs-lookup"><span data-stu-id="27bbb-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#60)]  
  
 <span data-ttu-id="27bbb-141">Los constructores se pueden marcar como [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) o [private protected](../../language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-141">Constructors can be marked as [public](../../language-reference/keywords/public.md), [private](../../language-reference/keywords/private.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md) or [private protected](../../language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="27bbb-142">Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase.</span><span class="sxs-lookup"><span data-stu-id="27bbb-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="27bbb-143">Para obtener más información, consulte [Modificadores de acceso](./access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-143">For more information, see [Access Modifiers](./access-modifiers.md).</span></span>  
  
 <span data-ttu-id="27bbb-144">Un constructor puede declararse estático mediante la palabra clave [static](../../language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="27bbb-144">A constructor can be declared static by using the [static](../../language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="27bbb-145">Los constructores estáticos se llaman automáticamente, inmediatamente antes de acceder a los campos estáticos y, por lo general, se usan para inicializar miembros de clase estática.</span><span class="sxs-lookup"><span data-stu-id="27bbb-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="27bbb-146">Para obtener más información, vea [Static Constructors](./static-constructors.md) (Constructores estáticos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="27bbb-146">For more information, see [Static Constructors](./static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="27bbb-147">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="27bbb-147">C# Language Specification</span></span>  

<span data-ttu-id="27bbb-148">Para obtener más información, vea las secciones [Constructores de instancia](~/_csharplang/spec/classes.md#instance-constructors) y [Constructores estáticos](~/_csharplang/spec/classes.md#static-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="27bbb-148">For more information, see [Instance constructors](~/_csharplang/spec/classes.md#instance-constructors) and [Static constructors](~/_csharplang/spec/classes.md#static-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="27bbb-149">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="27bbb-149">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="27bbb-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="27bbb-150">See also</span></span>

- [<span data-ttu-id="27bbb-151">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="27bbb-151">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="27bbb-152">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="27bbb-152">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="27bbb-153">Constructores</span><span class="sxs-lookup"><span data-stu-id="27bbb-153">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="27bbb-154">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="27bbb-154">Finalizers</span></span>](./destructors.md)
