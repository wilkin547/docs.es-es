---
title: 'Clases genéricas: Guía de programación de C#'
description: Aprenda sobre las clases genéricas utilizadas en colecciones como listas vinculadas, tablas hash, pilas, colas y árboles.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, generic classes
- generics [C#], classes
ms.assetid: 27d6f256-cd61-41e3-bc6e-b990a53b0224
ms.openlocfilehash: a885ae042eef939021d3a9b75616505c289bd43c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558092"
---
# <a name="generic-classes-c-programming-guide"></a><span data-ttu-id="235e2-103">Clases genéricas (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="235e2-103">Generic Classes (C# Programming Guide)</span></span>
<span data-ttu-id="235e2-104">Las clases genéricas encapsulan operaciones que no son específicas de un tipo de datos determinado.</span><span class="sxs-lookup"><span data-stu-id="235e2-104">Generic classes encapsulate operations that are not specific to a particular data type.</span></span> <span data-ttu-id="235e2-105">El uso más común de las clases genéricas es con colecciones como listas vinculadas, tablas hash, pilas, colas y árboles, entre otros.</span><span class="sxs-lookup"><span data-stu-id="235e2-105">The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on.</span></span> <span data-ttu-id="235e2-106">Las operaciones como la adición y eliminación de elementos de la colección se realizan básicamente de la misma manera independientemente del tipo de datos que se almacenan.</span><span class="sxs-lookup"><span data-stu-id="235e2-106">Operations such as adding and removing items from the collection are performed in basically the same way regardless of the type of data being stored.</span></span>  
  
 <span data-ttu-id="235e2-107">Para la mayoría de los escenarios que necesitan clases de colección, el enfoque recomendado es usar las que se proporcionan en la biblioteca de clases .NET.</span><span class="sxs-lookup"><span data-stu-id="235e2-107">For most scenarios that require collection classes, the recommended approach is to use the ones provided in the .NET class library.</span></span> <span data-ttu-id="235e2-108">Para más información sobre el uso de estas clases, vea [Colecciones genéricas en .NET](../../../standard/generics/collections.md).</span><span class="sxs-lookup"><span data-stu-id="235e2-108">For more information about using these classes, see [Generic Collections in .NET](../../../standard/generics/collections.md).</span></span>  
  
 <span data-ttu-id="235e2-109">Normalmente, crea clases genéricas empezando con una clase concreta existente, y cambiando tipos en parámetros de tipo de uno en uno hasta que alcanza el equilibrio óptimo de generalización y facilidad de uso.</span><span class="sxs-lookup"><span data-stu-id="235e2-109">Typically, you create generic classes by starting with an existing concrete class, and changing types into type parameters one at a time until you reach the optimal balance of generalization and usability.</span></span> <span data-ttu-id="235e2-110">Al crear sus propias clases genéricas, entre las consideraciones importantes se incluyen las siguientes:</span><span class="sxs-lookup"><span data-stu-id="235e2-110">When creating your own generic classes, important considerations include the following:</span></span>  
  
- <span data-ttu-id="235e2-111">Los tipos que se van a generalizar en parámetros de tipo.</span><span class="sxs-lookup"><span data-stu-id="235e2-111">Which types to generalize into type parameters.</span></span>  
  
     <span data-ttu-id="235e2-112">Como norma, cuantos más tipos pueda parametrizar, más flexible y reutilizable será su código.</span><span class="sxs-lookup"><span data-stu-id="235e2-112">As a rule, the more types you can parameterize, the more flexible and reusable your code becomes.</span></span> <span data-ttu-id="235e2-113">En cambio, demasiada generalización puede crear código que sea difícil de leer o entender para otros desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="235e2-113">However, too much generalization can create code that is difficult for other developers to read or understand.</span></span>  
  
- <span data-ttu-id="235e2-114">Las restricciones, si existen, que se van a aplicar a los parámetros de tipo (Vea [Restricciones de parámetros de tipo](./constraints-on-type-parameters.md)).</span><span class="sxs-lookup"><span data-stu-id="235e2-114">What constraints, if any, to apply to the type parameters (See [Constraints on Type Parameters](./constraints-on-type-parameters.md)).</span></span>  
  
     <span data-ttu-id="235e2-115">Una buena norma es aplicar el máximo número de restricciones posible que todavía le permitan tratar los tipos que debe controlar.</span><span class="sxs-lookup"><span data-stu-id="235e2-115">A good rule is to apply the maximum constraints possible that will still let you handle the types you must handle.</span></span> <span data-ttu-id="235e2-116">Por ejemplo, si sabe que su clase genérica está diseñada para usarse solo con tipos de referencia, aplique la restricción de clase.</span><span class="sxs-lookup"><span data-stu-id="235e2-116">For example, if you know that your generic class is intended for use only with reference types, apply the class constraint.</span></span> <span data-ttu-id="235e2-117">Esto evitará el uso no previsto de su clase con tipos de valor, y le permitirá usar el operador `as` en `T`, y comprobar si hay valores NULL.</span><span class="sxs-lookup"><span data-stu-id="235e2-117">That will prevent unintended use of your class with value types, and will enable you to use the `as` operator on `T`, and check for null values.</span></span>  
  
- <span data-ttu-id="235e2-118">Si separar el comportamiento genérico en clases base y subclases.</span><span class="sxs-lookup"><span data-stu-id="235e2-118">Whether to factor generic behavior into base classes and subclasses.</span></span>  
  
     <span data-ttu-id="235e2-119">Como las clases genéricas pueden servir como clases base, las mismas consideraciones de diseño se aplican aquí con clases no genéricas.</span><span class="sxs-lookup"><span data-stu-id="235e2-119">Because generic classes can serve as base classes, the same design considerations apply here as with non-generic classes.</span></span> <span data-ttu-id="235e2-120">Vea las reglas sobre cómo heredar de clases base genéricas posteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="235e2-120">See the rules about inheriting from generic base classes later in this topic.</span></span>  
  
- <span data-ttu-id="235e2-121">Si implementar una o más interfaces genéricas.</span><span class="sxs-lookup"><span data-stu-id="235e2-121">Whether to implement one or more generic interfaces.</span></span>  
  
     <span data-ttu-id="235e2-122">Por ejemplo, si está diseñando una clase que se usará para crear elementos en una colección basada en genéricos, puede que tenga que implementar una interfaz como <xref:System.IComparable%601> donde `T` es el tipo de su clase.</span><span class="sxs-lookup"><span data-stu-id="235e2-122">For example, if you are designing a class that will be used to create items in a generics-based collection, you may have to implement an interface such as <xref:System.IComparable%601> where `T` is the type of your class.</span></span>  
  
 <span data-ttu-id="235e2-123">Para obtener un ejemplo de una clase genérica simple, vea [Introducción a los genéricos](./index.md).</span><span class="sxs-lookup"><span data-stu-id="235e2-123">For an example of a simple generic class, see [Introduction to Generics](./index.md).</span></span>  
  
 <span data-ttu-id="235e2-124">Las reglas para los parámetros de tipo y las restricciones tienen varias implicaciones para el comportamiento de clase genérico, especialmente respecto a la herencia y a la accesibilidad de miembros.</span><span class="sxs-lookup"><span data-stu-id="235e2-124">The rules for type parameters and constraints have several implications for generic class behavior, especially regarding inheritance and member accessibility.</span></span> <span data-ttu-id="235e2-125">Antes de continuar, debe entender algunos términos.</span><span class="sxs-lookup"><span data-stu-id="235e2-125">Before proceeding, you should understand some terms.</span></span> <span data-ttu-id="235e2-126">Para una clase genérica `Node<T>,`, el código de cliente puede hacer referencia a la clase especificando un argumento de tipo, para crear un tipo construido cerrado (`Node<int>`).</span><span class="sxs-lookup"><span data-stu-id="235e2-126">For a generic class `Node<T>,` client code can reference the class either by specifying a type argument, to create a closed constructed type (`Node<int>`).</span></span> <span data-ttu-id="235e2-127">De manera alternativa, puede dejar el parámetro de tipo sin especificar, por ejemplo cuando especifica una clase base genérica, para crear un tipo construido abierto (`Node<T>`).</span><span class="sxs-lookup"><span data-stu-id="235e2-127">Alternatively, it can leave the type parameter unspecified, for example when you specify a generic base class, to create an open constructed type (`Node<T>`).</span></span> <span data-ttu-id="235e2-128">Las clases genéricas pueden heredar de determinadas clases base construidas abiertas o construidas cerradas:</span><span class="sxs-lookup"><span data-stu-id="235e2-128">Generic classes can inherit from concrete, closed constructed, or open constructed base classes:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#16)]  
  
 <span data-ttu-id="235e2-129">Las clases no genéricas, en otras palabras, concretas, pueden heredar de clases base construidas cerradas, pero no desde clases construidas abiertas ni desde parámetros de tipo porque no hay ninguna manera en tiempo de ejecución para que el código de cliente proporcione el argumento de tipo necesario para crear instancias de la clase base.</span><span class="sxs-lookup"><span data-stu-id="235e2-129">Non-generic, in other words, concrete, classes can inherit from closed constructed base classes, but not from open constructed classes or from type parameters because there is no way at run time for client code to supply the type argument required to instantiate the base class.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#17)]  
  
 <span data-ttu-id="235e2-130">Las clases genéricas que heredan de tipos construidos abiertos deben proporcionar argumentos de tipo para cualquier parámetro de tipo de clase base que no se comparta mediante la clase heredada, como se demuestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="235e2-130">Generic classes that inherit from open constructed types must supply type arguments for any base class type parameters that are not shared by the inheriting class, as demonstrated in the following code:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#18)]  
  
 <span data-ttu-id="235e2-131">Las clases genéricas que heredan de tipos construidos abiertos deben especificar restricciones que son un superconjunto de las restricciones del tipo base, o que las implican:</span><span class="sxs-lookup"><span data-stu-id="235e2-131">Generic classes that inherit from open constructed types must specify constraints that are a superset of, or imply, the constraints on the base type:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#19)]  
  
 <span data-ttu-id="235e2-132">Los tipos genéricos pueden usar varios parámetros de tipo y restricciones, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="235e2-132">Generic types can use multiple type parameters and constraints, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#20)]  
  
 <span data-ttu-id="235e2-133">Tipos construidos cerrados y construidos abiertos pueden usarse como parámetros de método:</span><span class="sxs-lookup"><span data-stu-id="235e2-133">Open constructed and closed constructed types can be used as method parameters:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#21)]  
  
 <span data-ttu-id="235e2-134">Si una clase genérica implementa una interfaz, todas las instancias de esa clase se pueden convertir en esa interfaz.</span><span class="sxs-lookup"><span data-stu-id="235e2-134">If a generic class implements an interface, all instances of that class can be cast to that interface.</span></span>  
  
 <span data-ttu-id="235e2-135">Las clases genéricas son invariables.</span><span class="sxs-lookup"><span data-stu-id="235e2-135">Generic classes are invariant.</span></span> <span data-ttu-id="235e2-136">En otras palabras, si un parámetro de entrada especifica un `List<BaseClass>`, obtendrá un error en tiempo de compilación si intenta proporcionar un `List<DerivedClass>`.</span><span class="sxs-lookup"><span data-stu-id="235e2-136">In other words, if an input parameter specifies a `List<BaseClass>`, you will get a compile-time error if you try to provide a `List<DerivedClass>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="235e2-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="235e2-137">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="235e2-138">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="235e2-138">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="235e2-139">Genéricos</span><span class="sxs-lookup"><span data-stu-id="235e2-139">Generics</span></span>](./index.md)
- [<span data-ttu-id="235e2-140">Guardar el estado de los enumeradores</span><span class="sxs-lookup"><span data-stu-id="235e2-140">Saving the State of Enumerators</span></span>](/archive/blogs/wesdyer/saving-the-state-of-enumerators)
- [<span data-ttu-id="235e2-141">Un puzle de herencia, parte uno</span><span class="sxs-lookup"><span data-stu-id="235e2-141">An Inheritance Puzzle, Part One</span></span>](/archive/blogs/ericlippert/an-inheritance-puzzle-part-one)
