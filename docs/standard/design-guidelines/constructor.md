---
title: Diseño de constructores
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d7ca279dc1626cd526910af93326280bcd8301d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33575562"
---
# <a name="constructor-design"></a><span data-ttu-id="bd271-102">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="bd271-102">Constructor Design</span></span>
<span data-ttu-id="bd271-103">Hay dos tipos de constructores: escriba constructores y los constructores de instancia.</span><span class="sxs-lookup"><span data-stu-id="bd271-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>  
  
 <span data-ttu-id="bd271-104">Constructores de tipos son estáticos y se ejecutan mediante CLR antes de que se utiliza el tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="bd271-105">Constructores de instancias se ejecutan cuando se crea una instancia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-105">Instance constructors run when an instance of a type is created.</span></span>  
  
 <span data-ttu-id="bd271-106">Constructores de tipo no toman ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="bd271-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="bd271-107">Constructores de instancias pueden.</span><span class="sxs-lookup"><span data-stu-id="bd271-107">Instance constructors can.</span></span> <span data-ttu-id="bd271-108">Constructores de instancias que no toman ningún parámetro a menudo se denominan constructores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bd271-108">Instance constructors that don’t take any parameters are often called default constructors.</span></span>  
  
 <span data-ttu-id="bd271-109">Los constructores son la forma más natural para crear instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="bd271-110">Mayoría de los desarrolladores buscará y pruebe a utilizar un constructor antes de que consideren formas alternativas de creación de instancias (por ejemplo, los métodos de fábrica).</span><span class="sxs-lookup"><span data-stu-id="bd271-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>  
  
 <span data-ttu-id="bd271-111">**✓ Considere la posibilidad de** proporcionar simple, lo ideal es que el valor predeterminado, constructores.</span><span class="sxs-lookup"><span data-stu-id="bd271-111">**✓ CONSIDER** providing simple, ideally default, constructors.</span></span>  
  
 <span data-ttu-id="bd271-112">Un constructor simple tiene un número muy pequeño de parámetros y todos los parámetros son tipos primitivos o enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="bd271-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="bd271-113">Estos constructores simples aumentan la usabilidad de framework.</span><span class="sxs-lookup"><span data-stu-id="bd271-113">Such simple constructors increase usability of the framework.</span></span>  
  
 <span data-ttu-id="bd271-114">**✓ Considere la posibilidad de** mediante un método de generador estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si no parece natural siguiendo las directrices de diseño del constructor.</span><span class="sxs-lookup"><span data-stu-id="bd271-114">**✓ CONSIDER** using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>  
  
 <span data-ttu-id="bd271-115">**✓ HACER** usar los parámetros de constructor como accesos directos para establecer las propiedades principales.</span><span class="sxs-lookup"><span data-stu-id="bd271-115">**✓ DO** use constructor parameters as shortcuts for setting main properties.</span></span>  
  
 <span data-ttu-id="bd271-116">No debería haber ninguna diferencia semántica entre usando el constructor vacío seguido por algunos conjuntos de propiedades y utilizando un constructor con varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="bd271-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>  
  
 <span data-ttu-id="bd271-117">**✓ HACER** utilizar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="bd271-117">**✓ DO** use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>  
  
 <span data-ttu-id="bd271-118">La única diferencia entre estos parámetros y las propiedades debe ser las mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="bd271-118">The only difference between such parameters and the properties should be casing.</span></span>  
  
 <span data-ttu-id="bd271-119">**✓ HACER** un trabajo mínimo en el constructor.</span><span class="sxs-lookup"><span data-stu-id="bd271-119">**✓ DO** minimal work in the constructor.</span></span>  
  
 <span data-ttu-id="bd271-120">Constructores no deberían hacer mucho trabajo que no sea de captura de los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="bd271-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="bd271-121">El costo de cualquier otro procesamiento se debería retrasar hasta que requiere.</span><span class="sxs-lookup"><span data-stu-id="bd271-121">The cost of any other processing should be delayed until required.</span></span>  
  
 <span data-ttu-id="bd271-122">**✓ HACER** genere excepciones desde los constructores de instancia, si procede.</span><span class="sxs-lookup"><span data-stu-id="bd271-122">**✓ DO** throw exceptions from instance constructors, if appropriate.</span></span>  
  
 <span data-ttu-id="bd271-123">**✓ HACER** declarar explícitamente el constructor predeterminado público en clases, si se requiere un constructor de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-123">**✓ DO** explicitly declare the public default constructor in classes, if such a constructor is required.</span></span>  
  
 <span data-ttu-id="bd271-124">Si no se declara explícitamente ningún constructor en un tipo, muchos lenguajes (por ejemplo, C#) agregará automáticamente un constructor predeterminado público.</span><span class="sxs-lookup"><span data-stu-id="bd271-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public default constructor.</span></span> <span data-ttu-id="bd271-125">(Las clases abstractas obtener un constructor protegido).</span><span class="sxs-lookup"><span data-stu-id="bd271-125">(Abstract classes get a protected constructor.)</span></span>  
  
 <span data-ttu-id="bd271-126">Agregar un constructor con parámetros a una clase, impide que el compilador agregue el constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bd271-126">Adding a parameterized constructor to a class prevents the compiler from adding the default constructor.</span></span> <span data-ttu-id="bd271-127">Esto hace que a menudo cambios accidentales.</span><span class="sxs-lookup"><span data-stu-id="bd271-127">This often causes accidental breaking changes.</span></span>  
  
 <span data-ttu-id="bd271-128">**X evitar** la definición explícita de constructores predeterminados en estructuras.</span><span class="sxs-lookup"><span data-stu-id="bd271-128">**X AVOID** explicitly defining default constructors on structs.</span></span>  
  
 <span data-ttu-id="bd271-129">Esto acelera la creación de una matriz, porque si no se define el constructor predeterminado, no tiene que ejecutarse en todas las ranuras de la matriz.</span><span class="sxs-lookup"><span data-stu-id="bd271-129">This makes array creation faster, because if the default constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="bd271-130">Tenga en cuenta que muchos compiladores, incluyendo C#, no permiten las estructuras que tienen constructores sin parámetros por esta razón.</span><span class="sxs-lookup"><span data-stu-id="bd271-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>  
  
 <span data-ttu-id="bd271-131">**X evitar** al llamar a los miembros virtuales en un objeto dentro de su constructor.</span><span class="sxs-lookup"><span data-stu-id="bd271-131">**X AVOID** calling virtual members on an object inside its constructor.</span></span>  
  
 <span data-ttu-id="bd271-132">Llamar a un miembro virtual hará que la invalidación más derivada llamarlo, incluso si el constructor del tipo más derivado no ha sido totalmente ejecutado todavía.</span><span class="sxs-lookup"><span data-stu-id="bd271-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>  
  
### <a name="type-constructor-guidelines"></a><span data-ttu-id="bd271-133">Directrices de Constructor de tipo</span><span class="sxs-lookup"><span data-stu-id="bd271-133">Type Constructor Guidelines</span></span>  
 <span data-ttu-id="bd271-134">**✓ HACER** hacer privado static (constructores).</span><span class="sxs-lookup"><span data-stu-id="bd271-134">**✓ DO** make static constructors private.</span></span>  
  
 <span data-ttu-id="bd271-135">Un constructor estático, que también se denomina un constructor de clase, se utiliza para inicializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="bd271-136">CLR llama al constructor estático antes de crear la primera instancia del tipo o se llama a cualquier miembro estático en ese tipo.</span><span class="sxs-lookup"><span data-stu-id="bd271-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="bd271-137">El usuario no tiene ningún control sobre cuándo se llama al constructor estático.</span><span class="sxs-lookup"><span data-stu-id="bd271-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="bd271-138">Si un constructor estático no es privado, se puede llamar mediante código que no sea de CLR.</span><span class="sxs-lookup"><span data-stu-id="bd271-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="bd271-139">Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="bd271-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="bd271-140">El compilador de C# fuerza constructores estáticos a ser privado.</span><span class="sxs-lookup"><span data-stu-id="bd271-140">The C# compiler forces static constructors to be private.</span></span>  
  
 <span data-ttu-id="bd271-141">**X DO NOT** genere excepciones desde constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="bd271-141">**X DO NOT** throw exceptions from static constructors.</span></span>  
  
 <span data-ttu-id="bd271-142">Si se produce una excepción desde un constructor de tipo, el tipo no es utilizable en el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="bd271-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>  
  
 <span data-ttu-id="bd271-143">**Considere la posibilidad de ✓** inicializar campos estáticos en línea, en lugar de utilizar explícitamente constructores estáticos, como el tiempo de ejecución se puede optimizar el rendimiento de tipos que no tienen un constructor estático definido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="bd271-143">**✓ CONSIDER** initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>  
  
 <span data-ttu-id="bd271-144">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="bd271-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="bd271-145">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="bd271-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd271-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="bd271-146">See Also</span></span>  
 [<span data-ttu-id="bd271-147">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="bd271-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="bd271-148">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="bd271-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
