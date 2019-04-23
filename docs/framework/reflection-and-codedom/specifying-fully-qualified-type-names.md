---
title: Especificar nombres de tipo completos
ms.date: 02/21/2019
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- reflection, fully qualified type names
- names [.NET Framework], assemblies
- tokens
- BNF
- assemblies [.NET Framework], names
- languages, grammar
- fully qualified type names
- type names
- special characters
- IDENTIFIER
ms.assetid: d90b1e39-9115-4f2a-81c0-05e7e74e5580
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dc8395492992c22da3c635f0de010516127f9be4
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612867"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="fbc34-102">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="fbc34-102">Specifying fully qualified type names</span></span>

<span data-ttu-id="fbc34-103">Debe especificar nombres de tipo para tener entradas válidas en varias operaciones de reflexión.</span><span class="sxs-lookup"><span data-stu-id="fbc34-103">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="fbc34-104">Un nombre de tipo completo consiste en una especificación de nombre de ensamblado, una especificación de espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="fbc34-104">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="fbc34-105">Las especificaciones de nombre de tipo las usan métodos como <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc34-105">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="fbc34-106">Gramática de los nombres de tipo</span><span class="sxs-lookup"><span data-stu-id="fbc34-106">Grammar for type names</span></span>

 <span data-ttu-id="fbc34-107">La gramática define la sintaxis de los lenguajes formales.</span><span class="sxs-lookup"><span data-stu-id="fbc34-107">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="fbc34-108">En la tabla siguiente se muestran las reglas léxicas que describen cómo reconocer una entrada válida.</span><span class="sxs-lookup"><span data-stu-id="fbc34-108">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="fbc34-109">Los terminales (es decir, los elementos que no se pueden reducir más) se muestran en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="fbc34-109">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="fbc34-110">Los no terminales (es decir, los elementos que se pueden reducir más) se muestran en cadenas con mayúsculas y minúsculas mezcladas o en cadenas entre comillas simples, pero la comilla simple (') no forma parte de la sintaxis en sí.</span><span class="sxs-lookup"><span data-stu-id="fbc34-110">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="fbc34-111">El carácter de canalización (&#124;) indica las reglas que tienen subreglas.</span><span class="sxs-lookup"><span data-stu-id="fbc34-111">The pipe character (&#124;) denotes rules that have subrules.</span></span>

<!-- markdownlint-disable MD010 -->
```antlr
TypeSpec
    : ReferenceTypeSpec
    | SimpleTypeSpec
    ;

ReferenceTypeSpec
    : SimpleTypeSpec '&'
    ;

SimpleTypeSpec
    : PointerTypeSpec
    | GenericTypeSpec
    | TypeName
    ;

GenericTypeSpec
   : SimpleTypeSpec ` NUMBER

PointerTypeSpec
    : SimpleTypeSpec '*'
    ;

ArrayTypeSpec
    : SimpleTypeSpec '[ReflectionDimension]'
    | SimpleTypeSpec '[ReflectionEmitDimension]'
    ;

ReflectionDimension
    : '*'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

ReflectionEmitDimension
    : '*'
    | Number '..' Number
    | Number '…'
    | ReflectionDimension ',' ReflectionDimension
    | NOTOKEN
    ;

Number
    : [0-9]+
    ;

TypeName
    : NamespaceTypeName
    | NamespaceTypeName ',' AssemblyNameSpec
    ;

NamespaceTypeName
    : NestedTypeName
    | NamespaceSpec '.' NestedTypeName
    ;

NestedTypeName
    : IDENTIFIER
    | NestedTypeName '+' IDENTIFIER
    ;

NamespaceSpec
    : IDENTIFIER
    | NamespaceSpec '.' IDENTIFIER
    ;

AssemblyNameSpec
    : IDENTIFIER
    | IDENTIFIER ',' AssemblyProperties
    ;

AssemblyProperties
    : AssemblyProperty
    | AssemblyProperties ',' AssemblyProperty
    ;

AssemblyProperty
    : AssemblyPropertyName '=' AssemblyPropertyValue
    ;
```
<!-- markdownlint-enable MD010 -->

## <a name="specifying-special-characters"></a><span data-ttu-id="fbc34-112">Especificación de caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="fbc34-112">Specifying special characters</span></span>

<span data-ttu-id="fbc34-113">En un nombre de tipo, IDENTIFIER es cualquier nombre válido determinado por las reglas de un lenguaje.</span><span class="sxs-lookup"><span data-stu-id="fbc34-113">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="fbc34-114">Use la barra diagonal inversa (\\) como carácter de escape para separar los tokens siguientes cuando se usan como parte de IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="fbc34-114">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="fbc34-115">Token</span><span class="sxs-lookup"><span data-stu-id="fbc34-115">Token</span></span>|<span data-ttu-id="fbc34-116">Significado</span><span class="sxs-lookup"><span data-stu-id="fbc34-116">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="fbc34-117">\\,</span><span class="sxs-lookup"><span data-stu-id="fbc34-117">\\,</span></span>|<span data-ttu-id="fbc34-118">Separador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="fbc34-118">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="fbc34-119">Separador de tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="fbc34-119">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="fbc34-120">Tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="fbc34-120">Reference type.</span></span>|
|\\*|<span data-ttu-id="fbc34-121">Tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="fbc34-121">Pointer type.</span></span>|
|<span data-ttu-id="fbc34-122">\\[</span><span class="sxs-lookup"><span data-stu-id="fbc34-122">\\[</span></span>|<span data-ttu-id="fbc34-123">Delimitador de dimensión de matriz.</span><span class="sxs-lookup"><span data-stu-id="fbc34-123">Array dimension delimiter.</span></span>|
|<span data-ttu-id="fbc34-124">\\]</span><span class="sxs-lookup"><span data-stu-id="fbc34-124">\\]</span></span>|<span data-ttu-id="fbc34-125">Delimitador de dimensión de matriz.</span><span class="sxs-lookup"><span data-stu-id="fbc34-125">Array dimension delimiter.</span></span>|
|<span data-ttu-id="fbc34-126">\\.</span><span class="sxs-lookup"><span data-stu-id="fbc34-126">\\.</span></span>|<span data-ttu-id="fbc34-127">Use la barra diagonal inversa delante de un punto únicamente si el punto se usa en una especificación de matriz.</span><span class="sxs-lookup"><span data-stu-id="fbc34-127">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="fbc34-128">Los puntos de NamespaceSpec no llevan barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="fbc34-128">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="fbc34-129">\\\|Barra diagonal inversa cuando es necesaria como cadena literal.</span><span class="sxs-lookup"><span data-stu-id="fbc34-129">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="fbc34-130">Tenga en cuenta que los espacios son relevantes en todos los componentes de TypeSpec, salvo en AssemblyNameSpec.</span><span class="sxs-lookup"><span data-stu-id="fbc34-130">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="fbc34-131">En AssemblyNameSpec, los espacios delante del separador "," son relevantes, pero los espacios detrás del separador "," se omiten.</span><span class="sxs-lookup"><span data-stu-id="fbc34-131">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="fbc34-132">Las clases de reflexión, como <xref:System.Type.FullName%2A?displayProperty=nameWithType>, devuelven el nombre alterado para que el nombre devuelto pueda usarse en una llamada a <xref:System.Type.GetType%2A>, como en `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-132">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="fbc34-133">Por ejemplo, el nombre completo de un tipo podría ser `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-133">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="fbc34-134">Si el espacio de nombres fuera `Ozzy.Out+Back`, el signo más debería ir precedido de una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="fbc34-134">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="fbc34-135">De lo contrario, el analizador lo interpretaría como un separador de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="fbc34-135">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="fbc34-136">La reflexión emite esta cadena como `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-136">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="fbc34-137">Especificación de nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="fbc34-137">Specifying assembly names</span></span>

<span data-ttu-id="fbc34-138">La información mínima necesaria en una especificación de nombre de ensamblado es el nombre textual (IDENTIFIER) del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="fbc34-138">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="fbc34-139">Puede seguir el IDENTIFIER mediante una lista separada por comas de pares de propiedad-valor, como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="fbc34-139">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="fbc34-140">La nomenclatura de IDENTIFIER debe seguir las reglas de la nomenclatura de archivos.</span><span class="sxs-lookup"><span data-stu-id="fbc34-140">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="fbc34-141">IDENTIFIER no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="fbc34-141">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="fbc34-142">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="fbc34-142">Property name</span></span>|<span data-ttu-id="fbc34-143">Descripción</span><span class="sxs-lookup"><span data-stu-id="fbc34-143">Description</span></span>|<span data-ttu-id="fbc34-144">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="fbc34-144">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="fbc34-145">**Versión**</span><span class="sxs-lookup"><span data-stu-id="fbc34-145">**Version**</span></span>|<span data-ttu-id="fbc34-146">Número de versión del ensamblado</span><span class="sxs-lookup"><span data-stu-id="fbc34-146">Assembly version number</span></span>|<span data-ttu-id="fbc34-147">*Major.Minor.Build.Revision*, donde *Major*, *Minor*, *Build* y *Revision* son números enteros entre 0 y 65535, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="fbc34-147">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="fbc34-148">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="fbc34-148">**PublicKey**</span></span>|<span data-ttu-id="fbc34-149">Clave pública completa</span><span class="sxs-lookup"><span data-stu-id="fbc34-149">Full public key</span></span>|<span data-ttu-id="fbc34-150">Valor de cadena de la clave pública completa en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fbc34-150">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="fbc34-151">Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="fbc34-151">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="fbc34-152">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="fbc34-152">**PublicKeyToken**</span></span>|<span data-ttu-id="fbc34-153">Token de clave pública (hash de 8 bytes de la clave pública completa)</span><span class="sxs-lookup"><span data-stu-id="fbc34-153">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="fbc34-154">Valor de cadena del token de clave pública en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="fbc34-154">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="fbc34-155">Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="fbc34-155">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="fbc34-156">**Referencia cultural**</span><span class="sxs-lookup"><span data-stu-id="fbc34-156">**Culture**</span></span>|<span data-ttu-id="fbc34-157">Referencia cultural del ensamblado</span><span class="sxs-lookup"><span data-stu-id="fbc34-157">Assembly culture</span></span>|<span data-ttu-id="fbc34-158">Referencia cultural del ensamblado en formato RFC-1766, o "neutral" para los ensamblados independientes del lenguaje (no satélite).</span><span class="sxs-lookup"><span data-stu-id="fbc34-158">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="fbc34-159">**Custom**</span><span class="sxs-lookup"><span data-stu-id="fbc34-159">**Custom**</span></span>|<span data-ttu-id="fbc34-160">Objeto binario grande personalizado (BLOB).</span><span class="sxs-lookup"><span data-stu-id="fbc34-160">Custom binary large object (BLOB).</span></span> <span data-ttu-id="fbc34-161">Actualmente esto solo se usa en los ensamblados generados por el [Generador de imágenes nativas (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="fbc34-161">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../../../docs/framework/tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="fbc34-162">Cadena personalizada que la herramienta Generador de imágenes nativas usa para notificar a la caché de ensamblados que el ensamblado que se está instalando es una imagen nativa y, por tanto, se tiene que instalar en la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="fbc34-162">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="fbc34-163">También se denomina cadena ZAP.</span><span class="sxs-lookup"><span data-stu-id="fbc34-163">Also called a zap string.</span></span>|

<span data-ttu-id="fbc34-164">En el ejemplo siguiente se muestra un **AssemblyName** para un ensamblado de nombre simple con una referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="fbc34-164">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="fbc34-165">En el ejemplo siguiente se muestra una referencia completa para un ensamblado con nombre seguro con la referencia cultural "en".</span><span class="sxs-lookup"><span data-stu-id="fbc34-165">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="fbc34-166">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se puede resolver mediante un ensamblado con un nombre simple o seguro.</span><span class="sxs-lookup"><span data-stu-id="fbc34-166">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="fbc34-167">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="fbc34-167">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="fbc34-168">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="fbc34-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="fbc34-169">Especificación de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="fbc34-169">Specifying generic types</span></span>

<span data-ttu-id="fbc34-170">SimpleTypeSpec\`NUMBER representa un tipo genérico abierto de 1 a *n* parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="fbc34-170">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="fbc34-171">Por ejemplo, para obtener la referencia al tipo genérico abierto List\<T> o el tipo genérico cerrado List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")``; para obtener una referencia al tipo genérico Dictionary\<TKey, TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span><span class="sxs-lookup"><span data-stu-id="fbc34-171">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="fbc34-172">Especificación de punteros</span><span class="sxs-lookup"><span data-stu-id="fbc34-172">Specifying pointers</span></span>

<span data-ttu-id="fbc34-173">SimpleTypeSpec\* representa un puntero no administrado.</span><span class="sxs-lookup"><span data-stu-id="fbc34-173">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="fbc34-174">Por ejemplo, para obtener un puntero al tipo MyType, use `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-174">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="fbc34-175">Para obtener un puntero a un puntero al tipo MyType, use `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-175">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="fbc34-176">Especificación de referencias</span><span class="sxs-lookup"><span data-stu-id="fbc34-176">Specifying references</span></span>

<span data-ttu-id="fbc34-177">SimpleTypeSpec & representa un puntero administrado o referencia.</span><span class="sxs-lookup"><span data-stu-id="fbc34-177">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="fbc34-178">Por ejemplo, para obtener una referencia al tipo MyType, use `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="fbc34-178">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="fbc34-179">Tenga en cuenta que, a diferencia de los punteros, las referencias están limitadas a un nivel.</span><span class="sxs-lookup"><span data-stu-id="fbc34-179">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="fbc34-180">Especificación de matrices</span><span class="sxs-lookup"><span data-stu-id="fbc34-180">Specifying arrays</span></span>

<span data-ttu-id="fbc34-181">En la gramática de BNF, ReflectionEmitDimension solo se aplica a las definiciones de tipo incompletas recuperadas mediante <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc34-181">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fbc34-182">Las definiciones de tipo incompletas son objetos <xref:System.Reflection.Emit.TypeBuilder> construidos mediante <xref:System.Reflection.Emit?displayProperty=nameWithType>, pero en los que no se ha llamado a <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fbc34-182">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="fbc34-183">Se puede usar ReflectionDimension para recuperar cualquier definición de tipo que se haya completado, es decir, un tipo que se haya cargado.</span><span class="sxs-lookup"><span data-stu-id="fbc34-183">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="fbc34-184">Para obtener acceso a las matrices en la reflexión, se debe especificar el rango de la matriz:</span><span class="sxs-lookup"><span data-stu-id="fbc34-184">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="fbc34-185">`Type.GetType("MyArray[]")` obtiene una matriz unidimensional con límite inferior 0.</span><span class="sxs-lookup"><span data-stu-id="fbc34-185">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="fbc34-186">`Type.GetType("MyArray[*]")` obtiene una matriz unidimensional con límite inferior desconocido.</span><span class="sxs-lookup"><span data-stu-id="fbc34-186">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="fbc34-187">`Type.GetType("MyArray[][]")` obtiene una matriz de la matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="fbc34-187">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="fbc34-188">`Type.GetType("MyArray[*,*]")` y `Type.GetType("MyArray[,]")` obtienen una matriz bidimensional rectangular con límites inferiores desconocidos.</span><span class="sxs-lookup"><span data-stu-id="fbc34-188">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="fbc34-189">Tenga en cuenta que, desde el punto de vista del tiempo de ejecución, `MyArray[] != MyArray[*]`, pero en el caso de las matrices multidimensionales, las dos notaciones son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="fbc34-189">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="fbc34-190">Es decir, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` se evalúa como **true**.</span><span class="sxs-lookup"><span data-stu-id="fbc34-190">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="fbc34-191">Para **ModuleBuilder.GetType**, `MyArray[0..5]` indica una matriz unidimensional de tamaño 6 y límite inferior 0.</span><span class="sxs-lookup"><span data-stu-id="fbc34-191">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="fbc34-192">`MyArray[4…]` indica una matriz unidimensional de tamaño desconocido y límite inferior 4.</span><span class="sxs-lookup"><span data-stu-id="fbc34-192">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbc34-193">Vea también</span><span class="sxs-lookup"><span data-stu-id="fbc34-193">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- <span data-ttu-id="fbc34-194">[Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md) (Ver información tipos)</span><span class="sxs-lookup"><span data-stu-id="fbc34-194">[Viewing Type Information](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)</span></span>
