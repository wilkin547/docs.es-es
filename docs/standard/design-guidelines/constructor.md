---
title: Diseño de constructores
ms.date: 10/22/2008
helpviewer_keywords:
- member design guidelines, constructors
- constructors, design guidelines
- instance constructors
- type constructors
- virtual members
- constructors, types
- parameterless constructors
- static constructors
ms.assetid: b4496afe-5fa7-4bb0-85ca-70b0ef21e6fc
ms.openlocfilehash: 27fb73aa01adf31117d1b82724873db3a03fd269
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821403"
---
# <a name="constructor-design"></a><span data-ttu-id="504b7-102">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="504b7-102">Constructor Design</span></span>

<span data-ttu-id="504b7-103">Hay dos tipos de constructores: constructores de tipo y constructores de instancia.</span><span class="sxs-lookup"><span data-stu-id="504b7-103">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="504b7-104">Los constructores de tipo son estáticos y los ejecuta CLR antes de que se use el tipo.</span><span class="sxs-lookup"><span data-stu-id="504b7-104">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="504b7-105">Los constructores de instancia se ejecutan cuando se crea una instancia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="504b7-105">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="504b7-106">Los constructores de tipo no pueden tomar ningún parámetro.</span><span class="sxs-lookup"><span data-stu-id="504b7-106">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="504b7-107">Los constructores de instancias pueden.</span><span class="sxs-lookup"><span data-stu-id="504b7-107">Instance constructors can.</span></span> <span data-ttu-id="504b7-108">Los constructores de instancias que no toman ningún parámetro se denominan a menudo constructores sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="504b7-108">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="504b7-109">Los constructores son la manera más natural de crear instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="504b7-109">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="504b7-110">La mayoría de los desarrolladores buscarán e intentarán usar un constructor antes de considerar formas alternativas de crear instancias (como métodos de generador).</span><span class="sxs-lookup"><span data-stu-id="504b7-110">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="504b7-111">✔️ considere la posibilidad de proporcionar constructores simples, idealesmente predeterminados.</span><span class="sxs-lookup"><span data-stu-id="504b7-111">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="504b7-112">Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son primitivos o enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="504b7-112">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="504b7-113">Estos constructores simples aumentan la facilidad de uso del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="504b7-113">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="504b7-114">✔️ considere la posibilidad de usar un Factory Method estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si las instrucciones de diseño del constructor no son naturales.</span><span class="sxs-lookup"><span data-stu-id="504b7-114">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="504b7-115">✔️ usar parámetros de constructor como métodos abreviados para establecer las propiedades principales.</span><span class="sxs-lookup"><span data-stu-id="504b7-115">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="504b7-116">No debe haber ninguna diferencia en la semántica entre el uso del constructor vacío seguido de algunos conjuntos de propiedades y el uso de un constructor con varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="504b7-116">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="504b7-117">✔️ usar el mismo nombre para los parámetros de constructor y una propiedad si los parámetros de constructor se utilizan para establecer simplemente la propiedad.</span><span class="sxs-lookup"><span data-stu-id="504b7-117">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="504b7-118">La única diferencia entre estos parámetros y las propiedades debe ser la grafía.</span><span class="sxs-lookup"><span data-stu-id="504b7-118">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="504b7-119">✔️ REALIZAR un trabajo mínimo en el constructor.</span><span class="sxs-lookup"><span data-stu-id="504b7-119">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="504b7-120">Los constructores no deben hacer mucho trabajo aparte de capturar los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="504b7-120">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="504b7-121">El costo de cualquier otro procesamiento debe retrasarse hasta que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="504b7-121">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="504b7-122">✔️ inician excepciones desde constructores de instancia, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="504b7-122">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="504b7-123">✔️ declaran explícitamente el constructor sin parámetros público en las clases, si se requiere este tipo de constructor.</span><span class="sxs-lookup"><span data-stu-id="504b7-123">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="504b7-124">Si no declara explícitamente ningún constructor en un tipo, muchos lenguajes (como C#) agregarán automáticamente un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="504b7-124">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="504b7-125">(Las clases abstractas obtienen un constructor protegido).</span><span class="sxs-lookup"><span data-stu-id="504b7-125">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="504b7-126">Agregar un constructor con parámetros a una clase impide que el compilador agregue el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="504b7-126">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="504b7-127">Esto suele provocar cambios bruscos accidentales.</span><span class="sxs-lookup"><span data-stu-id="504b7-127">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="504b7-128">❌ Evite definir explícitamente constructores sin parámetros en Structs.</span><span class="sxs-lookup"><span data-stu-id="504b7-128">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="504b7-129">Esto hace que la creación de matrices sea más rápida, ya que si no se define el constructor sin parámetros, no es necesario que se ejecute en cada ranura de la matriz.</span><span class="sxs-lookup"><span data-stu-id="504b7-129">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="504b7-130">Tenga en cuenta que muchos compiladores, incluido C#, no permiten que los Structs tengan constructores sin parámetros por esta razón.</span><span class="sxs-lookup"><span data-stu-id="504b7-130">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="504b7-131">❌ Evite llamar a miembros virtuales en un objeto dentro de su constructor.</span><span class="sxs-lookup"><span data-stu-id="504b7-131">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="504b7-132">La llamada a un miembro virtual hará que se llame a la invalidación más derivada, incluso si el constructor del tipo más derivado aún no se ha ejecutado completamente.</span><span class="sxs-lookup"><span data-stu-id="504b7-132">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="504b7-133">Instrucciones del constructor de tipos</span><span class="sxs-lookup"><span data-stu-id="504b7-133">Type Constructor Guidelines</span></span>

<span data-ttu-id="504b7-134">✔️ hacer que los constructores estáticos sean privados.</span><span class="sxs-lookup"><span data-stu-id="504b7-134">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="504b7-135">Un constructor estático, también denominado constructor de clase, se usa para inicializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="504b7-135">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="504b7-136">CLR llama al constructor estático antes de que se cree la primera instancia del tipo o se llame a cualquier miembro estático de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="504b7-136">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="504b7-137">El usuario no tiene control sobre cuándo se llama al constructor estático.</span><span class="sxs-lookup"><span data-stu-id="504b7-137">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="504b7-138">Si un constructor estático no es privado, se puede llamar mediante código que no sea CLR.</span><span class="sxs-lookup"><span data-stu-id="504b7-138">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="504b7-139">Dependiendo de las operaciones realizadas en el constructor, esto puede provocar un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="504b7-139">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="504b7-140">El compilador de C# obliga a los constructores estáticos a ser privados.</span><span class="sxs-lookup"><span data-stu-id="504b7-140">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="504b7-141">❌ NO genere excepciones desde constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="504b7-141">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="504b7-142">Si se produce una excepción desde un constructor de tipos, el tipo no se puede usar en el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="504b7-142">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="504b7-143">✔️ considere la posibilidad de inicializar campos estáticos en línea en lugar de usar explícitamente constructores estáticos, porque el tiempo de ejecución puede optimizar el rendimiento de los tipos que no tienen un constructor estático definido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="504b7-143">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="504b7-144">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="504b7-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="504b7-145">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="504b7-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="504b7-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="504b7-146">See also</span></span>

- [<span data-ttu-id="504b7-147">Instrucciones para el diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="504b7-147">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="504b7-148">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="504b7-148">Framework Design Guidelines</span></span>](index.md)
