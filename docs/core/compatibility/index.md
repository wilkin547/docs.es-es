---
title: 'Tipos de cambios importantes: .NET Core'
description: Obtenga más información sobre los esfuerzos de .NET Core por mantener la compatibilidad entre versiones de .NET para los desarrolladores, así como sobre los tipos de cambios que se consideran importantes.
ms.date: 06/10/2019
ms.openlocfilehash: a84468c0c0e04f367dc7e89ce806ac01b2b49b48
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740897"
---
# <a name="changes-that-affect-compatibility"></a><span data-ttu-id="cb3c1-103">Cambios que afectan a la compatibilidad</span><span class="sxs-lookup"><span data-stu-id="cb3c1-103">Changes that affect compatibility</span></span>

<span data-ttu-id="cb3c1-104">A lo largo de su historia, .NET ha intentado mantener un alto nivel de compatibilidad de versión a versión y a través de los sabores de .NET.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="cb3c1-105">Esto sigue siendo cierto para .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="cb3c1-106">Aunque .NET Core se puede considerar como una nueva tecnología que es independiente de .NET Framework, hay dos factores principales que limitan la capacidad de .NET Core para desviarse de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cb3c1-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="cb3c1-107">Un gran número de desarrolladores desarrollaron originalmente o continúan desarrollando aplicaciones .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="cb3c1-108">Esperan un comportamiento coherente en las implementaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="cb3c1-109">Los proyectos de bibliotecas .NET Standard permiten a los desarrolladores crear bibliotecas dirigidas a las API comunes compartidas por .NET Core y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="cb3c1-110">Los desarrolladores esperan que una biblioteca utilizada en una aplicación .NET Core se comporte de forma idéntica a la misma biblioteca utilizada en una aplicación .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="cb3c1-111">Junto con la compatibilidad entre las implementaciones de .NET, los desarrolladores esperan un alto nivel de compatibilidad entre las versiones .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="cb3c1-112">En particular, el código escrito para una versión anterior de .NET Core debería funcionar sin problemas en una versión posterior de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="cb3c1-113">De hecho, muchos desarrolladores esperan que las nuevas API que se encuentran en las versiones más recientes de .NET Core también sean compatibles con las versiones preliminares en las que se introdujeron dichas API.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="cb3c1-114">En este artículo se describen las categorías de cambios de compatibilidad (o cambios importantes) y la forma en que el equipo de .NET evalúa los cambios en cada una de estas categorías.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="cb3c1-115">Entender cómo el equipo de .NET aborda los posibles cambios importantes es particularmente útil para los desarrolladores que abren solicitudes de incorporación de cambios en el repositorio de GitHub [dotnet/runtime](https://github.com/dotnet/runtime) que tienen por objetivo modificar el comportamiento de las API existentes.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who open pull requests in the [dotnet/runtime](https://github.com/dotnet/runtime) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="cb3c1-116">Para una definición de las categorías de compatibilidad, como la compatibilidad binaria y la compatibilidad con versiones anteriores, consulte [Breaking change categories](categories.md) (Categorías de cambios importantes).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="cb3c1-117">En las secciones siguientes se describen las categorías de los cambios realizados en las API de .NET Core y su impacto sobre la compatibilidad de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="cb3c1-118">El icono ✔️ indica que se permite un determinado tipo de cambio, ❌ indica que no se permite y ❓ indica un cambio que puede permitirse o no.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="cb3c1-119">Los cambios en esta última categoría requieren un criterio y una evaluación de cuán predecible, obvio y coherente era el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-119">Changes in this last category require judgement and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="cb3c1-120">Además de servir como guía para evaluar los cambios en las bibliotecas .NET Core, los desarrolladores de bibliotecas también pueden utilizar estos criterios para evaluar los cambios en sus bibliotecas que tienen como objetivo varias implementaciones y versiones de .NET.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="cb3c1-121">Modificaciones en el contrato público</span><span class="sxs-lookup"><span data-stu-id="cb3c1-121">Modifications to the public contract</span></span>

<span data-ttu-id="cb3c1-122">Los cambios en esta categoría modifican el área expuesta pública de un tipo.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-122">Changes in this category modify the public surface area of a type.</span></span> <span data-ttu-id="cb3c1-123">No están permitidos la mayoría de los cambios en esta categoría ya que infringen la *compatibilidad con versiones anteriores* (la capacidad de una aplicación que se ha desarrollado con una versión anterior de una API para ejecutarse sin recompilación en una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="cb3c1-124">Tipos</span><span class="sxs-lookup"><span data-stu-id="cb3c1-124">Types</span></span>

- <span data-ttu-id="cb3c1-125">**✔️ Supresión de una implementación de interfaz de un tipo cuando la interfaz ya está implementada por un tipo base**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="cb3c1-126">**❓ Adición de una nueva implementación de interfaz a un tipo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="cb3c1-127">Este es un cambio aceptable porque no afecta negativamente a los clientes existentes.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="cb3c1-128">Cualquier cambio en el tipo debe funcionar dentro de los límites de los cambios aceptables definidos aquí para que la nueva implementación siga siendo aceptable.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="cb3c1-129">Es necesario extremar las precauciones cuando se agregan interfaces que afectan directamente a la capacidad de un diseñador o serializador para generar código o datos que no se pueden consumir a un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="cb3c1-130">Un ejemplo es la interfaz <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="cb3c1-131">**❓ Introducción a una nueva clase base**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="cb3c1-132">Un tipo puede introducirse en una jerarquía entre dos tipos existentes si no introduce nuevos miembros de tipo [abstract](../../csharp/language-reference/keywords/abstract.md) ni cambia la semántica o el comportamiento de los tipos existentes.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="cb3c1-133">Por ejemplo, en .NET Framework 2.0, la clase <xref:System.Data.Common.DbConnection> se ha convertido en una nueva clase base para <xref:System.Data.SqlClient.SqlConnection>, que anteriormente había derivado directamente de <xref:System.ComponentModel.Component>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="cb3c1-134">**✔️ Traslado de un tipo de un ensamblado a otro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="cb3c1-135">Tenga en cuenta que el ensamblado *anterior* debe estar marcado con <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> que indica el nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="cb3c1-136">**✔️ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo `readonly struct`**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="cb3c1-137">Tenga en cuenta que no se permite cambiar un tipo `readonly struct` a un tipo `struct`.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>

- <span data-ttu-id="cb3c1-138">**✔️ Adición de la palabra clave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo cuando hay ningún constructor *accesible* (público o protegido)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="cb3c1-139">**✔️ Expansión de la visibilidad de un tipo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="cb3c1-140">**❌ Cambio del espacio de nombres o del nombre de un tipo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="cb3c1-141">**❌ Cambio de nombre o eliminación de un tipo público**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="cb3c1-142">Esto interrumpe todo el código que utiliza el tipo cuyo nombre se ha cambiado o quitado.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="cb3c1-143">**❌ Cambio del tipo subyacente de una enumeración**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="cb3c1-144">Se trata de un cambio importante en tiempo de compilación y de comportamiento, así como de un cambio importante binario que puede hacer que los argumentos de atributos no se puedan analizar.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="cb3c1-145">**❌ Sellado de un tipo anteriormente no estaba sellado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="cb3c1-146">**❌ Adición de una interfaz al conjunto de tipos base de una interfaz**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="cb3c1-147">Si una interfaz implementa una interfaz que antes no se implementaba, todos los tipos que implementaron la versión original de la interfaz se interrumpen.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="cb3c1-148">**❓ Eliminación de una clase del conjunto de clases base o una interfaz desde el conjunto de interfaces implementadas**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="cb3c1-149">Hay una excepción a la regla para la eliminación de interfaces: puede agregar la implementación de una interfaz que se derive de la interfaz eliminada.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="cb3c1-150">Por ejemplo, puede quitar <xref:System.IDisposable> si el tipo o interfaz ahora implementa <xref:System.ComponentModel.IComponent>, que implementa <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="cb3c1-151">**❌ Cambio de un tipo `readonly struct` a un tipo [struct](../../csharp/language-reference/keywords/struct.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="cb3c1-152">Tenga en cuenta que se permite el cambio de un tipo `struct` a un tipo `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="cb3c1-153">**❌ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo `ref struct` y viceversa**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="cb3c1-154">**❌ Reducción de la visibilidad de un tipo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="cb3c1-155">Sin embargo, se permite aumentar la visibilidad de un tipo.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="cb3c1-156">Miembros</span><span class="sxs-lookup"><span data-stu-id="cb3c1-156">Members</span></span>

- <span data-ttu-id="cb3c1-157">**✔️ Expansión de la visibilidad de un miembro que no es [virtual](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="cb3c1-158">**✔️ Adición de un miembro de tipo abstract a un tipo público que no tiene ningún constructor *accesible* (público o protegido) o el tipo [sealed](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="cb3c1-159">Sin embargo, no se permite agregar un miembro de tipo abstract a un tipo que tenga constructores accesibles (públicos o protegidos) y que no sea `sealed`.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="cb3c1-160">**✔️ Restricción de la visibilidad de un miembro [protegido](../../csharp/language-reference/keywords/protected.md) cuando el tipo no tiene constructores accesibles (públicos o protegidos) o el tipo es [sellado](../../csharp/language-reference/keywords/sealed.md)** .</span><span class="sxs-lookup"><span data-stu-id="cb3c1-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="cb3c1-161">**✔️ Desplazamiento de un miembro a una clase superior en la jerarquía que el tipo del que fue eliminado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="cb3c1-162">**✔️ Adición o eliminación de una invalidación**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="cb3c1-163">Tenga en cuenta que la introducción de una invalidación puede hacer que los consumidores anteriores omitan la invalidación cuando llamen a la [base](../../csharp/language-reference/keywords/base.md).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="cb3c1-164">**✔️ Adición de un constructor a una clase, junto con un constructor sin parámetros si la clase no tenía previamente constructores**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-164">**✔️ Adding a constructor to a class, along with a parameterless constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="cb3c1-165">Sin embargo, no se permite agregar un constructor a una clase que antes no tenía constructores *sin* agregar el constructor sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-165">However, adding a constructor to a class that previously had no constructors *without* adding the parameterless constructor is not allowed.</span></span>

- <span data-ttu-id="cb3c1-166">**✔️ Cambio de un miembro de tipo [abstract](../../csharp/language-reference/keywords/abstract.md) a [virtual](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="cb3c1-167">**✔️ Cambio de un valor devuelto `ref readonly` a un `ref` (excepto para los métodos o interfaces virtuales)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="cb3c1-168">**✔️ Eliminación de [readonly](../../csharp/language-reference/keywords/readonly.md) desde un campo, a menos que el tipo estático del campo es un tipo de valor mutable**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="cb3c1-169">**✔️ Llamada a un nuevo evento que no se ha definido anteriormente**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="cb3c1-170">**❓ Adición de un nuevo campo de instancia a un tipo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="cb3c1-171">Este cambio afecta a la serialización.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-171">This change impacts serialization.</span></span>

- <span data-ttu-id="cb3c1-172">**❌ Cambio de nombre o eliminación de un miembro o parámetro público**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="cb3c1-173">Esto interrumpe todo el código que utiliza el miembro o parámetro cuyo nombre se ha cambiado o quitado.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="cb3c1-174">Tenga en cuenta que esto incluye el cambio de nombre o eliminación de un captador o establecedor de una propiedad, así como el cambio de nombre o eliminación de los miembros de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="cb3c1-175">**❌ Adición de un miembro a una interfaz**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="cb3c1-176">**❌ Cambio del valor de un miembro constante o de enumeración público**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="cb3c1-177">**❌ Cambio del tipo de una propiedad, campo, parámetro o valor devuelto**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="cb3c1-178">**❌ Adición, eliminación o cambio del orden de los parámetros**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="cb3c1-179">**❌ Adición o eliminación de la palabra clave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) en un parámetro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="cb3c1-180">**❌ Cambio de nombre de un parámetro (incluido el cambio de mayúsculas y minúsculas)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="cb3c1-181">Esto se considera importante por dos motivos:</span><span class="sxs-lookup"><span data-stu-id="cb3c1-181">This is considered breaking for two reasons:</span></span>

  - <span data-ttu-id="cb3c1-182">Interrumpe los escenarios de enlace en tiempo de ejecución, como la característica de enlace en tiempo de ejecución en Visual Basic y [dinámica](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) en C#.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) in C#.</span></span>

  - <span data-ttu-id="cb3c1-183">Interrumpe la [compatibilidad del origen](categories.md#source-compatibility) cuando los desarrolladores utilizan los [argumentos con nombre](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="cb3c1-184">**❌ Cambio de un valor `ref` devuelto a un valor `ref readonly` devuelto**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="cb3c1-185">**❌ Cambio de un valor `ref readonly` devuelto a un valor `ref` en una interfaz o método virtual**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="cb3c1-186">**❌ Adición o eliminación del tipo [abstract](../../csharp/language-reference/keywords/abstract.md) de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="cb3c1-187">**❌ Eliminación de la palabra clave [virtual](../../csharp/language-reference/keywords/virtual.md) de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="cb3c1-188">Aunque esto a menudo no es un cambio importante porque el compilador de C# tiende a emitir las instrucciones de lenguaje intermedio (IL) [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) para llamar a métodos no virtuales (`callvirt` realiza una comprobación nula, mientras que una llamada normal no lo hace), este comportamiento no es invariable por varias razones:</span><span class="sxs-lookup"><span data-stu-id="cb3c1-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="cb3c1-189">C# no es el único lenguaje al que se dirige .NET.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-189">C# is not the only language that .NET targets.</span></span>

  - <span data-ttu-id="cb3c1-190">El compilador de C# intenta cada vez más optimizar `callvirt` para una llamada normal cuando el método de destino no es virtual y probablemente no es nulo (como un método al que se accede a través del operador de propagación nula [?](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>

  <span data-ttu-id="cb3c1-191">Convertir un método en virtual significa que el código del consumidor a menudo acabaría llamándolo no virtual.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="cb3c1-192">**❌ Adición de la palabra clave [virtual](../../csharp/language-reference/keywords/virtual.md) a un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="cb3c1-193">**❌ Conversión de un miembro virtual en tipo abstract**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="cb3c1-194">Un [miembro virtual](../../csharp/language-reference/keywords/virtual.md) proporciona una implementación del método que *se puede* reemplazar por una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="cb3c1-195">Un [miembro abstract](../../csharp/language-reference/keywords/abstract.md) no proporciona ninguna implementación y *debe ser* reemplazado.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="cb3c1-196">**❌ Adición de un miembro de tipo abstract a un tipo público que tiene constructores accesibles (públicos o protegidos) y que no es de tipo [sealed](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="cb3c1-197">**❌ Adición y eliminación de la palabra clave [static](../../csharp/language-reference/keywords/static.md) de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="cb3c1-198">**❌ Adición de una sobrecarga que impide una sobrecarga existente y define un comportamiento diferente**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="cb3c1-199">Esto interrumpe a los clientes existentes que se enlazaron a la sobrecarga anterior.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="cb3c1-200">Por ejemplo, si una clase tiene una versión única de un método que acepta un <xref:System.UInt32>, un consumidor existente se enlazará correctamente a esa sobrecarga al pasar un valor <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="cb3c1-201">Sin embargo, si agrega una sobrecarga que acepte un <xref:System.Int32>, al volver a compilar o utilizar la característica de enlace en tiempo de ejecución, el compilador se enlaza ahora a la nueva sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="cb3c1-202">Si se produce un comportamiento diferente, se trata de un cambio importante.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="cb3c1-203">**❌ Adición de un constructor a una clase que antes no tenía constructores sin agregar el constructor sin parámetros**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-203">**❌ Adding a constructor to a class that previously had no constructor without adding the parameterless constructor**</span></span>

- <span data-ttu-id="cb3c1-204">**❌ Adición de [readonly](../../csharp/language-reference/keywords/readonly.md) a un campo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="cb3c1-205">**❌ Reducción de la visibilidad de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="cb3c1-206">Esto incluye la reducción de la visibilidad de un miembro [protegido](../../csharp/language-reference/keywords/protected.md) cuando hay constructores *accesibles* (públicos o protegidos) y el tipo *no* es de tipo [sealed](../../csharp/language-reference/keywords/sealed.md).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="cb3c1-207">Si no es así, se permite reducir la visibilidad de un miembro protegido.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="cb3c1-208">Tenga en cuenta que se permite aumentar la visibilidad de un miembro.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="cb3c1-209">**❌ Cambio del tipo de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="cb3c1-210">El valor devuelto de un método o el tipo de propiedad o campo no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="cb3c1-211">Por ejemplo, la firma de un método que devuelve un <xref:System.Object> no se puede cambiar para devolver un <xref:System.String>, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="cb3c1-212">**❌ Adición de un campo a una estructura que previamente no tenía ningún estado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="cb3c1-213">Las reglas de asignación definidas permiten el uso de variables no inicializadas siempre que el tipo de variable sea una estructura sin estado.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="cb3c1-214">Si la estructura se realiza con estado, el código podría acabar con datos sin inicializar.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="cb3c1-215">Esto es a la vez una posible interrupción del origen y un cambio importante de archivo binario.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="cb3c1-216">**❌ Desencadenamiento de un evento existente que nunca se desencadenó antes**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="cb3c1-217">Cambios de comportamiento</span><span class="sxs-lookup"><span data-stu-id="cb3c1-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="cb3c1-218">Ensamblados</span><span class="sxs-lookup"><span data-stu-id="cb3c1-218">Assemblies</span></span>

- <span data-ttu-id="cb3c1-219">**✔️ Portabilidad de un ensamblado cuando se siguen admitiendo las mismas plataformas**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="cb3c1-220">**❌ Cambio de nombre de un ensamblado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="cb3c1-221">**❌ Cambio de la clave pública de un ensamblado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="cb3c1-222">Propiedades, campos, parámetros y valores devueltos</span><span class="sxs-lookup"><span data-stu-id="cb3c1-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="cb3c1-223">**✔️ Cambio del valor de una propiedad, un campo, un valor devuelto o del parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) a un tipo más derivado**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="cb3c1-224">Por ejemplo, un método que devuelve un tipo de <xref:System.Object> puede devolver una instancia de <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="cb3c1-225">(Sin embargo, no se puede cambiar la firma del método).</span><span class="sxs-lookup"><span data-stu-id="cb3c1-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="cb3c1-226">**✔️ Aumento del intervalo de valores aceptados para una propiedad o parámetro si el miembro no es [virtual](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="cb3c1-227">Tenga en cuenta que mientras que el rango de valores que se pueden pasar al método o que se devuelven por el miembro puede expandirse, el parámetro o tipo de miembro no pueden.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="cb3c1-228">Por ejemplo, mientras que los valores pasados a un método pueden expandirse de 0-124 a 0-255, el tipo de parámetro no puede cambiar de <xref:System.Byte> a <xref:System.Int32>.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="cb3c1-229">**❌ Aumento del intervalo de valores aceptados para una propiedad o parámetro si el miembro es [virtual](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="cb3c1-230">Este cambio interrumpe los miembros invalidados existentes, que no funcionarán correctamente para la gama extendida de valores.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="cb3c1-231">**❌ Disminución del intervalo de valores aceptados para una propiedad o parámetro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="cb3c1-232">**❌ Aumento del intervalo de valores devueltos para una propiedad, un campo, un valor devuelto o el parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="cb3c1-233">**❌ Cambio de los valores devueltos para una propiedad, un campo, un valor devuelto del método o el parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="cb3c1-234">**❌ Cambio del valor predeterminado de una propiedad, un campo o un parámetro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="cb3c1-235">**❌ Cambio de la precisión de un valor devuelto numérico**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="cb3c1-236">**❓ Un cambio en el análisis de la entrada y el inicio de nuevas excepciones (incluso si el comportamiento de análisis no está especificado en la documentación)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="cb3c1-237">Excepciones</span><span class="sxs-lookup"><span data-stu-id="cb3c1-237">Exceptions</span></span>

- <span data-ttu-id="cb3c1-238">**✔️ Inicio de una excepción más derivada que una excepción existente**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="cb3c1-239">Debido a que la nueva excepción es una subclase de una excepción existente, el código de tratamiento de excepciones anterior continúa controlando la excepción.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="cb3c1-240">Por ejemplo, en .NET Framework 4, los métodos de creación y recuperación de la referencia cultural comenzaron a iniciar un <xref:System.Globalization.CultureNotFoundException> en lugar de un <xref:System.ArgumentException> si no se podía encontrar la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="cb3c1-241">Dado que <xref:System.Globalization.CultureNotFoundException> procede de <xref:System.ArgumentException>, se trata de un cambio aceptable.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="cb3c1-242">**✔️ Inicio de una excepción más específica que <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="cb3c1-243">**✔️ Inicio de una excepción que se considera irrecuperable**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="cb3c1-244">Las excepciones irrecuperables no deben capturarse, sino que deben tratarse por un controlador general de alto nivel.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="cb3c1-245">Por lo tanto, no se espera que los usuarios tengan un código que capte estas excepciones explícitas.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="cb3c1-246">Las excepciones irrecuperables son:</span><span class="sxs-lookup"><span data-stu-id="cb3c1-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="cb3c1-247">**✔️ Inicio de una nueva excepción en una nueva ruta de acceso del código**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="cb3c1-248">La excepción debe aplicarse solo a una nueva ruta de acceso del código que se ejecute con nuevos valores o estados de parámetros, y que no se pueda ejecutar por código existente que apunte a la versión anterior.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="cb3c1-249">**✔️ Eliminación de una excepción para permitir un comportamiento más sólido o nuevos escenarios**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="cb3c1-250">Por ejemplo, un método `Divide` que anteriormente solo trataba valores positivos e iniciaba un <xref:System.ArgumentOutOfRangeException> de lo contrario, puede cambiarse para admitir tanto valores negativos como positivos sin iniciar una excepción.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="cb3c1-251">**✔️ Cambio del texto de un mensaje de error**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="cb3c1-252">Los desarrolladores no deben confiar en el texto de los mensajes de error, que también cambian en función de la referencia cultural del usuario.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="cb3c1-253">**❌ Inicio de una excepción en cualquier otro caso no enumerado anteriormente**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="cb3c1-254">**❌ Eliminación de una excepción en cualquier otro caso no enumerado anteriormente**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="cb3c1-255">Atributos</span><span class="sxs-lookup"><span data-stu-id="cb3c1-255">Attributes</span></span>

- <span data-ttu-id="cb3c1-256">**✔️ Cambio del valor de un atributo que *no* es observable**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="cb3c1-257">**❌ Cambio del valor de un atributo que *es* observable**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="cb3c1-258">**❓ Eliminación de un atributo**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="cb3c1-259">En la mayoría de los casos, la eliminación de un atributo (como <xref:System.NonSerializedAttribute>) es un cambio importante.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="cb3c1-260">Compatibilidad con la plataforma</span><span class="sxs-lookup"><span data-stu-id="cb3c1-260">Platform support</span></span>

- <span data-ttu-id="cb3c1-261">**✔️ Admisión de una operación en una plataforma que antes no era posible**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="cb3c1-262">**❌ No admitir o requerir ahora un Service Pack específico para una operación que antes estaba admitida en una plataforma.**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="cb3c1-263">Cambios de implementación internos</span><span class="sxs-lookup"><span data-stu-id="cb3c1-263">Internal implementation changes</span></span>

- <span data-ttu-id="cb3c1-264">**❓ Cambio del área expuesta de un tipo interno**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="cb3c1-265">Por lo general se permiten estos cambios, aunque interrumpan la reflexión privada.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="cb3c1-266">En algunos casos, cuando las bibliotecas populares de terceros o un gran número de desarrolladores dependen de las API internas, es posible que no se permitan dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="cb3c1-267">**❓ Cambio de la implementación interna de un miembro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="cb3c1-268">Por lo general se permiten estos cambios, aunque interrumpan la reflexión privada.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="cb3c1-269">En algunos casos, cuando el código del cliente depende con frecuencia de una reflexión privada o cuando el cambio introduce efectos secundarios no deseados, estos cambios pueden no estar permitidos.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="cb3c1-270">**✔️ Mejora del rendimiento de una operación**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="cb3c1-271">La capacidad de modificar el rendimiento de una operación es esencial, pero tales cambios pueden interrumpir el código que depende de la velocidad actual de una operación.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="cb3c1-272">Esto es particularmente cierto en el caso del código que depende de la sincronización de las operaciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="cb3c1-273">Tenga en cuenta que el cambio en el rendimiento no debería tener ningún efecto en otro comportamiento de la API en cuestión; de lo contrario, el cambio se considerará importante.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="cb3c1-274">**✔️ Modificación indirecta (y a menudo de forma adversa) del rendimiento de una operación**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="cb3c1-275">Si el cambio en cuestión no está clasificado como importante por algún otro motivo, esto es aceptable.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="cb3c1-276">A menudo, es necesario tomar medidas que pueden incluir operaciones adicionales o que agregan nueva funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="cb3c1-277">Esto casi siempre afectará al rendimiento, pero puede ser esencial para que la API en cuestión funcione como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="cb3c1-278">**❌ Cambio de una API sincrónica en asincrónica (y viceversa)**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="cb3c1-279">Cambios en el código</span><span class="sxs-lookup"><span data-stu-id="cb3c1-279">Code changes</span></span>

- <span data-ttu-id="cb3c1-280">**✔️ Adición de [params](../../csharp/language-reference/keywords/params.md) a un parámetro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="cb3c1-281">**❌ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo [class](../../csharp/language-reference/keywords/class.md) y viceversa**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="cb3c1-282">**❌ Adición de la palabra clave [checked](../../csharp/language-reference/keywords/virtual.md) a un bloque de código**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="cb3c1-283">Este cambio puede causar que el código que se ejecutó previamente inicie un <xref:System.OverflowException> y es inaceptable.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="cb3c1-284">**❌ Eliminación de [params](../../csharp/language-reference/keywords/params.md) de un parámetro**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="cb3c1-285">**❌ Cambio del orden en el que se desencadenan los eventos**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="cb3c1-286">Los desarrolladores pueden esperar razonablemente que los eventos se desencadenen en el mismo orden, y el código de desarrollador depende frecuentemente del orden en el que se desencadenen los eventos.</span><span class="sxs-lookup"><span data-stu-id="cb3c1-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="cb3c1-287">**❌ Eliminación del inicio de un evento en una acción determinada**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="cb3c1-288">**❌ Cambio del número de veces que se llaman los eventos dados**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="cb3c1-289">**❌ Adición de <xref:System.FlagsAttribute> a un tipo de enumeración**</span><span class="sxs-lookup"><span data-stu-id="cb3c1-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
