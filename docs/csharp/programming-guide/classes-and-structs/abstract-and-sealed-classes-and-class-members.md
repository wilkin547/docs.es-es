---
title: 'Clases y miembros de clase abstractos y sellados: Guía de programación de C#'
description: La palabra clave abstract de C# crea clases y miembros de clase incompletos. La palabra clave sealed evita la herencia de clases o miembros de clase previamente virtuales.
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: ccbc6734d4e9bafe059dd45bfdf82af7c84438a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204039"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="c9618-104">Clases y miembros de clase abstractos y sellados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c9618-104">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>

<span data-ttu-id="c9618-105">La palabra clave [abstract](../../language-reference/keywords/abstract.md) permite crear clases y miembros [class](../../language-reference/keywords/class.md) que están incompletos y se deben implementar en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c9618-105">The [abstract](../../language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="c9618-106">La palabra clave [sealed](../../language-reference/keywords/sealed.md) permite impedir la herencia de una clase o de ciertos miembros de clase marcados previamente como [virtual](../../language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="c9618-106">The [sealed](../../language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="c9618-107">Clases y miembros de clase abstractos</span><span class="sxs-lookup"><span data-stu-id="c9618-107">Abstract Classes and Class Members</span></span>  

 <span data-ttu-id="c9618-108">Las clases se pueden declarar como abstractas si se incluye la palabra clave `abstract` antes de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="c9618-108">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="c9618-109">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9618-109">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 <span data-ttu-id="c9618-110">No se pueden crear instancias de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="c9618-110">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="c9618-111">El propósito de una clase abstracta es proporcionar una definición común de una clase base que múltiples clases derivadas pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="c9618-111">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="c9618-112">Por ejemplo, una biblioteca de clases puede definir una clase abstracta que se utiliza como parámetro para muchas de sus funciones y solicitar a los programadores que utilizan esa biblioteca que proporcionen su propia implementación de la clase mediante la creación de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="c9618-112">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="c9618-113">Las clases abstractas también pueden definir métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="c9618-113">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="c9618-114">Esto se consigue agregando la palabra clave `abstract` antes del tipo de valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="c9618-114">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="c9618-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9618-115">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 <span data-ttu-id="c9618-116">Los métodos abstractos no tienen ninguna implementación, de modo que la definición de método va seguida por un punto y coma en lugar de un bloque de método normal.</span><span class="sxs-lookup"><span data-stu-id="c9618-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="c9618-117">Las clases derivadas de la clase abstracta deben implementar todos los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="c9618-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="c9618-118">Cuando una clase abstracta hereda un método virtual de una clase base, la clase abstracta puede reemplazar el método virtual con un método abstracto.</span><span class="sxs-lookup"><span data-stu-id="c9618-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="c9618-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9618-119">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 <span data-ttu-id="c9618-120">Si un método `virtual` se declara como `abstract`, sigue siendo virtual para cualquier clase que herede de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="c9618-120">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="c9618-121">Una clase que hereda un método abstracto no puede tener acceso a la implementación original del método: en el ejemplo anterior, `DoWork` en la clase F no puede llamar a `DoWork` en la clase D. De esta manera, una clase abstracta puede exigir a las clases derivadas que proporcionen nuevas implementaciones de método para los métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="c9618-121">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="c9618-122">Clases y miembros de clase sellados</span><span class="sxs-lookup"><span data-stu-id="c9618-122">Sealed Classes and Class Members</span></span>  

 <span data-ttu-id="c9618-123">Las clases se pueden declarar como [selladas](../../language-reference/keywords/sealed.md) si se incluye la palabra clave `sealed` antes de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="c9618-123">Classes can be declared as [sealed](../../language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="c9618-124">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9618-124">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 <span data-ttu-id="c9618-125">Una clase sellada no se puede utilizar como clase base.</span><span class="sxs-lookup"><span data-stu-id="c9618-125">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="c9618-126">Por esta razón, tampoco puede ser una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="c9618-126">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="c9618-127">Las clases selladas evitan la derivación.</span><span class="sxs-lookup"><span data-stu-id="c9618-127">Sealed classes prevent derivation.</span></span> <span data-ttu-id="c9618-128">Puesto que nunca se pueden utilizar como clase base, algunas optimizaciones en tiempo de ejecución pueden hacer que sea un poco más rápido llamar a miembros de clase sellada.</span><span class="sxs-lookup"><span data-stu-id="c9618-128">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="c9618-129">Un método, indizador, propiedad o evento de una clase derivada que reemplaza a un miembro virtual de la clase base puede declarar ese miembro como sellado.</span><span class="sxs-lookup"><span data-stu-id="c9618-129">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="c9618-130">Esto niega el aspecto virtual del miembro para cualquier clase derivada adicional.</span><span class="sxs-lookup"><span data-stu-id="c9618-130">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="c9618-131">Esto se logra colocando la palabra clave `sealed` antes de la palabra clave [override](../../language-reference/keywords/override.md) en la declaración del miembro de clase.</span><span class="sxs-lookup"><span data-stu-id="c9618-131">This is accomplished by putting the `sealed` keyword before the [override](../../language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="c9618-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c9618-132">For example:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a><span data-ttu-id="c9618-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9618-133">See also</span></span>

- [<span data-ttu-id="c9618-134">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c9618-134">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c9618-135">Clases y structs</span><span class="sxs-lookup"><span data-stu-id="c9618-135">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="c9618-136">Herencia</span><span class="sxs-lookup"><span data-stu-id="c9618-136">Inheritance</span></span>](./inheritance.md)
- [<span data-ttu-id="c9618-137">Métodos</span><span class="sxs-lookup"><span data-stu-id="c9618-137">Methods</span></span>](./methods.md)
- [<span data-ttu-id="c9618-138">Campos</span><span class="sxs-lookup"><span data-stu-id="c9618-138">Fields</span></span>](./fields.md)
- [<span data-ttu-id="c9618-139">Procedimiento para definir propiedades abstractas</span><span class="sxs-lookup"><span data-stu-id="c9618-139">How to define abstract properties</span></span>](./how-to-define-abstract-properties.md)
