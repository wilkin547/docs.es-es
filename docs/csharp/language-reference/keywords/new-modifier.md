---
title: new (Modificador, Referencia de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- new modifier keyword [C#]
ms.assetid: a2e20856-33b9-4620-b535-a60dbce8349b
caps.latest.revision: 28
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f763b9a1d2f146b8ebb475a01bd12f1a4238050a
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="new-modifier-c-reference"></a><span data-ttu-id="8a547-102">new (Modificador, Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="8a547-102">new Modifier (C# Reference)</span></span>
<span data-ttu-id="8a547-103">Cuando se utiliza como modificador de una declaración, la palabra clave `new` oculta explícitamente un miembro heredado de una clase base.</span><span class="sxs-lookup"><span data-stu-id="8a547-103">When used as a declaration modifier, the `new` keyword explicitly hides a member that is inherited from a base class.</span></span> <span data-ttu-id="8a547-104">Cuando se oculta un miembro heredado, la versión derivada del miembro reemplaza a la versión de la clase base.</span><span class="sxs-lookup"><span data-stu-id="8a547-104">When you hide an inherited member, the derived version of the member replaces the base class version.</span></span> <span data-ttu-id="8a547-105">Aunque los miembros se pueden ocultar sin utilizar el modificador `new`, obtendrá una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="8a547-105">Although you can hide members without using the `new` modifier, you get a compiler warning.</span></span> <span data-ttu-id="8a547-106">Si utiliza `new` explícitamente para ocultar un miembro, se suprime esta advertencia.</span><span class="sxs-lookup"><span data-stu-id="8a547-106">If you use `new` to explicitly hide a member, it suppresses this warning.</span></span>  
  
 <span data-ttu-id="8a547-107">Para ocultar un miembro heredado, declárelo en la clase derivada con el mismo nombre de miembro y modifíquelo con la palabra clave `new`.</span><span class="sxs-lookup"><span data-stu-id="8a547-107">To hide an inherited member, declare it in the derived class by using the same member name, and modify it with the `new` keyword.</span></span> <span data-ttu-id="8a547-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8a547-108">For example:</span></span>  
  
 <span data-ttu-id="8a547-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a547-109">[!code-cs[csrefKeywordsOperator#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_1.cs)]</span></span>  
  
 <span data-ttu-id="8a547-110">En este ejemplo, `BaseC.Invoke` oculta `DerivedC.Invoke`.</span><span class="sxs-lookup"><span data-stu-id="8a547-110">In this example, `BaseC.Invoke` is hidden by `DerivedC.Invoke`.</span></span> <span data-ttu-id="8a547-111">El campo `x` no se ve afectado porque no lo oculta un nombre similar.</span><span class="sxs-lookup"><span data-stu-id="8a547-111">The field `x` is not affected because it is not hidden by a similar name.</span></span>  
  
 <span data-ttu-id="8a547-112">La ocultación de nombres por medio de la herencia toma una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="8a547-112">Name hiding through inheritance takes one of the following forms:</span></span>  
  
-   <span data-ttu-id="8a547-113">Normalmente, una constante, un campo, una propiedad o un tipo que se muestran en una clase o struct ocultan a todos los miembros de la clase base que comparten su nombre.</span><span class="sxs-lookup"><span data-stu-id="8a547-113">Generally, a constant, field, property, or type that is introduced in a class or struct hides all base class members that share its name.</span></span>  <span data-ttu-id="8a547-114">Hay casos especiales.</span><span class="sxs-lookup"><span data-stu-id="8a547-114">There are special cases.</span></span>  <span data-ttu-id="8a547-115">Por ejemplo, si declara un nuevo campo con el nombre `N` para tener un tipo que no es invocable y un tipo base declara `N` como método, el nuevo campo no oculta la declaración base en la sintaxis de invocación.</span><span class="sxs-lookup"><span data-stu-id="8a547-115">For example, if you declare a new field with name `N` to have a type that is not invocable, and a base type declares `N` to be a method, the new field does not hide the base declaration in invocation syntax.</span></span>  <span data-ttu-id="8a547-116">Vea [Especificación del lenguaje C#](http://go.microsoft.com/fwlink/?LinkId=199552) para obtener información detallada (vea la sección "Búsqueda de miembros" en la sección "Expresiones").</span><span class="sxs-lookup"><span data-stu-id="8a547-116">See the [C# language specification](http://go.microsoft.com/fwlink/?LinkId=199552) for details (see section "Member Lookup" in section "Expressions").</span></span>  
  
-   <span data-ttu-id="8a547-117">Un método introducido en una clase o struct oculta las propiedades, los campos y los tipos que comparten el nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="8a547-117">A method introduced in a class or struct hides properties, fields, and types that share that name in the base class.</span></span> <span data-ttu-id="8a547-118">También oculta todos los métodos de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="8a547-118">It also hides all base class methods that have the same signature.</span></span>  
  
-   <span data-ttu-id="8a547-119">Un indizador introducido en una clase o struct oculta todos los indizadores de la clase base que tienen la misma signatura.</span><span class="sxs-lookup"><span data-stu-id="8a547-119">An indexer introduced in a class or struct hides all base class indexers that have the same signature.</span></span>  
  
 <span data-ttu-id="8a547-120">Es un error usar `new` y [override](../../../csharp/language-reference/keywords/override.md) en el mismo miembro, porque los dos modificadores tienen significados mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="8a547-120">It is an error to use both `new` and [override](../../../csharp/language-reference/keywords/override.md) on the same member, because the two modifiers have mutually exclusive meanings.</span></span> <span data-ttu-id="8a547-121">El modificador `new` crea un nuevo miembro con el mismo nombre y oculta el miembro original.</span><span class="sxs-lookup"><span data-stu-id="8a547-121">The `new` modifier creates a new member with the same name and causes the original member to become hidden.</span></span> <span data-ttu-id="8a547-122">El modificador `override` amplía la implementación de un miembro heredado.</span><span class="sxs-lookup"><span data-stu-id="8a547-122">The `override` modifier extends the implementation for an inherited member.</span></span>  
  
 <span data-ttu-id="8a547-123">Si se utiliza el modificador `new` en una declaración que no oculta un miembro heredado, se genera una advertencia.</span><span class="sxs-lookup"><span data-stu-id="8a547-123">Using the `new` modifier in a declaration that does not hide an inherited member generates a warning.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a547-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a547-124">Example</span></span>  
 <span data-ttu-id="8a547-125">En este ejemplo, una clase base, `BaseC`, y una clase derivada, `DerivedC`, utilizan el mismo nombre de campo `x`, lo que oculta el valor del campo heredado.</span><span class="sxs-lookup"><span data-stu-id="8a547-125">In this example, a base class, `BaseC`, and a derived class, `DerivedC`, use the same field name `x`, which hides the value of the inherited field.</span></span> <span data-ttu-id="8a547-126">El ejemplo muestra el uso del modificador `new`.</span><span class="sxs-lookup"><span data-stu-id="8a547-126">The example demonstrates the use of the `new` modifier.</span></span> <span data-ttu-id="8a547-127">También muestra cómo obtener acceso a los miembros ocultos de la clase base mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="8a547-127">It also demonstrates how to access the hidden members of the base class by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="8a547-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a547-128">[!code-cs[csrefKeywordsOperator#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a547-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8a547-129">Example</span></span>  
 <span data-ttu-id="8a547-130">En este ejemplo, una clase anidada oculta una clase que tiene el mismo nombre en la clase base.</span><span class="sxs-lookup"><span data-stu-id="8a547-130">In this example, a nested class hides a class that has the same name in the base class.</span></span> <span data-ttu-id="8a547-131">El ejemplo muestra cómo utilizar el modificador `new` para eliminar el mensaje de advertencia y cómo obtener acceso a los miembros de la clase oculta mediante sus nombres completos.</span><span class="sxs-lookup"><span data-stu-id="8a547-131">The example demonstrates how to use the `new` modifier to eliminate the warning message and how to access the hidden class members by using their fully qualified names.</span></span>  
  
 <span data-ttu-id="8a547-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="8a547-132">[!code-cs[csrefKeywordsOperator#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/new-modifier_3.cs)]</span></span>  
  
 <span data-ttu-id="8a547-133">Si quita el modificador `new`, el programa seguirá compilándose y ejecutándose, pero aparecerá la siguiente advertencia:</span><span class="sxs-lookup"><span data-stu-id="8a547-133">If you remove the `new` modifier, the program will still compile and run, but you will get the following warning:</span></span>  
  
```  
The keyword new is required on 'MyDerivedC.x' because it hides inherited member 'MyBaseC.x'.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="8a547-134">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="8a547-134">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8a547-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="8a547-135">See Also</span></span>  
 <span data-ttu-id="8a547-136">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-136">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8a547-137">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-137">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8a547-138">[Palabras clave de C#](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-138">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="8a547-139">[Palabras clave de operador](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-139">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 <span data-ttu-id="8a547-140">[Modificadores](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-140">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="8a547-141">[Control de versiones con las palabras clave Override y New](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8a547-141">[Versioning with the Override and New Keywords](../../../csharp/programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) </span></span>  
 [<span data-ttu-id="8a547-142">Saber cuándo utilizar las palabras clave Override y New</span><span class="sxs-lookup"><span data-stu-id="8a547-142">Knowing When to Use Override and New Keywords</span></span>](../../../csharp/programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)

