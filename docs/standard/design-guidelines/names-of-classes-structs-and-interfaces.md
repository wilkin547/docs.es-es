---
title: Nombres de clases, estructuras e interfaces
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: bcb3d1c636c8f846be8290738f322f36e09c9dad
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="names-of-classes-structs-and-interfaces"></a><span data-ttu-id="540b0-102">Nombres de clases, estructuras e interfaces</span><span class="sxs-lookup"><span data-stu-id="540b0-102">Names of Classes, Structs, and Interfaces</span></span>
<span data-ttu-id="540b0-103">Sigan las instrucciones de nomenclatura que se aplican a la nomenclatura de tipo general.</span><span class="sxs-lookup"><span data-stu-id="540b0-103">The naming guidelines that follow apply to general type naming.</span></span>  
  
 <span data-ttu-id="540b0-104">**✓ HACER** nombre clases y structs con sustantivos o frases con Pascal.</span><span class="sxs-lookup"><span data-stu-id="540b0-104">**✓ DO** name classes and structs with nouns or noun phrases, using PascalCasing.</span></span>  
  
 <span data-ttu-id="540b0-105">Esto permite distinguir los nombres de tipo de métodos, que se denominan con frases verbales.</span><span class="sxs-lookup"><span data-stu-id="540b0-105">This distinguishes type names from methods, which are named with verb phrases.</span></span>  
  
 <span data-ttu-id="540b0-106">**✓ HACER** nombres de las interfaces con frases adjetivo o, en ocasiones con sustantivos o sintagmas nominales.</span><span class="sxs-lookup"><span data-stu-id="540b0-106">**✓ DO** name interfaces with adjective phrases, or occasionally with nouns or noun phrases.</span></span>  
  
 <span data-ttu-id="540b0-107">Nombres y frases deben se usan con poca frecuencia y podrían indicar que el tipo debe ser una clase abstracta y no una interfaz.</span><span class="sxs-lookup"><span data-stu-id="540b0-107">Nouns and noun phrases should be used rarely and they might indicate that the type should be an abstract class, and not an interface.</span></span>  
  
 <span data-ttu-id="540b0-108">**X DO NOT** dar a los nombres de clase un prefijo (p. ej., "C").</span><span class="sxs-lookup"><span data-stu-id="540b0-108">**X DO NOT** give class names a prefix (e.g., "C").</span></span>  
  
 <span data-ttu-id="540b0-109">**✓ Considere la posibilidad de** finalizar los nombres de las clases derivadas con el nombre de la clase base.</span><span class="sxs-lookup"><span data-stu-id="540b0-109">**✓ CONSIDER** ending the name of derived classes with the name of the base class.</span></span>  
  
 <span data-ttu-id="540b0-110">Esto es muy legible y explica la relación claramente.</span><span class="sxs-lookup"><span data-stu-id="540b0-110">This is very readable and explains the relationship clearly.</span></span> <span data-ttu-id="540b0-111">Algunos ejemplos de esto en el código son: `ArgumentOutOfRangeException`, que es un tipo de `Exception`, y `SerializableAttribute`, que es un tipo de `Attribute`.</span><span class="sxs-lookup"><span data-stu-id="540b0-111">Some examples of this in code are: `ArgumentOutOfRangeException`, which is a kind of `Exception`, and `SerializableAttribute`, which is a kind of `Attribute`.</span></span> <span data-ttu-id="540b0-112">Sin embargo, es importante que use un criterio razonable para aplicar esta directriz; Por ejemplo, el `Button` clase es un tipo de `Control` eventos, aunque `Control` no aparece en su nombre.</span><span class="sxs-lookup"><span data-stu-id="540b0-112">However, it is important to use reasonable judgment in applying this guideline; for example, the `Button` class is a kind of `Control` event, although `Control` doesn’t appear in its name.</span></span>  
  
 <span data-ttu-id="540b0-113">**✓ HACER** prefijo los nombres de interfaz con la letra I, para indicar que el tipo es una interfaz.</span><span class="sxs-lookup"><span data-stu-id="540b0-113">**✓ DO** prefix interface names with the letter I, to indicate that the type is an interface.</span></span>  
  
 <span data-ttu-id="540b0-114">Por ejemplo, `IComponent` (sustantivo descriptivo), `ICustomAttributeProvider` (frase), y `IPersistable` (adjetivo) son nombres de interfaz adecuada.</span><span class="sxs-lookup"><span data-stu-id="540b0-114">For example, `IComponent` (descriptive noun), `ICustomAttributeProvider` (noun phrase), and `IPersistable` (adjective) are appropriate interface names.</span></span> <span data-ttu-id="540b0-115">Al igual que con otros nombres de tipo, evite las abreviaturas.</span><span class="sxs-lookup"><span data-stu-id="540b0-115">As with other type names, avoid abbreviations.</span></span>  
  
 <span data-ttu-id="540b0-116">**✓ HACER** Asegúrese de que los nombres difieren solo en la "I" prefijo en el nombre de la interfaz cuando se define un par de interfaz de clase: donde la clase es una implementación estándar de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="540b0-116">**✓ DO** ensure that the names differ only by the "I" prefix on the interface name when you are defining a class–interface pair where the class is a standard implementation of the interface.</span></span>  
  
## <a name="names-of-generic-type-parameters"></a><span data-ttu-id="540b0-117">Nombres de parámetros de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="540b0-117">Names of Generic Type Parameters</span></span>  
 <span data-ttu-id="540b0-118">Los tipos genéricos se agregaron a .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="540b0-118">Generics were added to .NET Framework 2.0.</span></span> <span data-ttu-id="540b0-119">La característica integra un nuevo tipo de identificador denominado *parámetro de tipo*.</span><span class="sxs-lookup"><span data-stu-id="540b0-119">The feature introduced a new kind of identifier called *type parameter*.</span></span>  
  
 <span data-ttu-id="540b0-120">**✓ HACER** el nombre de parámetros de tipo genérico con nombres descriptivos a menos que sea totalmente explicativa un nombre de letra única y un nombre descriptivo no agregue ningún valor.</span><span class="sxs-lookup"><span data-stu-id="540b0-120">**✓ DO** name generic type parameters with descriptive names unless a single-letter name is completely self-explanatory and a descriptive name would not add value.</span></span>  
  
 <span data-ttu-id="540b0-121">**✓ Considere la posibilidad de** utilizando `T` como el nombre del parámetro de tipo para los tipos con un parámetro de tipo de letra única.</span><span class="sxs-lookup"><span data-stu-id="540b0-121">**✓ CONSIDER** using `T` as the type parameter name for types with one single-letter type parameter.</span></span>  
  
```  
public int IComparer<T> { ... }  
public delegate bool Predicate<T>(T item);  
public struct Nullable<T> where T:struct { ... }  
```  
  
 <span data-ttu-id="540b0-122">**✓ HACER** prefijo de nombres de parámetros de tipo descriptivos con `T`.</span><span class="sxs-lookup"><span data-stu-id="540b0-122">**✓ DO** prefix descriptive type parameter names with `T`.</span></span>  
  
```  
public interface ISessionChannel<TSession> where TSession : ISession{  
    TSession Session { get; }  
}  
```  
  
 <span data-ttu-id="540b0-123">**✓ Considere la posibilidad de** que indica las restricciones de coloca en un parámetro de tipo en el nombre del parámetro.</span><span class="sxs-lookup"><span data-stu-id="540b0-123">**✓ CONSIDER** indicating constraints placed on a type parameter in the name of the parameter.</span></span>  
  
 <span data-ttu-id="540b0-124">Por ejemplo, un parámetro restringido a `ISession` podría denominarse `TSession`.</span><span class="sxs-lookup"><span data-stu-id="540b0-124">For example, a parameter constrained to `ISession` might be called `TSession`.</span></span>  
  
## <a name="names-of-common-types"></a><span data-ttu-id="540b0-125">Nombres de tipos comunes</span><span class="sxs-lookup"><span data-stu-id="540b0-125">Names of Common Types</span></span>  
 <span data-ttu-id="540b0-126">**✓ HACER** siga las directrices descritas en la tabla siguiente al asignar nombres a los tipos derivados de o implementar determinados tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="540b0-126">**✓ DO** follow the guidelines described in the following table when naming types derived from or implementing certain .NET Framework types.</span></span>  
  
|<span data-ttu-id="540b0-127">Tipo base</span><span class="sxs-lookup"><span data-stu-id="540b0-127">Base Type</span></span>|<span data-ttu-id="540b0-128">Instrucciones de tipo derivado de implementación</span><span class="sxs-lookup"><span data-stu-id="540b0-128">Derived/Implementing Type Guideline</span></span>|  
|---------------|------------------------------------------|  
|`System.Attribute`|<span data-ttu-id="540b0-129">**✓ HACER** agregar el sufijo "Attribute" a los nombres de clases de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="540b0-129">**✓ DO** add the suffix "Attribute" to names of custom attribute classes.</span></span>|  
|`System.Delegate`|<span data-ttu-id="540b0-130">**✓ HACER** agregar el sufijo "EventHandler" a los nombres de los delegados que se usan en los eventos.</span><span class="sxs-lookup"><span data-stu-id="540b0-130">**✓ DO** add the suffix "EventHandler" to names of delegates that are used in events.</span></span><br /><br /> <span data-ttu-id="540b0-131">**✓ HACER** agregar el sufijo "Callback" a los nombres de los delegados distintos de los utilizados como controladores de eventos.</span><span class="sxs-lookup"><span data-stu-id="540b0-131">**✓ DO** add the suffix "Callback" to names of delegates other than those used as event handlers.</span></span><br /><br /> <span data-ttu-id="540b0-132">**X DO NOT** agregar el sufijo "Delegate" a un delegado.</span><span class="sxs-lookup"><span data-stu-id="540b0-132">**X DO NOT** add the suffix "Delegate" to a delegate.</span></span>|  
|`System.EventArgs`|<span data-ttu-id="540b0-133">**✓ HACER** agregar el sufijo "EventArgs".</span><span class="sxs-lookup"><span data-stu-id="540b0-133">**✓ DO** add the suffix "EventArgs."</span></span>|  
|`System.Enum`|<span data-ttu-id="540b0-134">**X DO NOT** derivan de esta clase; use la palabra clave admitida por el lenguaje en su lugar; por ejemplo, en C#, utilice el `enum` palabra clave.</span><span class="sxs-lookup"><span data-stu-id="540b0-134">**X DO NOT** derive from this class; use the keyword supported by your language instead; for example, in C#, use the `enum` keyword.</span></span><br /><br /> <span data-ttu-id="540b0-135">**X DO NOT** agregar el sufijo "Enum" o "Flag".</span><span class="sxs-lookup"><span data-stu-id="540b0-135">**X DO NOT** add the suffix "Enum" or "Flag."</span></span>|  
|`System.Exception`|<span data-ttu-id="540b0-136">**✓ HACER** agregar el sufijo "Exception".</span><span class="sxs-lookup"><span data-stu-id="540b0-136">**✓ DO** add the suffix "Exception."</span></span>|  
|`IDictionary` <br /> `IDictionary<TKey,TValue>`|<span data-ttu-id="540b0-137">**✓ HACER** agregar el sufijo "Diccionario".</span><span class="sxs-lookup"><span data-stu-id="540b0-137">**✓ DO** add the suffix "Dictionary."</span></span> <span data-ttu-id="540b0-138">Tenga en cuenta que `IDictionary` es un tipo específico de la colección, pero esta instrucción tiene prioridad sobre la instrucción de colecciones más general que sigue.</span><span class="sxs-lookup"><span data-stu-id="540b0-138">Note that `IDictionary` is a specific type of collection, but this guideline takes precedence over the more general collections guideline that follows.</span></span>|  
|`IEnumerable` <br /> `ICollection` <br /> `IList` <br /> `IEnumerable<T>` <br /> `ICollection<T>` <br /> `IList<T>`|<span data-ttu-id="540b0-139">**✓ HACER** agregar el sufijo "Colección".</span><span class="sxs-lookup"><span data-stu-id="540b0-139">**✓ DO** add the suffix "Collection."</span></span>|  
|`System.IO.Stream`|<span data-ttu-id="540b0-140">**✓ HACER** agregar el sufijo "Stream".</span><span class="sxs-lookup"><span data-stu-id="540b0-140">**✓ DO** add the suffix "Stream."</span></span>|  
|`CodeAccessPermission IPermission`|<span data-ttu-id="540b0-141">**✓ HACER** agregar el sufijo "Permisos".</span><span class="sxs-lookup"><span data-stu-id="540b0-141">**✓ DO** add the suffix "Permission."</span></span>|  
  
## <a name="naming-enumerations"></a><span data-ttu-id="540b0-142">Enumeraciones de nomenclaturas</span><span class="sxs-lookup"><span data-stu-id="540b0-142">Naming Enumerations</span></span>  
 <span data-ttu-id="540b0-143">Nombres de tipos de enumeración (también denominados enumeraciones) por lo general deben seguir las reglas de nomenclatura de tipo estándares (Pascal, etcetera).</span><span class="sxs-lookup"><span data-stu-id="540b0-143">Names of enumeration types (also called enums) in general should follow the standard type-naming rules (PascalCasing, etc.).</span></span> <span data-ttu-id="540b0-144">Sin embargo, hay directrices adicionales que se aplican específicamente a las enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="540b0-144">However, there are additional guidelines that apply specifically to enums.</span></span>  
  
 <span data-ttu-id="540b0-145">**✓ HACER** utilizar un nombre de tipo singular para una enumeración a menos que sus valores son campos de bits.</span><span class="sxs-lookup"><span data-stu-id="540b0-145">**✓ DO** use a singular type name for an enumeration unless its values are bit fields.</span></span>  
  
 <span data-ttu-id="540b0-146">**✓ HACER** utilizar un nombre de tipo plural para una enumeración con los campos de bits como valores, también denominados enumeración de marcas.</span><span class="sxs-lookup"><span data-stu-id="540b0-146">**✓ DO** use a plural type name for an enumeration with bit fields as values, also called flags enum.</span></span>  
  
 <span data-ttu-id="540b0-147">**X DO NOT** utilice el sufijo "Enum" en los nombres de tipo de enumeración.</span><span class="sxs-lookup"><span data-stu-id="540b0-147">**X DO NOT** use an "Enum" suffix in enum type names.</span></span>  
  
 <span data-ttu-id="540b0-148">**X DO NOT** usar "Marca" o sufijos "Indicadores" en la enumeración de nombres de tipo.</span><span class="sxs-lookup"><span data-stu-id="540b0-148">**X DO NOT** use "Flag" or "Flags" suffixes in enum type names.</span></span>  
  
 <span data-ttu-id="540b0-149">**X DO NOT** utiliza un prefijo en los nombres de valor de enumeración (p. ej., "ad" para las enumeraciones de ADO.), "rtf" para las enumeraciones de texto enriquecido, etcetera.</span><span class="sxs-lookup"><span data-stu-id="540b0-149">**X DO NOT** use a prefix on enumeration value names (e.g., "ad" for ADO enums, "rtf" for rich text enums, etc.).</span></span>  
  
 <span data-ttu-id="540b0-150">*Partes © 2005, 2009 Microsoft Corporation. Reservados todos los derechos.*</span><span class="sxs-lookup"><span data-stu-id="540b0-150">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="540b0-151">*Volver a imprimir en el permiso de educación de Pearson, Inc. de [directrices de diseño de marco de trabajo: convenciones, expresiones y patrones para las bibliotecas .NET de reutilizable, 2ª edición](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina y Brad Abrams, publicado el 22 de octubre de 2008 por Addison-Wesley Professional como parte de la serie de desarrollo de Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="540b0-151">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="540b0-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="540b0-152">See Also</span></span>  
 [<span data-ttu-id="540b0-153">Instrucciones de diseño de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="540b0-153">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="540b0-154">Instrucciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="540b0-154">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
