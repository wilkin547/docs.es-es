---
title: "Utilizar constructores (Guía de programación de C#)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: constructors [C#], about constructors
ms.assetid: 464253b2-fd5d-469a-836d-df0fdf2a43f7
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eb9fcd1e4090da300de17c7fd808669ba51767c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="using-constructors-c-programming-guide"></a><span data-ttu-id="c8f8e-102">Utilizar constructores (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c8f8e-102">Using Constructors (C# Programming Guide)</span></span>
<span data-ttu-id="c8f8e-103">Cuando se crea una [class](../../../csharp/language-reference/keywords/class.md) o un [struct](../../../csharp/language-reference/keywords/struct.md), se llama a su constructor.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-103">When a [class](../../../csharp/language-reference/keywords/class.md) or [struct](../../../csharp/language-reference/keywords/struct.md) is created, its constructor is called.</span></span> <span data-ttu-id="c8f8e-104">Los constructores tienen el mismo nombre que la class o el struct y suelen inicializar los miembros de datos del nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-104">Constructors have the same name as the class or struct, and they usually initialize the data members of the new object.</span></span>  
  
 <span data-ttu-id="c8f8e-105">En el ejemplo siguiente, una clase denominada `Taxi` se define mediante un constructor simple.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-105">In the following example, a class named `Taxi` is defined by using a simple constructor.</span></span> <span data-ttu-id="c8f8e-106">Luego, se crea una instancia de la clase con el operador [new](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-106">This class is then instantiated with the [new](../../../csharp/language-reference/keywords/new.md) operator.</span></span> <span data-ttu-id="c8f8e-107">El constructor `Taxi` se invoca con el operador `new` inmediatamente después de asignar memoria para el nuevo objeto.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-107">The `Taxi` constructor is invoked by the `new` operator immediately after memory is allocated for the new object.</span></span>  
  
 [!code-csharp[csProgGuideObjects#53](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_1.cs)]  
  
 <span data-ttu-id="c8f8e-108">Un constructor que no toma ningún parámetro se denomina *constructor predeterminado*.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-108">A constructor that takes no parameters is called a *default constructor*.</span></span> <span data-ttu-id="c8f8e-109">Los constructores predeterminados se invocan cada vez que se crea una instancia de un objeto mediante el operador `new` y no se especifica ningún argumento en `new`.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-109">Default constructors are invoked whenever an object is instantiated by using the `new` operator and no arguments are provided to `new`.</span></span> <span data-ttu-id="c8f8e-110">Para obtener más información, vea [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md) (Constructores de instancias [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-110">For more information, see [Instance Constructors](../../../csharp/programming-guide/classes-and-structs/instance-constructors.md).</span></span>  
  
 <span data-ttu-id="c8f8e-111">A menos que la clase sea [static](../../../csharp/language-reference/keywords/static.md), las clases sin constructores tienen un constructor público predeterminado por el compilador de C# con el fin de habilitar la creación de instancias de clase.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-111">Unless the class is [static](../../../csharp/language-reference/keywords/static.md), classes without constructors are given a public default constructor by the C# compiler in order to enable class instantiation.</span></span> <span data-ttu-id="c8f8e-112">Para obtener más información, consulte [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-112">For more information, see [Static Classes and Static Class Members](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).</span></span>  
  
 <span data-ttu-id="c8f8e-113">Puede impedir que se cree una instancia de una clase convirtiendo el constructor en privado, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-113">You can prevent a class from being instantiated by making the constructor private, as follows:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_2.cs)]  
  
 <span data-ttu-id="c8f8e-114">Para obtener más información, vea [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md) (Constructores privados [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-114">For more information, see [Private Constructors](../../../csharp/programming-guide/classes-and-structs/private-constructors.md).</span></span>  
  
 <span data-ttu-id="c8f8e-115">Los constructores de tipos [struct](../../../csharp/language-reference/keywords/struct.md) son similares a los constructores de clases, pero `structs` no puede contener un constructor predeterminado explícito porque el compilador proporciona uno automáticamente.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-115">Constructors for [struct](../../../csharp/language-reference/keywords/struct.md) types resemble class constructors, but `structs` cannot contain an explicit default constructor because one is provided automatically by the compiler.</span></span> <span data-ttu-id="c8f8e-116">Este constructor inicializa cada campo del `struct` en los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-116">This constructor initializes each field in the `struct` to the default values.</span></span> <span data-ttu-id="c8f8e-117">Para obtener más información, vea [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md) (Tabla de valores predeterminados [Referencia de C#]).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-117">For more information, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span> <span data-ttu-id="c8f8e-118">Pero este constructor predeterminado solo se invoca si las instancias de `struct` se crean con `new`.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-118">However, this default constructor is only invoked if the `struct` is instantiated with `new`.</span></span> <span data-ttu-id="c8f8e-119">Por ejemplo, este código usa el constructor predeterminado para <xref:System.Int32>, por lo que se tiene la certeza de que el entero se inicializa:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-119">For example, this code uses the default constructor for <xref:System.Int32>, so that you are assured that the integer is initialized:</span></span>  
  
```  
int i = new int();  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="c8f8e-120">Si bien, el siguiente código genera un error del compilador porque no usa `new` y porque intenta usar un objeto que no se ha inicializado:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-120">The following code, however, causes a compiler error because it does not use `new`, and because it tries to use an object that has not been initialized:</span></span>  
  
```  
int i;  
Console.WriteLine(i);  
```  
  
 <span data-ttu-id="c8f8e-121">También puede inicializar o asignar los objetos basados en `structs` (incluidos todos los tipos numéricos integrados) y luego usarlos como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-121">Alternatively, objects based on `structs` (including all built-in numeric types) can be initialized or assigned and then used as in the following example:</span></span>  
  
```  
int a = 44;  // Initialize the value type...  
int b;  
b = 33;      // Or assign it before using it.  
Console.WriteLine("{0}, {1}", a, b);  
```  
  
 <span data-ttu-id="c8f8e-122">Por lo que no es necesario llamar al constructor predeterminado para un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-122">So calling the default constructor for a value type is not required.</span></span>  
  
 <span data-ttu-id="c8f8e-123">Tanto las clases como los `structs` pueden definir constructores que toman parámetros.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-123">Both classes and `structs` can define constructors that take parameters.</span></span> <span data-ttu-id="c8f8e-124">Los constructores que toman parámetros deben llamarse mediante una instrucción `new` o [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-124">Constructors that take parameters must be called through a `new` statement or a [base](../../../csharp/language-reference/keywords/base.md) statement.</span></span> <span data-ttu-id="c8f8e-125">Las clases y `structs` también pueden definir varios constructores y no es necesario definir un constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-125">Classes and `structs` can also define multiple constructors, and neither is required to define a default constructor.</span></span> <span data-ttu-id="c8f8e-126">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-126">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#54](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_3.cs)]  
  
 <span data-ttu-id="c8f8e-127">Esta clase se puede crear mediante cualquiera de las siguientes instrucciones:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-127">This class can be created by using either of the following statements:</span></span>  
  
 [!code-csharp[csProgGuideObjects#55](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_4.cs)]  
  
 <span data-ttu-id="c8f8e-128">Un constructor puede usar la palabra clave `base` para llamar al constructor de una clase base.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-128">A constructor can use the `base` keyword to call the constructor of a base class.</span></span> <span data-ttu-id="c8f8e-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-129">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#56](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_5.cs)]  
  
 <span data-ttu-id="c8f8e-130">En este ejemplo, se llama al constructor de la clase base antes de ejecutar el bloque del constructor.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-130">In this example, the constructor for the base class is called before the block for the constructor is executed.</span></span> <span data-ttu-id="c8f8e-131">La palabra clave `base` puede usarse con o sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-131">The `base` keyword can be used with or without parameters.</span></span> <span data-ttu-id="c8f8e-132">Los parámetros del constructor se pueden usar como parámetros en `base` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-132">Any parameters to the constructor can be used as parameters to `base`, or as part of an expression.</span></span> <span data-ttu-id="c8f8e-133">Para obtener más información, vea [base](../../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-133">For more information, see [base](../../../csharp/language-reference/keywords/base.md).</span></span>  
  
 <span data-ttu-id="c8f8e-134">En una clase derivada, si un constructor de clase base no se llama explícitamente con la palabra clave `base`, se llama implícitamente al constructor predeterminado, si hay alguno.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-134">In a derived class, if a base-class constructor is not called explicitly by using the `base` keyword, the default constructor, if there is one, is called implicitly.</span></span> <span data-ttu-id="c8f8e-135">Esto significa que las siguientes declaraciones del constructor son en efecto iguales:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-135">This means that the following constructor declarations are effectively the same:</span></span>  
  
 [!code-csharp[csProgGuideObjects#58](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_6.cs)]  
  
 [!code-csharp[csProgGuideObjects#57](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_7.cs)]  
  
 <span data-ttu-id="c8f8e-136">Si una clase base no proporciona un constructor predeterminado, la clase derivada debe realizar una llamada explícita a un constructor base mediante `base`.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-136">If a base class does not offer a default constructor, the derived class must make an explicit call to a base constructor by using `base`.</span></span>  
  
 <span data-ttu-id="c8f8e-137">Un constructor puede invocar otro constructor en el mismo objeto mediante la palabra clave [this](../../../csharp/language-reference/keywords/this.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-137">A constructor can invoke another constructor in the same object by using the [this](../../../csharp/language-reference/keywords/this.md) keyword.</span></span> <span data-ttu-id="c8f8e-138">Igual que `base`, `this` puede usarse con o sin parámetros. Además, los parámetros del constructor están disponibles como parámetros en `this` o como parte de una expresión.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-138">Like `base`, `this` can be used with or without parameters, and any parameters in the constructor are available as parameters to `this`, or as part of an expression.</span></span> <span data-ttu-id="c8f8e-139">Por ejemplo, el segundo constructor del ejemplo anterior se puede reescribir con `this`:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-139">For example, the second constructor in the previous example can be rewritten using `this`:</span></span>  
  
 [!code-csharp[csProgGuideObjects#59](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_8.cs)]  
  
 <span data-ttu-id="c8f8e-140">El uso de la palabra clave `this` en el ejemplo anterior llama a este constructor:</span><span class="sxs-lookup"><span data-stu-id="c8f8e-140">The use of the `this` keyword in the previous example causes this constructor to be called:</span></span>  
  
 [!code-csharp[csProgGuideObjects#60](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/using-constructors_9.cs)]  
  
 <span data-ttu-id="c8f8e-141">Constructores se pueden marcar como [público](../../../csharp/language-reference/keywords/public.md), [privada](../../../csharp/language-reference/keywords/private.md), [protegido](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protegidointerno](../../../csharp/language-reference/keywords/protected-internal.md)o [privado protegido](../../../csharp/language-reference/keywords/private-protected.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-141">Constructors can be marked as [public](../../../csharp/language-reference/keywords/public.md), [private](../../../csharp/language-reference/keywords/private.md), [protected](../../../csharp/language-reference/keywords/protected.md), [internal](../../../csharp/language-reference/keywords/internal.md), [protected internal](../../../csharp/language-reference/keywords/protected-internal.md) or [private protected](../../../csharp/language-reference/keywords/private-protected.md).</span></span> <span data-ttu-id="c8f8e-142">Estos modificadores de acceso definen cómo los usuarios de la clase pueden construir la clase.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-142">These access modifiers define how users of the class can construct the class.</span></span> <span data-ttu-id="c8f8e-143">Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-143">For more information, see [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="c8f8e-144">Un constructor puede declararse estático mediante la palabra clave [static](../../../csharp/language-reference/keywords/static.md).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-144">A constructor can be declared static by using the [static](../../../csharp/language-reference/keywords/static.md) keyword.</span></span> <span data-ttu-id="c8f8e-145">Los constructores estáticos se llaman automáticamente, inmediatamente antes de acceder a los campos estáticos y, por lo general, se usan para inicializar miembros de clase estática.</span><span class="sxs-lookup"><span data-stu-id="c8f8e-145">Static constructors are called automatically, immediately before any static fields are accessed, and are generally used to initialize static class members.</span></span> <span data-ttu-id="c8f8e-146">Para obtener más información, vea [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md) (Constructores estáticos [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="c8f8e-146">For more information, see [Static Constructors](../../../csharp/programming-guide/classes-and-structs/static-constructors.md).</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c8f8e-147">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="c8f8e-147">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c8f8e-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f8e-148">See Also</span></span>  
 [<span data-ttu-id="c8f8e-149">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c8f8e-149">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="c8f8e-150">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="c8f8e-150">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [<span data-ttu-id="c8f8e-151">Constructores</span><span class="sxs-lookup"><span data-stu-id="c8f8e-151">Constructors</span></span>](../../../csharp/programming-guide/classes-and-structs/constructors.md)  
 [<span data-ttu-id="c8f8e-152">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="c8f8e-152">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
