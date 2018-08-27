---
title: sealed (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- sealed
- sealed_CSharpKeyword
helpviewer_keywords:
- sealed keyword [C#]
ms.assetid: 8e4ed5d3-10be-47db-9488-0da2008e6f3f
ms.openlocfilehash: be13e04dce12dfb60a1179e05a0a47eca1df1af4
ms.sourcegitcommit: a1e35d4e94edab384a63406c0a5438306873031b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2018
ms.locfileid: "42752118"
---
# <a name="sealed-c-reference"></a><span data-ttu-id="baf5b-102">sealed (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="baf5b-102">sealed (C# Reference)</span></span>
<span data-ttu-id="baf5b-103">Cuando se aplica a una clase, el modificador `sealed` impide que otras clases hereden de ella.</span><span class="sxs-lookup"><span data-stu-id="baf5b-103">When applied to a class, the `sealed` modifier prevents other classes from inheriting from it.</span></span> <span data-ttu-id="baf5b-104">En el ejemplo siguiente, la clase `B` hereda de la clase `A`, pero ninguna clase puede heredar de la clase `B`.</span><span class="sxs-lookup"><span data-stu-id="baf5b-104">In the following example, class `B` inherits from class `A`, but no class can inherit from class `B`.</span></span>  
  
```csharp  
class A {}      
sealed class B : A {}  
```  
  
 <span data-ttu-id="baf5b-105">También puede usar el modificador `sealed` en un método o propiedad que invalida un método o propiedad virtual en una clase base.</span><span class="sxs-lookup"><span data-stu-id="baf5b-105">You can also use the `sealed` modifier on a method or property that overrides a virtual method or property in a base class.</span></span> <span data-ttu-id="baf5b-106">De este modo, puede permitir que las clases deriven de su clase e impedir que invaliden determinados métodos o propiedades virtuales.</span><span class="sxs-lookup"><span data-stu-id="baf5b-106">This enables you to allow classes to derive from your class and prevent them from overriding specific virtual methods or properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="baf5b-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baf5b-107">Example</span></span>  
 <span data-ttu-id="baf5b-108">En el ejemplo siguiente, `Z` hereda de `Y` pero `Z` no puede invalidar la función virtual `F` que se declara en `X` y se sella en `Y`.</span><span class="sxs-lookup"><span data-stu-id="baf5b-108">In the following example, `Z` inherits from `Y` but `Z` cannot override the virtual function `F` that is declared in `X` and sealed in `Y`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_1.cs)]  
  
 <span data-ttu-id="baf5b-109">Al definir nuevos métodos o propiedades en una clase, puede impedir que las clases derivadas los invaliden. Para ello, no los declare como [virtuales](../../../csharp/language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="baf5b-109">When you define new methods or properties in a class, you can prevent deriving classes from overriding them by not declaring them as [virtual](../../../csharp/language-reference/keywords/virtual.md).</span></span>  
  
 <span data-ttu-id="baf5b-110">Es un error usar el modificador [abstract](../../../csharp/language-reference/keywords/abstract.md) con una clase sellada, porque una clase abstracta debe heredarla una clase que proporcione una implementación de los métodos o propiedades abstractos.</span><span class="sxs-lookup"><span data-stu-id="baf5b-110">It is an error to use the [abstract](../../../csharp/language-reference/keywords/abstract.md) modifier with a sealed class, because an abstract class must be inherited by a class that provides an implementation of the abstract methods or properties.</span></span>  
  
 <span data-ttu-id="baf5b-111">Cuando se aplica a un método o propiedad, el modificador `sealed` siempre se debe usar con [override](../../../csharp/language-reference/keywords/override.md).</span><span class="sxs-lookup"><span data-stu-id="baf5b-111">When applied to a method or property, the `sealed` modifier must always be used with [override](../../../csharp/language-reference/keywords/override.md).</span></span>  
  
 <span data-ttu-id="baf5b-112">Dado que los structs están sellados implícitamente, no puede heredarse.</span><span class="sxs-lookup"><span data-stu-id="baf5b-112">Because structs are implicitly sealed, they cannot be inherited.</span></span>  
  
 <span data-ttu-id="baf5b-113">Para obtener más información, vea [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="baf5b-113">For more information, see [Inheritance](../../../csharp/programming-guide/classes-and-structs/inheritance.md).</span></span>  
  
 <span data-ttu-id="baf5b-114">Para obtener más ejemplos, vea [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="baf5b-114">For more examples, see [Abstract and Sealed Classes and Class Members](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="baf5b-115">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="baf5b-115">Example</span></span>  
 [!code-csharp[csrefKeywordsModifiers#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/sealed_2.cs)]  
  
 <span data-ttu-id="baf5b-116">En el ejemplo anterior, podría intentar heredar de la clase sellada mediante la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="baf5b-116">In the previous example, you might try to inherit from the sealed class by using the following statement:</span></span>  
  
 `class MyDerivedC: SealedClass {}   // Error`  
  
 <span data-ttu-id="baf5b-117">El resultado es un mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="baf5b-117">The result is an error message:</span></span>  
  
 `'MyDerivedC': cannot derive from sealed type 'SealedClass'`  
  
## <a name="c-language-specification"></a><span data-ttu-id="baf5b-118">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="baf5b-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="remarks"></a><span data-ttu-id="baf5b-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="baf5b-119">Remarks</span></span>  
 <span data-ttu-id="baf5b-120">Para determinar si se debe sellar una clase, un método o una propiedad, por lo general debe tener en cuenta los dos puntos siguientes:</span><span class="sxs-lookup"><span data-stu-id="baf5b-120">To determine whether to seal a class, method, or property, you should generally consider the following two points:</span></span>  
  
-   <span data-ttu-id="baf5b-121">Las posibles ventajas que podrían obtener las clases derivadas con la capacidad de personalizar la clase.</span><span class="sxs-lookup"><span data-stu-id="baf5b-121">The potential benefits that deriving classes might gain through the ability to customize your class.</span></span>  
  
-   <span data-ttu-id="baf5b-122">La posibilidad de que las clases derivadas modifiquen las clases de tal manera que no funcionen correctamente o del modo esperado.</span><span class="sxs-lookup"><span data-stu-id="baf5b-122">The potential that deriving classes could modify your classes in such a way that they would no longer work correctly or as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf5b-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf5b-123">See Also</span></span>  
 [<span data-ttu-id="baf5b-124">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="baf5b-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="baf5b-125">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="baf5b-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="baf5b-126">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="baf5b-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="baf5b-127">Clases estáticas y sus miembros</span><span class="sxs-lookup"><span data-stu-id="baf5b-127">Static Classes and Static Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)  
 [<span data-ttu-id="baf5b-128">Clases y miembros de clase abstractos y sellados</span><span class="sxs-lookup"><span data-stu-id="baf5b-128">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)  
 [<span data-ttu-id="baf5b-129">Modificadores de acceso</span><span class="sxs-lookup"><span data-stu-id="baf5b-129">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="baf5b-130">Modificadores</span><span class="sxs-lookup"><span data-stu-id="baf5b-130">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="baf5b-131">override</span><span class="sxs-lookup"><span data-stu-id="baf5b-131">override</span></span>](../../../csharp/language-reference/keywords/override.md)  
 [<span data-ttu-id="baf5b-132">virtual</span><span class="sxs-lookup"><span data-stu-id="baf5b-132">virtual</span></span>](../../../csharp/language-reference/keywords/virtual.md)
