---
title: "Comparaciones de igualdad (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object equality [C#]
ms.assetid: 10b865ea-4e7b-4127-9242-c9b8f57d9f04
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
ms.openlocfilehash: 948bbc1b5b8535cc31ea362497fa69a816b43edc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="equality-comparisons-c-programming-guide"></a><span data-ttu-id="c93b4-102">Comparaciones de igualdad (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="c93b4-102">Equality Comparisons (C# Programming Guide)</span></span>
<span data-ttu-id="c93b4-103">A veces es necesario comparar si dos valores son iguales.</span><span class="sxs-lookup"><span data-stu-id="c93b4-103">It is sometimes necessary to compare two values for equality.</span></span> <span data-ttu-id="c93b4-104">En algunos casos, se prueba la *igualdad de valores*, también denominada *equivalencia*, lo que significa que los valores contenidos en las dos variables son iguales.</span><span class="sxs-lookup"><span data-stu-id="c93b4-104">In some cases, you are testing for *value equality*, also known as *equivalence*, which means that the values that are contained by the two variables are equal.</span></span> <span data-ttu-id="c93b4-105">En otros casos, hay que determinar si dos variables hacen referencia al mismo objeto subyacente de la memoria.</span><span class="sxs-lookup"><span data-stu-id="c93b4-105">In other cases, you have to determine whether two variables refer to the same underlying object in memory.</span></span> <span data-ttu-id="c93b4-106">Este tipo de igualdad se denomina *igualdad de referencia* o *identidad*.</span><span class="sxs-lookup"><span data-stu-id="c93b4-106">This type of equality is called *reference equality*, or *identity*.</span></span> <span data-ttu-id="c93b4-107">En este tema se describen estos dos tipos de igualdad y se proporcionan vínculos a otros temas para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="c93b4-107">This topic describes these two kinds of equality and provides links to other topics for more information.</span></span>  
  
## <a name="reference-equality"></a><span data-ttu-id="c93b4-108">Igualdad de referencia</span><span class="sxs-lookup"><span data-stu-id="c93b4-108">Reference Equality</span></span>  
 <span data-ttu-id="c93b4-109">La igualdad de referencia significa que dos referencias de objeto hacen referencia al mismo objeto subyacente.</span><span class="sxs-lookup"><span data-stu-id="c93b4-109">Reference equality means that two object references refer to the same underlying object.</span></span> <span data-ttu-id="c93b4-110">Esto puede suceder mediante una asignación simple, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c93b4-110">This can occur through simple assignment, as shown in the following example.</span></span>  
  
 <span data-ttu-id="c93b4-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c93b4-111">[!code-cs[csProgGuideStatements#18](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/equality-comparisons_1.cs)]</span></span>  
  
 <span data-ttu-id="c93b4-112">En este código, se crean dos objetos, pero después de la instrucción de asignación, ambas referencias hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="c93b4-112">In this code, two objects are created, but after the assignment statement, both references refer to the same object.</span></span> <span data-ttu-id="c93b4-113">Por consiguiente, presentan igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="c93b4-113">Therefore they have reference equality.</span></span> <span data-ttu-id="c93b4-114">Use el método <xref:System.Object.ReferenceEquals%2A> para determinar si dos referencias hacen referencia al mismo objeto.</span><span class="sxs-lookup"><span data-stu-id="c93b4-114">Use the <xref:System.Object.ReferenceEquals%2A> method to determine whether two references refer to the same object.</span></span>  
  
 <span data-ttu-id="c93b4-115">El concepto de igualdad de la referencia solo se aplica a los tipos de referencia.</span><span class="sxs-lookup"><span data-stu-id="c93b4-115">The concept of reference equality applies only to reference types.</span></span> <span data-ttu-id="c93b4-116">Los objetos de tipo de valor no pueden presentar igualdad de referencia porque al asignar una instancia de un tipo de valor a una variable, se realiza una copia del valor.</span><span class="sxs-lookup"><span data-stu-id="c93b4-116">Value type objects cannot have reference equality because when an instance of a value type is assigned to a variable, a copy of the value is made.</span></span> <span data-ttu-id="c93b4-117">Por consiguiente, nunca puede haber dos structs con conversión unboxing que hagan referencia a la misma ubicación de la memoria.</span><span class="sxs-lookup"><span data-stu-id="c93b4-117">Therefore you can never have two unboxed structs that refer to the same location in memory.</span></span> <span data-ttu-id="c93b4-118">Además, si se usa <xref:System.Object.ReferenceEquals%2A> para comparar dos tipos de valor, el resultado siempre será `false`, aunque todos los valores que contengan los objetos sean idénticos.</span><span class="sxs-lookup"><span data-stu-id="c93b4-118">Furthermore, if you use <xref:System.Object.ReferenceEquals%2A> to compare two value types, the result will always be `false`, even if the values that are contained in the objects are all identical.</span></span> <span data-ttu-id="c93b4-119">Esto se debe a que a cada variable se aplica la conversión boxing en una instancia de objeto independiente.</span><span class="sxs-lookup"><span data-stu-id="c93b4-119">This is because each variable is boxed into a separate object instance.</span></span> <span data-ttu-id="c93b4-120">Para obtener más información, vea [Cómo: Probar la igualdad de referencia (Identidad)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span><span class="sxs-lookup"><span data-stu-id="c93b4-120">For more information, see [How to: Test for Reference Equality (Identity)](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md).</span></span>  
  
## <a name="value-equality"></a><span data-ttu-id="c93b4-121">igualdad de valores</span><span class="sxs-lookup"><span data-stu-id="c93b4-121">Value Equality</span></span>  
 <span data-ttu-id="c93b4-122">La igualdad de valores significa que dos objetos contienen el mismo valor o valores.</span><span class="sxs-lookup"><span data-stu-id="c93b4-122">Value equality means that two objects contain the same value or values.</span></span> <span data-ttu-id="c93b4-123">Para los tipos de valor primitivos, como [int](../../../csharp/language-reference/keywords/int.md) o [bool](../../../csharp/language-reference/keywords/bool.md), las pruebas de igualdad de valores son sencillas.</span><span class="sxs-lookup"><span data-stu-id="c93b4-123">For primitive value types such as [int](../../../csharp/language-reference/keywords/int.md) or [bool](../../../csharp/language-reference/keywords/bool.md), tests for value equality are straightforward.</span></span> <span data-ttu-id="c93b4-124">Puede usar el operador [==](../../../csharp/language-reference/operators/equality-comparison-operator.md), como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="c93b4-124">You can use the [==](../../../csharp/language-reference/operators/equality-comparison-operator.md) operator, as shown in the following example.</span></span>  
  
```csharp  
int a = GetOriginalValue();  
int b = GetCurrentValue();  
  
// Test for value equality.   
if( b == a)   
{  
    // The two integers are equal.  
}  
```  
  
 <span data-ttu-id="c93b4-125">Para la mayoría de los otros tipos, las pruebas de igualdad de valores son más complejas, porque es preciso entender cómo la define el tipo.</span><span class="sxs-lookup"><span data-stu-id="c93b4-125">For most other types, testing for value equality is more complex because it requires that you understand how the type defines it.</span></span> <span data-ttu-id="c93b4-126">Para las clases y los structs que tienen varios campos o propiedades, la igualdad de valores suele definirse de modo que significa que todos los campos o propiedades tienen el mismo valor.</span><span class="sxs-lookup"><span data-stu-id="c93b4-126">For classes and structs that have multiple fields or properties, value equality is often defined to mean that all fields or properties have the same value.</span></span> <span data-ttu-id="c93b4-127">Por ejemplo, podrían definirse dos objetos `Point` que fueran equivalentes si pointA.X es igual a pointB.X y pointA.Y es igual a pointB.Y.</span><span class="sxs-lookup"><span data-stu-id="c93b4-127">For example, two `Point` objects might be defined to be equivalent if pointA.X is equal to pointB.X and pointA.Y is equal to pointB.Y.</span></span>  
  
 <span data-ttu-id="c93b4-128">En cambio, no hay ningún requisito que exija que la equivalencia se base en todos los campos de un tipo.</span><span class="sxs-lookup"><span data-stu-id="c93b4-128">However, there is no requirement that equivalence be based on all the fields in a type.</span></span> <span data-ttu-id="c93b4-129">Se puede basar en un subconjunto.</span><span class="sxs-lookup"><span data-stu-id="c93b4-129">It can be based on a subset.</span></span> <span data-ttu-id="c93b4-130">Al comparar tipos que no sean de su propiedad, es importante asegurarse concretamente de cómo se define la equivalencia para ese tipo.</span><span class="sxs-lookup"><span data-stu-id="c93b4-130">When you compare types that you do not own, you should make sure to understand specifically how equivalence is defined for that type.</span></span> <span data-ttu-id="c93b4-131">Para obtener más información sobre cómo definir la igualdad de valores en sus propias clases y structs, vea [Cómo: Definir la igualdad de valores para un tipo](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span><span class="sxs-lookup"><span data-stu-id="c93b4-131">For more information about how to define value equality in your own classes and structs, see [How to: Define Value Equality for a Type](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md).</span></span>  
  
### <a name="value-equality-for-floating-point-values"></a><span data-ttu-id="c93b4-132">Igualdad de valores en valores de número de punto flotante</span><span class="sxs-lookup"><span data-stu-id="c93b4-132">Value Equality for Floating Point Values</span></span>  
 <span data-ttu-id="c93b4-133">Las comparaciones de igualdad de valores de punto flotante ([double](../../../csharp/language-reference/keywords/double.md) y [float](../../../csharp/language-reference/keywords/float.md)) son problemáticas debido a la imprecisión de la aritmética de número de punto flotante en los equipos binarios.</span><span class="sxs-lookup"><span data-stu-id="c93b4-133">Equality comparisons of floating point values ([double](../../../csharp/language-reference/keywords/double.md) and [float](../../../csharp/language-reference/keywords/float.md)) are problematic because of the imprecision of floating point arithmetic on binary computers.</span></span> <span data-ttu-id="c93b4-134">Para obtener más información, vea los comentarios en el tema <xref:System.Double?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="c93b4-134">For more information, see the remarks in the topic <xref:System.Double?displayProperty=fullName>.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="c93b4-135">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c93b4-135">Related Topics</span></span>  
  
|<span data-ttu-id="c93b4-136">Título</span><span class="sxs-lookup"><span data-stu-id="c93b4-136">Title</span></span>|<span data-ttu-id="c93b4-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="c93b4-137">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="c93b4-138">Cómo: Probar la igualdad de referencia (Identidad)</span><span class="sxs-lookup"><span data-stu-id="c93b4-138">How to: Test for Reference Equality (Identity)</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-test-for-reference-equality-identity.md)|<span data-ttu-id="c93b4-139">Describe cómo determinar si dos variables presentan igualdad de referencia.</span><span class="sxs-lookup"><span data-stu-id="c93b4-139">Describes how to determine whether two variables have reference equality.</span></span>|  
|[<span data-ttu-id="c93b4-140">Cómo: Definir la igualdad de valores para un tipo</span><span class="sxs-lookup"><span data-stu-id="c93b4-140">How to: Define Value Equality for a Type</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-define-value-equality-for-a-type.md)|<span data-ttu-id="c93b4-141">Describe cómo proporcionar una definición personalizada de igualdad de valores para un tipo.</span><span class="sxs-lookup"><span data-stu-id="c93b4-141">Describes how to provide a custom definition of value equality for a type.</span></span>|  
|[<span data-ttu-id="c93b4-142">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c93b4-142">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)|<span data-ttu-id="c93b4-143">Proporciona vínculos a información detallada sobre importantes características del lenguaje C# y características que están disponibles para C# a través de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c93b4-143">Provides links to detailed information about important C# language features and features that are available to C# through the .NET Framework.</span></span>|  
|[<span data-ttu-id="c93b4-144">Tipos</span><span class="sxs-lookup"><span data-stu-id="c93b4-144">Types</span></span>](../../../csharp/programming-guide/types/index.md)|<span data-ttu-id="c93b4-145">Proporciona información sobre el sistema de tipos de C# y vínculos a información adicional.</span><span class="sxs-lookup"><span data-stu-id="c93b4-145">Provides information about the C# type system and links to additional information.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c93b4-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="c93b4-146">See Also</span></span>  
 [<span data-ttu-id="c93b4-147">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="c93b4-147">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

