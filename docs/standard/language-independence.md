---
title: Independencia del lenguaje y componentes independientes del lenguaje
description: Obtenga información sobre cómo puede desarrollar en uno de los muchos lenguajes admitidos en .NET, como C#, C++/CLI, F#, IronPython, VB, Visual COBOL y PowerShell.
ms.date: 07/22/2016
dev_langs:
- csharp
- vb
ms.technology: dotnet-standard
ms.assetid: 2dbed1bc-86f5-43cd-9a57-adbb1c5efba4
ms.openlocfilehash: f04ff902743c91147a6f056bca3292ee47952bbd
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420557"
---
# <a name="language-independence-and-language-independent-components"></a><span data-ttu-id="ff274-103">Independencia del lenguaje y componentes independientes del lenguaje</span><span class="sxs-lookup"><span data-stu-id="ff274-103">Language independence and language-independent components</span></span>

<span data-ttu-id="ff274-104">.NET es independiente del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-104">.NET is language independent.</span></span> <span data-ttu-id="ff274-105">Esto significa que, como desarrollador, puede desarrollar en uno de los muchos lenguajes que tienen como destino las implementaciones de .NET, como C#, F# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ff274-105">This means that, as a developer, you can develop in one of the many languages that target .NET implementations, such as C#, F#, and Visual Basic.</span></span> <span data-ttu-id="ff274-106">Puede tener acceso a los tipos y miembros de bibliotecas de clases desarrollados para implementaciones de .NET sin tener que conocer el lenguaje en el que se escribieron originalmente y sin tener que seguir las convenciones del lenguaje original.</span><span class="sxs-lookup"><span data-stu-id="ff274-106">You can access the types and members of class libraries developed for .NET implementations without having to know the language in which they were originally written and without having to follow any of the original language's conventions.</span></span> <span data-ttu-id="ff274-107">Si es un desarrollador de componentes, puede tener acceso al componente desde cualquier aplicación .NET independientemente de su lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-107">If you are a component developer, your component can be accessed by any .NET app regardless of its language.</span></span>

> [!NOTE]
> <span data-ttu-id="ff274-108">La primera parte de este artículo describe la creación de componentes independientes del lenguaje; es decir, los componentes que pueden usarse en aplicaciones escritas en cualquier lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-108">This first part of this article discusses creating language-independent components - that is, components that can be consumed by apps that are written in any language.</span></span> <span data-ttu-id="ff274-109">También puede crear una aplicación o componente únicos de código fuente escrito en varios lenguajes; consulte [Interoperabilidad entre lenguajes](#cross-language-interoperability) en la segunda parte de este artículo.</span><span class="sxs-lookup"><span data-stu-id="ff274-109">You can also create a single component or app from source code written in multiple languages; see [Cross-Language Interoperability](#cross-language-interoperability) in the second part of this article.</span></span>

<span data-ttu-id="ff274-110">Para que los objetos puedan tener una interacción total con otros objetos escritos en cualquier lenguaje, estos objetos solo deben exponer a los llamadores las características que son comunes a todos los lenguajes.</span><span class="sxs-lookup"><span data-stu-id="ff274-110">To fully interact with other objects written in any language, objects must expose to callers only those features that are common to all languages.</span></span> <span data-ttu-id="ff274-111">Este conjunto común de características se define mediante Common Language Specification (CLS), que es un conjunto de reglas que se aplican a los ensamblados generados.</span><span class="sxs-lookup"><span data-stu-id="ff274-111">This common set of features is defined by the Common Language Specification (CLS), which is a set of rules that apply to generated assemblies.</span></span> <span data-ttu-id="ff274-112">Common Language Specification se define en el apartado I, cláusulas 7 a 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ff274-112">The Common Language Specification is defined in Partition I, Clauses 7 through 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

<span data-ttu-id="ff274-113">Si el componente se ajusta a Common Language Specification, existe la garantía de que será conforme a CLS y que será accesible desde el código de un ensamblado escrito en cualquier lenguaje de programación que admita CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-113">If your component conforms to the Common Language Specification, it is guaranteed to be CLS-compliant and can be accessed from code in assemblies written in any programming language that supports the CLS.</span></span> <span data-ttu-id="ff274-114">Para determinar si el componente se ajusta o no a Common Language Specification en tiempo de compilación, puede aplicar el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="ff274-114">You can determine whether your component conforms to the Common Language Specification at compile time by applying the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute to your source code.</span></span> <span data-ttu-id="ff274-115">Para obtener más información, consulte [CLSCompliantAttribute (Atributo)](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="ff274-115">For more information, see The [CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute).</span></span>

<span data-ttu-id="ff274-116">En este artículo:</span><span class="sxs-lookup"><span data-stu-id="ff274-116">In this article:</span></span>

* [<span data-ttu-id="ff274-117">Reglas de conformidad con CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-117">CLS compliance rules</span></span>](#cls-compliance-rules)

  * [<span data-ttu-id="ff274-118">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-118">Types and type member signatures</span></span>](#types-and-type-member-signatures)

  * [<span data-ttu-id="ff274-119">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-119">Naming conventions</span></span>](#naming-conventions)

  * [<span data-ttu-id="ff274-120">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-120">Type conversion</span></span>](#type-conversion)

  * [<span data-ttu-id="ff274-121">Matrices</span><span class="sxs-lookup"><span data-stu-id="ff274-121">Arrays</span></span>](#arrays)

  * [<span data-ttu-id="ff274-122">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-122">Interfaces</span></span>](#interfaces)

  * [<span data-ttu-id="ff274-123">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-123">Enumerations</span></span>](#enumerations)

  * [<span data-ttu-id="ff274-124">Miembros de tipos en general</span><span class="sxs-lookup"><span data-stu-id="ff274-124">Type members in general</span></span>](#type-members-in-general)

  * [<span data-ttu-id="ff274-125">Accesibilidad de miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-125">Member accessibility</span></span>](#member-accessibility)

  * [<span data-ttu-id="ff274-126">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-126">Generic types and members</span></span>](#generic-types-and-members)

  * [<span data-ttu-id="ff274-127">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-127">Constructors</span></span>](#constructors)

  * [<span data-ttu-id="ff274-128">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-128">Properties</span></span>](#properties)

  * [<span data-ttu-id="ff274-129">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-129">Events</span></span>](#events)

  * [<span data-ttu-id="ff274-130">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="ff274-130">Overloads</span></span>](#overloads)

  * [<span data-ttu-id="ff274-131">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ff274-131">Exceptions</span></span>](#exceptions)

  * [<span data-ttu-id="ff274-132">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-132">Attributes</span></span>](#attributes)

* [<span data-ttu-id="ff274-133">CLSCompliantAttribute (Atributo)</span><span class="sxs-lookup"><span data-stu-id="ff274-133">CLSCompliantAttribute attribute</span></span>](#the-clscompliantattribute-attribute)

* [<span data-ttu-id="ff274-134">Interoperabilidad entre lenguajes</span><span class="sxs-lookup"><span data-stu-id="ff274-134">Cross-Language Interoperability</span></span>](#cross-language-interoperability)

## <a name="cls-compliance-rules"></a><span data-ttu-id="ff274-135">Reglas de conformidad con CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-135">CLS compliance rules</span></span>

<span data-ttu-id="ff274-136">En esta sección se explican las reglas para crear un componente conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-136">This section discusses the rules for creating a CLS-compliant component.</span></span> <span data-ttu-id="ff274-137">Para obtener una lista completa de las normas, vea el apartado I, cláusula 11 del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="ff274-137">For a complete list of rules, see Partition I, Clause 11 of the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="ff274-138">Common Language Specification describe en cada regla la conformidad con CLS en referencia a los consumidores (desarrolladores que acceden mediante programación a un componente que es conforme a CLS), los marcos (desarrolladores que usan un compilador de lenguaje para crear bibliotecas conformes a CLS) y los extensores (desarrolladores que crean una herramienta, como un compilador de lenguaje o un analizador de código, que crea componentes conformes a CLS).</span><span class="sxs-lookup"><span data-stu-id="ff274-138">The Common Language Specification discusses each rule for CLS compliance as it applies to consumers (developers who are programmatically accessing a component that is CLS-compliant), frameworks (developers who are using a language compiler to create CLS-compliant libraries), and extenders (developers who are creating a tool such as a language compiler or a code parser that creates CLS-compliant components).</span></span> <span data-ttu-id="ff274-139">Este artículo se centra en las reglas que se aplican a los marcos.</span><span class="sxs-lookup"><span data-stu-id="ff274-139">This article focuses on the rules as they apply to frameworks.</span></span> <span data-ttu-id="ff274-140">Pero observe que algunas de las reglas que se aplican a los extensores también se pueden aplicar a los ensamblados que se crean mediante [Reflection.Emit](xref:System.Reflection.Emit).</span><span class="sxs-lookup"><span data-stu-id="ff274-140">Note, though, that some of the rules that apply to extenders may also apply to assemblies that are created using [Reflection.Emit](xref:System.Reflection.Emit).</span></span>

<span data-ttu-id="ff274-141">Para diseñar un componente que sea independiente del lenguaje, solo tiene que aplicar las reglas de conformidad con CLS a la interfaz pública del componente.</span><span class="sxs-lookup"><span data-stu-id="ff274-141">To design a component that is language independent, you only need to apply the rules for CLS compliance to your component's public interface.</span></span> <span data-ttu-id="ff274-142">La implementación privada no tiene que ajustarse a la especificación.</span><span class="sxs-lookup"><span data-stu-id="ff274-142">Your private implementation does not have to conform to the specification.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff274-143">Las reglas de conformidad con CLS solo se aplican a la interfaz pública de un componente, y no a su implementación privada.</span><span class="sxs-lookup"><span data-stu-id="ff274-143">The rules for CLS compliance apply only to a component's public interface, not to its private implementation.</span></span>

<span data-ttu-id="ff274-144">Por ejemplo, los números enteros sin signo distintos de [Byte](xref:System.Byte) no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-144">For example, unsigned integers other than [Byte](xref:System.Byte) are not CLS-compliant.</span></span> <span data-ttu-id="ff274-145">Dado que la clase `Person` del siguiente ejemplo expone una propiedad `Age` del tipo [UInt16](xref:System.UInt16), el código siguiente desencadena una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="ff274-145">Because the `Person` class in the following example exposes an `Age` property of type [UInt16](xref:System.UInt16), the following code displays a compiler warning.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private UInt16 personAge = 0;

   public UInt16 Age
   { get { return personAge; } }
}
// The attempt to compile the example displays the following compiler warning:
//    Public1.cs(10,18): warning CS3003: Type of 'Person.Age' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As UInt16
      Get
         Return personAge
      End Get
   End Property
End Class
' The attempt to compile the example displays the following compiler warning:
'    Public1.vb(9) : warning BC40027: Return type of function 'Age' is not CLS-compliant.
'
'       Public ReadOnly Property Age As UInt16
'                                ~~~
```

<span data-ttu-id="ff274-146">Para hacer que la clase Person sea conforme a CLS, puede cambiar el tipo de la propiedad `Age` de `UInt16` a [Int16](xref:System.Int16), que es un entero de 16 bits con signo conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-146">You can make the Person class CLS-compliant by changing the type of `Age` property from `UInt16` to [Int16](xref:System.Int16), which is a CLS-compliant, 16-bit signed integer.</span></span> <span data-ttu-id="ff274-147">No es necesario que cambie el tipo del campo privado `personAge`.</span><span class="sxs-lookup"><span data-stu-id="ff274-147">You do not have to change the type of the private `personAge` field.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person
{
   private Int16 personAge = 0;

   public Int16 Age
   { get { return personAge; } }
}
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Person
   Private personAge As UInt16

   Public ReadOnly Property Age As Int16
      Get
         Return CType(personAge, Int16)
      End Get
   End Property
End Class
```

<span data-ttu-id="ff274-148">Las interfaces públicas de una biblioteca se componen de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff274-148">A library's public interface consists of the following:</span></span>

* <span data-ttu-id="ff274-149">Definiciones de clases públicas.</span><span class="sxs-lookup"><span data-stu-id="ff274-149">Definitions of public classes.</span></span>

* <span data-ttu-id="ff274-150">Definiciones de los miembros públicos de las clases públicas y de los miembros accesibles por las clases derivadas (es decir, miembros protegidos).</span><span class="sxs-lookup"><span data-stu-id="ff274-150">Definitions of the public members of public classes, and definitions of members accessible to derived classes (that is, protected members).</span></span>

* <span data-ttu-id="ff274-151">Parámetros y tipos devueltos de los métodos públicos de las clases públicas y parámetros y tipos devueltos de los métodos accesibles por las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ff274-151">Parameters and return types of public methods of public classes, and parameters and return types of methods accessible to derived classes.</span></span>

<span data-ttu-id="ff274-152">Las reglas de conformidad con CLS se muestran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff274-152">The rules for CLS compliance are listed in the following table.</span></span> <span data-ttu-id="ff274-153">El texto de las normas se toma literalmente del [estándar ECMA-335: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), Copyright de 2012 de Ecma International.</span><span class="sxs-lookup"><span data-stu-id="ff274-153">The text of the rules is taken verbatim from the [ECMA-335 Standard: Common Language Infrastructure](https://www.ecma-international.org/publications/standards/Ecma-335.htm), which is Copyright 2012 by Ecma International.</span></span> <span data-ttu-id="ff274-154">En las secciones siguientes encontrará información más detallada sobre estas reglas.</span><span class="sxs-lookup"><span data-stu-id="ff274-154">More detailed information about these rules is found in the following sections.</span></span>

<span data-ttu-id="ff274-155">Categoría</span><span class="sxs-lookup"><span data-stu-id="ff274-155">Category</span></span> | <span data-ttu-id="ff274-156">Vea</span><span class="sxs-lookup"><span data-stu-id="ff274-156">See</span></span> | <span data-ttu-id="ff274-157">Regla</span><span class="sxs-lookup"><span data-stu-id="ff274-157">Rule</span></span> | <span data-ttu-id="ff274-158">Número de regla</span><span class="sxs-lookup"><span data-stu-id="ff274-158">Rule Number</span></span>
-------- | --- | ---- | -----------
<span data-ttu-id="ff274-159">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="ff274-159">Accessibility</span></span> | [<span data-ttu-id="ff274-160">Accesibilidad de miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-160">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="ff274-161">Cuando se reemplacen métodos heredados, no debe modificarse la accesibilidad, excepto cuando se reemplace un método heredado de un ensamblado diferente cuya accesibilidad sea `family-or-assembly`.</span><span class="sxs-lookup"><span data-stu-id="ff274-161">Accessibility shall not be changed when overriding inherited methods, except when overriding a method inherited from a different assembly with accessibility `family-or-assembly`.</span></span> <span data-ttu-id="ff274-162">En este caso, el reemplazo debe tener accesibilidad `family`.</span><span class="sxs-lookup"><span data-stu-id="ff274-162">In this case, the override shall have accessibility `family`.</span></span> | <span data-ttu-id="ff274-163">10</span><span class="sxs-lookup"><span data-stu-id="ff274-163">10</span></span>
<span data-ttu-id="ff274-164">Accesibilidad</span><span class="sxs-lookup"><span data-stu-id="ff274-164">Accessibility</span></span> | [<span data-ttu-id="ff274-165">Accesibilidad de miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-165">Member accessibility</span></span>](#member-accessibility) | <span data-ttu-id="ff274-166">La visibilidad y accesibilidad de los tipos y miembros se establecerá de modo que los tipos de la signatura de cualquier miembro sean visibles y accesibles siempre que el propio miembro sea visible y accesible.</span><span class="sxs-lookup"><span data-stu-id="ff274-166">The visibility and accessibility of types and members shall be such that types in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="ff274-167">Por ejemplo, un método público que sea visible fuera del ensamblado no debe tener ningún argumento cuyo tipo solamente sea visible en el interior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ff274-167">For example, a public method that is visible outside its assembly shall not have an argument whose type is visible only within the assembly.</span></span> <span data-ttu-id="ff274-168">La visibilidad y la accesibilidad de los tipos que conforman un tipo genérico con instancias que se utilice en la signatura de cualquier miembro deben establecerse de forma que serán visibles y accesibles siempre que el propio miembro sea visible y accesible.</span><span class="sxs-lookup"><span data-stu-id="ff274-168">The visibility and accessibility of types composing an instantiated generic type used in the signature of any member shall be visible and accessible whenever the member itself is visible and accessible.</span></span> <span data-ttu-id="ff274-169">Por ejemplo, un tipo genérico con instancias que esté presente en la signatura de un miembro que sea visible fuera del ensamblado no debe tener ningún argumento genérico cuyo tipo solamente sea visible en el interior del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ff274-169">For example, an instantiated generic type present in the signature of a member that is visible outside its assembly shall not have a generic argument whose type is visible only within the assembly.</span></span> | <span data-ttu-id="ff274-170">12</span><span class="sxs-lookup"><span data-stu-id="ff274-170">12</span></span>
<span data-ttu-id="ff274-171">Matrices</span><span class="sxs-lookup"><span data-stu-id="ff274-171">Arrays</span></span> | [<span data-ttu-id="ff274-172">Matrices</span><span class="sxs-lookup"><span data-stu-id="ff274-172">Arrays</span></span>](#arrays) | <span data-ttu-id="ff274-173">Las matrices deben tener elementos con un tipo conforme a CLS y los límites inferiores de todas las dimensiones de la matriz deben ser iguales a cero.</span><span class="sxs-lookup"><span data-stu-id="ff274-173">Arrays shall have elements with a CLS-compliant type, and all dimensions of the array shall have lower bounds of zero.</span></span> <span data-ttu-id="ff274-174">Para distinguir entre sobrecargas, solo se tendrá en cuenta el hecho de que el elemento es una matriz y el tipo de elementos de la matriz.</span><span class="sxs-lookup"><span data-stu-id="ff274-174">Only the fact that an item is an array and the element type of the array shall be required to distinguish between overloads.</span></span> <span data-ttu-id="ff274-175">Cuando la sobrecarga se basa en dos o varios tipos de matrices, los tipos de elementos deben ser tipos con nombre.</span><span class="sxs-lookup"><span data-stu-id="ff274-175">When overloading is based on two or more array types the element types shall be named types.</span></span> | <span data-ttu-id="ff274-176">16</span><span class="sxs-lookup"><span data-stu-id="ff274-176">16</span></span>
<span data-ttu-id="ff274-177">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-177">Attributes</span></span> | [<span data-ttu-id="ff274-178">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-178">Attributes</span></span>](#attributes) | <span data-ttu-id="ff274-179">Los atributos deben ser del tipo [System.Attribute](xref:System.Attribute) o heredarse de este.</span><span class="sxs-lookup"><span data-stu-id="ff274-179">Attributes shall be of type [System.Attribute](xref:System.Attribute), or a type inheriting from it.</span></span> | <span data-ttu-id="ff274-180">41</span><span class="sxs-lookup"><span data-stu-id="ff274-180">41</span></span>
<span data-ttu-id="ff274-181">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-181">Attributes</span></span> | [<span data-ttu-id="ff274-182">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-182">Attributes</span></span>](#attributes) | <span data-ttu-id="ff274-183">CLS solo permite un subconjunto de codificaciones de atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ff274-183">The CLS only allows a subset of the encodings of custom attributes.</span></span> <span data-ttu-id="ff274-184">Los únicos tipos que deben aparecer en estas codificaciones son (vea el apartado IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double) y cualquier tipo de enumeración basada en un tipo entero base compatible con CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-184">The only types that shall appear in these encodings are (see Partition IV): [System.Type](xref:System.Type), [System.String](xref:System.String), [System.Char](xref:System.Char), [System.Boolean](xref:System.Boolean), [System.Byte](xref:System.Byte), [System.Int16](xref:System.Int16), [System.Int32](xref:System.Int32), [System.Int64](xref:System.Int64), [System.Single](xref:System.Single), [System.Double](xref:System.Double), and any enumeration type based on a CLS-compliant base integer type.</span></span> | <span data-ttu-id="ff274-185">34</span><span class="sxs-lookup"><span data-stu-id="ff274-185">34</span></span>
<span data-ttu-id="ff274-186">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-186">Attributes</span></span> | [<span data-ttu-id="ff274-187">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-187">Attributes</span></span>](#attributes) | <span data-ttu-id="ff274-188">CLS no admite modificadores obligatorios que sean visibles públicamente (`modreq`, vea el Apartado II), pero sí admite modificadores opcionales (`modopt`, vea el apartado II) que no comprenda.</span><span class="sxs-lookup"><span data-stu-id="ff274-188">The CLS does not allow publicly visible required modifiers (`modreq`, see Partition II), but does allow optional modifiers (`modopt`, see Partition II) it does not understand.</span></span> | <span data-ttu-id="ff274-189">35</span><span class="sxs-lookup"><span data-stu-id="ff274-189">35</span></span>
<span data-ttu-id="ff274-190">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-190">Constructors</span></span> | [<span data-ttu-id="ff274-191">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-191">Constructors</span></span>](#constructors) | <span data-ttu-id="ff274-192">Un constructor de objetos debe llamar a un constructor de instancias de su clase base antes de que tenga lugar cualquier acceso a los datos de instancia heredados.</span><span class="sxs-lookup"><span data-stu-id="ff274-192">An object constructor shall call some instance constructor of its base class before any access occurs to inherited instance data.</span></span> <span data-ttu-id="ff274-193">(Esto no se aplica a los tipos de valor, que no necesitan constructores.)</span><span class="sxs-lookup"><span data-stu-id="ff274-193">(This does not apply to value types, which need not have constructors.)</span></span>  | <span data-ttu-id="ff274-194">21</span><span class="sxs-lookup"><span data-stu-id="ff274-194">21</span></span>
<span data-ttu-id="ff274-195">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-195">Constructors</span></span> | [<span data-ttu-id="ff274-196">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-196">Constructors</span></span>](#constructors) | <span data-ttu-id="ff274-197">No debe llamarse a los constructores de objetos excepto durante la creación de un objeto y no podrá iniciarse dos veces un objeto.</span><span class="sxs-lookup"><span data-stu-id="ff274-197">An object constructor shall not be called except as part of the creation of an object, and an object shall not be initialized twice.</span></span> | <span data-ttu-id="ff274-198">22</span><span class="sxs-lookup"><span data-stu-id="ff274-198">22</span></span>
<span data-ttu-id="ff274-199">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-199">Enumerations</span></span> | [<span data-ttu-id="ff274-200">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-200">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ff274-201">El tipo subyacente de una enumeración debe ser un tipo de entero integrado en CLS, el nombre del campo debe ser “value__” y dicho campo debe marcarse como `RTSpecialName`.</span><span class="sxs-lookup"><span data-stu-id="ff274-201">The underlying type of an enum shall be a built-in CLS integer type, the name of the field shall be "value__", and that field shall be marked `RTSpecialName`.</span></span> |  <span data-ttu-id="ff274-202">7</span><span class="sxs-lookup"><span data-stu-id="ff274-202">7</span></span>
<span data-ttu-id="ff274-203">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-203">Enumerations</span></span> | [<span data-ttu-id="ff274-204">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-204">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ff274-205">Hay dos tipos distintos de enumeraciones, que se indican mediante la presencia o ausencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute) (consulte la biblioteca del apartado IV).</span><span class="sxs-lookup"><span data-stu-id="ff274-205">There are two distinct kinds of enums, indicated by the presence or absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) (see Partition IV Library) custom attribute.</span></span> <span data-ttu-id="ff274-206">Uno representa valores enteros con nombre; el otro representa los marcadores de bit con nombre que se pueden combinar para generar un valor sin nombre.</span><span class="sxs-lookup"><span data-stu-id="ff274-206">One represents named integer values; the other represents named bit flags that can be combined to generate an unnamed value.</span></span> <span data-ttu-id="ff274-207">El valor de `enum` no se limita a los valores especificados.</span><span class="sxs-lookup"><span data-stu-id="ff274-207">The value of an `enum` is not limited to the specified values.</span></span> |  <span data-ttu-id="ff274-208">8</span><span class="sxs-lookup"><span data-stu-id="ff274-208">8</span></span>
<span data-ttu-id="ff274-209">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-209">Enumerations</span></span> | [<span data-ttu-id="ff274-210">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-210">Enumerations</span></span>](#enumerations) | <span data-ttu-id="ff274-211">Los campos estáticos literales de una enumeración deben contener el tipo de la propia enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff274-211">Literal static fields of an enum shall have the type of the enum itself.</span></span> |  <span data-ttu-id="ff274-212">9</span><span class="sxs-lookup"><span data-stu-id="ff274-212">9</span></span>
<span data-ttu-id="ff274-213">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-213">Events</span></span> | [<span data-ttu-id="ff274-214">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-214">Events</span></span>](#events) | <span data-ttu-id="ff274-215">Los métodos que implementen un evento se marcarán como `SpecialName` en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ff274-215">The methods that implement an event shall be marked `SpecialName` in the metadata.</span></span> |<span data-ttu-id="ff274-216">29</span><span class="sxs-lookup"><span data-stu-id="ff274-216">29</span></span>
<span data-ttu-id="ff274-217">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-217">Events</span></span> | [<span data-ttu-id="ff274-218">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-218">Events</span></span>](#events) | <span data-ttu-id="ff274-219">La accesibilidad de un evento y sus descriptores de acceso será idéntica.</span><span class="sxs-lookup"><span data-stu-id="ff274-219">The accessibility of an event and of its accessors shall be identical.</span></span> |<span data-ttu-id="ff274-220">30</span><span class="sxs-lookup"><span data-stu-id="ff274-220">30</span></span>
<span data-ttu-id="ff274-221">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-221">Events</span></span> | [<span data-ttu-id="ff274-222">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-222">Events</span></span>](#events) | <span data-ttu-id="ff274-223">Los métodos `add` y `remove` de un evento deben estar presentes o ausentes a la vez.</span><span class="sxs-lookup"><span data-stu-id="ff274-223">The `add` and `remove` methods for an event shall both either be present or absent.</span></span> |<span data-ttu-id="ff274-224">31</span><span class="sxs-lookup"><span data-stu-id="ff274-224">31</span></span>
<span data-ttu-id="ff274-225">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-225">Events</span></span> | [<span data-ttu-id="ff274-226">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-226">Events</span></span>](#events) | <span data-ttu-id="ff274-227">Los métodos `add` y `remove` de un evento deben tomar un parámetro cuyo tipo defina el tipo del evento, y ese tipo debe derivarse de [System.Delegate](xref:System.Delegate).</span><span class="sxs-lookup"><span data-stu-id="ff274-227">The `add` and `remove` methods for an event shall each take one parameter whose type defines the type of the event and that shall be derived from [System.Delegate](xref:System.Delegate).</span></span> |<span data-ttu-id="ff274-228">32</span><span class="sxs-lookup"><span data-stu-id="ff274-228">32</span></span>
<span data-ttu-id="ff274-229">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-229">Events</span></span> | [<span data-ttu-id="ff274-230">Eventos</span><span class="sxs-lookup"><span data-stu-id="ff274-230">Events</span></span>](#events) | <span data-ttu-id="ff274-231">Los eventos deben adherirse a un patrón de asignación de nombres concreto.</span><span class="sxs-lookup"><span data-stu-id="ff274-231">Events shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="ff274-232">En las comparaciones de nombres correspondientes se omitirá el atributo SpecialName mencionado en la regla 29 de CLS y se seguirán las reglas del identificador.</span><span class="sxs-lookup"><span data-stu-id="ff274-232">The SpecialName attribute referred to in CLS rule 29 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span>  |<span data-ttu-id="ff274-233">33</span><span class="sxs-lookup"><span data-stu-id="ff274-233">33</span></span>
<span data-ttu-id="ff274-234">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ff274-234">Exceptions</span></span> | [<span data-ttu-id="ff274-235">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ff274-235">Exceptions</span></span>](#exceptions) | <span data-ttu-id="ff274-236">Los objetos que se inicien deberán ser de tipo [System.Exception](xref:System.Exception) o de un tipo que herede de él.</span><span class="sxs-lookup"><span data-stu-id="ff274-236">Objects that are thrown shall be of type [System.Exception](xref:System.Exception) or a type inheriting from it.</span></span> <span data-ttu-id="ff274-237">No obstante, los métodos conformes a CLS no necesitan bloquear la propagación de otros tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff274-237">Nonetheless, CLS-compliant methods are not required to block the propagation of other types of exceptions.</span></span> | <span data-ttu-id="ff274-238">40</span><span class="sxs-lookup"><span data-stu-id="ff274-238">40</span></span>
<span data-ttu-id="ff274-239">General</span><span class="sxs-lookup"><span data-stu-id="ff274-239">General</span></span> | [<span data-ttu-id="ff274-240">Reglas de conformidad con CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-240">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="ff274-241">Las reglas de CLS solo se aplican a las partes de los tipos que son accesibles o visibles desde fuera del ensamblado de definición.</span><span class="sxs-lookup"><span data-stu-id="ff274-241">CLS rules apply only to those parts of a type that are accessible or visible outside of the defining assembly.</span></span> | <span data-ttu-id="ff274-242">1</span><span class="sxs-lookup"><span data-stu-id="ff274-242">1</span></span>
<span data-ttu-id="ff274-243">General</span><span class="sxs-lookup"><span data-stu-id="ff274-243">General</span></span> | [<span data-ttu-id="ff274-244">Reglas de conformidad con CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-244">CLS compliance rules</span></span>](#cls-compliance-rules) | <span data-ttu-id="ff274-245">Los miembros de tipos no conformes con CLS no deben marcarse como conformes con CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-245">Members of non-CLS compliant types shall not be marked CLS-compliant.</span></span> | <span data-ttu-id="ff274-246">2</span><span class="sxs-lookup"><span data-stu-id="ff274-246">2</span></span>
<span data-ttu-id="ff274-247">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-247">Generics</span></span> | [<span data-ttu-id="ff274-248">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-248">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-249">Los tipos anidados deben tener, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="ff274-249">Nested types shall have at least as many generic parameters as the enclosing type.</span></span> <span data-ttu-id="ff274-250">Los parámetros genéricos de un tipo anidado se corresponden por posición con los parámetros genéricos del tipo contenedor.</span><span class="sxs-lookup"><span data-stu-id="ff274-250">Generic parameters in a nested type correspond by position to the generic parameters in its enclosing type.</span></span>  | <span data-ttu-id="ff274-251">42</span><span class="sxs-lookup"><span data-stu-id="ff274-251">42</span></span>
<span data-ttu-id="ff274-252">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-252">Generics</span></span> | [<span data-ttu-id="ff274-253">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-253">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-254">El nombre de un tipo genérico debe codificar el número de parámetros de tipo declarados en el tipo no anidado o que se acaban de introducir en el tipo, si este está anidado, según las reglas definidas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ff274-254">The name of a generic type shall encode the number of type parameters declared on the non-nested type, or newly introduced to the type if nested, according to the rules defined above.</span></span> | <span data-ttu-id="ff274-255">43</span><span class="sxs-lookup"><span data-stu-id="ff274-255">43</span></span>
<span data-ttu-id="ff274-256">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-256">Generics</span></span> | [<span data-ttu-id="ff274-257">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-257">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-258">Todo tipo genérico deberá volver a declarar restricciones suficientes como para garantizar que cualquier restricción de las interfaces o del tipo base se vea satisfecha por las restricciones del tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="ff274-258">A generic type shall redeclare sufficient constraints to guarantee that any constraints on the base type, or interfaces would be satisfied by the generic type constraints.</span></span> | <span data-ttu-id="ff274-259">44</span><span class="sxs-lookup"><span data-stu-id="ff274-259">44</span></span>
<span data-ttu-id="ff274-260">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-260">Generics</span></span> | [<span data-ttu-id="ff274-261">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-261">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-262">Los tipos que se utilicen como restricciones en parámetros genéricos deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-262">Types used as constraints on generic parameters shall themselves be CLS-compliant.</span></span> | <span data-ttu-id="ff274-263">45</span><span class="sxs-lookup"><span data-stu-id="ff274-263">45</span></span>
<span data-ttu-id="ff274-264">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-264">Generics</span></span> | [<span data-ttu-id="ff274-265">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-265">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-266">Se entiende que la visibilidad y accesibilidad de los miembros (incluidos los tipos anidados) de un tipo genérico con instancias deben quedar restringidas al ámbito específico de la creación de instancias, y no a la declaración de tipos genéricos en general.</span><span class="sxs-lookup"><span data-stu-id="ff274-266">The visibility and accessibility of members (including nested types) in an instantiated generic type shall be considered to be scoped to the specific instantiation rather than the generic type declaration as a whole.</span></span> <span data-ttu-id="ff274-267">Suponiendo que esto sea cierto, se seguirán aplicando las especificaciones de accesibilidad y visibilidad de la regla 12 de CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-267">Assuming this, the visibility and accessibility rules of CLS rule 12 still apply.</span></span> | <span data-ttu-id="ff274-268">46</span><span class="sxs-lookup"><span data-stu-id="ff274-268">46</span></span>
<span data-ttu-id="ff274-269">Genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-269">Generics</span></span> | [<span data-ttu-id="ff274-270">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-270">Generic types and members</span></span>](#generic-types-and-members) | <span data-ttu-id="ff274-271">Cada método genérico abstracto o virtual deberá tener su propia implementación concreta (no abstracta) predeterminada</span><span class="sxs-lookup"><span data-stu-id="ff274-271">For each abstract or virtual generic method, there shall be a default concrete (nonabstract) implementation</span></span> | <span data-ttu-id="ff274-272">47</span><span class="sxs-lookup"><span data-stu-id="ff274-272">47</span></span>
<span data-ttu-id="ff274-273">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-273">Interfaces</span></span> | [<span data-ttu-id="ff274-274">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-274">Interfaces</span></span>](#interfaces) | <span data-ttu-id="ff274-275">Las interfaces conformes a CLS no deben requerir la definición de métodos no conformes a CLS para su implementación.</span><span class="sxs-lookup"><span data-stu-id="ff274-275">CLS-compliant interfaces shall not require the definition of non-CLS compliant methods in order to implement them.</span></span> | <span data-ttu-id="ff274-276">18</span><span class="sxs-lookup"><span data-stu-id="ff274-276">18</span></span>
<span data-ttu-id="ff274-277">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-277">Interfaces</span></span> | [<span data-ttu-id="ff274-278">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-278">Interfaces</span></span>](#interfaces) | <span data-ttu-id="ff274-279">Las interfaces conformes a CLS no pueden definir métodos estáticos ni pueden definir campos.</span><span class="sxs-lookup"><span data-stu-id="ff274-279">CLS-compliant interfaces shall not define static methods, nor shall they define fields.</span></span> | <span data-ttu-id="ff274-280">19</span><span class="sxs-lookup"><span data-stu-id="ff274-280">19</span></span>
<span data-ttu-id="ff274-281">Miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-281">Members</span></span> | [<span data-ttu-id="ff274-282">Miembros de tipos en general</span><span class="sxs-lookup"><span data-stu-id="ff274-282">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="ff274-283">Los campos y métodos static globales no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-283">Global static fields and methods are not CLS-compliant.</span></span> | <span data-ttu-id="ff274-284">36</span><span class="sxs-lookup"><span data-stu-id="ff274-284">36</span></span>
<span data-ttu-id="ff274-285">Miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-285">Members</span></span> | -- | <span data-ttu-id="ff274-286">El valor de un estático literal se especifica mediante el uso de metadatos de inicialización de campos.</span><span class="sxs-lookup"><span data-stu-id="ff274-286">The value of a literal static is specified through the use of field initialization metadata.</span></span> <span data-ttu-id="ff274-287">Un literal conforme a CLS debe tener un valor especificado en los metadatos de inicialización de campos que sea exactamente del mismo tipo que el literal (o el tipo subyacente, si el literal es `enum`).</span><span class="sxs-lookup"><span data-stu-id="ff274-287">A CLS-compliant literal must have a value specified in field initialization metadata that is of exactly the same type as the literal (or of the underlying type, if that literal is an `enum`).</span></span> | <span data-ttu-id="ff274-288">13</span><span class="sxs-lookup"><span data-stu-id="ff274-288">13</span></span>
<span data-ttu-id="ff274-289">Miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-289">Members</span></span> | [<span data-ttu-id="ff274-290">Miembros de tipos en general</span><span class="sxs-lookup"><span data-stu-id="ff274-290">Type members in general</span></span>](#type-members-in-general) | <span data-ttu-id="ff274-291">La restricción vararg no forma parte de CLS y la única convención de llamada admitida por CLS es la convención de llamada administrada estándar.</span><span class="sxs-lookup"><span data-stu-id="ff274-291">The vararg constraint is not part of the CLS, and the only calling convention supported by the CLS is the standard managed calling convention.</span></span> | <span data-ttu-id="ff274-292">15</span><span class="sxs-lookup"><span data-stu-id="ff274-292">15</span></span>
<span data-ttu-id="ff274-293">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-293">Naming conventions</span></span> | [<span data-ttu-id="ff274-294">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-294">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ff274-295">Los ensamblados seguirán las directrices del anexo 7 del informe técnico 15 del estándar Unicode 3.0, que rige el conjunto de caracteres permitidos que pueden usarse como iniciales e incluirse en los identificadores. Estas directrices están disponibles en línea en [Formularios de normalización Unicode](https://www.unicode.org/unicode/reports/tr15/tr15-18.html).</span><span class="sxs-lookup"><span data-stu-id="ff274-295">Assemblies shall follow Annex 7 of Technical Report 15 of the Unicode Standard3.0 governing the set of characters permitted to start and be included in identifiers, available online at [Unicode Normalization Forms](https://www.unicode.org/unicode/reports/tr15/tr15-18.html).</span></span> <span data-ttu-id="ff274-296">Los identificadores deben aparecer en el formato canónico definido por el Formulario C de normalización Unicode. En aras de la conformidad con CLS, dos identificadores se considerarán iguales si sus asignaciones de minúsculas (tal y como se especificó en las asignaciones unívocas de minúsculas de Unicode en las que no se tiene en cuenta la configuración regional) son iguales.</span><span class="sxs-lookup"><span data-stu-id="ff274-296">Identifiers shall be in the canonical format defined by Unicode Normalization Form C. For CLS purposes, two identifiers are the same if their lowercase mappings (as specified by the Unicode locale-insensitive, one-to-one lowercase mappings) are the same.</span></span> <span data-ttu-id="ff274-297">Es decir, para que dos identificadores se consideren diferentes según CLS, tendrán que diferenciarse en algo más que en el uso de mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="ff274-297">That is, for two identifiers to be considered different under the CLS they shall differ in more than simply their case.</span></span> <span data-ttu-id="ff274-298">Pero para invalidar una definición heredada, CLI requiere que se use la codificación exacta de la declaración original.</span><span class="sxs-lookup"><span data-stu-id="ff274-298">However, in order to override an inherited definition the CLI requires the precise encoding of the original declaration be used.</span></span> | <span data-ttu-id="ff274-299">4</span><span class="sxs-lookup"><span data-stu-id="ff274-299">4</span></span>
<span data-ttu-id="ff274-300">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ff274-300">Overloading</span></span> | [<span data-ttu-id="ff274-301">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-301">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ff274-302">Todos los nombres especificados en un ámbito conforme a CLS deben ser distintos independientemente del tipo, salvo en los casos en los que los nombres sean idénticos y se resuelvan mediante sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ff274-302">All names introduced in a CLS-compliant scope shall be distinct independent of kind, except where the names are identical and resolved via overloading.</span></span> <span data-ttu-id="ff274-303">Es decir, mientras CTS permite que un tipo único use el mismo nombre para un método y un campo, CLS no.</span><span class="sxs-lookup"><span data-stu-id="ff274-303">That is, while the CTS allows a single type to use the same name for a method and a field, the CLS does not.</span></span> | <span data-ttu-id="ff274-304">5</span><span class="sxs-lookup"><span data-stu-id="ff274-304">5</span></span>
<span data-ttu-id="ff274-305">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ff274-305">Overloading</span></span> | [<span data-ttu-id="ff274-306">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-306">Naming conventions</span></span>](#naming-conventions) | <span data-ttu-id="ff274-307">Los campos y los tipos anidados deben distinguirse únicamente por la comparación de identificadores, aunque CTS permita que se distingan signaturas diferentes.</span><span class="sxs-lookup"><span data-stu-id="ff274-307">Fields and nested types shall be distinct by identifier comparison alone, even though the CTS allows distinct signatures to be distinguished.</span></span> <span data-ttu-id="ff274-308">Los métodos, las propiedades y los eventos que tengan el mismo nombre (por comparación de identificadores) deben distinguirse por algo más que el tipo de valor devuelto, excepto según lo especificado en la regla 39 de CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-308">Methods, properties, and events that have the same name (by identifier comparison) shall differ by more than just the return type,except as specified in CLS Rule 39</span></span> | <span data-ttu-id="ff274-309">6</span><span class="sxs-lookup"><span data-stu-id="ff274-309">6</span></span>
<span data-ttu-id="ff274-310">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ff274-310">Overloading</span></span> | [<span data-ttu-id="ff274-311">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="ff274-311">Overloads</span></span>](#overloads) | <span data-ttu-id="ff274-312">Solo las propiedades y los métodos se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="ff274-312">Only properties and methods can be overloaded.</span></span> | <span data-ttu-id="ff274-313">37</span><span class="sxs-lookup"><span data-stu-id="ff274-313">37</span></span>
<span data-ttu-id="ff274-314">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ff274-314">Overloading</span></span> | [<span data-ttu-id="ff274-315">Sobrecargas</span><span class="sxs-lookup"><span data-stu-id="ff274-315">Overloads</span></span>](#overloads) |<span data-ttu-id="ff274-316">Las propiedades y los métodos se pueden sobrecargar únicamente en función del número y los tipos de sus parámetros, excepto los operadores de conversión denominados `op_Implicit` y `op_Explicit`, que también se pueden sobrecargar en función del tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ff274-316">Properties and methods can be overloaded based only on the number and types of their parameters, except the conversion operators named `op_Implicit` and `op_Explicit`, which can also be overloaded based on their return type.</span></span> | <span data-ttu-id="ff274-317">38</span><span class="sxs-lookup"><span data-stu-id="ff274-317">38</span></span>
<span data-ttu-id="ff274-318">Sobrecarga</span><span class="sxs-lookup"><span data-stu-id="ff274-318">Overloading</span></span> | -- | <span data-ttu-id="ff274-319">Si dos o más de los métodos conformes a CLS declarados en un tipo tienen el mismo nombre y, en un conjunto específico de instancias de tipos, tienen los mismos tipos de valor devuelto y parámetros, todos estos métodos serán semánticamente equivalentes en esas instancias de tipos.</span><span class="sxs-lookup"><span data-stu-id="ff274-319">If two or more CLS-compliant methods declared in a type have the same name and, for a specific set of type instantiations, they have the same parameter and return types, then all these methods shall be semantically equivalent at those type instantiations.</span></span> | <span data-ttu-id="ff274-320">48</span><span class="sxs-lookup"><span data-stu-id="ff274-320">48</span></span>
<span data-ttu-id="ff274-321">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-321">Properties</span></span> | [<span data-ttu-id="ff274-322">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-322">Properties</span></span>](#properties) | <span data-ttu-id="ff274-323">Los métodos que implementan los métodos de captador y establecedor de una propiedad deben estar marcados con `SpecialName` en los metadatos.</span><span class="sxs-lookup"><span data-stu-id="ff274-323">The methods that implement the getter and setter methods of a property shall be marked `SpecialName` in the metadata.</span></span> | <span data-ttu-id="ff274-324">24</span><span class="sxs-lookup"><span data-stu-id="ff274-324">24</span></span>
<span data-ttu-id="ff274-325">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-325">Properties</span></span> | [<span data-ttu-id="ff274-326">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-326">Properties</span></span>](#properties) | <span data-ttu-id="ff274-327">Todos los descriptores de acceso de una propiedad deben ser estáticos, virtuales o de instancia.</span><span class="sxs-lookup"><span data-stu-id="ff274-327">A property's accessors shall all be static, all be virtual, or all be instance.</span></span> | <span data-ttu-id="ff274-328">26</span><span class="sxs-lookup"><span data-stu-id="ff274-328">26</span></span>
<span data-ttu-id="ff274-329">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-329">Properties</span></span> | [<span data-ttu-id="ff274-330">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-330">Properties</span></span>](#properties) | <span data-ttu-id="ff274-331">El tipo de una propiedad es el tipo de valor devuelto del método captador y el tipo del último argumento del método establecedor.</span><span class="sxs-lookup"><span data-stu-id="ff274-331">The type of a property shall be the return type of the getter and the type of the last argument of the setter.</span></span> <span data-ttu-id="ff274-332">Los tipos de los parámetros de la propiedad deben ser los tipos de los parámetros del método captador y los tipos de todos los parámetros del método establecedor, excepto el último.</span><span class="sxs-lookup"><span data-stu-id="ff274-332">The types of the parameters of the property shall be the types of the parameters to the getter and the types of all but the final parameter of the setter.</span></span> <span data-ttu-id="ff274-333">Todos estos tipos deben ser conformes a CLS y no pueden ser punteros administrados (es decir, no deben pasarse por referencia).</span><span class="sxs-lookup"><span data-stu-id="ff274-333">All of these types shall be CLS-compliant, and shall not be managed pointers (that is, shall not be passed by reference).</span></span> | <span data-ttu-id="ff274-334">27</span><span class="sxs-lookup"><span data-stu-id="ff274-334">27</span></span>
<span data-ttu-id="ff274-335">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-335">Properties</span></span> | [<span data-ttu-id="ff274-336">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-336">Properties</span></span>](#properties) | <span data-ttu-id="ff274-337">Las propiedades deben ajustarse a un patrón de asignación de nombres concreto.</span><span class="sxs-lookup"><span data-stu-id="ff274-337">Properties shall adhere to a specific naming pattern.</span></span> <span data-ttu-id="ff274-338">En las comparaciones de nombres correspondientes se omitirá el atributo `SpecialName` mencionado en la regla 24 de CLS y se seguirán las reglas del identificador.</span><span class="sxs-lookup"><span data-stu-id="ff274-338">The `SpecialName` attribute referred to in CLS rule 24 shall be ignored in appropriate name comparisons and shall adhere to identifier rules.</span></span> <span data-ttu-id="ff274-339">Una propiedad tendrá un método de captador, un método de establecedor o ambos.</span><span class="sxs-lookup"><span data-stu-id="ff274-339">A property shall have a getter method, a setter method, or both.</span></span> | <span data-ttu-id="ff274-340">28</span><span class="sxs-lookup"><span data-stu-id="ff274-340">28</span></span>
<span data-ttu-id="ff274-341">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-341">Type conversion</span></span> | [<span data-ttu-id="ff274-342">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-342">Type conversion</span></span>](#type-conversion) | <span data-ttu-id="ff274-343">Si se proporciona op_Implicit u op_Explicit, deben darse medios alternativos para realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="ff274-343">If either op_Implicit or op_Explicit is provided, an alternate means of providing the coercion shall be provided.</span></span> | <span data-ttu-id="ff274-344">39</span><span class="sxs-lookup"><span data-stu-id="ff274-344">39</span></span>
<span data-ttu-id="ff274-345">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-345">Types</span></span> | [<span data-ttu-id="ff274-346">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-346">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-347">Los tipos de valor a los que se les ha aplicado la conversión boxing no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-347">Boxed value types are not CLS-compliant.</span></span> | <span data-ttu-id="ff274-348">3</span><span class="sxs-lookup"><span data-stu-id="ff274-348">3</span></span>
<span data-ttu-id="ff274-349">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-349">Types</span></span> | [<span data-ttu-id="ff274-350">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-350">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-351">Todos los tipos que aparecen en una signatura deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-351">All types appearing in a signature shall be CLS-compliant.</span></span> <span data-ttu-id="ff274-352">Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-352">All types composing an instantiated generic type shall be CLS-compliant.</span></span> | <span data-ttu-id="ff274-353">11</span><span class="sxs-lookup"><span data-stu-id="ff274-353">11</span></span>
<span data-ttu-id="ff274-354">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-354">Types</span></span> | [<span data-ttu-id="ff274-355">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-355">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-356">Las referencias a tipos no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-356">Typed references are not CLS-compliant.</span></span> | <span data-ttu-id="ff274-357">14</span><span class="sxs-lookup"><span data-stu-id="ff274-357">14</span></span>
<span data-ttu-id="ff274-358">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-358">Types</span></span> | [<span data-ttu-id="ff274-359">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-359">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-360">Los tipos de puntero no administrados no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-360">Unmanaged pointer types are not CLS-compliant.</span></span> | <span data-ttu-id="ff274-361">17</span><span class="sxs-lookup"><span data-stu-id="ff274-361">17</span></span>
<span data-ttu-id="ff274-362">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-362">Types</span></span> | [<span data-ttu-id="ff274-363">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-363">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-364">Las interfaces, los tipos de valor y las clases conformes a CLS no deben requerir la implementación de miembros no conformes a CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-364">CLS-compliant classes, value types, and interfaces shall not require the implementation of non-CLS-compliant members</span></span> | <span data-ttu-id="ff274-365">20</span><span class="sxs-lookup"><span data-stu-id="ff274-365">20</span></span>
<span data-ttu-id="ff274-366">Tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-366">Types</span></span> | [<span data-ttu-id="ff274-367">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-367">Types and type member signatures</span></span>](#types-and-type-member-signatures) | <span data-ttu-id="ff274-368">[System.Object](xref:System.Object) es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-368">[System.Object](xref:System.Object) is CLS-compliant.</span></span> <span data-ttu-id="ff274-369">Cualquier otra clase conforme a CLS se heredará de una clase conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-369">Any other CLS-compliant class shall inherit from a CLS-compliant class.</span></span> | <span data-ttu-id="ff274-370">23</span><span class="sxs-lookup"><span data-stu-id="ff274-370">23</span></span>

### <a name="types-and-type-member-signatures"></a><span data-ttu-id="ff274-371">Signaturas de tipos y miembros de tipo</span><span class="sxs-lookup"><span data-stu-id="ff274-371">Types and type member signatures</span></span>

<span data-ttu-id="ff274-372">El tipo [System.Object](xref:System.Object) es conforme a CLS y es el tipo base de todos los tipos de objetos del sistema de tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff274-372">The [System.Object](xref:System.Object) type is CLS-compliant and is the base type of all object types in the .NET Framework type system.</span></span> <span data-ttu-id="ff274-373">La herencia de .NET Framework es implícita (por ejemplo, la clase [String](xref:System.String) hereda implícitamente de la clase `Object`) o explícita (por ejemplo, la clase [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) hereda explícitamente de la clase [ArgumentException](xref:System.ArgumentException), que a su vez hereda también explícitamente de la clase [Exception](xref:System.Exception)).</span><span class="sxs-lookup"><span data-stu-id="ff274-373">Inheritance in the .NET Framework is either implicit (for example, the [String](xref:System.String) class implicitly inherits from the `Object` class) or explicit (for example, the [CultureNotFoundException](xref:System.Globalization.CultureNotFoundException) class explicitly inherits from the [ArgumentException](xref:System.ArgumentException) class, which explicitly inherits from the [Exception](xref:System.Exception) class.</span></span> <span data-ttu-id="ff274-374">Para que un tipo derivado sea conforme a CLS, su tipo base también debe ser conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-374">For a derived type to be CLS compliant, its base type must also be CLS-compliant.</span></span>

<span data-ttu-id="ff274-375">En el ejemplo siguiente se muestra un tipo derivado cuyo tipo base no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-375">The following example shows a derived type whose base type is not CLS-compliant.</span></span> <span data-ttu-id="ff274-376">En el ejemplo, se define una clase base `Counter` que usa un entero de 32 bits sin signo como contador.</span><span class="sxs-lookup"><span data-stu-id="ff274-376">It defines a base `Counter` class that uses an unsigned 32-bit integer as a counter.</span></span> <span data-ttu-id="ff274-377">Dado que la clase proporciona la funcionalidad de contador ajustando un entero sin signo, la clase se marca como no conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-377">Because the class provides counter functionality by wrapping an unsigned integer, the class is marked as non-CLS-compliant.</span></span> <span data-ttu-id="ff274-378">Como resultado, la clase derivada, `NonZeroCounter`, tampoco es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-378">As a result, a derived class, `NonZeroCounter`, is also not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[CLSCompliant(false)]
public class Counter
{
   UInt32 ctr;

   public Counter()
   {
      ctr = 0;
   }

   protected Counter(UInt32 ctr)
   {
      this.ctr = ctr;
   }

   public override string ToString()
   {
      return $"{ctr}). ";
   }

   public UInt32 Value
   {
      get { return ctr; }
   }

   public void Increment()
   {
      ctr += (uint) 1;
   }
}

public class NonZeroCounter : Counter
{
   public NonZeroCounter(int startIndex) : this((uint) startIndex)
   {
   }

   private NonZeroCounter(UInt32 startIndex) : base(startIndex)
   {
   }
}
// Compilation produces a compiler warning like the following:
//    Type3.cs(37,14): warning CS3009: 'NonZeroCounter': base type 'Counter' is not
//            CLS-compliant
//    Type3.cs(7,14): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>

<CLSCompliant(False)> _
Public Class Counter
   Dim ctr As UInt32

   Public Sub New
      ctr = 0
   End Sub

   Protected Sub New(ctr As UInt32)
      ctr = ctr
   End Sub

   Public Overrides Function ToString() As String
      Return $"{ctr}). "
   End Function

   Public ReadOnly Property Value As UInt32
      Get
         Return ctr
      End Get
   End Property

   Public Sub Increment()
      ctr += CType(1, UInt32)
   End Sub
End Class

Public Class NonZeroCounter : Inherits Counter
   Public Sub New(startIndex As Integer)
      MyClass.New(CType(startIndex, UInt32))
   End Sub

   Private Sub New(startIndex As UInt32)
      MyBase.New(CType(startIndex, UInt32))
   End Sub
End Class
' Compilation produces a compiler warning like the following:
'    Type3.vb(34) : warning BC40026: 'NonZeroCounter' is not CLS-compliant
'    because it derives from 'Counter', which is not CLS-compliant.
'
'    Public Class NonZeroCounter : Inherits Counter
'                 ~~~~~~~~~~~~~~
```

<span data-ttu-id="ff274-379">Todos los tipos que aparecen en las signaturas de miembros, incluidos los tipos de propiedades y los tipos de valores devueltos de un método, deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-379">All types that appear in member signatures, including a method's return type or a property type, must be CLS-compliant.</span></span> <span data-ttu-id="ff274-380">Además, en el caso de los tipos genéricos:</span><span class="sxs-lookup"><span data-stu-id="ff274-380">In addition, for generic types:</span></span>

* <span data-ttu-id="ff274-381">Todos los tipos que forman un tipo genérico con instancias deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-381">All types that compose an instantiated generic type must be CLS-compliant.</span></span>

* <span data-ttu-id="ff274-382">Todos los tipos que se utilizan como restricciones en parámetros genéricos deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-382">All types used as constraints on generic parameters must be CLS-compliant.</span></span>

<span data-ttu-id="ff274-383">El [sistema de tipos común](common-type-system.md) de .NET incluye varios tipos integrados que se admiten directamente en Common Language Runtime y que se codifican de forma especial en los metadatos de un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ff274-383">The .NET [common type system](common-type-system.md) includes a number of built-in types that are supported directly by the common language runtime and are specially encoded in an assembly's metadata.</span></span> <span data-ttu-id="ff274-384">De estos tipos intrínsecos, los tipos enumerados en la tabla siguiente son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-384">Of these intrinsic types, the types listed in the following table are CLS-compliant.</span></span>

<span data-ttu-id="ff274-385">Tipo conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-385">CLS-compliant type</span></span> | <span data-ttu-id="ff274-386">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff274-386">Description</span></span>
------------------ | -----------
[<span data-ttu-id="ff274-387">Byte</span><span class="sxs-lookup"><span data-stu-id="ff274-387">Byte</span></span>](xref:System.Byte) | <span data-ttu-id="ff274-388">Entero de 8 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="ff274-388">8-bit unsigned integer</span></span>
[<span data-ttu-id="ff274-389">Int16</span><span class="sxs-lookup"><span data-stu-id="ff274-389">Int16</span></span>](xref:System.Int16) | <span data-ttu-id="ff274-390">Entero de 16 bits con signo</span><span class="sxs-lookup"><span data-stu-id="ff274-390">16-bit signed integer</span></span>
[<span data-ttu-id="ff274-391">Int32</span><span class="sxs-lookup"><span data-stu-id="ff274-391">Int32</span></span>](xref:System.Int32) | <span data-ttu-id="ff274-392">Entero de 32 bits con signo</span><span class="sxs-lookup"><span data-stu-id="ff274-392">32-bit signed integer</span></span>
[<span data-ttu-id="ff274-393">Int64</span><span class="sxs-lookup"><span data-stu-id="ff274-393">Int64</span></span>](xref:System.Int64) | <span data-ttu-id="ff274-394">Entero de 64 bits con signo</span><span class="sxs-lookup"><span data-stu-id="ff274-394">64-bit signed integer</span></span>
[<span data-ttu-id="ff274-395">Single</span><span class="sxs-lookup"><span data-stu-id="ff274-395">Single</span></span>](xref:System.Single) | <span data-ttu-id="ff274-396">Valor de punto flotante de precisión sencilla</span><span class="sxs-lookup"><span data-stu-id="ff274-396">Single-precision floating-point value</span></span>
[<span data-ttu-id="ff274-397">Double</span><span class="sxs-lookup"><span data-stu-id="ff274-397">Double</span></span>](xref:System.Double) | <span data-ttu-id="ff274-398">Valor de punto flotante de precisión doble</span><span class="sxs-lookup"><span data-stu-id="ff274-398">Double-precision floating-point value</span></span>
[<span data-ttu-id="ff274-399">Boolean</span><span class="sxs-lookup"><span data-stu-id="ff274-399">Boolean</span></span>](xref:System.Boolean) | <span data-ttu-id="ff274-400">tipo de valor true o false</span><span class="sxs-lookup"><span data-stu-id="ff274-400">true or false value type</span></span>
[<span data-ttu-id="ff274-401">Char</span><span class="sxs-lookup"><span data-stu-id="ff274-401">Char</span></span>](xref:System.Char) | <span data-ttu-id="ff274-402">Unidad de código con la codificación UTF-16</span><span class="sxs-lookup"><span data-stu-id="ff274-402">UTF-16 encoded code unit</span></span>
[<span data-ttu-id="ff274-403">Decimal</span><span class="sxs-lookup"><span data-stu-id="ff274-403">Decimal</span></span>](xref:System.Decimal) | <span data-ttu-id="ff274-404">Número decimal de punto no flotante</span><span class="sxs-lookup"><span data-stu-id="ff274-404">Non-floating-point decimal number</span></span>
[<span data-ttu-id="ff274-405">IntPtr</span><span class="sxs-lookup"><span data-stu-id="ff274-405">IntPtr</span></span>](xref:System.IntPtr) | <span data-ttu-id="ff274-406">Puntero o identificador de un tamaño definido por la plataforma</span><span class="sxs-lookup"><span data-stu-id="ff274-406">Pointer or handle of a platform-defined size</span></span>
[<span data-ttu-id="ff274-407">String</span><span class="sxs-lookup"><span data-stu-id="ff274-407">String</span></span>](xref:System.String) | <span data-ttu-id="ff274-408">Colección de cero, uno o varios objetos Char</span><span class="sxs-lookup"><span data-stu-id="ff274-408">Collection of zero, one, or more Char objects</span></span>

<span data-ttu-id="ff274-409">Los tipos intrínsecos enumerados en la tabla siguiente no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-409">The intrinsic types listed in the following table are not CLS-Compliant.</span></span>

<span data-ttu-id="ff274-410">Tipo no conforme</span><span class="sxs-lookup"><span data-stu-id="ff274-410">Non-compliant type</span></span> | <span data-ttu-id="ff274-411">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff274-411">Description</span></span> | <span data-ttu-id="ff274-412">Alternativa conforme a CLS</span><span class="sxs-lookup"><span data-stu-id="ff274-412">CLS-compliant alternative</span></span>
------------------ | ----------- | -------------------------
[<span data-ttu-id="ff274-413">SByte</span><span class="sxs-lookup"><span data-stu-id="ff274-413">SByte</span></span>](xref:System.SByte) | <span data-ttu-id="ff274-414">Tipo de datos enteros de 8 bits con signo</span><span class="sxs-lookup"><span data-stu-id="ff274-414">8-bit signed integer data type</span></span> | [<span data-ttu-id="ff274-415">Int16</span><span class="sxs-lookup"><span data-stu-id="ff274-415">Int16</span></span>](xref:System.Int16)
[<span data-ttu-id="ff274-416">UInt16</span><span class="sxs-lookup"><span data-stu-id="ff274-416">UInt16</span></span>](xref:System.UInt16) | <span data-ttu-id="ff274-417">Entero de 16 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="ff274-417">16-bit unsigned integer</span></span> | [<span data-ttu-id="ff274-418">Int32</span><span class="sxs-lookup"><span data-stu-id="ff274-418">Int32</span></span>](xref:System.Int32)
[<span data-ttu-id="ff274-419">UInt32</span><span class="sxs-lookup"><span data-stu-id="ff274-419">UInt32</span></span>](xref:System.UInt32) | <span data-ttu-id="ff274-420">Entero de 32 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="ff274-420">32-bit unsigned integer</span></span> | [<span data-ttu-id="ff274-421">Int64</span><span class="sxs-lookup"><span data-stu-id="ff274-421">Int64</span></span>](xref:System.Int64)
[<span data-ttu-id="ff274-422">UInt64</span><span class="sxs-lookup"><span data-stu-id="ff274-422">UInt64</span></span>](xref:System.UInt64) | <span data-ttu-id="ff274-423">Entero de 64 bits sin signo</span><span class="sxs-lookup"><span data-stu-id="ff274-423">64-bit unsigned integer</span></span> | <span data-ttu-id="ff274-424">[Int64](xref:System.Int64) (se puede desbordar), [BigInteger](xref:System.Numerics.BigInteger) o [Double](xref:System.Double)</span><span class="sxs-lookup"><span data-stu-id="ff274-424">[Int64](xref:System.Int64) (may overflow), [BigInteger](xref:System.Numerics.BigInteger), or [Double](xref:System.Double)</span></span>
[<span data-ttu-id="ff274-425">UIntPtr</span><span class="sxs-lookup"><span data-stu-id="ff274-425">UIntPtr</span></span>](xref:System.UIntPtr) | <span data-ttu-id="ff274-426">Puntero o identificador sin signo</span><span class="sxs-lookup"><span data-stu-id="ff274-426">Unsigned pointer or handle</span></span> | [<span data-ttu-id="ff274-427">IntPtr</span><span class="sxs-lookup"><span data-stu-id="ff274-427">IntPtr</span></span>](xref:System.IntPtr)

<span data-ttu-id="ff274-428">La biblioteca de clases de .NET Framework o cualquier otra biblioteca de clases puede incluir otros tipos que no sean conformes a CLS; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="ff274-428">The .NET Framework Class Library or any other class library may include other types that aren't CLS-compliant; for example:</span></span>

* <span data-ttu-id="ff274-429">Tipos de valor a los que se les ha aplicado la conversión boxing.</span><span class="sxs-lookup"><span data-stu-id="ff274-429">Boxed value types.</span></span> <span data-ttu-id="ff274-430">En el siguiente ejemplo de C# se crea una clase con una propiedad pública de tipo `int*` denominada `Value`.</span><span class="sxs-lookup"><span data-stu-id="ff274-430">The following C# example creates a class that has a public property of type `int*` named `Value`.</span></span> <span data-ttu-id="ff274-431">Dado que `int*` es un tipo de valor al que se le ha aplicado la conversión boxing, el compilador lo marca como no conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-431">Because an `int*` is a boxed value type, the compiler flags it as non-CLS-compliant.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public unsafe class TestClass
{
   private int* val;

   public TestClass(int number)
   {
      val = (int*) number;
   }

   public int* Value {
      get { return val; }
   }
}
// The compiler generates the following output when compiling this example:
//        warning CS3003: Type of 'TestClass.Value' is not CLS-compliant
```

* <span data-ttu-id="ff274-432">Referencias con establecimiento de tipos, que son construcciones especiales que contienen una referencia a un objeto y una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="ff274-432">Typed references, which are special constructs that contain a reference to an object and a reference to a type.</span></span>

<span data-ttu-id="ff274-433">Si un tipo no es conforme a CLS, debe aplicar el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) con un parámetro *isCompliant* con un valor de `false` en él.</span><span class="sxs-lookup"><span data-stu-id="ff274-433">If a type is not CLS-compliant, you should apply the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute with an *isCompliant* parameter with a value of `false` to it.</span></span> <span data-ttu-id="ff274-434">Para obtener más información, consulte la sección [CLSCompliantAttribute (Atributo)](#the-clscompliantattribute-attribute).</span><span class="sxs-lookup"><span data-stu-id="ff274-434">For more information, see the [CLSCompliantAttribute attribute](#the-clscompliantattribute-attribute) section.</span></span>

<span data-ttu-id="ff274-435">En el ejemplo siguiente se muestra el problema de la conformidad con CLS en la creación de instancias de tipos genéricos y signaturas de métodos.</span><span class="sxs-lookup"><span data-stu-id="ff274-435">The following example illustrates the problem of CLS compliance in a method signature and in generic type instantiation.</span></span> <span data-ttu-id="ff274-436">En este ejemplo, se define una clase `InvoiceItem` con una propiedad de tipo [UInt32](xref:System.UInt32), una propiedad de tipo [Nullable(Of UInt32)](xref:System.Nullable%601) y un constructor con parámetros de tipo `UInt32` y `Nullable(Of UInt32)`.</span><span class="sxs-lookup"><span data-stu-id="ff274-436">It defines an `InvoiceItem` class with a property of type [UInt32](xref:System.UInt32), a property of type [Nullable(Of UInt32)](xref:System.Nullable%601), and a constructor with parameters of type `UInt32` and `Nullable(Of UInt32)`.</span></span> <span data-ttu-id="ff274-437">Cuando intente compilar este ejemplo, aparecerán cuatro advertencias del compilador.</span><span class="sxs-lookup"><span data-stu-id="ff274-437">You get four compiler warnings when you try to compile this example.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<uint> qty;

   public InvoiceItem(uint sku, Nullable<uint> quantity)
   {
      itemId = sku;
      qty = quantity;
   }

   public Nullable<uint> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public uint InvoiceId
   {
      get { return invId; }
      set { invId = value; }
   }
}
// The attempt to compile the example displays the following output:
//    Type1.cs(13,23): warning CS3001: Argument type 'uint' is not CLS-compliant
//    Type1.cs(13,33): warning CS3001: Argument type 'uint?' is not CLS-compliant
//    Type1.cs(19,26): warning CS3003: Type of 'InvoiceItem.Quantity' is not CLS-compliant
//    Type1.cs(25,16): warning CS3003: Type of 'InvoiceItem.InvoiceId' is not CLS-compliant
```

```vb
<Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of UInteger)

   Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
      itemId = sku
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of UInteger)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As UInteger
      Get
         Return invId
      End Get
      Set
         invId = value
      End Set
   End Property
End Class
' The attempt to compile the example displays output similar to the following:
'    Type1.vb(13) : warning BC40028: Type of parameter 'sku' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                      ~~~
'    Type1.vb(13) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Sub New(sku As UInteger, quantity As Nullable(Of UInteger))
'                                                               ~~~~~~~~
'    Type1.vb(18) : warning BC40041: Type 'UInteger' is not CLS-compliant.
'
'       Public Property Quantity As Nullable(Of UInteger)
'                                               ~~~~~~~~
'    Type1.vb(27) : warning BC40027: Return type of function 'InvoiceId' is not CLS-compliant.
'
'       Public Property InvoiceId As UInteger
```

<span data-ttu-id="ff274-438">Para eliminar las advertencias del compilador, reemplace los tipos no conformes a CLS de la interfaz pública de `InvoiceItem` por tipos conformes:</span><span class="sxs-lookup"><span data-stu-id="ff274-438">To eliminate the compiler warnings, replace the non-CLS-compliant types in the `InvoiceItem` public interface with compliant types:</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class InvoiceItem
{
   private uint invId = 0;
   private uint itemId = 0;
   private Nullable<int> qty;

   public InvoiceItem(int sku, Nullable<int> quantity)
   {
      if (sku <= 0)
         throw new ArgumentOutOfRangeException("The item number is zero or negative.");
      itemId = (uint) sku;

      qty = quantity;
   }

   public Nullable<int> Quantity
   {
      get { return qty; }
      set { qty = value; }
   }

   public int InvoiceId
   {
      get { return (int) invId; }
      set {
         if (value <= 0)
            throw new ArgumentOutOfRangeException("The invoice number is zero or negative.");
         invId = (uint) value; }
   }
}
```

```vb
Assembly: CLSCompliant(True)>

Public Class InvoiceItem

   Private invId As UInteger = 0
   Private itemId As UInteger = 0
   Private qty AS Nullable(Of Integer)

   Public Sub New(sku As Integer, quantity As Nullable(Of Integer))
      If sku <= 0 Then
         Throw New ArgumentOutOfRangeException("The item number is zero or negative.")
      End If
      itemId = CUInt(sku)
      qty = quantity
   End Sub

   Public Property Quantity As Nullable(Of Integer)
      Get
         Return qty
      End Get
      Set
         qty = value
      End Set
   End Property

   Public Property InvoiceId As Integer
      Get
         Return CInt(invId)
      End Get
      Set
         invId = CUInt(value)
      End Set
   End Property
End Class
```

<span data-ttu-id="ff274-439">Además de los tipos específicos indicados, algunas categorías de tipos no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-439">In addition to the specific types listed, some categories of types are not CLS compliant.</span></span> <span data-ttu-id="ff274-440">Entre estas categorías se incluyen tipos de punteros no administrados y tipos de punteros de función.</span><span class="sxs-lookup"><span data-stu-id="ff274-440">These include unmanaged pointer types and function pointer types.</span></span> <span data-ttu-id="ff274-441">En el ejemplo siguiente se genera una advertencia del compilador, ya que se utiliza un puntero a un entero para crear una matriz de enteros.</span><span class="sxs-lookup"><span data-stu-id="ff274-441">The following example generates a compiler warning because it uses a pointer to an integer to create an array of integers.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ArrayHelper
{
   unsafe public static Array CreateInstance(Type type, int* ptr, int items)
   {
      Array arr = Array.CreateInstance(type, items);
      int* addr = ptr;
      for (int ctr = 0; ctr < items; ctr++) {
          int value = *addr;
          arr.SetValue(value, ctr);
          addr++;
      }
      return arr;
   }
}
// The attempt to compile this example displays the following output:
//    UnmanagedPtr1.cs(8,57): warning CS3001: Argument type 'int*' is not CLS-compliant
```

<span data-ttu-id="ff274-442">En las clases abstractas conformes a CLS (es decir, clases marcadas como `abstract` en C#), todos los miembros de dichas clases deben ser también conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-442">For CLS-compliant abstract classes (that is, classes marked as `abstract` in C#), all members of the class must also be CLS-compliant.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="ff274-443">Convenciones de nomenclatura</span><span class="sxs-lookup"><span data-stu-id="ff274-443">Naming conventions</span></span>

<span data-ttu-id="ff274-444">Dado que algunos lenguajes de programación distinguen entre mayúsculas y minúsculas, los identificadores (como los nombres de espacios de nombres, los tipos y los miembros) deben tener otro elemento distintivo aparte del uso de mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="ff274-444">Because some programming languages are case-insensitive, identifiers (such as the names of namespaces, types, and members) must differ by more than case.</span></span> <span data-ttu-id="ff274-445">Dos identificadores se consideran equivalentes si sus asignaciones de minúsculas son iguales.</span><span class="sxs-lookup"><span data-stu-id="ff274-445">Two identifiers are considered equivalent if their lowercase mappings are the same.</span></span> <span data-ttu-id="ff274-446">En el ejemplo de C# siguiente, se definen dos clases públicas: `Person` y `person`.</span><span class="sxs-lookup"><span data-stu-id="ff274-446">The following C# example defines two public classes, `Person` and `person`.</span></span> <span data-ttu-id="ff274-447">Como solo se distinguen por el uso de mayúsculas, el compilador de C# las marca como no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-447">Because they differ only by case, the C# compiler flags them as not CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Person : person
{

}

public class person
{

}
// Compilation produces a compiler warning like the following:
//    Naming1.cs(11,14): warning CS3005: Identifier 'person' differing
//                       only in case is not CLS-compliant
//    Naming1.cs(6,14): (Location of symbol related to previous warning)
```

<span data-ttu-id="ff274-448">Los identificadores de los lenguajes de programación, como los nombres de los espacios de nombres, tipos y miembros, deben ajustarse al [Estándar Unicode 3.0, Informe técnico 15, Anexo 7](https://www.unicode.org/reports/tr15/tr15-18.html).</span><span class="sxs-lookup"><span data-stu-id="ff274-448">Programming language identifiers, such as the names of namespaces, types, and members, must conform to the [Unicode Standard 3.0, Technical Report 15, Annex 7](https://www.unicode.org/reports/tr15/tr15-18.html).</span></span> <span data-ttu-id="ff274-449">Esto significa que:</span><span class="sxs-lookup"><span data-stu-id="ff274-449">This means that:</span></span>

* <span data-ttu-id="ff274-450">El primer carácter de un identificador puede ser cualquier letra en mayúscula, letra en minúscula, letra de inicial en mayúscula, letra modificadora, otra letra o número de letra.</span><span class="sxs-lookup"><span data-stu-id="ff274-450">The first character of an identifier can be any Unicode uppercase letter, lowercase letter, title case letter, modifier letter, other letter, or letter number.</span></span> <span data-ttu-id="ff274-451">Para obtener información acerca de las categorías de caracteres Unicode, consulte la enumeración [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory).</span><span class="sxs-lookup"><span data-stu-id="ff274-451">For information on Unicode character categories, see the [System.Globalization.UnicodeCategory](xref:System.Globalization.UnicodeCategory) enumeration.</span></span>

* <span data-ttu-id="ff274-452">Los caracteres siguientes pueden proceder de cualquier categoría cuando funcionan como primer carácter y también pueden incluir marcas no espaciadas, marcas de combinación de espaciado, números decimales, puntuaciones de conexión y códigos de formato.</span><span class="sxs-lookup"><span data-stu-id="ff274-452">Subsequent characters can be from any of the categories as the first character, and can also include non-spacing marks, spacing combining marks, decimal numbers, connector punctuations, and formatting codes.</span></span>

<span data-ttu-id="ff274-453">Antes de comparar los identificadores, debe filtrar los códigos de formato y convertir los identificadores a la forma de normalización Unicode C, ya que un mismo carácter se puede representar mediante diferentes unidades de código UTF-16.</span><span class="sxs-lookup"><span data-stu-id="ff274-453">Before you compare identifiers, you should filter out formatting codes and convert the identifiers to Unicode Normalization Form C, because a single character can be represented by multiple UTF-16-encoded code units.</span></span> <span data-ttu-id="ff274-454">Las secuencias de caracteres que producen las mismas unidades de código en la forma de normalización Unicode C no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-454">Character sequences that produce the same code units in Unicode Normalization Form C are not CLS-compliant.</span></span> <span data-ttu-id="ff274-455">En el ejemplo siguiente se define una propiedad llamada `Å`, que se compone del carácter SIGNO DE ANGSTROM (U+212B) y una segunda propiedad llamada `Å`, que se compone de la LETRA MAYÚSCULA A LATINA CON UN ANILLO ENCIMA (U+00C5).</span><span class="sxs-lookup"><span data-stu-id="ff274-455">The following example defines a property named `Å`, which consists of the character ANGSTROM SIGN (U+212B), and a second property named `Å` which consists of the character LATIN CAPITAL LETTER A WITH RING ABOVE (U+00C5).</span></span> <span data-ttu-id="ff274-456">El compilador de C# marca el código fuente como no conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-456">The C# compiler flags the source code as non-CLS-compliant.</span></span>

```csharp
public class Size
{
   private double a1;
   private double a2;

   public double Å
   {
       get { return a1; }
       set { a1 = value; }
   }

   public double Å
   {
       get { return a2; }
       set { a2 = value; }
   }
}
// Compilation produces a compiler warning like the following:
//    Naming2a.cs(16,18): warning CS3005: Identifier 'Size.Å' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(10,18): (Location of symbol related to previous warning)
//    Naming2a.cs(18,8): warning CS3005: Identifier 'Size.Å.get' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(12,8): (Location of symbol related to previous warning)
//    Naming2a.cs(19,8): warning CS3005: Identifier 'Size.Å.set' differing only in case is not
//            CLS-compliant
//    Naming2a.cs(13,8): (Location of symbol related to previous warning)
```

```vb
<Assembly: CLSCompliant(True)>
Public Class Size
   Private a1 As Double
   Private a2 As Double

   Public Property Å As Double
       Get
          Return a1
       End Get
       Set
          a1 = value
       End Set
   End Property

   Public Property Å As Double
       Get
          Return a2
       End Get
       Set
          a2 = value
       End Set
   End Property
End Class
' Compilation produces a compiler warning like the following:
'    Naming1.vb(9) : error BC30269: 'Public Property Å As Double' has multiple definitions
'     with identical signatures.
'
'       Public Property Å As Double
'                       ~
```

<span data-ttu-id="ff274-457">Los nombres de miembros con un ámbito determinado (como los espacios de nombres de un ensamblado, los tipos de un espacio de nombres o los miembros de un tipo) deben ser únicos, excepto los nombres que se resuelven a través de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ff274-457">Member names within a particular scope (such as the namespaces within an assembly, the types within a namespace, or the members within a type) must be unique except for names that are resolved through overloading.</span></span> <span data-ttu-id="ff274-458">Este requisito es más estricto que el del sistema de tipos comunes, que permite a varios miembros de un ámbito tener nombres idénticos siempre que sean diferentes tipos de miembros (por ejemplo, que uno sea un método y otro, un campo).</span><span class="sxs-lookup"><span data-stu-id="ff274-458">This requirement is more stringent than that of the common type system, which allows multiple members within a scope to have identical names as long as they are different kinds of members (for example, one is a method and one is a field).</span></span> <span data-ttu-id="ff274-459">En particular, en el caso de los miembros de tipo:</span><span class="sxs-lookup"><span data-stu-id="ff274-459">In particular, for type members:</span></span>

* <span data-ttu-id="ff274-460">Los campos y los tipos anidados solo se distinguen por el nombre.</span><span class="sxs-lookup"><span data-stu-id="ff274-460">Fields and nested types are distinguished by name alone.</span></span>

* <span data-ttu-id="ff274-461">Los métodos, las propiedades y los eventos que tienen el mismo nombre deben distinguirse por algo más que el tipo de valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ff274-461">Methods, properties, and events that have the same name must differ by more than just return type.</span></span>

<span data-ttu-id="ff274-462">En el ejemplo siguiente se muestra el requisito que establece que los nombres de miembro deben ser únicos dentro de su ámbito.</span><span class="sxs-lookup"><span data-stu-id="ff274-462">The following example illustrates the requirement that member names must be unique within their scope.</span></span> <span data-ttu-id="ff274-463">En este ejemplo se define una clase denominada `Converter`, que incluye cuatro miembros denominados `Conversion`.</span><span class="sxs-lookup"><span data-stu-id="ff274-463">It defines a class named `Converter` that includes four members named `Conversion`.</span></span> <span data-ttu-id="ff274-464">Tres son métodos y uno es una propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff274-464">Three are methods, and one is a property.</span></span> <span data-ttu-id="ff274-465">El método que incluye un parámetro `Int64` recibe un nombre único, pero no ocurre lo mismo con los dos métodos que tienen un parámetro `Int32`, ya que el valor devuelto no se considera parte de la signatura del miembro.</span><span class="sxs-lookup"><span data-stu-id="ff274-465">The method that includes an `Int64` parameter is uniquely named, but the two methods with an `Int32` parameter are not, because return value is not considered a part of a member's signature.</span></span> <span data-ttu-id="ff274-466">La propiedad `Conversion` también infringe este requisito, ya que las propiedades no pueden tener el mismo nombre que los métodos sobrecargados.</span><span class="sxs-lookup"><span data-stu-id="ff274-466">The `Conversion` property also violates this requirement, because properties cannot have the same name as overloaded methods.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Converter
{
   public double Conversion(int number)
   {
      return (double) number;
   }

   public float Conversion(int number)
   {
      return (float) number;
   }

   public double Conversion(long number)
   {
      return (double) number;
   }

   public bool Conversion
   {
      get { return true; }
   }
}
// Compilation produces a compiler error like the following:
//    Naming3.cs(13,17): error CS0111: Type 'Converter' already defines a member called
//            'Conversion' with the same parameter types
//    Naming3.cs(8,18): (Location of symbol related to previous error)
//    Naming3.cs(23,16): error CS0102: The type 'Converter' already contains a definition for
//            'Conversion'
//    Naming3.cs(8,18): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Converter
   Public Function Conversion(number As Integer) As Double
      Return CDbl(number)
   End Function

   Public Function Conversion(number As Integer) As Single
      Return CSng(number)
   End Function

   Public Function Conversion(number As Long) As Double
      Return CDbl(number)
   End Function

   Public ReadOnly Property Conversion As Boolean
      Get
         Return True
      End Get
   End Property
End Class
' Compilation produces a compiler error like the following:
'    Naming3.vb(8) : error BC30301: 'Public Function Conversion(number As Integer) As Double'
'                    and 'Public Function Conversion(number As Integer) As Single' cannot
'                    overload each other because they differ only by return types.
'
'       Public Function Conversion(number As Integer) As Double
'                       ~~~~~~~~~~
'    Naming3.vb(20) : error BC30260: 'Conversion' is already declared as 'Public Function
'                     Conversion(number As Integer) As Single' in this class.
'
'       Public ReadOnly Property Conversion As Boolean
'                                ~~~~~~~~~~
```

<span data-ttu-id="ff274-467">Todos los lenguajes contienen palabras claves únicas, de modo que los lenguajes dirigidos a Common Language Runtime también deben proporcionar un mecanismo para hacer referencia a identificadores (como nombres de tipo) que coincidan con las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="ff274-467">Individual languages include unique keywords, so languages that target the common language runtime must also provide some mechanism for referencing identifiers (such as type names) that coincide with keywords.</span></span> <span data-ttu-id="ff274-468">Por ejemplo, `case` es una palabra clave en C# y Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ff274-468">For example, `case` is a keyword in both C# and Visual Basic.</span></span> <span data-ttu-id="ff274-469">Sin embargo, en el siguiente ejemplo de Visual Basic se elimina la ambigüedad entre una clase denominada `case` y la palabra clave `case` mediante llaves de apertura y cierre.</span><span class="sxs-lookup"><span data-stu-id="ff274-469">However, the following Visual Basic example is able to disambiguate a class named `case` from the `case` keyword by using opening and closing braces.</span></span> <span data-ttu-id="ff274-470">De lo contrario, el ejemplo produciría el mensaje de error "Una palabra clave no es válida como identificador" y no se compilaría.</span><span class="sxs-lookup"><span data-stu-id="ff274-470">Otherwise, the example would produce the error message, "Keyword is not valid as an identifier," and fail to compile.</span></span>

```vb
Public Class [case]
   Private _id As Guid
   Private name As String

   Public Sub New(name As String)
      _id = Guid.NewGuid()
      Me.name = name
   End Sub

   Public ReadOnly Property ClientName As String
      Get
         Return name
      End Get
   End Property
End Class
```

<span data-ttu-id="ff274-471">En el siguiente ejemplo de C# se crean instancias de la clase `case` usando el símbolo @ para eliminar la ambigüedad entre el identificador y la palabra clave del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-471">The following C# example is able to instantiate the `case` class by using the @ symbol to disambiguate the identifier from the language keyword.</span></span> <span data-ttu-id="ff274-472">Sin él, el compilador de C# mostraría dos mensajes de error similares a los siguientes: "Se esperaba un tipo" y "'Término 'case' de expresión no válido".</span><span class="sxs-lookup"><span data-stu-id="ff274-472">Without it, the C# compiler would display two error messages, "Type expected" and "Invalid expression term 'case'."</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      @case c = new @case("John");
      Console.WriteLine(c.ClientName);
   }
}
```

### <a name="type-conversion"></a><span data-ttu-id="ff274-473">Conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="ff274-473">Type conversion</span></span>

<span data-ttu-id="ff274-474">Common Language Specification define dos operadores de conversión:</span><span class="sxs-lookup"><span data-stu-id="ff274-474">The Common Language Specification defines two conversion operators:</span></span>

* <span data-ttu-id="ff274-475">`op_Implicit`, que se utiliza en las conversiones de ampliación que no dan lugar a la pérdida de datos o de precisión.</span><span class="sxs-lookup"><span data-stu-id="ff274-475">`op_Implicit`, which is used for widening conversions that do not result in loss of data or precision.</span></span> <span data-ttu-id="ff274-476">Por ejemplo, la estructura [Decimal](xref:System.Decimal) contiene un operador sobrecargado `op_Implicit` para convertir valores de tipos enteros y valores [Char](xref:System.Char) en valores `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="ff274-476">For example, the [Decimal](xref:System.Decimal) structure includes an overloaded `op_Implicit` operator to convert values of integral types and [Char](xref:System.Char) values to `Decimal` values.</span></span>

* <span data-ttu-id="ff274-477">`op_Explicit`, que se utiliza en las conversiones de restricción que pueden producir una pérdida de magnitud (un valor se convierte en un valor que tiene un intervalo menor) o de precisión.</span><span class="sxs-lookup"><span data-stu-id="ff274-477">`op_Explicit`, which is used for narrowing conversions that can result in loss of magnitude (a value is converted to a value that has a smaller range) or precision.</span></span> <span data-ttu-id="ff274-478">Por ejemplo, la estructura `Decimal` contiene un operador sobrecargado `op_Explicit` para convertir los valores [Double](xref:System.Double) y [Single](xref:System.Single) en `Decimal`, y convertir los valores `Decimal` en los valores integrales`Double`, `Single` y `Char`.</span><span class="sxs-lookup"><span data-stu-id="ff274-478">For example, the `Decimal` structure includes an overloaded `op_Explicit` operator to convert [Double](xref:System.Double) and [Single](xref:System.Single) values to `Decimal` and to convert `Decimal` values to integral values, `Double`, `Single`, and `Char`.</span></span>

<span data-ttu-id="ff274-479">Sin embargo, no todos los lenguajes admiten la sobrecarga de operadores o la definición de operadores personalizados.</span><span class="sxs-lookup"><span data-stu-id="ff274-479">However, not all languages support operator overloading or the definition of custom operators.</span></span> <span data-ttu-id="ff274-480">Si decide implementar estos operadores de conversión, debe proporcionar un mecanismo alternativo para realizar la conversión.</span><span class="sxs-lookup"><span data-stu-id="ff274-480">If you choose to implement these conversion operators, you should also provide an alternate way to perform the conversion.</span></span> <span data-ttu-id="ff274-481">Se recomienda proporcionar los métodos `From`Xxx y `To`Xxx.</span><span class="sxs-lookup"><span data-stu-id="ff274-481">We recommend that you provide `From`Xxx and `To`Xxx methods.</span></span>

<span data-ttu-id="ff274-482">En el ejemplo siguiente se definen conversiones implícitas y explícitas conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-482">The following example defines CLS-compliant implicit and explicit conversions.</span></span> <span data-ttu-id="ff274-483">En este ejemplo, se crea una clase `UDouble` que representa un número de punto flotante con signo de precisión doble.</span><span class="sxs-lookup"><span data-stu-id="ff274-483">It creates a `UDouble` class that represents an signed double-precision, floating-point number.</span></span> <span data-ttu-id="ff274-484">En las conversiones implícitas, pasa de `UDouble` a `Double` y, en las conversiones explícitas, de `UDouble` a `Single`, de `Double` a `UDouble` y de `Single` a `UDouble`.</span><span class="sxs-lookup"><span data-stu-id="ff274-484">It provides for implicit conversions from `UDouble` to `Double` and for explicit conversions from `UDouble` to `Single`, `Double` to `UDouble`, and `Single` to `UDouble`.</span></span> <span data-ttu-id="ff274-485">También define un método `ToDouble` como alternativa al operador de conversión implícita y los métodos `ToSingle`, `FromDouble` y `FromSingle` como alternativas a los operadores de conversión explícitos.</span><span class="sxs-lookup"><span data-stu-id="ff274-485">It also defines a `ToDouble` method as an alternative to the implicit conversion operator and the `ToSingle`, `FromDouble`, and `FromSingle` methods as alternatives to the explicit conversion operators.</span></span>

```csharp
using System;

public struct UDouble
{
   private double number;

   public UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      number = value;
   }

   public static readonly UDouble MinValue = (UDouble) 0.0;
   public static readonly UDouble MaxValue = (UDouble) Double.MaxValue;

   public static explicit operator Double(UDouble value)
   {
      return value.number;
   }

   public static implicit operator Single(UDouble value)
   {
      if (value.number > (double) Single.MaxValue)
         throw new InvalidCastException("A UDouble value is out of range of the Single type.");

      return (float) value.number;
   }

   public static explicit operator UDouble(double value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static implicit operator UDouble(float value)
   {
      if (value < 0)
         throw new InvalidCastException("A negative value cannot be converted to a UDouble.");

      return new UDouble(value);
   }

   public static Double ToDouble(UDouble value)
   {
      return (Double) value;
   }

   public static float ToSingle(UDouble value)
   {
      return (float) value;
   }

   public static UDouble FromDouble(double value)
   {
      return new UDouble(value);
   }

   public static UDouble FromSingle(float value)
   {
      return new UDouble(value);
   }
}
```

```vb
Public Structure UDouble
   Private number As Double

   Public Sub New(value As Double)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Sub New(value As Single)
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      number = value
   End Sub

   Public Shared ReadOnly MinValue As UDouble = CType(0.0, UDouble)
   Public Shared ReadOnly MaxValue As UDouble = Double.MaxValue

   Public Shared Widening Operator CType(value As UDouble) As Double
      Return value.number
   End Operator

   Public Shared Narrowing Operator CType(value As UDouble) As Single
      If value.number > CDbl(Single.MaxValue) Then
         Throw New InvalidCastException("A UDouble value is out of range of the Single type.")
      End If
      Return CSng(value.number)
   End Operator

   Public Shared Narrowing Operator CType(value As Double) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Narrowing Operator CType(value As Single) As UDouble
      If value < 0 Then
         Throw New InvalidCastException("A negative value cannot be converted to a UDouble.")
      End If
      Return New UDouble(value)
   End Operator

   Public Shared Function ToDouble(value As UDouble) As Double
      Return CType(value, Double)
   End Function

   Public Shared Function ToSingle(value As UDouble) As Single
      Return CType(value, Single)
   End Function

   Public Shared Function FromDouble(value As Double) As UDouble
      Return New UDouble(value)
   End Function

   Public Shared Function FromSingle(value As Single) As UDouble
      Return New UDouble(value)
   End Function
End Structure
```

### <a name="arrays"></a><span data-ttu-id="ff274-486">Matrices</span><span class="sxs-lookup"><span data-stu-id="ff274-486">Arrays</span></span>

<span data-ttu-id="ff274-487">Las matrices conformes a CLS cumplen las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff274-487">CLS-compliant arrays conform to the following rules:</span></span>

* <span data-ttu-id="ff274-488">Todas las dimensiones de una matriz deben tener un límite inferior igual a cero.</span><span class="sxs-lookup"><span data-stu-id="ff274-488">All dimensions of an array must have a lower bound of zero.</span></span> <span data-ttu-id="ff274-489">En el ejemplo siguiente se crea una matriz no conforme a CLS cuyo límite inferior es uno.</span><span class="sxs-lookup"><span data-stu-id="ff274-489">The following example creates a non-CLS-compliant array with a lower bound of one.</span></span> <span data-ttu-id="ff274-490">Observe que, a pesar de la presencia del atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute), el compilador no detecta que la matriz devuelta por el método `Numbers.GetTenPrimes` no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-490">Note that, despite the presence of the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute, the compiler does not detect that the array returned by the `Numbers.GetTenPrimes` method is not CLS-compliant.</span></span>

  ```csharp
  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static Array GetTenPrimes()
    {
        Array arr = Array.CreateInstance(typeof(Int32), new int[] {10}, new int[] {1});
        arr.SetValue(1, 1);
        arr.SetValue(2, 2);
        arr.SetValue(3, 3);
        arr.SetValue(5, 4);
        arr.SetValue(7, 5);
        arr.SetValue(11, 6);
        arr.SetValue(13, 7);
        arr.SetValue(17, 8);
        arr.SetValue(19, 9);
        arr.SetValue(23, 10);

        return arr;
    }
  }
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As Array
        Dim arr As Array = Array.CreateInstance(GetType(Int32), {10}, {1})
        arr.SetValue(1, 1)
        arr.SetValue(2, 2)
        arr.SetValue(3, 3)
        arr.SetValue(5, 4)
        arr.SetValue(7, 5)
        arr.SetValue(11, 6)
        arr.SetValue(13, 7)
        arr.SetValue(17, 8)
        arr.SetValue(19, 9)
        arr.SetValue(23, 10)
        Return arr
     End Function
  End Class
  ```

* <span data-ttu-id="ff274-491">Todos los elementos de la matriz deben componerse de tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-491">All array elements must consist of CLS-compliant types.</span></span> <span data-ttu-id="ff274-492">En el ejemplo siguiente se definen dos métodos que devuelven matrices no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-492">The following example defines two methods that return non-CLS-compliant arrays.</span></span> <span data-ttu-id="ff274-493">El primero devuelve una matriz de valores [UInt32](xref:System.UInt32).</span><span class="sxs-lookup"><span data-stu-id="ff274-493">The first returns an array of [UInt32](xref:System.UInt32) values.</span></span> <span data-ttu-id="ff274-494">El segundo devuelve una matriz [Object](xref:System.Object) que contiene los valores [Int32](xref:System.Int32) y `UInt32`.</span><span class="sxs-lookup"><span data-stu-id="ff274-494">The second returns an [Object](xref:System.Object) array that includes [Int32](xref:System.Int32) and `UInt32` values.</span></span> <span data-ttu-id="ff274-495">Aunque el compilador identifica la primera matriz como no conforme debido a su tipo `UInt32`, no reconoce que la segunda matriz incluye elementos no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-495">Although the compiler identifies the first array as non-compliant because of its `UInt32` type, it fails to recognize that the second array includes non-CLS-compliant elements.</span></span>

  ```csharp
  using System;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static UInt32[] GetTenPrimes()
    {
        uint[] arr = { 1u, 2u, 3u, 5u, 7u, 11u, 13u, 17u, 19u };
        return arr;
    }

    public static Object[] GetFivePrimes()
    {
        Object[] arr = { 1, 2, 3, 5u, 7u };
        return arr;
    }
  }
  // Compilation produces a compiler warning like the following:
  //    Array2.cs(8,27): warning CS3002: Return type of 'Numbers.GetTenPrimes()' is not
  //            CLS-compliant
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Class Numbers
     Public Shared Function GetTenPrimes() As UInt32()
        Return { 1ui, 2ui, 3ui, 5ui, 7ui, 11ui, 13ui, 17ui, 19ui }
     End Function
     Public Shared Function GetFivePrimes() As Object()
        Dim arr() As Object = { 1, 2, 3, 5ui, 7ui }
        Return arr
     End Function
  End Class
  ' Compilation produces a compiler warning like the following:
  '    warning BC40027: Return type of function 'GetTenPrimes' is not CLS-compliant.
  ```

* <span data-ttu-id="ff274-496">La resolución de desbordamiento de los métodos que tienen parámetros de matriz se basa en el hecho de que son matrices y en su tipo de elemento.</span><span class="sxs-lookup"><span data-stu-id="ff274-496">Overload resolution for methods that have array parameters is based on the fact that they are arrays and on their element type.</span></span> <span data-ttu-id="ff274-497">Por esta razón, la siguiente definición de un método `GetSquares` sobrecargado es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-497">For this reason, the following definition of an overloaded `GetSquares` method is CLS-compliant.</span></span>

  ```csharp
  using System;
  using System.Numerics;

  [assembly: CLSCompliant(true)]

  public class Numbers
  {
    public static byte[] GetSquares(byte[] numbers)
    {
        byte[] numbersOut = new byte[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++) {
            int square = ((int) numbers[ctr]) * ((int) numbers[ctr]);
            if (square <= Byte.MaxValue)
                numbersOut[ctr] = (byte) square;
            // If there's an overflow, assign MaxValue to the corresponding
            // element.
            else
                numbersOut[ctr] = Byte.MaxValue;

        }
        return numbersOut;
    }

    public static BigInteger[] GetSquares(BigInteger[] numbers)
  {
        BigInteger[] numbersOut = new BigInteger[numbers.Length];
        for (int ctr = 0; ctr < numbers.Length; ctr++)
            numbersOut[ctr] = numbers[ctr] * numbers[ctr];

       return numbersOut;
    }
  }
  ```

  ```vb
  Imports System.Numerics

  <Assembly: CLSCompliant(True)>

  Public Module Numbers
     Public Function GetSquares(numbers As Byte()) As Byte()
        Dim numbersOut(numbers.Length - 1) As Byte
        For ctr As Integer = 0 To numbers.Length - 1
           Dim square As Integer = (CInt(numbers(ctr)) * CInt(numbers(ctr)))
           If square <= Byte.MaxValue Then
              numbersOut(ctr) = CByte(square)
           ' If there's an overflow, assign MaxValue to the corresponding
           ' element.
           Else
              numbersOut(ctr) = Byte.MaxValue
           End If
        Next
        Return numbersOut
     End Function

     Public Function GetSquares(numbers As BigInteger()) As BigInteger()
         Dim numbersOut(numbers.Length - 1) As BigInteger
         For ctr As Integer = 0 To numbers.Length - 1
            numbersOut(ctr) = numbers(ctr) * numbers(ctr)
         Next
         Return numbersOut
     End Function
  End Module
  ```

### <a name="interfaces"></a><span data-ttu-id="ff274-498">Interfaces</span><span class="sxs-lookup"><span data-stu-id="ff274-498">Interfaces</span></span>

<span data-ttu-id="ff274-499">Las interfaces conformes a CLS pueden definir propiedades, eventos y métodos virtuales (métodos sin implementación).</span><span class="sxs-lookup"><span data-stu-id="ff274-499">CLS-compliant interfaces can define properties, events, and virtual methods (methods with no implementation).</span></span> <span data-ttu-id="ff274-500">Una interfaz conforme a CLS no puede tener ninguno de los elementos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff274-500">A CLS-compliant interface cannot have any of the following:</span></span>

* <span data-ttu-id="ff274-501">Métodos estáticos o campos estáticos.</span><span class="sxs-lookup"><span data-stu-id="ff274-501">Static methods or static fields.</span></span> <span data-ttu-id="ff274-502">El compilador de C# genera errores de compilador si se define un miembro estático en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ff274-502">The C# compiler generates compiler errors if you define a static member in an interface.</span></span>

* <span data-ttu-id="ff274-503">Campos.</span><span class="sxs-lookup"><span data-stu-id="ff274-503">Fields.</span></span> <span data-ttu-id="ff274-504">El compilador de C# genera errores de compilador si se define un campo en una interfaz.</span><span class="sxs-lookup"><span data-stu-id="ff274-504">The C# a compiler generates compiler errors if you define a field in an interface.</span></span>

* <span data-ttu-id="ff274-505">Métodos que no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-505">Methods that are not CLS-compliant.</span></span> <span data-ttu-id="ff274-506">Por ejemplo, la siguiente definición de interfaz incluye un método, `INumber.GetUnsigned`, que está marcado como no conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-506">For example, the following interface definition includes a method, `INumber.GetUnsigned`, that is marked as non-CLS-compliant.</span></span> <span data-ttu-id="ff274-507">Este ejemplo genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="ff274-507">This example generates a compiler warning.</span></span>

  ```csharp
  using System;

  [assembly:CLSCompliant(true)]

  public interface INumber
  {
      int Length();
      [CLSCompliant(false)] ulong GetUnsigned();
  }
  // Attempting to compile the example displays output like the following:
  //    Interface2.cs(8,32): warning CS3010: 'INumber.GetUnsigned()': CLS-compliant interfaces
  //            must have only CLS-compliant members
  ```

  ```vb
  <Assembly: CLSCompliant(True)>

  Public Interface INumber
    Function Length As Integer
      <CLSCompliant(False)> Function GetUnsigned As ULong
    End Interface
    ' Attempting to compile the example displays output like the following:
    '    Interface2.vb(9) : warning BC40033: Non CLS-compliant 'function' is not allowed in a
    '    CLS-compliant interface.
    '
    '       <CLSCompliant(False)> Function GetUnsigned As ULong
    '                                      ~~~~~~~~~~~
  ```

  <span data-ttu-id="ff274-508">Debido a esta regla, no se necesitan tipos conformes a CLS para implementar miembros no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-508">Because of this rule, CLS-compliant types are not required to implement non-CLS-compliant members.</span></span> <span data-ttu-id="ff274-509">Si un marco conforme a CLS expone una clase que implementa una interfaz no conforme a CLS, también debe proporcionar implementaciones concretas de todos los miembros no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-509">If a CLS-compliant framework does expose a class that implements a non-CLS compliant interface, it should also provide concrete implementations of all non-CLS-compliant members.</span></span>

<span data-ttu-id="ff274-510">Los compiladores de lenguaje conformes a CLS también deben permitir que una clase proporcione implementaciones independientes de miembros con el mismo nombre y la misma signatura en varias interfaces.</span><span class="sxs-lookup"><span data-stu-id="ff274-510">CLS-compliant language compilers must also allow a class to provide separate implementations of members that have the same name and signature in multiple interfaces.</span></span> <span data-ttu-id="ff274-511">C# admite implementaciones de interfaz explícitas para proporcionar diferentes implementaciones de métodos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="ff274-511">C# supports explicit interface implementations to provide different implementations of identically named methods.</span></span> <span data-ttu-id="ff274-512">En el ejemplo siguiente se muestra este escenario con la definición de una clase `Temperature` que implementa las interfaces `ICelsius` y `IFahrenheit` como implementaciones de interfaces explícitas.</span><span class="sxs-lookup"><span data-stu-id="ff274-512">The following example illustrates this scenario by defining a `Temperature` class that implements the `ICelsius` and `IFahrenheit` interfaces as explicit interface implementations.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public interface IFahrenheit
{
   decimal GetTemperature();
}

public interface ICelsius
{
   decimal GetTemperature();
}

public class Temperature : ICelsius, IFahrenheit
{
   private decimal _value;

   public Temperature(decimal value)
   {
      // We assume that this is the Celsius value.
      _value = value;
   }

   decimal IFahrenheit.GetTemperature()
   {
      return _value * 9 / 5 + 32;
   }

   decimal ICelsius.GetTemperature()
   {
      return _value;
   }
}
public class Example
{
   public static void Main()
   {
      Temperature temp = new Temperature(100.0m);
      ICelsius cTemp = temp;
      IFahrenheit fTemp = temp;
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        cTemp.GetTemperature());
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        fTemp.GetTemperature());
   }
}
// The example displays the following output:
//       Temperature in Celsius: 100.0 degrees
//       Temperature in Fahrenheit: 212.0 degrees
```

```vb
Assembly: CLSCompliant(True)>

Public Interface IFahrenheit
   Function GetTemperature() As Decimal
End Interface

Public Interface ICelsius
   Function GetTemperature() As Decimal
End Interface

Public Class Temperature : Implements ICelsius, IFahrenheit
   Private _value As Decimal

   Public Sub New(value As Decimal)
      ' We assume that this is the Celsius value.
      _value = value
   End Sub

   Public Function GetFahrenheit() As Decimal _
          Implements IFahrenheit.GetTemperature
      Return _value * 9 / 5 + 32
   End Function

   Public Function GetCelsius() As Decimal _
          Implements ICelsius.GetTemperature
      Return _value
   End Function
End Class

Module Example
   Public Sub Main()
      Dim temp As New Temperature(100.0d)
      Console.WriteLine("Temperature in Celsius: {0} degrees",
                        temp.GetCelsius())
      Console.WriteLine("Temperature in Fahrenheit: {0} degrees",
                        temp.GetFahrenheit())
   End Sub
End Module
' The example displays the following output:
'       Temperature in Celsius: 100.0 degrees
'       Temperature in Fahrenheit: 212.0 degrees
```

### <a name="enumerations"></a><span data-ttu-id="ff274-513">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ff274-513">Enumerations</span></span>

<span data-ttu-id="ff274-514">Las enumeraciones conformes a CLS deben seguir estas reglas:</span><span class="sxs-lookup"><span data-stu-id="ff274-514">CLS-compliant enumerations must follow these rules:</span></span>

* <span data-ttu-id="ff274-515">El tipo subyacente de una enumeración debe ser un entero intrínseco conforme a CLS ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32) o [Int64](xref:System.Int64)).</span><span class="sxs-lookup"><span data-stu-id="ff274-515">The underlying type of the enumeration must be an intrinsic CLS-compliant integer ([Byte](xref:System.Byte), [Int16](xref:System.Int16), [Int32](xref:System.Int32), or [Int64](xref:System.Int64)).</span></span> <span data-ttu-id="ff274-516">Por ejemplo, el código siguiente intenta definir una enumeración cuyo tipo subyacente es [UInt32](xref:System.UInt32) y genera una advertencia del compilador.</span><span class="sxs-lookup"><span data-stu-id="ff274-516">For example, the following code tries to define an enumeration whose underlying type is [UInt32](xref:System.UInt32) and generates a compiler warning.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public enum Size : uint {
        Unspecified = 0,
        XSmall = 1,
        Small = 2,
        Medium = 3,
        Large = 4,
        XLarge = 5
    };

    public class Clothing
    {
        public string Name;
        public string Type;
        public string Size;
    }
    // The attempt to compile the example displays a compiler warning like the following:
    //    Enum3.cs(6,13): warning CS3009: 'Size': base type 'uint' is not CLS-compliant
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Enum Size As UInt32
       Unspecified = 0
       XSmall = 1
       Small = 2
       Medium = 3
       Large = 4
       XLarge = 5
    End Enum

    Public Class Clothing
       Public Name As String
       Public Type As String
       Public Size As Size
    End Class
    ' The attempt to compile the example displays a compiler warning like the following:
    '    Enum3.vb(6) : warning BC40032: Underlying type 'UInt32' of Enum is not CLS-compliant.
    '
    '    Public Enum Size As UInt32
    '                ~~~~
    ```

* <span data-ttu-id="ff274-517">Un tipo de enumeración debe tener un campo de instancia único denominado `Value__` marcado con el atributo `FieldAttributes.RTSpecialName`.</span><span class="sxs-lookup"><span data-stu-id="ff274-517">An enumeration type must have a single instance field named `Value__` that is marked with the `FieldAttributes.RTSpecialName` attribute.</span></span> <span data-ttu-id="ff274-518">Esto permite hacer referencia al valor del campo de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="ff274-518">This enables you to reference the field value implicitly.</span></span>

* <span data-ttu-id="ff274-519">Las enumeraciones incluyen campos estáticos literales del mismo tipo que el de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff274-519">An enumeration includes literal static fields whose types match the type of the enumeration itself.</span></span> <span data-ttu-id="ff274-520">Por ejemplo, si define una enumeración `State` con los valores `State.On` y `State.Off`, `State.On` y `State.Off` son campos estáticos literales cuyo tipo será `State`.</span><span class="sxs-lookup"><span data-stu-id="ff274-520">For example, if you define a `State` enumeration with values of `State.On` and `State.Off`, `State.On` and `State.Off` are both literal static fields whose type is `State`.</span></span>

* <span data-ttu-id="ff274-521">Hay dos tipos de enumeraciones:</span><span class="sxs-lookup"><span data-stu-id="ff274-521">There are two kinds of enumerations:</span></span>

  * <span data-ttu-id="ff274-522">Las enumeraciones que representan un conjunto de valores enteros con nombre mutuamente excluyentes.</span><span class="sxs-lookup"><span data-stu-id="ff274-522">An enumeration that represents a set of mutually exclusive, named integer values.</span></span> <span data-ttu-id="ff274-523">Este tipo de enumeración se indica por la ausencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="ff274-523">This type of enumeration is indicated by the absence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

  * <span data-ttu-id="ff274-524">Las enumeraciones que representan un conjunto de marcadores de bits que se pueden combinar para generar un valor sin nombre.</span><span class="sxs-lookup"><span data-stu-id="ff274-524">An enumeration that represents a set of bit flags that can combine to generate an unnamed value.</span></span> <span data-ttu-id="ff274-525">Este tipo de enumeración se indica por la presencia del atributo personalizado [System.FlagsAttribute](xref:System.FlagsAttribute).</span><span class="sxs-lookup"><span data-stu-id="ff274-525">This type of enumeration is indicated by the presence of the [System.FlagsAttribute](xref:System.FlagsAttribute) custom attribute.</span></span>

<span data-ttu-id="ff274-526">Para obtener más información, consulte la documentación de la estructura [Enum](xref:System.Enum).</span><span class="sxs-lookup"><span data-stu-id="ff274-526">For more information, see the documentation for the [Enum](xref:System.Enum) structure.</span></span>

* <span data-ttu-id="ff274-527">El valor de una enumeración no se limita al intervalo de sus valores especificados.</span><span class="sxs-lookup"><span data-stu-id="ff274-527">The value of an enumeration is not limited to the range of its specified values.</span></span> <span data-ttu-id="ff274-528">Es decir, el intervalo de valores de una enumeración es el intervalo de su valor subyacente.</span><span class="sxs-lookup"><span data-stu-id="ff274-528">In other words, the range of values in an enumeration is the range of its underlying value.</span></span> <span data-ttu-id="ff274-529">Puede utilizar el método `Enum.IsDefined` para determinar si un valor especificado es miembro de una enumeración.</span><span class="sxs-lookup"><span data-stu-id="ff274-529">You can use the `Enum.IsDefined` method to determine whether a specified value is a member of an enumeration.</span></span>

### <a name="type-members-in-general"></a><span data-ttu-id="ff274-530">Miembros de tipos en general</span><span class="sxs-lookup"><span data-stu-id="ff274-530">Type members in general</span></span>

<span data-ttu-id="ff274-531">Common Language Specification necesita todos los campos y métodos accesibles como miembros de una clase determinada.</span><span class="sxs-lookup"><span data-stu-id="ff274-531">The Common Language Specification requires all fields and methods to be accessed as members of a particular class.</span></span> <span data-ttu-id="ff274-532">Por tanto, los métodos y los campos estáticos globales (es decir, los métodos o los campos que se definen con independencia de un tipo) no son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-532">Therefore, global static fields and methods (that is, static fields or methods that are defined apart from a type) are not CLS-compliant.</span></span> <span data-ttu-id="ff274-533">Si intenta incluir un campo o un método global en el código fuente, el compilador de C# generará un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="ff274-533">If you try to include a global field or method in your source code, the C# compiler generates a compiler error.</span></span>

<span data-ttu-id="ff274-534">Common Language Specification solo admite la convención de llamada administrada estándar.</span><span class="sxs-lookup"><span data-stu-id="ff274-534">The Common Language Specification supports only the standard managed calling convention.</span></span> <span data-ttu-id="ff274-535">No admite convenciones de llamada ni métodos no administrados con listas de argumentos variables marcados con la palabra clave `varargs`.</span><span class="sxs-lookup"><span data-stu-id="ff274-535">It doesn't support unmanaged calling conventions and methods with variable argument lists marked with the `varargs` keyword.</span></span> <span data-ttu-id="ff274-536">En el caso de las listas de argumentos variables que son compatibles con la convención de llamada administrada estándar, use el atributo [ParamArrayAttribute](xref:System.ParamArrayAttribute) o la implementación del lenguaje específico, como la palabra clave `params` en C# y la palabra clave `ParamArray` en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ff274-536">For variable argument lists that are compatible with the standard managed calling convention, use the [ParamArrayAttribute](xref:System.ParamArrayAttribute) attribute or the individual language's implementation, such as the `params` keyword in C# and the `ParamArray` keyword in Visual Basic.</span></span>

### <a name="member-accessibility"></a><span data-ttu-id="ff274-537">Accesibilidad de miembros</span><span class="sxs-lookup"><span data-stu-id="ff274-537">Member accessibility</span></span>

<span data-ttu-id="ff274-538">Al reemplazar un miembro heredado no se puede cambiar la accesibilidad de dicho miembro.</span><span class="sxs-lookup"><span data-stu-id="ff274-538">Overriding an inherited member cannot change the accessibility of that member.</span></span> <span data-ttu-id="ff274-539">Por ejemplo, un método público de una clase base no se puede reemplazar por un método privado de una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="ff274-539">For example, a public method in a base class cannot be overridden by a private method in a derived class.</span></span> <span data-ttu-id="ff274-540">Existe una excepción: un miembro `protected internal` (en C#) o `Protected Friend` (en Visual Basic) de un ensamblado que se haya reemplazado por un tipo de un ensamblado diferente.</span><span class="sxs-lookup"><span data-stu-id="ff274-540">There is one exception: a `protected internal` (in C#) or `Protected Friend` (in Visual Basic) member in one assembly that is overridden by a type in a different assembly.</span></span>  <span data-ttu-id="ff274-541">En ese caso, la accesibilidad del reemplazo es `Protected`.</span><span class="sxs-lookup"><span data-stu-id="ff274-541">In that case, the accessibility of the override is `Protected`.</span></span>

<span data-ttu-id="ff274-542">En el ejemplo siguiente se muestra el error que se genera cuando el atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) se establece en `true` y `Person`, que es una clase derivada de `Animal`, intenta cambiar la accesibilidad de la propiedad `Species` de pública a privada.</span><span class="sxs-lookup"><span data-stu-id="ff274-542">The following example illustrates the error that is generated when the [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is set to `true`, and `Person`, which is a class derived from `Animal`, tries to change the accessibility of the `Species` property from public to private.</span></span> <span data-ttu-id="ff274-543">El ejemplo se compila correctamente si su accesibilidad se cambia a pública.</span><span class="sxs-lookup"><span data-stu-id="ff274-543">The example compiles successfully if its accessibility is changed to public.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class Animal
{
   private string _species;

   public Animal(string species)
   {
      _species = species;
   }

   public virtual string Species
   {
      get { return _species; }
   }

   public override string ToString()
   {
      return _species;
   }
}

public class Human : Animal
{
   private string _name;

   public Human(string name) : base("Homo Sapiens")
   {
      _name = name;
   }

   public string Name
   {
      get { return _name; }
   }

   private override string Species
   {
      get { return base.Species; }
   }

   public override string ToString()
   {
      return _name;
   }
}

public class Example
{
   public static void Main()
   {
      Human p = new Human("John");
      Console.WriteLine(p.Species);
      Console.WriteLine(p.ToString());
   }
}
// The example displays the following output:
//    error CS0621: 'Human.Species': virtual or abstract members cannot be private
```

```vb
<Assembly: CLSCompliant(True)>

Public Class Animal
   Private _species As String

   Public Sub New(species As String)
      _species = species
   End Sub

   Public Overridable ReadOnly Property Species As String
      Get
         Return _species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _species
   End Function
End Class

Public Class Human : Inherits Animal
   Private _name As String

   Public Sub New(name As String)
      MyBase.New("Homo Sapiens")
      _name = name
   End Sub

   Public ReadOnly Property Name As String
      Get
         Return _name
      End Get
   End Property

   Private Overrides ReadOnly Property Species As String
      Get
         Return MyBase.Species
      End Get
   End Property

   Public Overrides Function ToString() As String
      Return _name
   End Function
End Class

Public Module Example
   Public Sub Main()
      Dim p As New Human("John")
      Console.WriteLine(p.Species)
      Console.WriteLine(p.ToString())
   End Sub
End Module
' The example displays the following output:
'     'Private Overrides ReadOnly Property Species As String' cannot override
'     'Public Overridable ReadOnly Property Species As String' because
'      they have different access levels.
'
'         Private Overrides ReadOnly Property Species As String
```

<span data-ttu-id="ff274-544">Los tipos de la signatura de un miembro deben estar accesibles siempre que dicho miembro esté accesible.</span><span class="sxs-lookup"><span data-stu-id="ff274-544">Types in the signature of a member must be accessible whenever that member is accessible.</span></span> <span data-ttu-id="ff274-545">Esto significa, por ejemplo, que un miembro público no puede incluir un parámetro cuyo tipo sea privado, protegido o interno.</span><span class="sxs-lookup"><span data-stu-id="ff274-545">For example, this means that a public member cannot include a parameter whose type is private, protected, or internal.</span></span> <span data-ttu-id="ff274-546">En el ejemplo siguiente se muestra el error del compilador que se produce cuando un constructor de clase `StringWrapper` expone un valor de enumeración `StringOperationType` interno que determina cómo debe ajustarse un valor de cadena.</span><span class="sxs-lookup"><span data-stu-id="ff274-546">The following example illustrates the compiler error that results when a `StringWrapper` class constructor exposes an internal `StringOperationType` enumeration value that determines how a string value should be wrapped.</span></span>

```csharp
using System;
using System.Text;

public class StringWrapper
{
   string internalString;
   StringBuilder internalSB = null;
   bool useSB = false;

   public StringWrapper(StringOperationType type)
   {
      if (type == StringOperationType.Normal) {
         useSB = false;
      }
      else {
         useSB = true;
         internalSB = new StringBuilder();
      }
   }

   // The remaining source code...
}

internal enum StringOperationType { Normal, Dynamic }
// The attempt to compile the example displays the following output:
//    error CS0051: Inconsistent accessibility: parameter type
//            'StringOperationType' is less accessible than method
//            'StringWrapper.StringWrapper(StringOperationType)'
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class StringWrapper

   Dim internalString As String
   Dim internalSB As StringBuilder = Nothing
   Dim useSB As Boolean = False

   Public Sub New(type As StringOperationType)
      If type = StringOperationType.Normal Then
         useSB = False
      Else
         internalSB = New StringBuilder()
         useSB = True
      End If
   End Sub

   ' The remaining source code...
End Class

Friend Enum StringOperationType As Integer
   Normal = 0
   Dynamic = 1
End Enum
' The attempt to compile the example displays the following output:
'    error BC30909: 'type' cannot expose type 'StringOperationType'
'     outside the project through class 'StringWrapper'.
'
'       Public Sub New(type As StringOperationType)
'                              ~~~~~~~~~~~~~~~~~~~
```

### <a name="generic-types-and-members"></a><span data-ttu-id="ff274-547">Miembros y tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="ff274-547">Generic types and members</span></span>

<span data-ttu-id="ff274-548">Los tipos anidados siempre tienen, como mínimo, el mismo número de parámetros genéricos que el tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="ff274-548">Nested types always have at least as many generic parameters as their enclosing type.</span></span> <span data-ttu-id="ff274-549">Estos se corresponden por posición con los parámetros genéricos del tipo envolvente.</span><span class="sxs-lookup"><span data-stu-id="ff274-549">These correspond by position to the generic parameters in the enclosing type.</span></span> <span data-ttu-id="ff274-550">El tipo genérico también puede incluir nuevos parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="ff274-550">The generic type can also include new generic parameters.</span></span>

<span data-ttu-id="ff274-551">Las relaciones entre los parámetros de tipo genérico de un tipo envolvente y sus tipos anidados se pueden ocultar en la sintaxis de cada lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-551">The relationship between the generic type parameters of a containing type and its nested types may be hidden by the syntax of individual languages.</span></span> <span data-ttu-id="ff274-552">En el ejemplo siguiente, un tipo genérico `Outer<T>` contiene dos clases anidadas: `Inner1A` e `Inner1B<U>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-552">In the following example, a generic type `Outer<T>` contains two nested classes, `Inner1A` and `Inner1B<U>`.</span></span> <span data-ttu-id="ff274-553">Las llamadas al método `ToString`, donde cada clase hereda de `Object.ToString`, muestran que cada clase anidada contiene los parámetros de tipo de la clase contenedora.</span><span class="sxs-lookup"><span data-stu-id="ff274-553">The calls to the `ToString` method, which each class inherits from `Object.ToString`, show that each nested class includes the type parameters of its containing class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Outer<T>
{
   T value;

   public Outer(T value)
   {
      this.value = value;
   }

   public class Inner1A : Outer<T>
   {
      public Inner1A(T value) : base(value)
      {  }
   }

   public class Inner1B<U> : Outer<T>
   {
      U value2;

      public Inner1B(T value1, U value2) : base(value1)
      {
         this.value2 = value2;
      }
   }
}

public class Example
{
   public static void Main()
   {
      var inst1 = new Outer<String>("This");
      Console.WriteLine(inst1);

      var inst2 = new Outer<String>.Inner1A("Another");
      Console.WriteLine(inst2);

      var inst3 = new Outer<String>.Inner1B<int>("That", 2);
      Console.WriteLine(inst3);
   }
}
// The example displays the following output:
//       Outer`1[System.String]
//       Outer`1+Inner1A[System.String]
//       Outer`1+Inner1B`1[System.String,System.Int32]
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Outer(Of T)
   Dim value As T

   Public Sub New(value As T)
      Me.value = value
   End Sub

   Public Class Inner1A : Inherits Outer(Of T)
      Public Sub New(value As T)
         MyBase.New(value)
      End Sub
   End Class

   Public Class Inner1B(Of U) : Inherits Outer(Of T)
      Dim value2 As U

      Public Sub New(value1 As T, value2 As U)
         MyBase.New(value1)
         Me.value2 = value2
      End Sub
   End Class
End Class

Public Module Example
   Public Sub Main()
      Dim inst1 As New Outer(Of String)("This")
      Console.WriteLine(inst1)

      Dim inst2 As New Outer(Of String).Inner1A("Another")
      Console.WriteLine(inst2)

      Dim inst3 As New Outer(Of String).Inner1B(Of Integer)("That", 2)
      Console.WriteLine(inst3)
   End Sub
End Module
' The example displays the following output:
'       Outer`1[System.String]
'       Outer`1+Inner1A[System.String]
'       Outer`1+Inner1B`1[System.String,System.Int32]
```

<span data-ttu-id="ff274-554">Los nombres de tipos genéricos se codifican con el formato *name* *n*, donde *name* es el nombre del tipo, *\`* es un carácter literal y *n* es el número de parámetros declarados en el tipo o, en el caso de tipos genéricos anidados, el número de parámetros de tipo recién incorporados.</span><span class="sxs-lookup"><span data-stu-id="ff274-554">Generic type names are encoded in the form *name*'*n*, where *name* is the type name, *\`* is a character literal, and *n* is the number of parameters declared on the type, or, for nested generic types, the number of newly introduced type parameters.</span></span> <span data-ttu-id="ff274-555">Esta codificación de nombres de tipo genérico tiene interés fundamentalmente para los desarrolladores que utilizan la reflexión a fin de acceder a los tipos genéricos conformes a CLS de una biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ff274-555">This encoding of generic type names is primarily of interest to developers who use reflection to access CLS-complaint generic types in a library.</span></span>

<span data-ttu-id="ff274-556">Si las restricciones se aplican a un tipo genérico, los tipos utilizados como restricciones también deben ser conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-556">If constraints are applied to a generic type, any types used as constraints must also be CLS-compliant.</span></span> <span data-ttu-id="ff274-557">En el ejemplo siguiente se define una clase denominada `BaseClass` que no es conforme a CLS y una clase genérica denominada `BaseCollection` cuyo parámetro de tipo debe derivarse de `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="ff274-557">The following example defines a class named `BaseClass` that is not CLS-compliant and a generic class named `BaseCollection` whose type parameter must derive from `BaseClass`.</span></span> <span data-ttu-id="ff274-558">Sin embargo, puesto que `BaseClass` no es conforme a CLS, el compilador emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ff274-558">But because `BaseClass` is not CLS-compliant, the compiler emits a warning.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

[CLSCompliant(false)] public class BaseClass
{}

public class BaseCollection<T> where T : BaseClass
{}
// Attempting to compile the example displays the following output:
//    warning CS3024: Constraint type 'BaseClass' is not CLS-compliant
```

```vb
Assembly: CLSCompliant(True)>

<CLSCompliant(False)> Public Class BaseClass
End Class

Public Class BaseCollection(Of T As BaseClass)
End Class
' Attempting to compile the example displays the following output:
'    warning BC40040: Generic parameter constraint type 'BaseClass' is not
'    CLS-compliant.
'
'    Public Class BaseCollection(Of T As BaseClass)
'                                        ~~~~~~~~~
```

<span data-ttu-id="ff274-559">Si un tipo genérico se deriva de un tipo base genérico, es necesario volver a declarar las restricciones para que se pueda garantizar que las restricciones del tipo base también se cumplen.</span><span class="sxs-lookup"><span data-stu-id="ff274-559">If a generic type is derived from a generic base type, it must redeclare any constraints so that it can guarantee that constraints on the base type are also satisfied.</span></span> <span data-ttu-id="ff274-560">En el ejemplo siguiente se define un objeto `Number<T>` que puede representar cualquier tipo numérico.</span><span class="sxs-lookup"><span data-stu-id="ff274-560">The following example defines a `Number<T>` that can represent any numeric type.</span></span> <span data-ttu-id="ff274-561">También se define una clase `FloatingPoint<T>` que representa un valor de punto flotante.</span><span class="sxs-lookup"><span data-stu-id="ff274-561">It also defines a `FloatingPoint<T>` class that represents a floating point value.</span></span> <span data-ttu-id="ff274-562">Sin embargo, el código fuente no puede compilarse, ya que no aplica la restricción de `Number<T>` (T debe ser un tipo de valor) en `FloatingPoint<T>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-562">However, the source code fails to compile, because it does not apply the constraint on `Number<T>` (that T must be a value type) to `FloatingPoint<T>`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T>
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
// The attempt to compile the example displays the following output:
//       error CS0453: The type 'T' must be a non-nullable value type in
//               order to use it as parameter 'T' in the generic type or method 'Number<T>'
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
' The attempt to compile the example displays the following output:
'    error BC32105: Type argument 'T' does not satisfy the 'Structure'
'    constraint for type parameter 'T'.
'
'    Public Class FloatingPoint(Of T) : Inherits Number(Of T)
'                                                          ~
```

<span data-ttu-id="ff274-563">El ejemplo se compila correctamente si se agrega la restricción a la clase `FloatingPoint<T>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-563">The example compiles successfully if the constraint is added to the `FloatingPoint<T>` class.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class Number<T> where T : struct
{
   // use Double as the underlying type, since its range is a superset of
   // the ranges of all numeric types except BigInteger.
   protected double number;

   public Number(T value)
   {
      try {
         this.number = Convert.ToDouble(value);
      }
      catch (OverflowException e) {
         throw new ArgumentException("value is too large.", e);
      }
      catch (InvalidCastException e) {
         throw new ArgumentException("The value parameter is not numeric.", e);
      }
   }

   public T Add(T value)
   {
      return (T) Convert.ChangeType(number + Convert.ToDouble(value), typeof(T));
   }

   public T Subtract(T value)
   {
      return (T) Convert.ChangeType(number - Convert.ToDouble(value), typeof(T));
   }
}

public class FloatingPoint<T> : Number<T> where T : struct
{
   public FloatingPoint(T number) : base(number)
   {
      if (typeof(float) == number.GetType() ||
          typeof(double) == number.GetType() ||
          typeof(decimal) == number.GetType())
         this.number = Convert.ToDouble(number);
      else
         throw new ArgumentException("The number parameter is not a floating-point number.");
   }
}
```

```vb
<Assembly:CLSCompliant(True)>

Public Class Number(Of T As Structure)
   ' Use Double as the underlying type, since its range is a superset of
   ' the ranges of all numeric types except BigInteger.
   Protected number As Double

   Public Sub New(value As T)
      Try
         Me.number = Convert.ToDouble(value)
      Catch e As OverflowException
         Throw New ArgumentException("value is too large.", e)
      Catch e As InvalidCastException
         Throw New ArgumentException("The value parameter is not numeric.", e)
      End Try
   End Sub

   Public Function Add(value As T) As T
      Return CType(Convert.ChangeType(number + Convert.ToDouble(value), GetType(T)), T)
   End Function

   Public Function Subtract(value As T) As T
      Return CType(Convert.ChangeType(number - Convert.ToDouble(value), GetType(T)), T)
   End Function
End Class

Public Class FloatingPoint(Of T As Structure) : Inherits Number(Of T)
   Public Sub New(number As T)
      MyBase.New(number)
      If TypeOf number Is Single Or
               TypeOf number Is Double Or
               TypeOf number Is Decimal Then
         Me.number = Convert.ToDouble(number)
      Else
         throw new ArgumentException("The number parameter is not a floating-point number.")
      End If
   End Sub
End Class
```

<span data-ttu-id="ff274-564">Common Language Specification impone un modelo conservador adaptado a cada instancia en los tipos anidados y los miembros protegidos.</span><span class="sxs-lookup"><span data-stu-id="ff274-564">The Common Language Specification imposes a conservative per-instantiation model for nested types and protected members.</span></span> <span data-ttu-id="ff274-565">Los tipos genéricos abiertos no pueden exponer campos ni miembros con signaturas que contengan una instancia específica de un tipo genérico anidado y protegido.</span><span class="sxs-lookup"><span data-stu-id="ff274-565">Open generic types cannot expose fields or members with signatures that contain a specific instantiation of a nested, protected generic type.</span></span> <span data-ttu-id="ff274-566">Los tipos no genéricos que amplíen una instancia específica de una interfaz o clase base genérica no pueden exponer campos ni miembros con signaturas que contengan otra instancia de un tipo genérico anidado y protegido.</span><span class="sxs-lookup"><span data-stu-id="ff274-566">Non-generic types that extend a specific instantiation of a generic base class or interface cannot expose fields or members with signatures that contain a different instantiation of a nested, protected generic type.</span></span>

<span data-ttu-id="ff274-567">En el ejemplo siguiente se define un tipo genérico, `C1<T>`, y una clase protegida, `C1<T>.N`.</span><span class="sxs-lookup"><span data-stu-id="ff274-567">The following example defines a generic type, `C1<T>`, and a protected class, `C1<T>.N`.</span></span> <span data-ttu-id="ff274-568">`C1<T>` tiene dos métodos: `M1` y `M2`.</span><span class="sxs-lookup"><span data-stu-id="ff274-568">`C1<T>` has two methods, `M1` and `M2`.</span></span> <span data-ttu-id="ff274-569">Pero `M1` no es conforme a CLS porque intenta devolver un objeto `C1<int>.N` a partir de `C1<T>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-569">However, `M1` is not CLS-compliant because it tries to return a `C1<int>.N` object from `C1<T>`.</span></span> <span data-ttu-id="ff274-570">Una segunda clase, `C2`, se deriva de `C1<long>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-570">A second class, `C2`, is derived from `C1<long>`.</span></span> <span data-ttu-id="ff274-571">Esta clase tiene dos métodos, `M3` y `M4`.</span><span class="sxs-lookup"><span data-stu-id="ff274-571">It has two methods, `M3` and `M4`.</span></span> <span data-ttu-id="ff274-572">`M3` o es conforme a CLS porque intenta devolver un objeto `C1<int>.N` a partir de una subclase de `C1<long>`.</span><span class="sxs-lookup"><span data-stu-id="ff274-572">`M3` is not CLS-compliant because it tries to return a `C1<int>.N` object from a subclass of `C1<long>`.</span></span> <span data-ttu-id="ff274-573">Observe que los compiladores del lenguaje pueden ser aun más restrictivos.</span><span class="sxs-lookup"><span data-stu-id="ff274-573">Note that language compilers can be even more restrictive.</span></span> <span data-ttu-id="ff274-574">En este ejemplo, Visual Basic muestra un error cuando intenta compilar `M4`.</span><span class="sxs-lookup"><span data-stu-id="ff274-574">In this example, Visual Basic displays an error when it tries to compile `M4`.</span></span>

```csharp
using System;

[assembly:CLSCompliant(true)]

public class C1<T>
{
   protected class N { }

   protected void M1(C1<int>.N n) { } // Not CLS-compliant - C1<int>.N not
                                      // accessible from within C1<T> in all
                                      // languages
   protected void M2(C1<T>.N n) { }   // CLS-compliant – C1<T>.N accessible
                                      // inside C1<T>
}

public class C2 : C1<long>
{
   protected void M3(C1<int>.N n) { }  // Not CLS-compliant – C1<int>.N is not
                                       // accessible in C2 (extends C1<long>)

   protected void M4(C1<long>.N n) { } // CLS-compliant, C1<long>.N is
                                       // accessible in C2 (extends C1<long>)
}
// Attempting to compile the example displays output like the following:
//       Generics4.cs(9,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
//       Generics4.cs(18,22): warning CS3001: Argument type 'C1<int>.N' is not CLS-compliant
```

```vb
<Assembly:CLSCompliant(True)>

Public Class C1(Of T)
   Protected Class N
   End Class

   Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
                                             ' accessible from within C1(Of T) in all
   End Sub                                   ' languages

   Protected Sub M2(n As C1(Of T).N)     ' CLS-compliant – C1(Of T).N accessible
   End Sub                               ' inside C1(Of T)
End Class

Public Class C2 : Inherits C1(Of Long)
   Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant – C1(Of Integer).N is not
   End Sub                                   ' accessible in C2 (extends C1(Of Long))

   Protected Sub M4(n As C1(Of Long).N)
   End Sub
End Class
' Attempting to compile the example displays output like the following:
'    error BC30508: 'n' cannot expose type 'C1(Of Integer).N' in namespace
'    '<Default>' through class 'C1'.
'
'       Protected Sub M1(n As C1(Of Integer).N)   ' Not CLS-compliant - C1<int>.N not
'                             ~~~~~~~~~~~~~~~~
'    error BC30389: 'C1(Of T).N' is not accessible in this context because
'    it is 'Protected'.
'
'       Protected Sub M3(n As C1(Of Integer).N)   ' Not CLS-compliant - C1(Of Integer).N is not
'
'                             ~~~~~~~~~~~~~~~~
'
'    error BC30389: 'C1(Of T).N' is not accessible in this context because it is 'Protected'.
'
'       Protected Sub M4(n As C1(Of Long).N)
'                             ~~~~~~~~~~~~~
```

### <a name="constructors"></a><span data-ttu-id="ff274-575">Constructores</span><span class="sxs-lookup"><span data-stu-id="ff274-575">Constructors</span></span>

<span data-ttu-id="ff274-576">Los constructores de clases y estructuras conformes a CLS deben seguir estas reglas:</span><span class="sxs-lookup"><span data-stu-id="ff274-576">Constructors in CLS-compliant classes and structures must follow these rules:</span></span>

* <span data-ttu-id="ff274-577">Un constructor de una clase derivada debe llamar al constructor de instancia de su clase base antes de tener acceso a datos de instancia heredados.</span><span class="sxs-lookup"><span data-stu-id="ff274-577">A constructor of a derived class must call the instance constructor of its base class before it accesses inherited instance data.</span></span> <span data-ttu-id="ff274-578">Este requisito se debe al hecho de que los constructores de clase base no se heredan por sus clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="ff274-578">This requirement is due to the fact that base class constructors are not inherited by their derived classes.</span></span> <span data-ttu-id="ff274-579">Esta regla no se aplica a las estructuras, que no admiten la herencia directa.</span><span class="sxs-lookup"><span data-stu-id="ff274-579">This rule does not apply to structures, which do not support direct inheritance.</span></span>

  <span data-ttu-id="ff274-580">Normalmente, los compiladores aplican esta regla independientemente de la conformidad con CLS, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="ff274-580">Typically, compilers enforce this rule independently of CLS compliance, as the following example shows.</span></span> <span data-ttu-id="ff274-581">En este ejemplo, se crea una clase `Doctor` que se deriva de una clase `Person`, pero la clase `Doctor` no consigue llamar al constructor de la clase `Person` para inicializar los campos de instancia heredados.</span><span class="sxs-lookup"><span data-stu-id="ff274-581">It creates a `Doctor` class that is derived from a `Person` class, but the `Doctor` class fails to call the `Person` class constructor to initialize inherited instance fields.</span></span>

    ```csharp
    using System;

    [assembly: CLSCompliant(true)]

    public class Person
    {
    private string fName, lName, _id;

    public Person(string firstName, string lastName, string id)
    {
        if (String.IsNullOrEmpty(firstName + lastName))
            throw new ArgumentNullException("Either a first name or a last name must be provided.");

        fName = firstName;
        lName = lastName;
        _id = id;
    }

    public string FirstName
    {
        get { return fName; }
    }

    public string LastName
    {
        get { return lName; }
    }

    public string Id
    {
        get { return _id; }
    }

    public override string ToString()
    {
        return String.Format("{0}{1}{2}", fName,
                            String.IsNullOrEmpty(fName) ?  "" : " ",
                            lName);
    }
    }

    public class Doctor : Person
    {
    public Doctor(string firstName, string lastName, string id)
    {
    }

    public override string ToString()
    {
        return "Dr. " + base.ToString();
    }
    }
    // Attempting to compile the example displays output like the following:
    //    ctor1.cs(45,11): error CS1729: 'Person' does not contain a constructor that takes 0
    //            arguments
    //    ctor1.cs(10,11): (Location of symbol related to previous error)
    ```

    ```vb
    <Assembly: CLSCompliant(True)>

    Public Class Person
       Private fName, lName, _id As String

       Public Sub New(firstName As String, lastName As String, id As String)
          If String.IsNullOrEmpty(firstName + lastName) Then
             Throw New ArgumentNullException("Either a first name or a last name must be provided.")
          End If

          fName = firstName
          lName = lastName
          _id = id
       End Sub

       Public ReadOnly Property FirstName As String
          Get
             Return fName
          End Get
       End Property

       Public ReadOnly Property LastName As String
          Get
             Return lName
          End Get
       End Property

       Public ReadOnly Property Id As String
          Get
             Return _id
          End Get
       End Property

       Public Overrides Function ToString() As String
          Return String.Format("{0}{1}{2}", fName,
                               If(String.IsNullOrEmpty(fName), "", " "),
                               lName)
       End Function
    End Class

    Public Class Doctor : Inherits Person
       Public Sub New(firstName As String, lastName As String, id As String)
       End Sub

       Public Overrides Function ToString() As String
          Return "Dr. " + MyBase.ToString()
       End Function
    End Class
    ' Attempting to compile the example displays output like the following:
    '    Ctor1.vb(46) : error BC30148: First statement of this 'Sub New' must be a call
    '    to 'MyBase.New' or 'MyClass.New' because base class 'Person' of 'Doctor' does
    '    not have an accessible 'Sub New' that can be called with no arguments.
    '
    '       Public Sub New()
    '                  ~~~
    ````

* <span data-ttu-id="ff274-582">No se puede llamar a un constructor de objetos excepto para crear un objeto.</span><span class="sxs-lookup"><span data-stu-id="ff274-582">An object constructor cannot be called except to create an object.</span></span> <span data-ttu-id="ff274-583">Además, un objeto no se puede inicializar dos veces.</span><span class="sxs-lookup"><span data-stu-id="ff274-583">In addition, an object cannot be initialized twice.</span></span> <span data-ttu-id="ff274-584">Por ejemplo, esto significa que `Object.MemberwiseClone` no debe llamar a los constructores.</span><span class="sxs-lookup"><span data-stu-id="ff274-584">For example, this means that `Object.MemberwiseClone` must not call constructors.</span></span>

### <a name="properties"></a><span data-ttu-id="ff274-585">Propiedades</span><span class="sxs-lookup"><span data-stu-id="ff274-585">Properties</span></span>

<span data-ttu-id="ff274-586">Las propiedades de los tipos conformes a CLS deben seguir estas reglas:</span><span class="sxs-lookup"><span data-stu-id="ff274-586">Properties in CLS-compliant types must follow these rules:</span></span>

* <span data-ttu-id="ff274-587">Una propiedad debe tener un establecedor, un captador o ambos.</span><span class="sxs-lookup"><span data-stu-id="ff274-587">A property must have a setter, a getter, or both.</span></span> <span data-ttu-id="ff274-588">En un ensamblado, estos elementos se implementan como métodos especiales, lo que significa que aparecerán como métodos independientes (el captador se llama `get`\_*propertyname* y el establecedor es `set`\_*propertyname*) marcados como `SpecialName` en los metadatos del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ff274-588">In an assembly, these are implemented as special methods, which means that they will appear as separate methods (the getter is named `get`\_*propertyname* and the setter is `set`\_*propertyname*) marked as `SpecialName` in the assembly's metadata.</span></span> <span data-ttu-id="ff274-589">El compilador de C# aplica esta regla automáticamente sin necesidad de aplicar el atributo <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ff274-589">The C# compiler enforces this rule automatically without the need to apply the <xref:System.CLSCompliantAttribute> attribute.</span></span>

* <span data-ttu-id="ff274-590">El tipo de una propiedad es el tipo de valor devuelto del captador de la propiedad y el último argumento del establecedor.</span><span class="sxs-lookup"><span data-stu-id="ff274-590">A property's type is the return type of the property getter and the last argument of the setter.</span></span> <span data-ttu-id="ff274-591">Estos tipos deben ser conformes a CLS y los argumentos no se pueden asignar a la propiedad por referencia (es decir, no pueden ser punteros administrados).</span><span class="sxs-lookup"><span data-stu-id="ff274-591">These types must be CLS compliant, and arguments cannot be assigned to the property by reference (that is, they cannot be managed pointers).</span></span>

* <span data-ttu-id="ff274-592">Si una propiedad tiene un captador y un establecedor, estos deben ser virtuales, estáticos o de instancia.</span><span class="sxs-lookup"><span data-stu-id="ff274-592">If a property has both a getter and a setter, they must both be virtual, both static, or both instance.</span></span> <span data-ttu-id="ff274-593">El compilador de C# aplica automáticamente esta regla mediante la sintaxis de la definición de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="ff274-593">The C# compiler automatically enforces this rule through property definition syntax.</span></span>

### <a name="events"></a><span data-ttu-id="ff274-594">Events</span><span class="sxs-lookup"><span data-stu-id="ff274-594">Events</span></span>

<span data-ttu-id="ff274-595">Un evento se define por su nombre y su tipo.</span><span class="sxs-lookup"><span data-stu-id="ff274-595">An event is defined by its name and its type.</span></span> <span data-ttu-id="ff274-596">El tipo de evento es un delegado que se utiliza para indicar el evento.</span><span class="sxs-lookup"><span data-stu-id="ff274-596">The event type is a delegate that is used to indicate the event.</span></span> <span data-ttu-id="ff274-597">Por ejemplo, el evento `DbConnection.StateChange` es del tipo `StateChangeEventHandler`.</span><span class="sxs-lookup"><span data-stu-id="ff274-597">For example, the `DbConnection.StateChange` event is of type `StateChangeEventHandler`.</span></span> <span data-ttu-id="ff274-598">Además del propio evento, hay tres métodos con nombres basados en el nombre de evento que proporcionan la implementación del evento y que se marcan como `SpecialName` en los metadatos de ensamblado:</span><span class="sxs-lookup"><span data-stu-id="ff274-598">In addition to the event itself, three methods with names based on the event name provide the event's implementation and are marked as `SpecialName` in the assembly's metadata:</span></span>

* <span data-ttu-id="ff274-599">Un método para agregar un controlador de eventos, llamado `add`_*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ff274-599">A method for adding an event handler, named `add`_*EventName*.</span></span> <span data-ttu-id="ff274-600">Por ejemplo, el método de suscripción de eventos del evento `DbConnection.StateChange` se denomina `add_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="ff274-600">For example, the event subscription method for the `DbConnection.StateChange` event is named `add_StateChange`.</span></span>

* <span data-ttu-id="ff274-601">Un método para quitar un controlador de eventos, llamado `remove`_*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ff274-601">A method for removing an event handler, named `remove`_*EventName*.</span></span> <span data-ttu-id="ff274-602">Por ejemplo, el método de eliminación del evento `DbConnection.StateChange` se denomina `remove_StateChange`.</span><span class="sxs-lookup"><span data-stu-id="ff274-602">For example, the removal method for the `DbConnection.StateChange` event is named `remove_StateChange`.</span></span>

* <span data-ttu-id="ff274-603">Un método para indicar que el evento se ha producido, llamado `raise`\_*EventName*.</span><span class="sxs-lookup"><span data-stu-id="ff274-603">A method for indicating that the event has occurred, named `raise`\_*EventName*.</span></span>

> [!NOTE]
> <span data-ttu-id="ff274-604">La mayoría de las reglas de Common Language Specification relacionadas con los eventos se implementan mediante compiladores del lenguaje y son transparentes para los desarrolladores de componentes.</span><span class="sxs-lookup"><span data-stu-id="ff274-604">Most of the Common Language Specification's rules regarding events are implemented by language compilers and are transparent to component developers.</span></span>

<span data-ttu-id="ff274-605">Los métodos para agregar, quitar y generar el evento deben tener la misma accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="ff274-605">The methods for adding, removing, and raising the event must have the same accessibility.</span></span> <span data-ttu-id="ff274-606">Además, todos deben ser estáticos, virtuales o de instancia.</span><span class="sxs-lookup"><span data-stu-id="ff274-606">They must also all be static, instance, or virtual.</span></span> <span data-ttu-id="ff274-607">Los métodos para agregar y quitar un evento tienen un parámetro cuyo tipo es el mismo que el del delegado de eventos.</span><span class="sxs-lookup"><span data-stu-id="ff274-607">The methods for adding and removing an event have one parameter whose type is the event delegate type.</span></span> <span data-ttu-id="ff274-608">Los métodos para agregar y quitar deben estar presentes o ausentes al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ff274-608">The add and remove methods must both be present or both be absent.</span></span>

<span data-ttu-id="ff274-609">En el ejemplo siguiente se define una clase conforme a CLS denominada `Temperature` que genera un evento `TemperatureChanged` si el cambio de temperatura entre dos lecturas es igual o mayor que el valor de umbral.</span><span class="sxs-lookup"><span data-stu-id="ff274-609">The following example defines a CLS-compliant class named `Temperature` that raises a `TemperatureChanged` event if the change in temperature between two readings equals or exceeds a threshold value.</span></span> <span data-ttu-id="ff274-610">La clase `Temperature` define de manera explícita un método `raise_TemperatureChanged` para que pueda ejecutar controladores de eventos de forma selectiva.</span><span class="sxs-lookup"><span data-stu-id="ff274-610">The `Temperature` class explicitly defines a `raise_TemperatureChanged` method so that it can selectively execute event handlers.</span></span>

```csharp
using System;
using System.Collections;
using System.Collections.Generic;

[assembly: CLSCompliant(true)]

public class TemperatureChangedEventArgs : EventArgs
{
   private Decimal originalTemp;
   private Decimal newTemp;
   private DateTimeOffset when;

   public TemperatureChangedEventArgs(Decimal original, Decimal @new, DateTimeOffset time)
   {
      originalTemp = original;
      newTemp = @new;
      when = time;
   }

   public Decimal OldTemperature
   {
      get { return originalTemp; }
   }

   public Decimal CurrentTemperature
   {
      get { return newTemp; }
   }

   public DateTimeOffset Time
   {
      get { return when; }
   }
}

public delegate void TemperatureChanged(Object sender, TemperatureChangedEventArgs e);

public class Temperature
{
   private struct TemperatureInfo
   {
      public Decimal Temperature;
      public DateTimeOffset Recorded;
   }

   public event TemperatureChanged TemperatureChanged;

   private Decimal previous;
   private Decimal current;
   private Decimal tolerance;
   private List<TemperatureInfo> tis = new List<TemperatureInfo>();

   public Temperature(Decimal temperature, Decimal tolerance)
   {
      current = temperature;
      TemperatureInfo ti = new TemperatureInfo();
      ti.Temperature = temperature;
      tis.Add(ti);
      ti.Recorded = DateTimeOffset.UtcNow;
      this.tolerance = tolerance;
   }

   public Decimal CurrentTemperature
   {
      get { return current; }
      set {
         TemperatureInfo ti = new TemperatureInfo();
         ti.Temperature = value;
         ti.Recorded = DateTimeOffset.UtcNow;
         previous = current;
         current = value;
         if (Math.Abs(current - previous) >= tolerance)
            raise_TemperatureChanged(new TemperatureChangedEventArgs(previous, current, ti.Recorded));
      }
   }

   public void raise_TemperatureChanged(TemperatureChangedEventArgs eventArgs)
   {
      if (TemperatureChanged == null)
         return;

      foreach (TemperatureChanged d in TemperatureChanged.GetInvocationList()) {
         if (d.Method.Name.Contains("Duplicate"))
            Console.WriteLine("Duplicate event handler; event handler not executed.");
         else
            d.Invoke(this, eventArgs);
      }
   }
}

public class Example
{
   public Temperature temp;

   public static void Main()
   {
      Example ex = new Example();
   }

   public Example()
   {
      temp = new Temperature(65, 3);
      temp.TemperatureChanged += this.TemperatureNotification;
      RecordTemperatures();
      Example ex = new Example(temp);
      ex.RecordTemperatures();
   }

   public Example(Temperature t)
   {
      temp = t;
      RecordTemperatures();
   }

   public void RecordTemperatures()
   {
      temp.TemperatureChanged += this.DuplicateTemperatureNotification;
      temp.CurrentTemperature = 66;
      temp.CurrentTemperature = 63;
   }

   internal void TemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }

   public void DuplicateTemperatureNotification(Object sender, TemperatureChangedEventArgs e)
   {
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature);
   }
}
```

```vb
Imports System.Collections
Imports System.Collections.Generic

<Assembly: CLSCompliant(True)>

Public Class TemperatureChangedEventArgs   : Inherits EventArgs
   Private originalTemp As Decimal
   Private newTemp As Decimal
   Private [when] As DateTimeOffset

   Public Sub New(original As Decimal, [new] As Decimal, [time] As DateTimeOffset)
      originalTemp = original
      newTemp = [new]
      [when] = [time]
   End Sub

   Public ReadOnly Property OldTemperature As Decimal
      Get
         Return originalTemp
      End Get
   End Property

   Public ReadOnly Property CurrentTemperature As Decimal
      Get
         Return newTemp
      End Get
   End Property

   Public ReadOnly Property [Time] As DateTimeOffset
      Get
         Return [when]
      End Get
   End Property
End Class

Public Delegate Sub TemperatureChanged(sender As Object, e As TemperatureChangedEventArgs)

Public Class Temperature
   Private Structure TemperatureInfo
      Dim Temperature As Decimal
      Dim Recorded As DateTimeOffset
   End Structure

   Public Event TemperatureChanged As TemperatureChanged

   Private previous As Decimal
   Private current As Decimal
   Private tolerance As Decimal
   Private tis As New List(Of TemperatureInfo)

   Public Sub New(temperature As Decimal, tolerance As Decimal)
      current = temperature
      Dim ti As New TemperatureInfo()
      ti.Temperature = temperature
      ti.Recorded = DateTimeOffset.UtcNow
      tis.Add(ti)
      Me.tolerance = tolerance
   End Sub

   Public Property CurrentTemperature As Decimal
      Get
         Return current
      End Get
      Set
         Dim ti As New TemperatureInfo
         ti.Temperature = value
         ti.Recorded = DateTimeOffset.UtcNow
         previous = current
         current = value
         If Math.Abs(current - previous) >= tolerance Then
            raise_TemperatureChanged(New TemperatureChangedEventArgs(previous, current, ti.Recorded))
         End If
      End Set
   End Property

   Public Sub raise_TemperatureChanged(eventArgs As TemperatureChangedEventArgs)
      If TemperatureChangedEvent Is Nothing Then Exit Sub

      Dim ListenerList() As System.Delegate = TemperatureChangedEvent.GetInvocationList()
      For Each d As TemperatureChanged In TemperatureChangedEvent.GetInvocationList()
         If d.Method.Name.Contains("Duplicate") Then
            Console.WriteLine("Duplicate event handler; event handler not executed.")
         Else
            d.Invoke(Me, eventArgs)
         End If
      Next
   End Sub
End Class

Public Class Example
   Public WithEvents temp As Temperature

   Public Shared Sub Main()
      Dim ex As New Example()
   End Sub

   Public Sub New()
      temp = New Temperature(65, 3)
      RecordTemperatures()
      Dim ex As New Example(temp)
      ex.RecordTemperatures()
   End Sub

   Public Sub New(t As Temperature)
      temp = t
      RecordTemperatures()
   End Sub

   Public Sub RecordTemperatures()
      temp.CurrentTemperature = 66
      temp.CurrentTemperature = 63

   End Sub

   Friend Shared Sub TemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 1: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub

   Friend Shared Sub DuplicateTemperatureNotification(sender As Object, e As TemperatureChangedEventArgs) _
          Handles temp.TemperatureChanged
      Console.WriteLine("Notification 2: The temperature changed from {0} to {1}", e.OldTemperature, e.CurrentTemperature)
   End Sub
End Class
```

### <a name="overloads"></a><span data-ttu-id="ff274-611">Overloads</span><span class="sxs-lookup"><span data-stu-id="ff274-611">Overloads</span></span>

<span data-ttu-id="ff274-612">Common Language Specification impone los siguientes requisitos a los miembros sobrecargados:</span><span class="sxs-lookup"><span data-stu-id="ff274-612">The Common Language Specification imposes the following requirements on overloaded members:</span></span>

* <span data-ttu-id="ff274-613">Los miembros se pueden sobrecargar según el número de parámetros y el tipo de cualquiera de los parámetros.</span><span class="sxs-lookup"><span data-stu-id="ff274-613">Members can be overloaded based on the number of parameters and the type of any parameter.</span></span> <span data-ttu-id="ff274-614">A la hora de distinguir entre sobrecargas, no se tienen en cuenta los factores de convención de llamada, el tipo de valor devuelto, los modificadores personalizados aplicados al método o a su parámetro, ni si los parámetros se pasan por valor o por referencia.</span><span class="sxs-lookup"><span data-stu-id="ff274-614">Calling convention, return type, custom modifiers applied to the method or its parameter, and whether parameters are passed by value or by reference are not considered when differentiating between overloads.</span></span> <span data-ttu-id="ff274-615">Para consultar un ejemplo, vea el código del requisito que establece que los nombres deben ser únicos en cada ámbito que se incluye en la sección [Convenciones de nomenclatura](#naming-conventions).</span><span class="sxs-lookup"><span data-stu-id="ff274-615">For an example, see the code for the requirement that names must be unique within a scope in the [Naming conventions](#naming-conventions) section.</span></span>

* <span data-ttu-id="ff274-616">Solo las propiedades y los métodos se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="ff274-616">Only properties and methods can be overloaded.</span></span> <span data-ttu-id="ff274-617">Los campos y eventos no se pueden sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="ff274-617">Fields and events cannot be overloaded.</span></span>

* <span data-ttu-id="ff274-618">Los métodos genéricos pueden sobrecargarse en función del número de parámetros genéricos.</span><span class="sxs-lookup"><span data-stu-id="ff274-618">Generic methods can be overloaded based on the number of their generic parameters.</span></span>

> [!NOTE]
> <span data-ttu-id="ff274-619">Los operadores `op_Explicit` y `op_Implicit` son una excepción de la regla que establece que el valor devuelto no se considera parte de la signatura de un método en la resolución de la sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="ff274-619">The `op_Explicit` and `op_Implicit` operators are exceptions to the rule that return value is not considered part of a method signature for overload resolution.</span></span> <span data-ttu-id="ff274-620">Estos dos operadores se pueden sobrecargar según sus parámetros y su valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="ff274-620">These two operators can be overloaded based on both their parameters and their return value.</span></span>

### <a name="exceptions"></a><span data-ttu-id="ff274-621">Excepciones</span><span class="sxs-lookup"><span data-stu-id="ff274-621">Exceptions</span></span>

<span data-ttu-id="ff274-622">Los objetos de excepción deben derivar de [System.Exception](xref:System.Exception) o de otro tipo derivado de `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="ff274-622">Exception objects must derive from [System.Exception](xref:System.Exception) or from another type derived from `System.Exception`.</span></span> <span data-ttu-id="ff274-623">En el ejemplo siguiente se muestra el error de compilador que se produce cuando una clase personalizada denominada `ErrorClass` se utiliza para el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="ff274-623">The following example illustrates the compiler error that results when a custom class named `ErrorClass` is used for exception handling.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
// Compilation produces a compiler error like the following:
//    Exceptions1.cs(26,16): error CS0155: The type caught or thrown must be derived from
//            System.Exception
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
' Compilation produces a compiler error like the following:
'    Exceptions1.vb(27) : error BC30665: 'Throw' operand must derive from 'System.Exception'.
'
'             Throw BadIndex
'             ~~~~~~~~~~~~~~
```

<span data-ttu-id="ff274-624">Para corregir este error, la clase `ErrorClass` debe heredar de `System.Exception`.</span><span class="sxs-lookup"><span data-stu-id="ff274-624">To correct this error, the `ErrorClass` class must inherit from `System.Exception`.</span></span> <span data-ttu-id="ff274-625">Además, la propiedad Message debe invalidarse.</span><span class="sxs-lookup"><span data-stu-id="ff274-625">In addition, the Message property must be overridden.</span></span> <span data-ttu-id="ff274-626">En el ejemplo siguiente se corrigen estos errores para definir una clase `ErrorClass` que sea conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-626">The following example corrects these errors to define an `ErrorClass` class that is CLS-compliant.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

public class ErrorClass : Exception
{
   string msg;

   public ErrorClass(string errorMessage)
   {
      msg = errorMessage;
   }

   public override string Message
   {
      get { return msg; }
   }
}

public static class StringUtilities
{
   public static string[] SplitString(this string value, int index)
   {
      if (index < 0 | index > value.Length) {
         ErrorClass badIndex = new ErrorClass("The index is not within the string.");
         throw badIndex;
      }
      string[] retVal = { value.Substring(0, index - 1),
                          value.Substring(index) };
      return retVal;
   }
}
```

```vb
Imports System.Runtime.CompilerServices

<Assembly: CLSCompliant(True)>

Public Class ErrorClass : Inherits Exception
   Dim msg As String

   Public Sub New(errorMessage As String)
      msg = errorMessage
   End Sub

   Public Overrides ReadOnly Property Message As String
      Get
         Return msg
      End Get
   End Property
End Class

Public Module StringUtilities
   <Extension()> Public Function SplitString(value As String, index As Integer) As String()
      If index < 0 Or index > value.Length Then
         Dim BadIndex As New ErrorClass("The index is not within the string.")
         Throw BadIndex
      End If
      Dim retVal() As String = { value.Substring(0, index - 1),
                                 value.Substring(index) }
      Return retVal
   End Function
End Module
```

### <a name="attributes"></a><span data-ttu-id="ff274-627">Atributos</span><span class="sxs-lookup"><span data-stu-id="ff274-627">Attributes</span></span>

<span data-ttu-id="ff274-628">En los ensamblados de .NET Framework, los atributos personalizados proporcionan un mecanismo extensible para almacenar atributos personalizados y recuperar metadatos sobre objetos de programación, tales como ensamblados, tipos, miembros y parámetros de método.</span><span class="sxs-lookup"><span data-stu-id="ff274-628">In.NET Framework assemblies, custom attributes provide an extensible mechanism for storing custom attributes and retrieving metadata about programming objects, such as assemblies, types, members, and method parameters.</span></span> <span data-ttu-id="ff274-629">Los atributos personalizados deben derivar de [System.Attribute](xref:System.Attribute) o de un tipo derivado de `System.Attribute`.</span><span class="sxs-lookup"><span data-stu-id="ff274-629">Custom attributes must derive from [System.Attribute](xref:System.Attribute) or from a type derived from `System.Attribute`.</span></span>

<span data-ttu-id="ff274-630">En el ejemplo siguiente se infringe esta regla.</span><span class="sxs-lookup"><span data-stu-id="ff274-630">The following example violates this rule.</span></span> <span data-ttu-id="ff274-631">Define una clase `NumericAttribute` que no se deriva de `System.Attribute`.</span><span class="sxs-lookup"><span data-stu-id="ff274-631">It defines a `NumericAttribute` class that does not derive from `System.Attribute`.</span></span> <span data-ttu-id="ff274-632">Tenga en cuenta que un error del compilador solo se produce cuando se aplica el atributo no conforme a CLS, y no cuando se define la clase.</span><span class="sxs-lookup"><span data-stu-id="ff274-632">Note that a compiler error results only when the non-CLS-compliant attribute is applied, not when the class is defined.</span></span>

```csharp
using System;

[assembly: CLSCompliant(true)]

[AttributeUsageAttribute(AttributeTargets.Class | AttributeTargets.Struct)]
public class NumericAttribute
{
   private bool _isNumeric;

   public NumericAttribute(bool isNumeric)
   {
      _isNumeric = isNumeric;
   }

   public bool IsNumeric
   {
      get { return _isNumeric; }
   }
}

[Numeric(true)] public struct UDouble
{
   double Value;
}
// Compilation produces a compiler error like the following:
//    Attribute1.cs(22,2): error CS0616: 'NumericAttribute' is not an attribute class
//    Attribute1.cs(7,14): (Location of symbol related to previous error)
```

```vb
<Assembly: CLSCompliant(True)>

<AttributeUsageAttribute(AttributeTargets.Class Or AttributeTargets.Struct)> _
Public Class NumericAttribute
   Private _isNumeric As Boolean

   Public Sub New(isNumeric As Boolean)
      _isNumeric = isNumeric
   End Sub

   Public ReadOnly Property IsNumeric As Boolean
      Get
         Return _isNumeric
      End Get
   End Property
End Class

<Numeric(True)> Public Structure UDouble
   Dim Value As Double
End Structure
' Compilation produces a compiler error like the following:
'    error BC31504: 'NumericAttribute' cannot be used as an attribute because it
'    does not inherit from 'System.Attribute'.
'
'    <Numeric(True)> Public Structure UDouble
'     ~~~~~~~~~~~~~
```

<span data-ttu-id="ff274-633">El constructor o las propiedades de un atributo conforme a CLS pueden exponer solo los tipos siguientes:</span><span class="sxs-lookup"><span data-stu-id="ff274-633">The constructor or the properties of a CLS-compliant attribute can expose only the following types:</span></span>

* [<span data-ttu-id="ff274-634">Boolean</span><span class="sxs-lookup"><span data-stu-id="ff274-634">Boolean</span></span>](xref:System.Boolean)

* [<span data-ttu-id="ff274-635">Byte</span><span class="sxs-lookup"><span data-stu-id="ff274-635">Byte</span></span>](xref:System.Byte)

* [<span data-ttu-id="ff274-636">Char</span><span class="sxs-lookup"><span data-stu-id="ff274-636">Char</span></span>](xref:System.Char)

* [<span data-ttu-id="ff274-637">Double</span><span class="sxs-lookup"><span data-stu-id="ff274-637">Double</span></span>](xref:System.Double)

* [<span data-ttu-id="ff274-638">Int16</span><span class="sxs-lookup"><span data-stu-id="ff274-638">Int16</span></span>](xref:System.Int16)

* [<span data-ttu-id="ff274-639">Int32</span><span class="sxs-lookup"><span data-stu-id="ff274-639">Int32</span></span>](xref:System.Int32)

* [<span data-ttu-id="ff274-640">Int64</span><span class="sxs-lookup"><span data-stu-id="ff274-640">Int64</span></span>](xref:System.Int64)

* [<span data-ttu-id="ff274-641">Single</span><span class="sxs-lookup"><span data-stu-id="ff274-641">Single</span></span>](xref:System.Single)

* [<span data-ttu-id="ff274-642">String</span><span class="sxs-lookup"><span data-stu-id="ff274-642">String</span></span>](xref:System.String)

* [<span data-ttu-id="ff274-643">Type</span><span class="sxs-lookup"><span data-stu-id="ff274-643">Type</span></span>](xref:System.Type)

* <span data-ttu-id="ff274-644">Cualquier tipo de enumeración cuyo tipo subyacente sea `Byte`, `Int16`, `Int32` o `Int64`.</span><span class="sxs-lookup"><span data-stu-id="ff274-644">Any enumeration type whose underlying type is `Byte`, `Int16`, `Int32`, or `Int64`.</span></span>

<span data-ttu-id="ff274-645">En el ejemplo siguiente se define una clase `DescriptionAttribute` que se deriva de [Attribute](xref:System.Attribute).</span><span class="sxs-lookup"><span data-stu-id="ff274-645">The following example defines a `DescriptionAttribute` class that derives from [Attribute](xref:System.Attribute).</span></span> <span data-ttu-id="ff274-646">El constructor de clase tiene un parámetro de tipo `Descriptor`, de modo que la clase no es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-646">The class constructor has a parameter of type `Descriptor`, so the class is not CLS-compliant.</span></span> <span data-ttu-id="ff274-647">Tenga en cuenta que el compilador de C# emite una advertencia pero se compila correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff274-647">Note that the C# compiler emits a warning but compiles successfully.</span></span>

```csharp
using System;

[assembly:CLSCompliantAttribute(true)]

public enum DescriptorType { type, member };

public class Descriptor
{
   public DescriptorType Type;
   public String Description;
}

[AttributeUsage(AttributeTargets.All)]
public class DescriptionAttribute : Attribute
{
   private Descriptor desc;

   public DescriptionAttribute(Descriptor d)
   {
      desc = d;
   }

   public Descriptor Descriptor
   { get { return desc; } }
}
// Attempting to compile the example displays output like the following:
//       warning CS3015: 'DescriptionAttribute' has no accessible
//               constructors which use only CLS-compliant types
```

```vb
<Assembly:CLSCompliantAttribute(True)>

Public Enum DescriptorType As Integer
   Type = 0
   Member = 1
End Enum

Public Class Descriptor
   Public Type As DescriptorType
   Public Description As String
End Class

<AttributeUsage(AttributeTargets.All)> _
Public Class DescriptionAttribute : Inherits Attribute
   Private desc As Descriptor

   Public Sub New(d As Descriptor)
      desc = d
   End Sub

   Public ReadOnly Property Descriptor As Descriptor
      Get
         Return desc
      End Get
   End Property
End Class
```

## <a name="the-clscompliantattribute-attribute"></a><span data-ttu-id="ff274-648">CLSCompliantAttribute (Atributo)</span><span class="sxs-lookup"><span data-stu-id="ff274-648">The CLSCompliantAttribute attribute</span></span>

<span data-ttu-id="ff274-649">El atributo [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) se usa para indicar si un elemento del programa es conforme a Common Language Specification.</span><span class="sxs-lookup"><span data-stu-id="ff274-649">The [CLSCompliantAttribute](xref:System.CLSCompliantAttribute) attribute is used to indicate whether a program element complies with the Common Language Specification.</span></span> <span data-ttu-id="ff274-650">El constructor `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` contiene un único parámetro obligatorio, *isCompliant*, que indica si el elemento del programa es conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-650">The `CLSCompliantAttribute.CLSCompliantAttribute(Boolean)` constructor includes a single required parameter, *isCompliant*, that indicates whether the program element is CLS-compliant.</span></span>

<span data-ttu-id="ff274-651">En tiempo de compilación, el compilador detecta los elementos que supuestamente deberían ser conformes a CLS y emite una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ff274-651">At compile time, the compiler detects non-compliant elements that are presumed to be CLS-compliant and emits a warning.</span></span> <span data-ttu-id="ff274-652">El compilador no emite advertencias relacionadas con los tipos o miembros cuya no conformidad se declara explícitamente.</span><span class="sxs-lookup"><span data-stu-id="ff274-652">The compiler does not emit warnings for types or members that are explicitly declared to be non-compliant.</span></span>

<span data-ttu-id="ff274-653">Los desarrolladores de componentes pueden usar el atributo `CLSCompliantAttribute` de dos maneras:</span><span class="sxs-lookup"><span data-stu-id="ff274-653">Component developers can use the `CLSCompliantAttribute` attribute in two ways:</span></span>

* <span data-ttu-id="ff274-654">Para definir las partes de la interfaz pública expuestas por un componente que son conformes a CLS y las que no lo son.</span><span class="sxs-lookup"><span data-stu-id="ff274-654">To define the parts of the public interface exposed by a component that are CLS-compliant and the parts that are not CLS-compliant.</span></span> <span data-ttu-id="ff274-655">Cuando el atributo se utiliza para marcar determinados elementos del programa como conformes a CLS, este uso garantiza que dichos elementos son accesibles desde todos los lenguajes y herramientas que tienen como destino .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff274-655">When the attribute is used to mark particular program elements as CLS-compliant, its use guarantees that those elements are accessible from all languages and tools that target the .NET Framework.</span></span>

* <span data-ttu-id="ff274-656">Para garantizar que la interfaz pública de la biblioteca de componentes expone solo elementos del programa que son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-656">To ensure that the component library's public interface exposes only program elements that are CLS-compliant.</span></span> <span data-ttu-id="ff274-657">Si los elementos no son conformes a CLS, los compiladores normalmente emitirán una advertencia.</span><span class="sxs-lookup"><span data-stu-id="ff274-657">If elements are not CLS-compliant, compilers will generally issue a warning.</span></span>

> [!WARNING]
> <span data-ttu-id="ff274-658">En algunos casos, los compiladores de lenguaje aplican reglas conformes a CLS independientemente de si se usa el atributo `CLSCompliantAttribute` o no.</span><span class="sxs-lookup"><span data-stu-id="ff274-658">In some cases, language compilers enforce CLS-compliant rules regardless of whether the `CLSCompliantAttribute` attribute is used.</span></span> <span data-ttu-id="ff274-659">Por ejemplo, la definición de un miembro `*static` en una interfaz infringe una regla de CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-659">For example, defining a `*static` member in an interface violates a CLS rule.</span></span> <span data-ttu-id="ff274-660">Pero si define un miembro `*static` en una interfaz, el compilador de C# muestra un mensaje de error y se produce un error al compilar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ff274-660">However, if you define a `*static` member in an interface, the C# compiler displays an error message and fails to compile the app.</span></span>

<span data-ttu-id="ff274-661">El atributo `CLSCompliantAttribute` está marcado con un atributo [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) que tiene el valor `AttributeTargets.All`.</span><span class="sxs-lookup"><span data-stu-id="ff274-661">The `CLSCompliantAttribute` attribute is marked with an [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) attribute that has a value of `AttributeTargets.All`.</span></span> <span data-ttu-id="ff274-662">Este valor le permite aplicar el atributo `CLSCompliantAttribute` a cualquier elemento de programa, incluidos los ensamblados, módulos, tipos (clases, estructuras, enumeraciones, interfaces, delegados), miembros de tipo (constructores, métodos, propiedades, campos y eventos), parámetros, parámetros genéricos y valores devueltos.</span><span class="sxs-lookup"><span data-stu-id="ff274-662">This value allows you to apply the `CLSCompliantAttribute` attribute to any program element, including assemblies, modules, types (classes, structures, enumerations, interfaces, and delegates), type members (constructors, methods, properties, fields, and events), parameters, generic parameters, and return values.</span></span> <span data-ttu-id="ff274-663">Sin embargo, en la práctica, solo debe aplicar el atributo a los ensamblados, tipos y miembros del tipo.</span><span class="sxs-lookup"><span data-stu-id="ff274-663">However, in practice, you should apply the attribute only to assemblies, types, and type members.</span></span> <span data-ttu-id="ff274-664">De lo contrario, los compiladores omitirán el atributo y seguirán generando advertencias de compilación siempre que encuentren un parámetro no conforme, un parámetro genérico o un valor devuelto en la interfaz pública de la biblioteca.</span><span class="sxs-lookup"><span data-stu-id="ff274-664">Otherwise, compilers ignore the attribute and continue to generate compiler warnings whenever they encounter a non-compliant parameter, generic parameter, or return value in your library's public interface.</span></span>

<span data-ttu-id="ff274-665">El valor del atributo `CLSCompliantAttribute` lo heredan los elementos del programa contenidos.</span><span class="sxs-lookup"><span data-stu-id="ff274-665">The value of the `CLSCompliantAttribute` attribute is inherited by contained program elements.</span></span> <span data-ttu-id="ff274-666">Por ejemplo, si se marca un ensamblado como conforme a CLS, sus tipos también son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-666">For example, if an assembly is marked as CLS-compliant, its types are also CLS-compliant.</span></span> <span data-ttu-id="ff274-667">Si un tipo se marca como conforme a CLS, sus tipos anidados y miembros también serán conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-667">If a type is marked as CLS-compliant, its nested types and members are also CLS-compliant.</span></span>

<span data-ttu-id="ff274-668">Puede invalidar explícitamente la conformidad heredada aplicando el atributo `CLSCompliantAttribute` a un elemento del programa contenido.</span><span class="sxs-lookup"><span data-stu-id="ff274-668">You can explicitly override the inherited compliance by applying the `CLSCompliantAttribute` attribute to a contained program element.</span></span> <span data-ttu-id="ff274-669">Por ejemplo, puede usar el atributo `CLSCompliantAttribute` con el valor *isCompliant* establecido en `false` para definir un tipo no conforme en un ensamblado conforme, y puede usar el atributo con el valor *isCompliant* establecido en `true` para definir un tipo conforme en un ensamblado no conforme.</span><span class="sxs-lookup"><span data-stu-id="ff274-669">For example, you can use the `CLSCompliantAttribute` attribute with an *isCompliant* value of `false` to define a non-compliant type in a compliant assembly, and you can use the attribute with an *isCompliant* value of `true` to define a compliant type in a non-compliant assembly.</span></span> <span data-ttu-id="ff274-670">También puede definir miembros no conformes en un tipo conforme.</span><span class="sxs-lookup"><span data-stu-id="ff274-670">You can also define non-compliant members in a compliant type.</span></span> <span data-ttu-id="ff274-671">Pero un tipo no conforme no puede tener miembros conformes, por lo que no puede usar el atributo con el valor *isCompliant* establecido en `true` para invalidar la herencia de un tipo no conforme.</span><span class="sxs-lookup"><span data-stu-id="ff274-671">However, a non-compliant type cannot have compliant members, so you cannot use the attribute with an *isCompliant* value of `true` to override inheritance from a non-compliant type.</span></span>

<span data-ttu-id="ff274-672">Cuando desarrolle componentes, debe utilizar siempre el atributo `CLSCompliantAttribute` para indicar si el ensamblado, sus tipos y sus miembros son conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-672">When you are developing components, you should always use the `CLSCompliantAttribute` attribute to indicate whether your assembly, its types, and its members are CLS-compliant.</span></span>

<span data-ttu-id="ff274-673">Para crear componentes conformes a CLS:</span><span class="sxs-lookup"><span data-stu-id="ff274-673">To create CLS-compliant components:</span></span>

1. <span data-ttu-id="ff274-674">Utilice `CLSCompliantAttribute` para marcar el ensamblado como conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-674">Use the `CLSCompliantAttribute` to mark you assembly as CLS-compliant.</span></span>

2. <span data-ttu-id="ff274-675">Marque como no conforme los tipos expuestos públicamente en el ensamblado que no sean conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-675">Mark any publicly exposed types in the assembly that are not CLS-compliant as non-compliant.</span></span>

3. <span data-ttu-id="ff274-676">Marque como no conforme los miembros expuestos públicamente en tipos conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-676">Mark any publicly exposed members in CLS-compliant types as non-compliant.</span></span>

4. <span data-ttu-id="ff274-677">Proporcione una alternativa conforme a CLS para los miembros que no sean conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-677">Provide a CLS-compliant alternative for non-CLS-compliant members.</span></span>

<span data-ttu-id="ff274-678">Si ha marcado correctamente todos los tipos y miembros no conformes, el compilador no debe emitir ninguna advertencia de no conformidad.</span><span class="sxs-lookup"><span data-stu-id="ff274-678">If you've successfully marked all your non-compliant types and members, your compiler should not emit any non-compliance warnings.</span></span> <span data-ttu-id="ff274-679">Sin embargo, debe indicar qué miembros no son conformes a CLS y mostrar las alternativas conformes a CLS en la documentación del producto.</span><span class="sxs-lookup"><span data-stu-id="ff274-679">However, you should indicate which members are not CLS-compliant and list their CLS-compliant alternatives in your product documentation.</span></span>

<span data-ttu-id="ff274-680">En el ejemplo siguiente se usa el atributo `CLSCompliantAttribute` para definir un ensamblado conforme a CLS y un tipo, `CharacterUtilities`, que tiene dos miembros no conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-680">The following example uses the `CLSCompliantAttribute` attribute to define a CLS-compliant assembly and a type, `CharacterUtilities`, that has two non-CLS-compliant members.</span></span> <span data-ttu-id="ff274-681">Dado que ambos miembros están etiquetados con el atributo `CLSCompliant(false)`, el compilador no genera ninguna advertencia.</span><span class="sxs-lookup"><span data-stu-id="ff274-681">Because both members are tagged with the `CLSCompliant(false)` attribute, the compiler produces no warnings.</span></span> <span data-ttu-id="ff274-682">La clase también proporciona una alternativa conforme a CLS para ambos métodos.</span><span class="sxs-lookup"><span data-stu-id="ff274-682">The class also provides a CLS-compliant alternative for both methods.</span></span> <span data-ttu-id="ff274-683">Por lo general, simplemente se agregarían dos sobrecargas al método `ToUTF16` para proporcionar alternativas conformes a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-683">Ordinarily, we would just add two overloads to the `ToUTF16` method to provide CLS-compliant alternatives.</span></span> <span data-ttu-id="ff274-684">Sin embargo, puesto que no se pueden sobrecargar los métodos en función de un valor devuelto, los nombres de los métodos conformes a CLS son distintos de los nombres de los métodos no conformes.</span><span class="sxs-lookup"><span data-stu-id="ff274-684">However, because methods cannot be overloaded based on return value, the names of the CLS-compliant methods are different from the names of the non-compliant methods.</span></span>

```csharp
using System;
using System.Text;

[assembly:CLSCompliant(true)]

public class CharacterUtilities
{
   [CLSCompliant(false)] public static ushort ToUTF16(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return Convert.ToUInt16(s[0]);
   }

   [CLSCompliant(false)] public static ushort ToUTF16(Char ch)
   {
      return Convert.ToUInt16(ch);
   }

   // CLS-compliant alternative for ToUTF16(String).
   public static int ToUTF16CodeUnit(String s)
   {
      s = s.Normalize(NormalizationForm.FormC);
      return (int) Convert.ToUInt16(s[0]);
   }

   // CLS-compliant alternative for ToUTF16(Char).
   public static int ToUTF16CodeUnit(Char ch)
   {
      return Convert.ToInt32(ch);
   }

   public bool HasMultipleRepresentations(String s)
   {
      String s1 = s.Normalize(NormalizationForm.FormC);
      return s.Equals(s1);
   }

   public int GetUnicodeCodePoint(Char ch)
   {
      if (Char.IsSurrogate(ch))
         throw new ArgumentException("ch cannot be a high or low surrogate.");

      return Char.ConvertToUtf32(ch.ToString(), 0);
   }

   public int GetUnicodeCodePoint(Char[] chars)
   {
      if (chars.Length > 2)
         throw new ArgumentException("The array has too many characters.");

      if (chars.Length == 2) {
         if (! Char.IsSurrogatePair(chars[0], chars[1]))
            throw new ArgumentException("The array must contain a low and a high surrogate.");
         else
            return Char.ConvertToUtf32(chars[0], chars[1]);
      }
      else {
         return Char.ConvertToUtf32(chars.ToString(), 0);
      }
   }
}
```

```vb
Imports System.Text

<Assembly:CLSCompliant(True)>

Public Class CharacterUtilities
   <CLSCompliant(False)> Public Shared Function ToUTF16(s As String) As UShort
      s = s.Normalize(NormalizationForm.FormC)
      Return Convert.ToUInt16(s(0))
   End Function

   <CLSCompliant(False)> Public Shared Function ToUTF16(ch As Char) As UShort
      Return Convert.ToUInt16(ch)
   End Function

   ' CLS-compliant alternative for ToUTF16(String).
   Public Shared Function ToUTF16CodeUnit(s As String) As Integer
      s = s.Normalize(NormalizationForm.FormC)
      Return CInt(Convert.ToInt16(s(0)))
   End Function

   ' CLS-compliant alternative for ToUTF16(Char).
   Public Shared Function ToUTF16CodeUnit(ch As Char) As Integer
      Return Convert.ToInt32(ch)
   End Function

   Public Function HasMultipleRepresentations(s As String) As Boolean
      Dim s1 As String = s.Normalize(NormalizationForm.FormC)
      Return s.Equals(s1)
   End Function

   Public Function GetUnicodeCodePoint(ch As Char) As Integer
      If Char.IsSurrogate(ch) Then
         Throw New ArgumentException("ch cannot be a high or low surrogate.")
      End If
      Return Char.ConvertToUtf32(ch.ToString(), 0)
   End Function

   Public Function GetUnicodeCodePoint(chars() As Char) As Integer
      If chars.Length > 2 Then
         Throw New ArgumentException("The array has too many characters.")
      End If
      If chars.Length = 2 Then
         If Not Char.IsSurrogatePair(chars(0), chars(1)) Then
            Throw New ArgumentException("The array must contain a low and a high surrogate.")
         Else
            Return Char.ConvertToUtf32(chars(0), chars(1))
         End If
      Else
         Return Char.ConvertToUtf32(chars.ToString(), 0)
      End If
   End Function
End Class
```

<span data-ttu-id="ff274-685">Si está desarrollando una aplicación en lugar de una biblioteca (es decir, si no expone los tipos o miembros que pueden consumir otros desarrolladores de aplicaciones), la conformidad con CLS de los elementos del programa usados por la aplicación solo tendrá interés si su lenguaje admite estos elementos.</span><span class="sxs-lookup"><span data-stu-id="ff274-685">If you are developing an app rather than a library (that is, if you aren't exposing types or members that can be consumed by other app developers), the CLS compliance of the program elements that your app consumes are of interest only if your language does not support them.</span></span> <span data-ttu-id="ff274-686">En ese caso, el compilador del lenguaje generará un error cuando intente utilizar un elemento no conforme a CLS.</span><span class="sxs-lookup"><span data-stu-id="ff274-686">In that case, your language compiler will generate an error when you try to use a non-CLS-compliant element.</span></span>

## <a name="cross-language-interoperability"></a><span data-ttu-id="ff274-687">Interoperabilidad entre lenguajes</span><span class="sxs-lookup"><span data-stu-id="ff274-687">Cross-Language Interoperability</span></span>

<span data-ttu-id="ff274-688">La independencia de lenguaje tiene varios significados posibles.</span><span class="sxs-lookup"><span data-stu-id="ff274-688">Language independence has a number of possible meanings.</span></span> <span data-ttu-id="ff274-689">Un significado implica perfectamente tipos escritos en un lenguaje desde una aplicación escrita en otro lenguaje.</span><span class="sxs-lookup"><span data-stu-id="ff274-689">One meaning involves seamlessly consuming types written in one language from an app written in another language.</span></span> <span data-ttu-id="ff274-690">Un segundo significado, que es el descrito en este artículo, implica combinar código escrito en varios lenguajes en un único ensamblado de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ff274-690">A second meaning, which is the focus of this article, involves combining code written in multiple languages into a single .NET Framework assembly.</span></span>

<span data-ttu-id="ff274-691">El ejemplo siguiente muestra la interoperabilidad entre lenguajes creando una biblioteca de clases de denominada Utilities.dll que incluye dos clases, `NumericLib` y `StringLib`.</span><span class="sxs-lookup"><span data-stu-id="ff274-691">The following example illustrates cross-language interoperability by creating a class library named Utilities.dll that includes two classes, `NumericLib` and `StringLib`.</span></span> <span data-ttu-id="ff274-692">La clase `NumericLib` está escrita en C#, y la clase `StringLib` está escrita en Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="ff274-692">The `NumericLib` class is written in C#, and the `StringLib` class is written in Visual Basic.</span></span> <span data-ttu-id="ff274-693">A continuación se muestra el código fuente para `StringUtil.vb`, que incluye un solo miembro, `ToTitleCase`, en su clase `StringLib`.</span><span class="sxs-lookup"><span data-stu-id="ff274-693">Here's the source code for `StringUtil.vb`, which includes a single member, `ToTitleCase`, in its `StringLib` class.</span></span>

```vb
Imports System.Collections.Generic
Imports System.Runtime.CompilerServices

Public Module StringLib
   Private exclusions As List(Of String)

   Sub New()
      Dim words() As String = { "a", "an", "and", "of", "the" }
      exclusions = New List(Of String)
      exclusions.AddRange(words)
   End Sub

   <Extension()> _
   Public Function ToTitleCase(title As String) As String
      Dim words() As String = title.Split()
      Dim result As String = String.Empty

      For ctr As Integer = 0 To words.Length - 1
         Dim word As String = words(ctr)
         If ctr = 0 OrElse Not exclusions.Contains(word.ToLower()) Then
            result += word.Substring(0, 1).ToUpper() + _
                      word.Substring(1).ToLower()
         Else
            result += word.ToLower()
         End If
         If ctr <= words.Length - 1 Then
            result += " "
         End If
      Next
      Return result
   End Function
End Module
```

<span data-ttu-id="ff274-694">A continuación se muestra el código fuente para NumberUtil.cs, que define una clase `NumericLib` con dos miembros, `IsEven` y `NearZero`.</span><span class="sxs-lookup"><span data-stu-id="ff274-694">Here's the source code for NumberUtil.cs, which defines a `NumericLib` class that has two members, `IsEven` and `NearZero`.</span></span>

```csharp
using System;

public static class NumericLib
{
   public static bool IsEven(this IConvertible number)
   {
      if (number is Byte ||
          number is SByte ||
          number is Int16 ||
          number is UInt16 ||
          number is Int32 ||
          number is UInt32 ||
          number is Int64)
         return ((long) number) % 2 == 0;
      else if (number is UInt64)
         return ((ulong) number) %2 == 0;
      else
         throw new NotSupportedException("IsEven called for a non-integer value.");
   }

   public static bool NearZero(double number)
   {
      return number < .00001;
   }
}
```

<span data-ttu-id="ff274-695">Para empaquetar las dos clases en un solo ensamblado, debe compilarlas en módulos.</span><span class="sxs-lookup"><span data-stu-id="ff274-695">To package the two classes in a single assembly, you must compile them into modules.</span></span> <span data-ttu-id="ff274-696">Para compilar el archivo de código fuente de Visual Basic en un módulo, use este comando:</span><span class="sxs-lookup"><span data-stu-id="ff274-696">To compile the Visual Basic source code file into a module, use this command:</span></span>

```console
vbc /t:module StringUtil.vb
```

<span data-ttu-id="ff274-697">Para compilar el archivo de código fuente de C# en un módulo, use este comando:</span><span class="sxs-lookup"><span data-stu-id="ff274-697">To compile the C# source code file into a module, use this command:</span></span>

```console
csc /t:module NumberUtil.cs
```

<span data-ttu-id="ff274-698">A continuación, use la herramienta de vinculación (Link.exe) para compilar los dos módulos en un ensamblado:</span><span class="sxs-lookup"><span data-stu-id="ff274-698">You then use the Link tool (Link.exe) to compile the two modules into an assembly:</span></span>

```console
link numberutil.netmodule stringutil.netmodule /out:UtilityLib.dll /dll
```

<span data-ttu-id="ff274-699">El ejemplo siguiente llama a los métodos `NumericLib.NearZero` y `StringLib.ToTitleCase`.</span><span class="sxs-lookup"><span data-stu-id="ff274-699">The following example then calls the `NumericLib.NearZero` and `StringLib.ToTitleCase` methods.</span></span> <span data-ttu-id="ff274-700">Observe que el código de Visual Basic y el código de C# pueden tener acceso a los métodos en ambas clases.</span><span class="sxs-lookup"><span data-stu-id="ff274-700">Note that both the Visual Basic code and the C# code are able to access the methods in both classes.</span></span>

```csharp
using System;

public class Example
{
   public static void Main()
   {
      Double dbl = 0.0 - Double.Epsilon;
      Console.WriteLine(NumericLib.NearZero(dbl));

      string s = "war and peace";
      Console.WriteLine(s.ToTitleCase());
   }
}
// The example displays the following output:
//       True
//       War and Peace
```

```vb
Module Example
   Public Sub Main()
      Dim dbl As Double = 0.0 - Double.Epsilon
      Console.WriteLine(NumericLib.NearZero(dbl))

      Dim s As String = "war and peace"
      Console.WriteLine(s.ToTitleCase())
   End Sub
End Module
' The example displays the following output:
'       True
'       War and Peace
```

<span data-ttu-id="ff274-701">Para compilar el código de Visual Basic, use este comando:</span><span class="sxs-lookup"><span data-stu-id="ff274-701">To compile the Visual Basic code, use this command:</span></span>

```console
vbc example.vb /r:UtilityLib.dll
```

<span data-ttu-id="ff274-702">Para compilar con C#, cambie el nombre del compilador de vbc a csc y cambie la extensión de archivo .vb a .cs:</span><span class="sxs-lookup"><span data-stu-id="ff274-702">To compile with C#, change the name of the compiler from vbc to csc, and change the file extension from .vb to .cs:</span></span>

```console
csc example.cs /r:UtilityLib.dll
```
