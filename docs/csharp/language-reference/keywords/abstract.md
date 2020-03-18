---
title: 'abstract: Referencia de C#'
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 96e8bbce2e67c316d5cd1cd78e3e2506dabead25
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713861"
---
# <a name="abstract-c-reference"></a><span data-ttu-id="5474c-102">abstract (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="5474c-102">abstract (C# Reference)</span></span>
<span data-ttu-id="5474c-103">El modificador `abstract` indica que lo que se modifica carece de implementación o tiene una implementación incompleta.</span><span class="sxs-lookup"><span data-stu-id="5474c-103">The `abstract` modifier indicates that the thing being modified has a missing or incomplete implementation.</span></span> <span data-ttu-id="5474c-104">El modificador abstract puede usarse con clases, métodos, propiedades, indexadores y eventos.</span><span class="sxs-lookup"><span data-stu-id="5474c-104">The abstract modifier can be used with classes, methods, properties, indexers, and events.</span></span> <span data-ttu-id="5474c-105">Use el modificador `abstract` en una declaración de clase para indicar que una clase está diseñada como clase base de otras clases, no para crear instancias por sí misma.</span><span class="sxs-lookup"><span data-stu-id="5474c-105">Use the `abstract` modifier in a class declaration to indicate that a class is intended only to be a base class of other classes, not instantiated on its own.</span></span> <span data-ttu-id="5474c-106">Los miembros marcados como abstractos deben implementarse con clases no abstractas derivadas de la clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="5474c-106">Members marked as abstract must be implemented by non-abstract classes that derive from the abstract class.</span></span>
  
## <a name="example"></a><span data-ttu-id="5474c-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5474c-107">Example</span></span>  
 <span data-ttu-id="5474c-108">En este ejemplo, la clase `Square` debe proporcionar una implementación de `GetArea` porque se deriva de `Shape`:</span><span class="sxs-lookup"><span data-stu-id="5474c-108">In this example, the class `Square` must provide an implementation of `GetArea` because it derives from `Shape`:</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 <span data-ttu-id="5474c-109">Las clases abstractas tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5474c-109">Abstract classes have the following features:</span></span>  
  
- <span data-ttu-id="5474c-110">No se pueden crear instancias de una clase abstracta.</span><span class="sxs-lookup"><span data-stu-id="5474c-110">An abstract class cannot be instantiated.</span></span>  
  
- <span data-ttu-id="5474c-111">Una clase abstracta puede contener descriptores de acceso y métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="5474c-111">An abstract class may contain abstract methods and accessors.</span></span>  
  
- <span data-ttu-id="5474c-112">No es posible modificar una clase abstracta con el modificador [sealed](./sealed.md) porque los dos modificadores tienen significados opuestos.</span><span class="sxs-lookup"><span data-stu-id="5474c-112">It is not possible to modify an abstract class with the [sealed](./sealed.md) modifier because the two modifiers have opposite meanings.</span></span> <span data-ttu-id="5474c-113">El modificador `sealed` impide que una clase se herede y el modificador `abstract` requiere que una clase se herede.</span><span class="sxs-lookup"><span data-stu-id="5474c-113">The `sealed` modifier prevents a class from being inherited and the `abstract` modifier requires a class to be inherited.</span></span>  
  
- <span data-ttu-id="5474c-114">Una clase no abstracta que derive de una clase abstracta debe incluir implementaciones reales de todos los descriptores de acceso y métodos abstractos heredados.</span><span class="sxs-lookup"><span data-stu-id="5474c-114">A non-abstract class derived from an abstract class must include actual implementations of all inherited abstract methods and accessors.</span></span>  
  
 <span data-ttu-id="5474c-115">Use el modificador `abstract` en una declaración de método o de propiedad para indicar que el método o la propiedad no contienen implementación.</span><span class="sxs-lookup"><span data-stu-id="5474c-115">Use the `abstract` modifier in a method or property declaration to indicate that the method or property does not contain implementation.</span></span>  
  
 <span data-ttu-id="5474c-116">Los métodos abstractos tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5474c-116">Abstract methods have the following features:</span></span>  
  
- <span data-ttu-id="5474c-117">Un método abstracto es, implícitamente, un método virtual.</span><span class="sxs-lookup"><span data-stu-id="5474c-117">An abstract method is implicitly a virtual method.</span></span>  
  
- <span data-ttu-id="5474c-118">Solo se permiten declaraciones de métodos abstractos en clases abstractas.</span><span class="sxs-lookup"><span data-stu-id="5474c-118">Abstract method declarations are only permitted in abstract classes.</span></span>  
  
- <span data-ttu-id="5474c-119">Dado que una declaración de método abstracto no proporciona una implementación real, no hay ningún cuerpo de método; la declaración de método finaliza simplemente con un punto y coma y no hay llaves ({ }) después de la firma.</span><span class="sxs-lookup"><span data-stu-id="5474c-119">Because an abstract method declaration provides no actual implementation, there is no method body; the method declaration simply ends with a semicolon and there are no curly braces ({ }) following the signature.</span></span> <span data-ttu-id="5474c-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5474c-120">For example:</span></span>  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     <span data-ttu-id="5474c-121">La implementación la proporciona un método, [override](./override.md), que es miembro de una clase no abstracta.</span><span class="sxs-lookup"><span data-stu-id="5474c-121">The implementation is provided by a method [override](./override.md), which is a member of a non-abstract class.</span></span>  
  
- <span data-ttu-id="5474c-122">Es un error usar los modificadores [static](./static.md) o [virtual](./virtual.md) en una declaración de método abstracto.</span><span class="sxs-lookup"><span data-stu-id="5474c-122">It is an error to use the [static](./static.md) or [virtual](./virtual.md) modifiers in an abstract method declaration.</span></span>  
  
 <span data-ttu-id="5474c-123">Las propiedades abstractas se comportan como métodos abstractos, salvo por las diferencias en la sintaxis de declaración e invocación.</span><span class="sxs-lookup"><span data-stu-id="5474c-123">Abstract properties behave like abstract methods, except for the differences in declaration and invocation syntax.</span></span>  
  
- <span data-ttu-id="5474c-124">Es un error usar el modificador `abstract` en una propiedad estática.</span><span class="sxs-lookup"><span data-stu-id="5474c-124">It is an error to use the `abstract` modifier on a static property.</span></span>  
  
- <span data-ttu-id="5474c-125">Una propiedad abstracta heredada se puede invalidar en una clase derivada incluyendo una declaración de propiedad que use el modificador [override](./override.md).</span><span class="sxs-lookup"><span data-stu-id="5474c-125">An abstract inherited property can be overridden in a derived class by including a property declaration that uses the [override](./override.md) modifier.</span></span>  
  
 <span data-ttu-id="5474c-126">Para obtener más información sobre las clases abstractas, vea [Clases y miembros de clase abstractos y sellados ](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="5474c-126">For more information about abstract classes, see [Abstract and Sealed Classes and Class Members](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
 <span data-ttu-id="5474c-127">Una clase abstracta debe proporcionar implementación para todos los miembros de interfaz.</span><span class="sxs-lookup"><span data-stu-id="5474c-127">An abstract class must provide implementation for all interface members.</span></span>  
  
 <span data-ttu-id="5474c-128">Una clase abstracta que implemente una interfaz podría asignar los métodos de interfaz a métodos abstractos.</span><span class="sxs-lookup"><span data-stu-id="5474c-128">An abstract class that implements an interface might map the interface methods onto abstract methods.</span></span> <span data-ttu-id="5474c-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5474c-129">For example:</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a><span data-ttu-id="5474c-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5474c-130">Example</span></span>  
 <span data-ttu-id="5474c-131">En este ejemplo, la clase `DerivedClass` se deriva de una clase abstracta `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="5474c-131">In this example, the class `DerivedClass` is derived from an abstract class `BaseClass`.</span></span> <span data-ttu-id="5474c-132">La clase abstracta contiene un método abstracto, `AbstractMethod`, y dos propiedades abstractas, `X` y `Y`.</span><span class="sxs-lookup"><span data-stu-id="5474c-132">The abstract class contains an abstract method, `AbstractMethod`, and two abstract properties, `X` and `Y`.</span></span>  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 <span data-ttu-id="5474c-133">En el ejemplo anterior, si intenta crear una instancia de la clase abstracta mediante una instrucción como esta:</span><span class="sxs-lookup"><span data-stu-id="5474c-133">In the preceding example, if you attempt to instantiate the abstract class by using a statement like this:</span></span>  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
<span data-ttu-id="5474c-134">Se mostrará un mensaje de error en el que se indica que el compilador no puede crear una instancia de la clase abstracta "BaseClass".</span><span class="sxs-lookup"><span data-stu-id="5474c-134">You will get an error saying that the compiler cannot create an instance of the abstract class 'BaseClass'.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5474c-135">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5474c-135">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5474c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="5474c-136">See also</span></span>

- [<span data-ttu-id="5474c-137">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="5474c-137">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5474c-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5474c-138">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5474c-139">Modificadores</span><span class="sxs-lookup"><span data-stu-id="5474c-139">Modifiers</span></span>](index.md)
- [<span data-ttu-id="5474c-140">virtual</span><span class="sxs-lookup"><span data-stu-id="5474c-140">virtual</span></span>](./virtual.md)
- [<span data-ttu-id="5474c-141">override</span><span class="sxs-lookup"><span data-stu-id="5474c-141">override</span></span>](./override.md)
- [<span data-ttu-id="5474c-142">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="5474c-142">C# Keywords</span></span>](./index.md)
