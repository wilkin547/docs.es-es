---
title: Nombres de clases, estructuras e interfaces
description: Siga estas instrucciones para asignar nombres a clases, Structs e interfaces como parte de las instrucciones para diseñar bibliotecas que extienden e interactúan con las bibliotecas de .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- type names, guidelines
- classes [.NET Framework], names
- enumerations [.NET Framework], names
- names [.NET Framework], interfaces
- common type names
- names [.NET Framework], type names
- names [.NET Framework], classes
- interfaces [.NET Framework], names
- generic type parameters
ms.assetid: 87a4b0da-ed64-43b1-ac43-968576c444ce
ms.openlocfilehash: e7eee414c5bf5c69f63543ef240e50a4d2d948a3
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419088"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="1d731-103">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="1d731-103">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="1d731-104">Las instrucciones de nomenclatura que se indican a continuación se aplican a la nomenclatura general de tipos.</span><span class="sxs-lookup"><span data-stu-id="1d731-104">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="1d731-105">✔️ los nombres de las clases y los Structs con sustantivos o sintagmas nominales, mediante PascalCasing.</span><span class="sxs-lookup"><span data-stu-id="1d731-105">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="1d731-106">Esto distingue los nombres de tipo de los métodos, que se denominan con frases verbales.</span><span class="sxs-lookup"><span data-stu-id="1d731-106">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="1d731-107">✔️ las interfaces de nombre con frases adjetivales, o ocasionalmente, con sustantivos o sintagmas nominales.</span><span class="sxs-lookup"><span data-stu-id="1d731-107">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="1d731-108">Los nombres y frases deben usarse con poca frecuencia y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.</span><span class="sxs-lookup"><span data-stu-id="1d731-108">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="1d731-109">❌NO proporcione a los nombres de clase un prefijo (por ejemplo, "C").</span><span class="sxs-lookup"><span data-stu-id="1d731-109">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="1d731-110">✔️ considere la posibilidad de terminar el nombre de las clases derivadas con el nombre de la clase base.</span><span class="sxs-lookup"><span data-stu-id="1d731-110">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="1d731-111">Esto es muy legible y explica claramente la relación.</span><span class="sxs-lookup"><span data-stu-id="1d731-111">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="1d731-112">Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException` , que es un tipo de `Exception` , y `SerializableAttribute` , que es un tipo de `Attribute` .</span><span class="sxs-lookup"><span data-stu-id="1d731-112">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="1d731-113">Sin embargo, es importante utilizar una resolución razonable para aplicar esta directriz; por ejemplo, la `Button` clase es un tipo de `Control` evento, aunque `Control` no aparece en su nombre.</span><span class="sxs-lookup"><span data-stu-id="1d731-113">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="1d731-114">✔️ Prefije los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="1d731-114">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="1d731-115">Por ejemplo, `IComponent` (nombre descriptivo), `ICustomAttributeProvider` (frase) y `IPersistable` (adjetivo) son nombres de interfaz apropiados.</span><span class="sxs-lookup"><span data-stu-id="1d731-115">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="1d731-116">Como con otros nombres de tipo, evite las abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="1d731-116">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="1d731-117">✔️ asegurarse de que los nombres solo difieren en el prefijo "I" del nombre de la interfaz cuando se define un par clase-interfaz, donde la clase es una implementación estándar de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="1d731-117">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="1d731-118">Nombres de parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="1d731-118">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="1d731-119">Los genéricos se agregaron a .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="1d731-119">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="1d731-120">La característica presentó un nuevo tipo de identificador denominado *parámetro de tipo*.</span><span class="sxs-lookup"><span data-stu-id="1d731-120">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="1d731-121">✔️ los parámetros de tipo genérico de nombre con nombres descriptivos a menos que un nombre de una sola letra sea completamente descriptivo y un nombre descriptivo no agregue ningún valor.</span><span class="sxs-lookup"><span data-stu-id="1d731-121">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="1d731-122">✔️ CONSIDERE `T` la posibilidad de usar como nombre de parámetro de tipo para los tipos con un parámetro de tipo de una sola letra.</span><span class="sxs-lookup"><span data-stu-id="1d731-122">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="1d731-123">✔️ HACER prefijos para los nombres de parámetro de tipo descriptivo con `T` .</span><span class="sxs-lookup"><span data-stu-id="1d731-123">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="1d731-124">✔️ considere la posibilidad de indicar restricciones colocadas en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1d731-124">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="1d731-125">Por ejemplo, se podría llamar a un parámetro restringido a `ISession` `TSession` .</span><span class="sxs-lookup"><span data-stu-id="1d731-125">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="1d731-126">Nombres de tipos comunes</span><span class="sxs-lookup"><span data-stu-id="1d731-126">Names of Common Types</span></span>
 <span data-ttu-id="1d731-127">✔️ Siga las instrucciones que se describen en la tabla siguiente al asignar nombres a tipos derivados de o implementar determinados tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d731-127">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="1d731-128">Tipo base</span><span class="sxs-lookup"><span data-stu-id="1d731-128">Base Type</span></span>|<span data-ttu-id="1d731-129">Instrucciones de tipo derivada o de implementación</span><span class="sxs-lookup"><span data-stu-id="1d731-129">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="1d731-130">✔️ Agregue el sufijo "Attribute" a los nombres de las clases de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="1d731-130">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="1d731-131">✔️ Agregue el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.</span><span class="sxs-lookup"><span data-stu-id="1d731-131">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="1d731-132">✔️ Agregue el sufijo "callback" a los nombres de los delegados distintos de los que se usan como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="1d731-132">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="1d731-133">❌NO agregue el sufijo "Delegate" a un delegado.</span><span class="sxs-lookup"><span data-stu-id="1d731-133">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="1d731-134">✔️ Agregue el sufijo "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="1d731-134">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="1d731-135">❌NO derive de esta clase; Use en su lugar la palabra clave compatible con el lenguaje; por ejemplo, en C#, use la `enum` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1d731-135">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="1d731-136">❌NO agregue el sufijo "enum" o "flag".</span><span class="sxs-lookup"><span data-stu-id="1d731-136">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="1d731-137">✔️ Agregue el sufijo "Exception".</span><span class="sxs-lookup"><span data-stu-id="1d731-137">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="1d731-138">✔️ Agregue el sufijo "Dictionary".</span><span class="sxs-lookup"><span data-stu-id="1d731-138">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="1d731-139">Tenga en cuenta que `IDictionary` es un tipo específico de colección, pero esta directriz tiene prioridad sobre las instrucciones de colecciones más generales que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="1d731-139">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="1d731-140">✔️ agregar el sufijo "Collection".</span><span class="sxs-lookup"><span data-stu-id="1d731-140">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="1d731-141">✔️ agregar el sufijo "Stream".</span><span class="sxs-lookup"><span data-stu-id="1d731-141">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="1d731-142">✔️ agregar el sufijo "Permission".</span><span class="sxs-lookup"><span data-stu-id="1d731-142">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="1d731-143">Enumeración de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1d731-143">Naming Enumerations</span></span>
 <span data-ttu-id="1d731-144">Los nombres de los tipos de enumeración (también denominados enumeraciones) en general deben seguir las reglas estándar de nomenclatura de tipos (PascalCasing, etc.).</span><span class="sxs-lookup"><span data-stu-id="1d731-144">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="1d731-145">Sin embargo, hay instrucciones adicionales que se aplican específicamente a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="1d731-145">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="1d731-146">✔️ usar un nombre de tipo singular para una enumeración a menos que sus valores sean campos de bits.</span><span class="sxs-lookup"><span data-stu-id="1d731-146">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="1d731-147">✔️ usar un nombre de tipo plural para una enumeración con campos de bits como valores, también denominados enumeración Flags.</span><span class="sxs-lookup"><span data-stu-id="1d731-147">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="1d731-148">❌No use un sufijo "enum" en los nombres de tipo enum.</span><span class="sxs-lookup"><span data-stu-id="1d731-148">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="1d731-149">❌No utilice los sufijos "flag" o "flags" en los nombres de tipo enum.</span><span class="sxs-lookup"><span data-stu-id="1d731-149">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="1d731-150">❌No use un prefijo en los nombres de los valores de enumeración (por ejemplo, "ad" en las enumeraciones de ADO, "rtf" para las enumeraciones de texto enriquecido, etc.).</span><span class="sxs-lookup"><span data-stu-id="1d731-150">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="1d731-151">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1d731-151">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1d731-152">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1d731-152">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1d731-153">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1d731-153">See also</span></span>

- [<span data-ttu-id="1d731-154">Directrices de diseño de marco</span><span class="sxs-lookup"><span data-stu-id="1d731-154">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="1d731-155">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1d731-155">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
