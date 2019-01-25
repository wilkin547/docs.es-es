---
title: Diseño de constructores
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- default constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
author: KrzysztofCwalina
ms.openlocfilehash: 68192e3b75a120c73b82c34005d4dee650540bf3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722174"
---
# <a name="constructor-design"></a><span data-ttu-id="263cc-102">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="263cc-102">Constructor Design</span></span>
<span data-ttu-id="263cc-103">Hay dos tipos de constructores: escriba los constructores y los constructores de instancia.</span><span class="sxs-lookup"><span data-stu-id="263cc-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="263cc-104">Constructores de tipos son estáticos y se ejecutan en el CLR antes de utilizar el tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="263cc-105">Constructores de instancias se ejecutan cuando se crea una instancia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="263cc-106">Constructores de tipos no toman ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="263cc-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="263cc-107">Constructores de instancias pueden.</span><span class="sxs-lookup"><span data-stu-id="263cc-107">Instance constructors can.</span></span> <span data-ttu-id="263cc-108">Constructores de instancias que no toman ningún parámetro se denominan a menudo los constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="263cc-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="263cc-109">Los constructores son la forma más natural para crear instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="263cc-110">La mayoría de los desarrolladores buscará y pruebe a utilizar un constructor antes de que consideran modos alternativos de creación de instancias (por ejemplo, los métodos de fábrica).</span><span class="sxs-lookup"><span data-stu-id="263cc-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="263cc-111">**✓ CONSIDER** proporcionar simple, lo ideal es que el valor predeterminado, constructores.</span><span class="sxs-lookup"><span data-stu-id="263cc-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="263cc-112">Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son tipos primitivos o enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="263cc-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="263cc-113">Estos constructores simple aumentan la usabilidad de framework.</span><span class="sxs-lookup"><span data-stu-id="263cc-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="263cc-114">**✓ CONSIDER** mediante un método de generador estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si no parece natural siguiendo las directrices de diseño del constructor.</span><span class="sxs-lookup"><span data-stu-id="263cc-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="263cc-115">**✓ DO** usar los parámetros de constructor como accesos directos para establecer las propiedades principales.</span><span class="sxs-lookup"><span data-stu-id="263cc-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="263cc-116">No debería haber ninguna diferencia semántica entre mediante el constructor vacío seguido de algunos conjuntos de propiedades y utilizando un constructor con varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="263cc-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="263cc-117">**✓ DO** utilizar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="263cc-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="263cc-118">La única diferencia entre estos parámetros y las propiedades debe ser las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="263cc-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="263cc-119">**✓ DO** un trabajo mínimo en el constructor.</span><span class="sxs-lookup"><span data-stu-id="263cc-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="263cc-120">Los constructores no deben hacer mucho trabajo que no sea la captura de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="263cc-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="263cc-121">El costo de cualquier otro procesamiento debe retrasarse hasta que es necesario.</span><span class="sxs-lookup"><span data-stu-id="263cc-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="263cc-122">**✓ DO** genere excepciones desde los constructores de instancia, si procede.</span><span class="sxs-lookup"><span data-stu-id="263cc-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="263cc-123">**✓ DO** declarar explícitamente el constructor predeterminado público en clases, si se requiere un constructor de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="263cc-124">Si no declara ningún constructor en un tipo explícitamente, muchos lenguajes (por ejemplo, C#) agregará automáticamente un constructor predeterminado público.</span><span class="sxs-lookup"><span data-stu-id="263cc-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="263cc-125">(Las clases abstractas obtención un constructor protegido).</span><span class="sxs-lookup"><span data-stu-id="263cc-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="263cc-126">Agregando un constructor con parámetros a una clase, impide que el compilador agregue el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="263cc-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="263cc-127">Esto hace que a menudo cambios accidentales.</span><span class="sxs-lookup"><span data-stu-id="263cc-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="263cc-128">**X AVOID** la definición explícita de constructores predeterminados en estructuras.</span><span class="sxs-lookup"><span data-stu-id="263cc-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="263cc-129">Esto acelera la creación de una matriz, porque si no se define el constructor predeterminado, no tiene que ejecutarse en todas las ranuras de la matriz.</span><span class="sxs-lookup"><span data-stu-id="263cc-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="263cc-130">Tenga en cuenta que muchos compiladores, incluidos C# no permite que las estructuras tienen constructores sin parámetros por este motivo.</span><span class="sxs-lookup"><span data-stu-id="263cc-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="263cc-131">**X AVOID** al llamar a los miembros virtuales en un objeto dentro de su constructor.</span><span class="sxs-lookup"><span data-stu-id="263cc-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="263cc-132">Una llamada a un miembro virtual hará que la invalidación más derivada que se llame, aunque el constructor del tipo más derivado no totalmente ejecutado todavía.</span><span class="sxs-lookup"><span data-stu-id="263cc-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="263cc-133">Instrucciones de Constructor de tipos</span><span class="sxs-lookup"><span data-stu-id="263cc-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="263cc-134">**✓ DO** hacer privado static (constructores).</span><span class="sxs-lookup"><span data-stu-id="263cc-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="263cc-135">Un constructor estático, que también se denomina un constructor de clase, se usa para inicializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="263cc-136">CLR llama al constructor estático antes de crea la primera instancia del tipo o se llama a los miembros estáticos en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="263cc-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="263cc-137">El usuario no tiene control sobre cuando se llama al constructor estático.</span><span class="sxs-lookup"><span data-stu-id="263cc-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="263cc-138">Si un constructor estático no es privado, se puede llamar mediante código distinto de CLR.</span><span class="sxs-lookup"><span data-stu-id="263cc-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="263cc-139">Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="263cc-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="263cc-140">El compilador de C# obliga a los constructores estáticos para ser privado.</span><span class="sxs-lookup"><span data-stu-id="263cc-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="263cc-141">**X DO NOT** genere excepciones desde constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="263cc-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="263cc-142">Si se produce una excepción desde un constructor de tipo, el tipo no es utilizable en el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="263cc-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="263cc-143">**✓ CONSIDER** inicializar campos estáticos en línea, en lugar de utilizar explícitamente constructores estáticos, como el tiempo de ejecución se puede optimizar el rendimiento de tipos que no tienen un constructor estático definido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="263cc-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="263cc-144">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="263cc-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="263cc-145">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="263cc-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="263cc-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="263cc-146">See also</span></span>

- [<span data-ttu-id="263cc-147">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="263cc-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="263cc-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="263cc-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
