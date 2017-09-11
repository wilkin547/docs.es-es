---
title: "Clases y miembros de clase abstractos y sellados (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0788ea0778b3f8b846231fc2408938b2236314c9
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a><span data-ttu-id="b559f-102">Clases y miembros de clase abstractos y sellados (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="b559f-102">Abstract and Sealed Classes and Class Members (C# Programming Guide)</span></span>
<span data-ttu-id="b559f-103">La palabra clave [abstract](../../../csharp/language-reference/keywords/abstract.md) permite crear clases y miembros [class](../../../csharp/language-reference/keywords/class.md) que están incompletos y se deben implementar en una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="b559f-103">The [abstract](../../../csharp/language-reference/keywords/abstract.md) keyword enables you to create classes and [class](../../../csharp/language-reference/keywords/class.md) members that are incomplete and must be implemented in a derived class.</span></span>  
  
 <span data-ttu-id="b559f-104">La palabra clave [sealed](../../../csharp/language-reference/keywords/sealed.md) permite impedir la herencia de una clase o de ciertos miembros de clase marcados previamente como [virtual](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="b559f-104">The [sealed](../../../csharp/language-reference/keywords/sealed.md) keyword enables you to prevent the inheritance of a class or certain class members that were previously marked [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
## <a name="abstract-classes-and-class-members"></a><span data-ttu-id="b559f-105">Clases y miembros de clase abstractos</span><span class="sxs-lookup"><span data-stu-id="b559f-105">Abstract Classes and Class Members</span></span>  
 <span data-ttu-id="b559f-106">Las clases se pueden declarar como abstractas si se incluye la palabra clave `abstract` antes de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="b559f-106">Classes can be declared as abstract by putting the keyword `abstract` before the class definition.</span></span> <span data-ttu-id="b559f-107">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b559f-107">For example:</span></span>  
  
 <span data-ttu-id="b559f-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b559f-108">[!code-cs[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]</span></span>  
  
 <span data-ttu-id="b559f-109">No se pueden crear instancias de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="b559f-109">An abstract class cannot be instantiated.</span></span> <span data-ttu-id="b559f-110">El propósito de una clase abstracta es proporcionar una definición común de una clase base que múltiples clases derivadas pueden compartir.</span><span class="sxs-lookup"><span data-stu-id="b559f-110">The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share.</span></span> <span data-ttu-id="b559f-111">Por ejemplo, una biblioteca de clases puede definir una clase abstracta que se utiliza como parámetro para muchas de sus funciones y solicitar a los programadores que utilizan esa biblioteca que proporcionen su propia implementación de la clase mediante la creación de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="b559f-111">For example, a class library may define an abstract class that is used as a parameter to many of its functions, and require programmers using that library to provide their own implementation of the class by creating a derived class.</span></span>  
  
 <span data-ttu-id="b559f-112">Las clases abstractas también pueden definir métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="b559f-112">Abstract classes may also define abstract methods.</span></span> <span data-ttu-id="b559f-113">Esto se consigue agregando la palabra clave `abstract` antes del tipo de valor que devuelve el método.</span><span class="sxs-lookup"><span data-stu-id="b559f-113">This is accomplished by adding the keyword `abstract` before the return type of the method.</span></span> <span data-ttu-id="b559f-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b559f-114">For example:</span></span>  
  
 <span data-ttu-id="b559f-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b559f-115">[!code-cs[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]</span></span>  
  
 <span data-ttu-id="b559f-116">Los métodos abstractos no tienen ninguna implementación, de modo que la definición de método va seguida por un punto y coma en lugar de un bloque de método normal.</span><span class="sxs-lookup"><span data-stu-id="b559f-116">Abstract methods have no implementation, so the method definition is followed by a semicolon instead of a normal method block.</span></span> <span data-ttu-id="b559f-117">Las clases derivadas de la clase abstracta deben implementar todos los métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="b559f-117">Derived classes of the abstract class must implement all abstract methods.</span></span> <span data-ttu-id="b559f-118">Cuando una clase abstracta hereda un método virtual de una clase base, la clase abstracta puede reemplazar el método virtual con un método abstracto.</span><span class="sxs-lookup"><span data-stu-id="b559f-118">When an abstract class inherits a virtual method from a base class, the abstract class can override the virtual method with an abstract method.</span></span> <span data-ttu-id="b559f-119">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b559f-119">For example:</span></span>  
  
 <span data-ttu-id="b559f-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="b559f-120">[!code-cs[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]</span></span>  
  
 <span data-ttu-id="b559f-121">Si un método `virtual` se declara como `abstract`, sigue siendo virtual para cualquier clase que herede de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="b559f-121">If a `virtual` method is declared `abstract`, it is still virtual to any class inheriting from the abstract class.</span></span> <span data-ttu-id="b559f-122">Una clase que hereda un método abstracto no puede tener acceso a la implementación original del método: en el ejemplo anterior, `DoWork` en la clase F no puede llamar a `DoWork` en la clase D. De esta manera, una clase abstracta puede exigir a las clases derivadas que proporcionen nuevas implementaciones de método para los métodos virtuales.</span><span class="sxs-lookup"><span data-stu-id="b559f-122">A class inheriting an abstract method cannot access the original implementation of the method—in the previous example, `DoWork` on class F cannot call `DoWork` on class D. In this way, an abstract class can force derived classes to provide new method implementations for virtual methods.</span></span>  
  
## <a name="sealed-classes-and-class-members"></a><span data-ttu-id="b559f-123">Clases y miembros de clase sellados</span><span class="sxs-lookup"><span data-stu-id="b559f-123">Sealed Classes and Class Members</span></span>  
 <span data-ttu-id="b559f-124">Las clases se pueden declarar como [selladas](../../../csharp/language-reference/keywords/sealed.md) si se incluye la palabra clave `sealed` antes de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="b559f-124">Classes can be declared as [sealed](../../../csharp/language-reference/keywords/sealed.md) by putting the keyword `sealed` before the class definition.</span></span> <span data-ttu-id="b559f-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b559f-125">For example:</span></span>  
  
 <span data-ttu-id="b559f-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="b559f-126">[!code-cs[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]</span></span>  
  
 <span data-ttu-id="b559f-127">Una clase sellada no se puede utilizar como clase base.</span><span class="sxs-lookup"><span data-stu-id="b559f-127">A sealed class cannot be used as a base class.</span></span> <span data-ttu-id="b559f-128">Por esta razón, tampoco puede ser una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="b559f-128">For this reason, it cannot also be an abstract class.</span></span> <span data-ttu-id="b559f-129">Las clases selladas evitan la derivación.</span><span class="sxs-lookup"><span data-stu-id="b559f-129">Sealed classes prevent derivation.</span></span> <span data-ttu-id="b559f-130">Puesto que nunca se pueden utilizar como clase base, algunas optimizaciones en tiempo de ejecución pueden hacer que sea un poco más rápido llamar a miembros de clase sellada.</span><span class="sxs-lookup"><span data-stu-id="b559f-130">Because they can never be used as a base class, some run-time optimizations can make calling sealed class members slightly faster.</span></span>  
  
 <span data-ttu-id="b559f-131">Un método, indizador, propiedad o evento de una clase derivada que reemplaza a un miembro virtual de la clase base puede declarar ese miembro como sellado.</span><span class="sxs-lookup"><span data-stu-id="b559f-131">A method, indexer, property, or event, on a derived class that is overriding a virtual member of the base class can declare that member as sealed.</span></span> <span data-ttu-id="b559f-132">Esto niega el aspecto virtual del miembro para cualquier clase derivada adicional.</span><span class="sxs-lookup"><span data-stu-id="b559f-132">This negates the virtual aspect of the member for any further derived class.</span></span> <span data-ttu-id="b559f-133">Esto se logra colocando la palabra clave `sealed` antes de la palabra clave [override](../../../csharp/language-reference/keywords/override.md) en la declaración del miembro de clase.</span><span class="sxs-lookup"><span data-stu-id="b559f-133">This is accomplished by putting the `sealed` keyword before the [override](../../../csharp/language-reference/keywords/override.md) keyword in the class member declaration.</span></span> <span data-ttu-id="b559f-134">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b559f-134">For example:</span></span>  
  
 <span data-ttu-id="b559f-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="b559f-135">[!code-cs[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b559f-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="b559f-136">See Also</span></span>  
 <span data-ttu-id="b559f-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b559f-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b559f-138">[Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span><span class="sxs-lookup"><span data-stu-id="b559f-138">[Classes and Structs](../../../csharp/programming-guide/classes-and-structs/index.md) </span></span>  
 <span data-ttu-id="b559f-139">[Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span><span class="sxs-lookup"><span data-stu-id="b559f-139">[Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md) </span></span>  
 <span data-ttu-id="b559f-140">[Métodos](../../../csharp/programming-guide/classes-and-structs/methods.md) </span><span class="sxs-lookup"><span data-stu-id="b559f-140">[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md) </span></span>  
 <span data-ttu-id="b559f-141">[Campos](../../../csharp/programming-guide/classes-and-structs/fields.md) </span><span class="sxs-lookup"><span data-stu-id="b559f-141">[Fields](../../../csharp/programming-guide/classes-and-structs/fields.md) </span></span>  
 [<span data-ttu-id="b559f-142">Cómo: Definir propiedades abstractas</span><span class="sxs-lookup"><span data-stu-id="b559f-142">How to: Define Abstract Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)

