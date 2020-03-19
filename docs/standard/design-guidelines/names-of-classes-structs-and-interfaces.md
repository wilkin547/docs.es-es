---
title: Nombres de clases, estructuras e interfaces
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
ms.openlocfilehash: 2c528348c0e84037a80df9797c56f03b51c73adc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401242"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="1a6c5-102">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="1a6c5-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="1a6c5-103">Las directrices de nomenclatura siguientes se aplican a la nomenclatura de tipos generales.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-103">The naming guidelines that follow apply to general type naming.</span></span>

 <span data-ttu-id="1a6c5-104">✔️ DO nombra clases y estructuras con sustantivos o frases de sustantivo, utilizando PascalCasing.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-104">✔️ DO name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>

 <span data-ttu-id="1a6c5-105">Esto distingue los nombres de tipo de los métodos, que se nombran con frases verbales.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>

 <span data-ttu-id="1a6c5-106">✔️ el nombre DO interactúa con frases adjetivas, o ocasionalmente con sustantivos o frases de sustantivo.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-106">✔️ DO name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>

 <span data-ttu-id="1a6c5-107">Los sustantivos y las frases de sustantivos se deben usar raramente y pueden indicar que el tipo debe ser una clase abstracta y no una interfaz.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>

 <span data-ttu-id="1a6c5-108">❌NO asigne a los nombres de clase un prefijo (por ejemplo, "C").</span><span class="sxs-lookup"><span data-stu-id="1a6c5-108">❌ DO NOT give class names a prefix (e.g., "C").</span></span>

 <span data-ttu-id="1a6c5-109">✔️ CONSIDER termina el nombre de las clases derivadas con el nombre de la clase base.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-109">✔️ CONSIDER ending the name of derived classes with the name of the base class.</span></span>

 <span data-ttu-id="1a6c5-110">Esto es muy legible y explica la relación claramente.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="1a6c5-111">Algunos ejemplos de esto `ArgumentOutOfRangeException`en el código `Exception`son: `SerializableAttribute`, que es `Attribute`una especie de , y , que es una especie de .</span><span class="sxs-lookup"><span data-stu-id="1a6c5-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="1a6c5-112">Sin embargo, es importante utilizar un juicio razonable al aplicar esta directriz; por ejemplo, `Button` la clase `Control` es un `Control` tipo de evento, aunque no aparece en su nombre.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>

 <span data-ttu-id="1a6c5-113">✔️ nombres de interfaz de prefijo DO con la letra I, para indicar que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-113">✔️ DO prefix interface names with the letter I, to indicate that the type is an interface.</span></span>

 <span data-ttu-id="1a6c5-114">Por ejemplo, `IComponent` (nombre `ICustomAttributeProvider` descriptivo), (frase `IPersistable` de sustantivo) y (adjetivo) son nombres de interfaz adecuados.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="1a6c5-115">Al igual que con otros nombres de tipo, evite las abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-115">As with other type names, avoid abbreviations.</span></span>

 <span data-ttu-id="1a6c5-116">✔️ do asegurarse de que los nombres difieren sólo por el prefijo "I" en el nombre de la interfaz cuando se define un par clase-interfaz donde la clase es una implementación estándar de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-116">✔️ DO ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>

## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="1a6c5-117">Nombres de parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="1a6c5-117">Names of Generic Type Parameters</span></span>
 <span data-ttu-id="1a6c5-118">Los genéricos se agregaron a .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="1a6c5-119">La característica introdujo un nuevo tipo de identificador llamado *parámetro de tipo*.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>

 <span data-ttu-id="1a6c5-120">✔️ DO nombra parámetros de tipo genérico con nombres descriptivos a menos que un nombre de una sola letra sea completamente autoexplicativo y un nombre descriptivo no agregaría valor.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-120">✔️ DO name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>

 <span data-ttu-id="1a6c5-121">✔️ considerar `T` como nombre de parámetro de tipo para tipos con un parámetro de tipo de letra única.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-121">✔️ CONSIDER using `T` as the type parameter name for types with one single-letter type parameter.</span></span>

```csharp
public int IComparer<T> { ... }
public delegate bool Predicate<T>(T item);
public struct Nullable<T> where T:struct { ... }
```

 <span data-ttu-id="1a6c5-122">✔️ nombres de parámetro `T`de tipo descriptivo de prefijo DO con .</span><span class="sxs-lookup"><span data-stu-id="1a6c5-122">✔️ DO prefix descriptive type parameter names with `T`.</span></span>

```csharp
public interface ISessionChannel<TSession> where TSession : ISession {
    TSession Session { get; }
}
```

 <span data-ttu-id="1a6c5-123">✔️ CONSIDERA que indica las restricciones colocadas en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-123">✔️ CONSIDER indicating constraints placed on a type parameter in the name of the parameter.</span></span>

 <span data-ttu-id="1a6c5-124">Por ejemplo, un parámetro `ISession` restringido `TSession`a podría llamarse .</span><span class="sxs-lookup"><span data-stu-id="1a6c5-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>

## <a name="names-of-common-types"></a><span data-ttu-id="1a6c5-125">Nombres de tipos comunes</span><span class="sxs-lookup"><span data-stu-id="1a6c5-125">Names of Common Types</span></span>
 <span data-ttu-id="1a6c5-126">✔️ siguen las instrucciones que se describen en la tabla siguiente al asignar nombres a los tipos derivados o implementar determinados tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-126">✔️ DO follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>

|<span data-ttu-id="1a6c5-127">Tipo base</span><span class="sxs-lookup"><span data-stu-id="1a6c5-127">Base Type</span></span>|<span data-ttu-id="1a6c5-128">Guía de tipos derivados/de implementación</span><span class="sxs-lookup"><span data-stu-id="1a6c5-128">Derived/Implementing Type Guideline</span></span>|
|---------------|------------------------------------------|
|`System.Attribute`|<span data-ttu-id="1a6c5-129">✔️ , agregue el sufijo "Attribute" a los nombres de las clases de atributo personalizadas.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-129">✔️ DO add the suffix "Attribute" to names of custom attribute classes.</span></span>|
|`System.Delegate`|<span data-ttu-id="1a6c5-130">✔️ DO agregue el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-130">✔️ DO add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="1a6c5-131">✔️ , agregue el sufijo "Callback" a los nombres de delegados distintos de los utilizados como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-131">✔️ DO add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="1a6c5-132">❌NO agregue el sufijo "Delegate" a un delegado.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-132">❌ DO NOT add the suffix "Delegate" to a delegate.</span></span>|
|`System.EventArgs`|<span data-ttu-id="1a6c5-133">✔️ , agregue el sufijo "EventArgs."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-133">✔️ DO add the suffix "EventArgs."</span></span>|
|`System.Enum`|<span data-ttu-id="1a6c5-134">❌NO derive de esta clase; utilizar la palabra clave admitida por su idioma en su lugar; por ejemplo, en C-, utilice la `enum` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-134">❌ DO NOT derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="1a6c5-135">❌NO agregue el sufijo "Enum" o "Flag."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-135">❌ DO NOT add the suffix "Enum" or "Flag."</span></span>|
|`System.Exception`|<span data-ttu-id="1a6c5-136">✔️ no agregue el sufijo "Exception."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-136">✔️ DO add the suffix "Exception."</span></span>|
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="1a6c5-137">✔️ no agregue el sufijo "Dictionary."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-137">✔️ DO add the suffix "Dictionary."</span></span> <span data-ttu-id="1a6c5-138">Tenga `IDictionary` en cuenta que es un tipo específico de colección, pero esta directriz tiene prioridad sobre la directriz de colecciones más general que sigue.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="1a6c5-139">✔️, agregue el sufijo "Collection."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-139">✔️ DO add the suffix "Collection."</span></span>|
|`System.IO.Stream`|<span data-ttu-id="1a6c5-140">✔️ , agregue el sufijo "Stream."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-140">✔️ DO add the suffix "Stream."</span></span>|
|`CodeAccessPermission IPermission`|<span data-ttu-id="1a6c5-141">✔️ no agregue el sufijo "Permiso."</span><span class="sxs-lookup"><span data-stu-id="1a6c5-141">✔️ DO add the suffix "Permission."</span></span>|

## <a name="naming-enumerations"></a><span data-ttu-id="1a6c5-142">Nombrar enumeraciones</span><span class="sxs-lookup"><span data-stu-id="1a6c5-142">Naming Enumerations</span></span>
 <span data-ttu-id="1a6c5-143">Los nombres de los tipos de enumeración (también denominados enumeraciones) en general deben seguir las reglas de nomenclatura de tipos estándar (PascalCasing, etc.).</span><span class="sxs-lookup"><span data-stu-id="1a6c5-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="1a6c5-144">Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-144">However, there are additional guidelines that apply specifically to enums.</span></span>

 <span data-ttu-id="1a6c5-145">✔️ DO usan un nombre de tipo singular para una enumeración a menos que sus valores sean campos de bits.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-145">✔️ DO use a singular type name for an enumeration unless its values are bit fields.</span></span>

 <span data-ttu-id="1a6c5-146">✔️ DO usa un nombre de tipo plural para una enumeración con campos de bits como valores, también denominados flags enum.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-146">✔️ DO use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>

 <span data-ttu-id="1a6c5-147">❌NO utilice un sufijo "Enum" en los nombres de tipo enum.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-147">❌ DO NOT use an "Enum" suffix in enum type names.</span></span>

 <span data-ttu-id="1a6c5-148">❌NO utilice sufijos "Flag" o "Flags" en los nombres de tipo enum.</span><span class="sxs-lookup"><span data-stu-id="1a6c5-148">❌ DO NOT use "Flag" or "Flags" suffixes in enum type names.</span></span>

 <span data-ttu-id="1a6c5-149">❌NO utilice un prefijo en los nombres de valores de enumeración (por ejemplo, "ad" para enumeraciones de ADO, "rtf" para enumeraciones de texto enriquecido, etc.).</span><span class="sxs-lookup"><span data-stu-id="1a6c5-149">❌ DO NOT use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>

 <span data-ttu-id="1a6c5-150">*Partes © 2005, 2009 Microsoft Corporation. Todos los derechos reservados.*</span><span class="sxs-lookup"><span data-stu-id="1a6c5-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="1a6c5-151">*Material reimpreso con el consentimiento de Pearson Education, Inc. y extraído de [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) (Instrucciones de diseño de .NET Framework: convenciones, expresiones y patrones para bibliotecas .NET reutilizables, 2.ª edición), de Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie Microsoft Windows Development.*</span><span class="sxs-lookup"><span data-stu-id="1a6c5-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="1a6c5-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1a6c5-152">See also</span></span>

- [<span data-ttu-id="1a6c5-153">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="1a6c5-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="1a6c5-154">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="1a6c5-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
