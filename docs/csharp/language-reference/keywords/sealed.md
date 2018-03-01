---
title: sealed (Referencia de C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 8248b451f0431286fdaba3583fc2031eb6cdbcd7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="sealed-c-reference"></a><span data-ttu-id="815b1-102">sealed (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="815b1-102">sealed (C# Reference)</span></span>
<span data-ttu-id="815b1-103">Cuando se aplica a una clase, el modificador `sealed` impide que otras clases hereden de ella.</span><span class="sxs-lookup"><span data-stu-id="815b1-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="815b1-104">En el ejemplo siguiente, la clase `B` hereda de la clase `A`, pero ninguna clase puede heredar de la clase `B`.</span><span class="sxs-lookup"><span data-stu-id="815b1-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="815b1-105">También puede usar el modificador `sealed` en un método o propiedad que invalida un método o propiedad virtual en una clase base.</span><span class="sxs-lookup"><span data-stu-id="815b1-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="815b1-106">De este modo, puede permitir que las clases deriven de su clase e impedir que invaliden determinados métodos o propiedades virtuales.</span><span class="sxs-lookup"><span data-stu-id="815b1-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="815b1-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="815b1-107">Example</span></span>  
 <span data-ttu-id="815b1-108">En el ejemplo siguiente, `Z` hereda de `Y` pero `Z` no puede invalidar la función virtual `F` que se declara en `X` y se sella en `Y`.</span><span class="sxs-lookup"><span data-stu-id="815b1-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 <span data-ttu-id="815b1-109">Al definir nuevos métodos o propiedades en una clase, puede impedir que las clases derivadas los invaliden. Para ello, no los declare como [virtuales](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="815b1-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="815b1-110">Es un error usar el modificador [abstract](../../../csharp/language-reference/keywords/abstract.md) con una clase sellada, porque una clase abstracta debe heredarla una clase que proporcione una implementación de los métodos o propiedades abstractos.</span><span class="sxs-lookup"><span data-stu-id="815b1-110">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="815b1-111">Cuando se aplica a un método o propiedad, el modificador `sealed` siempre se debe usar con [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="815b1-111">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="815b1-112">Dado que los structs están sellados implícitamente, no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="815b1-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="815b1-113">Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="815b1-113">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="815b1-114">Para obtener más ejemplos, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="815b1-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="815b1-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="815b1-115">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 <span data-ttu-id="815b1-116">En el ejemplo anterior, podría intentar heredar de la clase sellada mediante la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="815b1-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="815b1-117">El resultado es un mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="815b1-117">The result is an error message:</span></span>  
  
 `'MyDerivedC' cannot inherit from sealed class 'SealedClass'.`  
  
## <a name="c-language-specification"></a><span data-ttu-id="815b1-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="815b1-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="815b1-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="815b1-119">Remarks</span></span>  
 <span data-ttu-id="815b1-120">Para determinar si se debe sellar una clase, un método o una propiedad, por lo general debe tener en cuenta los dos puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="815b1-120">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="815b1-121">Las posibles ventajas que podrían obtener las clases derivadas con la capacidad de personalizar la clase.</span><span class="sxs-lookup"><span data-stu-id="815b1-121">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="815b1-122">La posibilidad de que las clases derivadas modifiquen las clases de tal manera que no funcionen correctamente o del modo esperado.</span><span class="sxs-lookup"><span data-stu-id="815b1-122">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815b1-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="815b1-123">See Also</span></span>  
 [<span data-ttu-id="815b1-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="815b1-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="815b1-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="815b1-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="815b1-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="815b1-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="815b1-127">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="815b1-127">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="815b1-128">Clases y miembros de clase abstractos y sellados</span><span class="sxs-lookup"><span data-stu-id="815b1-128">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="815b1-129">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="815b1-129">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="815b1-130">Modificadores</span><span class="sxs-lookup"><span data-stu-id="815b1-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="815b1-131">override</span><span class="sxs-lookup"><span data-stu-id="815b1-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="815b1-132">virtual</span><span class="sxs-lookup"><span data-stu-id="815b1-132">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)
