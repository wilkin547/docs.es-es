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
author: KrzysztofCwalina
ms.openlocfilehash: c0790cd20daf859ec81e2252dc9bce46673daf90
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54621830"
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="e3d9a-102">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="e3d9a-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="e3d9a-103">Sigan las instrucciones de nomenclatura se aplican a los nombres de tipo general.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="e3d9a-104">**✓ DO** nombre clases y structs con sustantivos o frases con Pascal.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="e3d9a-105">Esto distingue los nombres de tipo de métodos, que se denominan con frases de verbo.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="e3d9a-106">**✓ DO** nombres de las interfaces con frases adjetivo o, en ocasiones con sustantivos o sintagmas nominales.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="e3d9a-107">Nombres y frases se deben usar con poca frecuencia y podrían indicar que el tipo debe ser una clase abstracta y no una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="e3d9a-108">**X DO NOT** dar a los nombres de clase un prefijo (p. ej., "C").</span><span class="sxs-lookup"><span data-stu-id="e3d9a-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="e3d9a-109">**✓ CONSIDER** finalizar los nombres de las clases derivadas con el nombre de la clase base.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="e3d9a-110">Esto es muy legible y explica claramente la relación.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="e3d9a-111">Algunos ejemplos de este código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception`, y `SerializableAttribute`, que es un tipo de `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="e3d9a-112">Sin embargo, es importante utilizar la lógica en la aplicación de esta instrucción; Por ejemplo, el `Button` clase es un tipo de `Control` evento, aunque `Control` no aparece en su nombre.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="e3d9a-113">**✓ DO** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="e3d9a-114">Por ejemplo, `IComponent` (sustantivo descriptivo), `ICustomAttributeProvider` (frase), y `IPersistable` (adjetivo) son nombres de interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="e3d9a-115">Al igual que con otros nombres de tipo, evite las abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="e3d9a-116">**✓ DO** Asegúrese de que los nombres difieren solo en la "I" prefijo en el nombre de la interfaz cuando se define un par de interfaz de clase: donde la clase es una implementación estándar de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="e3d9a-117">Nombres de parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="e3d9a-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="e3d9a-118">Los genéricos se agregaron a .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="e3d9a-119">La característica introdujo un nuevo tipo de identificador denominada *parámetro de tipo*.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="e3d9a-120">**✓ DO** el nombre de parámetros de tipo genérico con nombres descriptivos a menos que sea totalmente explicativa un nombre de letra única y un nombre descriptivo no agregue ningún valor.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="e3d9a-121">**✓ CONSIDER** utilizando `T` como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de letra única.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="e3d9a-122">**✓ DO** prefijo de nombres de parámetros de tipo descriptivos con `T`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession {  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="e3d9a-123">**✓ CONSIDER** que indica las restricciones de coloca en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="e3d9a-124">Por ejemplo, un parámetro restringido a `ISession` podría denominarse `TSession`.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="e3d9a-125">Nombres de tipos comunes</span><span class="sxs-lookup"><span data-stu-id="e3d9a-125">Names of Common Types</span></span>  
 <span data-ttu-id="e3d9a-126">**✓ DO** siga las directrices descritas en la tabla siguiente al asignar nombres a los tipos derivados de o implementar determinados tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="e3d9a-127">Tipo base</span><span class="sxs-lookup"><span data-stu-id="e3d9a-127">Base Type</span></span>|<span data-ttu-id="e3d9a-128">Directriz de tipo derivado y la implementación</span><span class="sxs-lookup"><span data-stu-id="e3d9a-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="e3d9a-129">**✓ DO** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="e3d9a-130">**✓ DO** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="e3d9a-131">**✓ DO** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="e3d9a-132">**X DO NOT** agregar el sufijo "Delegate" a un delegado.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="e3d9a-133">**✓ DO** agregar el sufijo "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="e3d9a-134">**X DO NOT** derivan de esta clase; use la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C#, utilice el `enum` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="e3d9a-135">**X DO NOT** agregar el sufijo "Enum" o "Flag".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="e3d9a-136">**✓ DO** agregar el sufijo "Exception".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="e3d9a-137">**✓ DO** agregar el sufijo "Diccionario".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="e3d9a-138">Tenga en cuenta que `IDictionary` es un tipo específico de la colección, pero esta directriz tiene prioridad sobre la instrucción de colecciones más general que sigue.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="e3d9a-139">**✓ DO** agregar el sufijo "Colección".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="e3d9a-140">**✓ DO** agregar el sufijo "Stream".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="e3d9a-141">**✓ DO** agregar el sufijo "Permisos".</span><span class="sxs-lookup"><span data-stu-id="e3d9a-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="e3d9a-142">Enumeraciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e3d9a-142">Naming Enumerations</span></span>  
 <span data-ttu-id="e3d9a-143">En general, nombres de tipos de enumeración (también denominados enumeraciones) deben seguir las reglas de nomenclatura de tipo estándar (Pascal, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="e3d9a-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="e3d9a-144">Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="e3d9a-145">**✓ DO** utilizar un nombre de tipo singular para una enumeración a menos que sus valores son campos de bits.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="e3d9a-146">**✓ DO** utilizar un nombre de tipo plural para una enumeración con los campos de bits como valores, también denominados enumeración de marcas.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="e3d9a-147">**X DO NOT** utilice el sufijo "Enum" en los nombres de tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="e3d9a-148">**X DO NOT** usar "Marca" o sufijos "Indicadores" en la enumeración de nombres de tipo.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="e3d9a-149">**X DO NOT** utiliza un prefijo en los nombres de valor de enumeración (p. ej., "ad" para las enumeraciones de ADO.), "rtf" para las enumeraciones de texto enriquecido, etcetera.</span><span class="sxs-lookup"><span data-stu-id="e3d9a-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="e3d9a-150">*Portions © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="e3d9a-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="e3d9a-151">*Reimpreso con permiso de Pearson Education, Inc. de [instrucciones de diseño de Framework: Convenciones, expresiones y patrones para bibliotecas reutilizables. NET, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicada el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="e3d9a-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3d9a-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3d9a-152">See also</span></span>

- [<span data-ttu-id="e3d9a-153">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="e3d9a-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="e3d9a-154">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="e3d9a-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
