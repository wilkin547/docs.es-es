---
title: "Clases genéricas (Guía de programación de C#)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
caps.latest.revision: 30
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
ms.openlocfilehash: 17ec9f5d26c01b7f7f7f95026bfdfaa88d709b60
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="9a924-102">Clases genéricas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="9a924-102">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="9a924-103">Las clases genéricas encapsulan operaciones que no son específicas de un tipo de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="9a924-103">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="9a924-104">El uso más común de las clases genéricas es con colecciones como listas vinculadas, tablas hash, pilas, colas y árboles, entre otros.</span><span class="sxs-lookup"><span data-stu-id="9a924-104">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="9a924-105">Las operaciones como la adición y eliminación de elementos de la colección se realizan básicamente de la misma manera independientemente del tipo de datos que se almacenan.</span><span class="sxs-lookup"><span data-stu-id="9a924-105">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="9a924-106">Para la mayoría de los escenarios que necesitan clases de colección, el enfoque recomendado es usar las que se proporcionan en la biblioteca de clases .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a924-106">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET Framework class library.</span></span> <span data-ttu-id="9a924-107">Para obtener más información sobre el uso de estas clases, vea [Tipos genéricos en la biblioteca de clases de .NET Framework](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span><span class="sxs-lookup"><span data-stu-id="9a924-107">For more information about using these classes, see [Generics in the .NET Framework Class Library](../../../csharp/programming-guide/generics/generics-in-the-net-framework-class-library.md).</span></span>  
  
 <span data-ttu-id="9a924-108">Normalmente, crea clases genéricas empezando con una clase concreta existente, y cambiando tipos en parámetros de tipo de uno en uno hasta que alcanza el equilibrio óptimo de generalización y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="9a924-108">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="9a924-109">Al crear sus propias clases genéricas, entre las consideraciones importantes se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="9a924-109">When creating your own generic classes, important considerations include the following:</span></span>  
  
-   <span data-ttu-id="9a924-110">Los tipos que se van a generalizar en parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="9a924-110">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="9a924-111">Como norma, cuantos más tipos pueda parametrizar, más flexible y reutilizable será su código.</span><span class="sxs-lookup"><span data-stu-id="9a924-111">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="9a924-112">En cambio, demasiada generalización puede crear código que sea difícil de leer o entender para otros desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="9a924-112">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
-   <span data-ttu-id="9a924-113">Las restricciones, si existen, que se van a aplicar a los parámetros de tipo (Vea [Restricciones de parámetros de tipo](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="9a924-113">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](../../../csharp/programming-guide/generics/constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="9a924-114">Una buena norma es aplicar el máximo número de restricciones posible que todavía le permitan tratar los tipos que debe controlar.</span><span class="sxs-lookup"><span data-stu-id="9a924-114">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="9a924-115">Por ejemplo, si sabe que su clase genérica está diseñada para usarse solo con tipos de referencia, aplique la restricción de clase.</span><span class="sxs-lookup"><span data-stu-id="9a924-115">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="9a924-116">Esto evitará el uso no previsto de su clase con tipos de valor, y le permitirá usar el operador `as` en `T`, y comprobar si hay valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9a924-116">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
-   <span data-ttu-id="9a924-117">Si separar el comportamiento genérico en clases base y subclases.</span><span class="sxs-lookup"><span data-stu-id="9a924-117">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="9a924-118">Como las clases genéricas pueden servir como clases base, las mismas consideraciones de diseño se aplican aquí con clases no genéricas.</span><span class="sxs-lookup"><span data-stu-id="9a924-118">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="9a924-119">Vea las reglas sobre cómo heredar de clases base genéricas posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="9a924-119">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
-   <span data-ttu-id="9a924-120">Si implementar una o más interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="9a924-120">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="9a924-121">Por ejemplo, si está diseñando una clase que se usará para crear elementos en una colección basada en genéricos, puede que tenga que implementar una interfaz como <xref:System.IComparable%601> donde `T` es el tipo de su clase.</span><span class="sxs-lookup"><span data-stu-id="9a924-121">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="9a924-122">Para obtener un ejemplo de una clase genérica simple, vea [Introducción a los genéricos](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span><span class="sxs-lookup"><span data-stu-id="9a924-122">For an example of a simple generic class, see [Introduction to Generics](../../../csharp/programming-guide/generics/introduction-to-generics.md).</span></span>  
  
 <span data-ttu-id="9a924-123">Las reglas para los parámetros de tipo y las restricciones tienen varias implicaciones para el comportamiento de clase genérico, especialmente respecto a la herencia y a la accesibilidad de miembros.</span><span class="sxs-lookup"><span data-stu-id="9a924-123">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="9a924-124">Antes de continuar, debe entender algunos términos.</span><span class="sxs-lookup"><span data-stu-id="9a924-124">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="9a924-125">Para una clase genérica `Node<T>,`, el código de cliente puede hacer referencia a la clase especificando un argumento de tipo, para crear un tipo construido cerrado (`Node<int>`).</span><span class="sxs-lookup"><span data-stu-id="9a924-125">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="9a924-126">De manera alternativa, puede dejar el parámetro de tipo sin especificar, por ejemplo cuando especifica una clase base genérica, para crear un tipo construido abierto (`Node<T>`).</span><span class="sxs-lookup"><span data-stu-id="9a924-126">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="9a924-127">Las clases genéricas pueden heredar de determinadas clases base construidas abiertas o construidas cerradas:</span><span class="sxs-lookup"><span data-stu-id="9a924-127">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 <span data-ttu-id="9a924-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-128">[!code-cs[csProgGuideGenerics#16](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_1.cs)]</span></span>  
  
 <span data-ttu-id="9a924-129">Las clases no genéricas, en otras palabras, concretas, pueden heredar de clases base construidas cerradas, pero no desde clases construidas abiertas ni desde parámetros de tipo porque no hay ninguna manera en tiempo de ejecución para que el código de cliente proporcione el argumento de tipo necesario para crear instancias de la clase base.</span><span class="sxs-lookup"><span data-stu-id="9a924-129">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 <span data-ttu-id="9a924-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-130">[!code-cs[csProgGuideGenerics#17](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_2.cs)]</span></span>  
  
 <span data-ttu-id="9a924-131">Las clases genéricas que heredan de tipos construidos abiertos deben proporcionar argumentos de tipo para cualquier parámetro de tipo de clase base que no se comparta mediante la clase heredada, como se demuestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a924-131">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 <span data-ttu-id="9a924-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-132">[!code-cs[csProgGuideGenerics#18](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_3.cs)]</span></span>  
  
 <span data-ttu-id="9a924-133">Las clases genéricas que heredan de tipos construidos abiertos deben especificar restricciones que son un superconjunto de las restricciones del tipo base, o que las implican:</span><span class="sxs-lookup"><span data-stu-id="9a924-133">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 <span data-ttu-id="9a924-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-134">[!code-cs[csProgGuideGenerics#19](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_4.cs)]</span></span>  
  
 <span data-ttu-id="9a924-135">Los tipos genéricos pueden usar varios parámetros de tipo y restricciones, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a924-135">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 <span data-ttu-id="9a924-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-136">[!code-cs[csProgGuideGenerics#20](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_5.cs)]</span></span>  
  
 <span data-ttu-id="9a924-137">Tipos construidos cerrados y construidos abiertos pueden usarse como parámetros de método:</span><span class="sxs-lookup"><span data-stu-id="9a924-137">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 <span data-ttu-id="9a924-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="9a924-138">[!code-cs[csProgGuideGenerics#21](../../../csharp/programming-guide/generics/codesnippet/CSharp/generic-classes_6.cs)]</span></span>  
  
 <span data-ttu-id="9a924-139">Si una clase genérica implementa una interfaz, todas las instancias de esa clase se pueden convertir en esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="9a924-139">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="9a924-140">Las clases genéricas son invariables.</span><span class="sxs-lookup"><span data-stu-id="9a924-140">Generic classes are invariant.</span></span> <span data-ttu-id="9a924-141">En otras palabras, si un parámetro de entrada especifica un `List<BaseClass>`, obtendrá un error en tiempo de compilación si intenta proporcionar un `List<DerivedClass>`.</span><span class="sxs-lookup"><span data-stu-id="9a924-141">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a924-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a924-142">See Also</span></span>  
 <span data-ttu-id="9a924-143"><xref:System.Collections.Generic></span><span class="sxs-lookup"><span data-stu-id="9a924-143"><xref:System.Collections.Generic></span></span>   
 <span data-ttu-id="9a924-144">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a924-144">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9a924-145">[Genéricos](../../../csharp/programming-guide/generics/index.md) </span><span class="sxs-lookup"><span data-stu-id="9a924-145">[Generics](../../../csharp/programming-guide/generics/index.md) </span></span>  
 <span data-ttu-id="9a924-146">[Guardar el estado de los enumeradores](http://go.microsoft.com/fwlink/?LinkId=112390) </span><span class="sxs-lookup"><span data-stu-id="9a924-146">[Saving the State of Enumerators](http://go.microsoft.com/fwlink/?LinkId=112390) </span></span>  
 [<span data-ttu-id="9a924-147">Un puzle de herencia, parte uno</span><span class="sxs-lookup"><span data-stu-id="9a924-147">An Inheritance Puzzle, Part One</span></span>](http://go.microsoft.com/fwlink/?LinkId=112380)

