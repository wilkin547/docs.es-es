---
title: 'Constructores privados: Guía de programación de C#'
description: Un constructor privado es un constructor de instancia especial de C# que se usa para restringir el modo en el que se puede crear un objeto. Se puede usar con métodos de fábrica u otras expresiones de construcción.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: 980a638fbe6250b3d47a3effc7cbad5ec57fbcad
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899410"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="9759d-104">Constructores privados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9759d-104">Private Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="9759d-105">Un constructor privado es un constructor de instancia especial.</span><span class="sxs-lookup"><span data-stu-id="9759d-105">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="9759d-106">Se usa generalmente en clases que contienen solo miembros estáticos.</span><span class="sxs-lookup"><span data-stu-id="9759d-106">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="9759d-107">Si una clase tiene uno o más constructores privados y ningún constructor público, el resto de clases (excepto las anidadas) no podrán crear instancias de esta clase.</span><span class="sxs-lookup"><span data-stu-id="9759d-107">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="9759d-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9759d-108">For example:</span></span>  
  
 [!code-csharp[ClassWithPrivateConstructorExample#1](snippets/private-constructors/Program.cs#1)]
  
 <span data-ttu-id="9759d-109">La declaración de un constructor vacío evita la generación automática de un constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="9759d-109">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="9759d-110">Observe que si no usa un modificador de acceso en el constructor, este será privado de manera predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9759d-110">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="9759d-111">En cambio, normalmente se usa el modificador [private](../../language-reference/keywords/private.md) de manera explícita para aclarar que no es posible crear una instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="9759d-111">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="9759d-112">Los constructores privados se usan para evitar la creación de instancias de una clase cuando no hay campos o métodos de instancia, por ejemplo, la clase <xref:System.Math>, o cuando se llama a un método para obtener una instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="9759d-112">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="9759d-113">Si todos los métodos de la clase son estáticos, considere convertir la clase completa en estática.</span><span class="sxs-lookup"><span data-stu-id="9759d-113">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="9759d-114">Para obtener más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="9759d-114">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9759d-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9759d-115">Example</span></span>  

 <span data-ttu-id="9759d-116">El siguiente es un ejemplo de clase que usa un constructor privado.</span><span class="sxs-lookup"><span data-stu-id="9759d-116">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[CounterClassWithPrivateConstructor#2](snippets/private-constructors/Program.cs#2)]
  
 <span data-ttu-id="9759d-117">Observe que si quita el comentario de la siguiente instrucción del ejemplo, se producirá un error porque el constructor es inaccesible debido a su nivel de protección:</span><span class="sxs-lookup"><span data-stu-id="9759d-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[ErrorInstantiatingUsingPrivateConstructor#13](snippets/private-constructors/Program.cs#3)]
  
## <a name="c-language-specification"></a><span data-ttu-id="9759d-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9759d-118">C# Language Specification</span></span>  

<span data-ttu-id="9759d-119">Para obtener más información, vea la sección [Constructores privados](~/_csharplang/spec/classes.md#private-constructors) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="9759d-119">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="9759d-120">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="9759d-120">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9759d-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9759d-121">See also</span></span>

- [<span data-ttu-id="9759d-122">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9759d-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9759d-123">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="9759d-123">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="9759d-124">Constructores</span><span class="sxs-lookup"><span data-stu-id="9759d-124">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="9759d-125">Finalizadores</span><span class="sxs-lookup"><span data-stu-id="9759d-125">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="9759d-126">private</span><span class="sxs-lookup"><span data-stu-id="9759d-126">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="9759d-127">public</span><span class="sxs-lookup"><span data-stu-id="9759d-127">public</span></span>](../../language-reference/keywords/public.md)
