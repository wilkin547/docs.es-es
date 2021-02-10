---
description: 'Más información acerca de: Diseño de constructores'
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
ms.openlocfilehash: 2a5c85e1dea3349f897c24fa5d40d73c6e1f9d7f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99642323"
---
# <a name="constructor-design"></a><span data-ttu-id="786dc-103">Diseño de constructores</span><span class="sxs-lookup"><span data-stu-id="786dc-103">Constructor Design</span></span>

<span data-ttu-id="786dc-104">Hay dos tipos de constructores: constructores de tipo y constructores de instancia.</span><span class="sxs-lookup"><span data-stu-id="786dc-104">There are two kinds of constructors: type constructors and instance constructors.</span></span>

<span data-ttu-id="786dc-105">Los constructores de tipo son estáticos y los ejecuta CLR antes de que se use el tipo.</span><span class="sxs-lookup"><span data-stu-id="786dc-105">Type constructors are static and are run by the CLR before the type is used.</span></span> <span data-ttu-id="786dc-106">Los constructores de instancias se ejecutan cuando se crea una instancia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="786dc-106">Instance constructors run when an instance of a type is created.</span></span>

<span data-ttu-id="786dc-107">Los constructores de tipo no pueden tomar ningún parámetro,</span><span class="sxs-lookup"><span data-stu-id="786dc-107">Type constructors cannot take any parameters.</span></span> <span data-ttu-id="786dc-108">pero los constructores de instancias sí que pueden hacerlo.</span><span class="sxs-lookup"><span data-stu-id="786dc-108">Instance constructors can.</span></span> <span data-ttu-id="786dc-109">Los constructores de instancias que no toman ningún parámetro se suelen denominar "constructores sin parámetros".</span><span class="sxs-lookup"><span data-stu-id="786dc-109">Instance constructors that don’t take any parameters are often called parameterless constructors.</span></span>

<span data-ttu-id="786dc-110">Los constructores son la manera más natural de crear instancias de un tipo.</span><span class="sxs-lookup"><span data-stu-id="786dc-110">Constructors are the most natural way to create instances of a type.</span></span> <span data-ttu-id="786dc-111">La mayoría de los desarrolladores buscarán e intentarán usar un constructor antes de plantearse usar formas alternativas de crear instancias (por ejemplo, Factory Method).</span><span class="sxs-lookup"><span data-stu-id="786dc-111">Most developers will search and try to use a constructor before they consider alternative ways of creating instances (such as factory methods).</span></span>

<span data-ttu-id="786dc-112">✔️ Recomendamos proporcionar constructores simples, idealmente de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="786dc-112">✔️ CONSIDER providing simple, ideally default, constructors.</span></span>

<span data-ttu-id="786dc-113">Un constructor simple tiene un número muy pequeño de parámetros, y todos los parámetros son primitivos o enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="786dc-113">A simple constructor has a very small number of parameters, and all parameters are primitives or enums.</span></span> <span data-ttu-id="786dc-114">Estos constructores simples aumentan la facilidad de uso del marco.</span><span class="sxs-lookup"><span data-stu-id="786dc-114">Such simple constructors increase usability of the framework.</span></span>

<span data-ttu-id="786dc-115">✔️ Recomendamos usar un método Factory Method estático en lugar de un constructor si la semántica de la operación deseada no se asigna directamente a la construcción de una nueva instancia, o si las instrucciones de diseño de constructores no son naturales.</span><span class="sxs-lookup"><span data-stu-id="786dc-115">✔️ CONSIDER using a static factory method instead of a constructor if the semantics of the desired operation do not map directly to the construction of a new instance, or if following the constructor design guidelines feels unnatural.</span></span>

<span data-ttu-id="786dc-116">✔️ Use parámetros de constructor como accesos directos para establecer las propiedades principales.</span><span class="sxs-lookup"><span data-stu-id="786dc-116">✔️ DO use constructor parameters as shortcuts for setting main properties.</span></span>

<span data-ttu-id="786dc-117">En la semántica no debería haber ninguna diferencia entre el uso del constructor vacío seguido de algunos conjuntos de propiedades y el uso de un constructor con varios argumentos.</span><span class="sxs-lookup"><span data-stu-id="786dc-117">There should be no difference in semantics between using the empty constructor followed by some property sets and using a constructor with multiple arguments.</span></span>

<span data-ttu-id="786dc-118">✔️ Use el mismo nombre para los parámetros del constructor y una propiedad si los parámetros del constructor se utilizan simplemente para establecer la propiedad.</span><span class="sxs-lookup"><span data-stu-id="786dc-118">✔️ DO use the same name for constructor parameters and a property if the constructor parameters are used to simply set the property.</span></span>

<span data-ttu-id="786dc-119">La única diferencia entre estos parámetros y las propiedades debe ser el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="786dc-119">The only difference between such parameters and the properties should be casing.</span></span>

<span data-ttu-id="786dc-120">✔️ Realice un trabajo mínimo en el constructor.</span><span class="sxs-lookup"><span data-stu-id="786dc-120">✔️ DO minimal work in the constructor.</span></span>

<span data-ttu-id="786dc-121">Los constructores no deberían hacer mucho más que capturar los parámetros del constructor.</span><span class="sxs-lookup"><span data-stu-id="786dc-121">Constructors should not do much work other than capture the constructor parameters.</span></span> <span data-ttu-id="786dc-122">El costo de cualquier otro procesamiento debe retrasarse hasta que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="786dc-122">The cost of any other processing should be delayed until required.</span></span>

<span data-ttu-id="786dc-123">✔️ Genere excepciones desde constructores de instancias, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="786dc-123">✔️ DO throw exceptions from instance constructors, if appropriate.</span></span>

<span data-ttu-id="786dc-124">✔️ Declare explícitamente el constructor sin parámetros público en las clases, si se requiere este tipo de constructor.</span><span class="sxs-lookup"><span data-stu-id="786dc-124">✔️ DO explicitly declare the public parameterless constructor in classes, if such a constructor is required.</span></span>

<span data-ttu-id="786dc-125">Si no declara explícitamente ningún constructor en un tipo, muchos lenguajes (como C# ) agregarán automáticamente un constructor sin parámetros público.</span><span class="sxs-lookup"><span data-stu-id="786dc-125">If you don’t explicitly declare any constructors on a type, many languages (such as C#) will automatically add a public parameterless constructor.</span></span> <span data-ttu-id="786dc-126">Las clases abstractas obtienen un constructor protegido.</span><span class="sxs-lookup"><span data-stu-id="786dc-126">(Abstract classes get a protected constructor.)</span></span>

<span data-ttu-id="786dc-127">Al agregar un constructor con parámetros a una clase, se impide que el compilador agregue el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="786dc-127">Adding a parameterized constructor to a class prevents the compiler from adding the parameterless constructor.</span></span> <span data-ttu-id="786dc-128">Esto suele provocar cambios importantes de forma accidental.</span><span class="sxs-lookup"><span data-stu-id="786dc-128">This often causes accidental breaking changes.</span></span>

<span data-ttu-id="786dc-129">❌ EVITE definir explícitamente constructores sin parámetros en estructuras.</span><span class="sxs-lookup"><span data-stu-id="786dc-129">❌ AVOID explicitly defining parameterless constructors on structs.</span></span>

<span data-ttu-id="786dc-130">Gracias a esto, la creación de matrices es más rápida, ya que si no se define el constructor sin parámetros, no es necesario que se ejecute en cada ranura de la matriz.</span><span class="sxs-lookup"><span data-stu-id="786dc-130">This makes array creation faster, because if the parameterless constructor is not defined, it does not have to be run on every slot in the array.</span></span> <span data-ttu-id="786dc-131">Tenga en cuenta que muchos compiladores, incluido C#, no permiten que las estructuras tengan constructores sin parámetros por esta razón.</span><span class="sxs-lookup"><span data-stu-id="786dc-131">Note that many compilers, including C#, don’t allow structs to have parameterless constructors for this reason.</span></span>

<span data-ttu-id="786dc-132">❌ EVITE llamar a miembros virtuales en un objeto dentro de su constructor.</span><span class="sxs-lookup"><span data-stu-id="786dc-132">❌ AVOID calling virtual members on an object inside its constructor.</span></span>

<span data-ttu-id="786dc-133">Al llamar a un miembro virtual, se provocará que se llame a la invalidación más derivada, incluso si el constructor del tipo más derivado aún no se ha ejecutado completamente.</span><span class="sxs-lookup"><span data-stu-id="786dc-133">Calling a virtual member will cause the most derived override to be called, even if the constructor of the most derived type has not been fully run yet.</span></span>

## <a name="type-constructor-guidelines"></a><span data-ttu-id="786dc-134">Instrucciones de constructores de tipo</span><span class="sxs-lookup"><span data-stu-id="786dc-134">Type Constructor Guidelines</span></span>

<span data-ttu-id="786dc-135">✔️ Haga que los constructores estáticos sean privados.</span><span class="sxs-lookup"><span data-stu-id="786dc-135">✔️ DO make static constructors private.</span></span>

<span data-ttu-id="786dc-136">Un constructor estático, también denominado "constructor de clase", se usa para inicializar un tipo.</span><span class="sxs-lookup"><span data-stu-id="786dc-136">A static constructor, also called a class constructor, is used to initialize a type.</span></span> <span data-ttu-id="786dc-137">CLR llama al constructor estático antes de crear la primera instancia del tipo o antes de llamar a cualquier miembro estático.</span><span class="sxs-lookup"><span data-stu-id="786dc-137">The CLR calls the static constructor before the first instance of the type is created or any static members on that type are called.</span></span> <span data-ttu-id="786dc-138">El usuario no tiene control sobre cuándo se llama al constructor estático.</span><span class="sxs-lookup"><span data-stu-id="786dc-138">The user has no control over when the static constructor is called.</span></span> <span data-ttu-id="786dc-139">Si un constructor estático no es privado, se puede llamar a través de un código distinto del de CLR.</span><span class="sxs-lookup"><span data-stu-id="786dc-139">If a static constructor is not private, it can be called by code other than the CLR.</span></span> <span data-ttu-id="786dc-140">En función de las operaciones que se realizan en el constructor, esto puede producir un comportamiento inesperado.</span><span class="sxs-lookup"><span data-stu-id="786dc-140">Depending on the operations performed in the constructor, this can cause unexpected behavior.</span></span> <span data-ttu-id="786dc-141">El compilador de C# fuerza a los constructores estáticos a que sean privados.</span><span class="sxs-lookup"><span data-stu-id="786dc-141">The C# compiler forces static constructors to be private.</span></span>

<span data-ttu-id="786dc-142">❌ NO genere excepciones desde constructores estáticos.</span><span class="sxs-lookup"><span data-stu-id="786dc-142">❌ DO NOT throw exceptions from static constructors.</span></span>

<span data-ttu-id="786dc-143">Si se inicia una excepción desde un constructor de tipo, el tipo no se podrá usar en el dominio de aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="786dc-143">If an exception is thrown from a type constructor, the type is not usable in the current application domain.</span></span>

<span data-ttu-id="786dc-144">✔️ Recomendamos inicializar campos estáticos en línea en lugar de usar explícitamente constructores estáticos, porque el runtime puede optimizar el rendimiento de los tipos que no tienen un constructor estático definido explícitamente.</span><span class="sxs-lookup"><span data-stu-id="786dc-144">✔️ CONSIDER initializing static fields inline rather than explicitly using static constructors, because the runtime is able to optimize the performance of types that don’t have an explicitly defined static constructor.</span></span>

<span data-ttu-id="786dc-145">*Portions © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="786dc-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="786dc-146">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="786dc-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="786dc-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="786dc-147">See also</span></span>

- [<span data-ttu-id="786dc-148">Instrucciones de diseño de miembros</span><span class="sxs-lookup"><span data-stu-id="786dc-148">Member Design Guidelines</span></span>](member.md)
- [<span data-ttu-id="786dc-149">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="786dc-149">Framework Design Guidelines</span></span>](index.md)
