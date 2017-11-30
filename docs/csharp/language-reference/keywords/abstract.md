---
title: abstract (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords: abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
caps.latest.revision: "24"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 785c23294abdbfa0684560a38fbd0279200a7d02
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="abstract-c-reference"></a><span data-ttu-id="cb208-102">abstract (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="cb208-102">abstract (C# Reference)</span></span>
<span data-ttu-id="cb208-103">El modificador `abstract` indica que lo que se modifica carece de implementación o tiene una implementación incompleta.</span><span class="sxs-lookup"><span data-stu-id="cb208-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="cb208-104">El modificador abstract puede usarse con clases, métodos, propiedades, indexadores y eventos.</span><span class="sxs-lookup"><span data-stu-id="cb208-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="cb208-105">Use el modificador `abstract` en una declaración de clase para indicar que una clase solo está diseñada como clase base de otras clases.</span><span class="sxs-lookup"><span data-stu-id="cb208-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes.</span></span> <span data-ttu-id="cb208-106">Los miembros marcados como abstractos o incluidos en una clase abstracta, deben implementarse con clases que deriven de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="cb208-106">Members marked as abstract, or included in an abstract class, must be implemented by classes that derive from the abstract class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cb208-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb208-107">Example</span></span>  
 <span data-ttu-id="cb208-108">En este ejemplo, la clase `Square` debe proporcionar una implementación de `Area` porque se deriva de `ShapesClass`:</span><span class="sxs-lookup"><span data-stu-id="cb208-108">In this example, the class `Square` must provide an implementation of `Area` because it derives from `ShapesClass`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_1.cs)]  
  
 <span data-ttu-id="cb208-109">Las clases abstractas tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="cb208-109">Abstract classes have the following features:</span></span>  
  
-   <span data-ttu-id="cb208-110">No se pueden crear instancias de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="cb208-110">An abstract class cannot be instantiated.</span></span>  
  
-   <span data-ttu-id="cb208-111">Una clase abstracta puede contener descriptores de acceso y métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="cb208-111">An abstract class may contain abstract methods and accessors.</span></span>  
  
-   <span data-ttu-id="cb208-112">No es posible modificar una clase abstracta con el modificador [sealed](../../../csharp/language-reference/keywords/sealed.md) porque los dos modificadores tienen significados opuestos.</span><span class="sxs-lookup"><span data-stu-id="cb208-112">It is not possible to modify an abstract class with the [sealed](../../../csharp/language-reference/keywords/sealed.md) modifier because the two modifers have opposite meanings.</span></span> <span data-ttu-id="cb208-113">El modificador `sealed` impide que una clase se herede y el modificador `abstract` requiere que una clase se herede.</span><span class="sxs-lookup"><span data-stu-id="cb208-113">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
-   <span data-ttu-id="cb208-114">Una clase no abstracta que derive de una clase abstracta debe incluir implementaciones reales de todos los descriptores de acceso y métodos abstractos heredados.</span><span class="sxs-lookup"><span data-stu-id="cb208-114">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="cb208-115">Use el modificador `abstract` en una declaración de método o de propiedad para indicar que el método o la propiedad no contienen implementación.</span><span class="sxs-lookup"><span data-stu-id="cb208-115">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="cb208-116">Los métodos abstractos tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="cb208-116">Abstract methods have the following features:</span></span>  
  
-   <span data-ttu-id="cb208-117">Un método abstracto es, implícitamente, un método virtual.</span><span class="sxs-lookup"><span data-stu-id="cb208-117">An abstract method is implicitly a virtual method.</span></span>  
  
-   <span data-ttu-id="cb208-118">Solo se permiten declaraciones de métodos abstractos en clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="cb208-118">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
-   <span data-ttu-id="cb208-119">Dado que una declaración de método abstracto no proporciona una implementación real, no hay ningún cuerpo de método; la declaración de método finaliza simplemente con un punto y coma y no hay llaves ({ }) después de la firma.</span><span class="sxs-lookup"><span data-stu-id="cb208-119">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="cb208-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb208-120">For example:</span></span>  
  
    ```  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="cb208-121">La implementación la proporciona un método de invalidación, [override](../../../csharp/language-reference/keywords/override.md), que es miembro de una clase no abstracta.</span><span class="sxs-lookup"><span data-stu-id="cb208-121">The implementation is provided by an overriding method[override](../../../csharp/language-reference/keywords/override.md), which is a member of a non-abstract class.</span></span>  
  
-   <span data-ttu-id="cb208-122">Es un error usar los modificadores [static](../../../csharp/language-reference/keywords/static.md) o [virtual](../../../csharp/language-reference/keywords/virtual.md) en una declaración de método abstracto.</span><span class="sxs-lookup"><span data-stu-id="cb208-122">It is an error to use the [static](../../../csharp/language-reference/keywords/static.md) or [virtual](../../../csharp/language-reference/keywords/virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="cb208-123">Las propiedades abstractas se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.</span><span class="sxs-lookup"><span data-stu-id="cb208-123">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
-   <span data-ttu-id="cb208-124">Es un error usar el modificador `abstract` en una propiedad estática.</span><span class="sxs-lookup"><span data-stu-id="cb208-124">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
-   <span data-ttu-id="cb208-125">Una propiedad abstracta heredada se puede invalidar en una clase derivada incluyendo una declaración de propiedad que use el modificador [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="cb208-125">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](../../../csharp/language-reference/keywords/override.md) modifier.</span></span>  
  
 <span data-ttu-id="cb208-126">Para obtener más información sobre las clases abstractas, vea [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md) (Clases y miembros de clase abstractos y sellados [Guía de programación de C#]).</span><span class="sxs-lookup"><span data-stu-id="cb208-126">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="cb208-127">Una clase abstracta debe proporcionar implementación para todos los miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="cb208-127">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="cb208-128">Una clase abstracta que implemente una interfaz podría asignar los métodos de interfaz a métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="cb208-128">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="cb208-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cb208-129">For example:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="cb208-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb208-130">Example</span></span>  
 <span data-ttu-id="cb208-131">En este ejemplo, la clase `DerivedClass` se deriva de una clase abstracta `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="cb208-131">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="cb208-132">La clase abstracta contiene un método abstracto, `AbstractMethod`, y dos propiedades abstractas, `X` y `Y`.</span><span class="sxs-lookup"><span data-stu-id="cb208-132">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/abstract_3.cs)]  
  
 <span data-ttu-id="cb208-133">En el ejemplo anterior, si intenta crear una instancia de la clase abstracta mediante una instrucción como esta:</span><span class="sxs-lookup"><span data-stu-id="cb208-133">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```  
BaseClass bc = new BaseClass();   // Error  
```  
  
 <span data-ttu-id="cb208-134">obtendrá un error que indica que el compilador no puede crear una instancia de la clase abstracta "BaseClass".</span><span class="sxs-lookup"><span data-stu-id="cb208-134">you will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="cb208-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="cb208-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb208-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb208-136">See Also</span></span>  
 [<span data-ttu-id="cb208-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="cb208-137">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="cb208-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cb208-138">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="cb208-139">Modificadores</span><span class="sxs-lookup"><span data-stu-id="cb208-139">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="cb208-140">virtual</span><span class="sxs-lookup"><span data-stu-id="cb208-140">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)  
 [<span data-ttu-id="cb208-141">override</span><span class="sxs-lookup"><span data-stu-id="cb208-141">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="cb208-142">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="cb208-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
