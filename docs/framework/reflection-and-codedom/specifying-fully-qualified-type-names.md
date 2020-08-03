---
title: Especificar nombres de tipo completos
description: Para la entrada válida para las operaciones de reflexión, use nombres de tipo completos, que tienen especificaciones de nombre de ensamblado, especificaciones de espacio de nombres y nombres de tipo.
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
ms.openlocfilehash: ff33b6abd31a82c6b80aa794564c5c48648cde63
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865234"
---
# <a name="specifying-fully-qualified-type-names"></a><span data-ttu-id="9a772-103">Especificar nombres de tipo completos</span><span class="sxs-lookup"><span data-stu-id="9a772-103">Specifying fully qualified type names</span></span>

<span data-ttu-id="9a772-104">Debe especificar nombres de tipo para tener entradas válidas en varias operaciones de reflexión.</span><span class="sxs-lookup"><span data-stu-id="9a772-104">You must specify type names to have valid input to various reflection operations.</span></span> <span data-ttu-id="9a772-105">Un nombre de tipo completo consiste en una especificación de nombre de ensamblado, una especificación de espacio de nombres y un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="9a772-105">A fully qualified type name consists of an assembly name specification, a namespace specification, and a type name.</span></span> <span data-ttu-id="9a772-106">Las especificaciones de nombre de tipo las usan métodos como <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType> y <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a772-106">Type name specifications are used by methods such as <xref:System.Type.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>, <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>, and <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>.</span></span>

## <a name="grammar-for-type-names"></a><span data-ttu-id="9a772-107">Gramática de los nombres de tipo</span><span class="sxs-lookup"><span data-stu-id="9a772-107">Grammar for type names</span></span>

 <span data-ttu-id="9a772-108">La gramática define la sintaxis de los lenguajes formales.</span><span class="sxs-lookup"><span data-stu-id="9a772-108">The grammar defines the syntax of formal languages.</span></span> <span data-ttu-id="9a772-109">En la tabla siguiente se muestran las reglas léxicas que describen cómo reconocer una entrada válida.</span><span class="sxs-lookup"><span data-stu-id="9a772-109">The following table lists lexical rules that describe how to recognize a valid input.</span></span> <span data-ttu-id="9a772-110">Los terminales (es decir, los elementos que no se pueden reducir más) se muestran en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="9a772-110">Terminals (those elements that are not further reducible) are shown in all uppercase letters.</span></span> <span data-ttu-id="9a772-111">Los no terminales (es decir, los elementos que se pueden reducir más) se muestran en cadenas con mayúsculas y minúsculas mezcladas o en cadenas entre comillas simples, pero la comilla simple (') no forma parte de la sintaxis en sí.</span><span class="sxs-lookup"><span data-stu-id="9a772-111">Nonterminals (those elements that are further reducible) are shown in mixed-case or singly quoted strings, but the single quote (') is not a part of the syntax itself.</span></span> <span data-ttu-id="9a772-112">El carácter de canalización (&#124;) indica las reglas que tienen subreglas.</span><span class="sxs-lookup"><span data-stu-id="9a772-112">The pipe character (&#124;) denotes rules that have subrules.</span></span>

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

## <a name="specifying-special-characters"></a><span data-ttu-id="9a772-113">Especificación de caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="9a772-113">Specifying special characters</span></span>

<span data-ttu-id="9a772-114">En un nombre de tipo, IDENTIFIER es cualquier nombre válido determinado por las reglas de un lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9a772-114">In a type name, IDENTIFIER is any valid name determined by the rules of a language.</span></span>

<span data-ttu-id="9a772-115">Use la barra diagonal inversa (\\) como carácter de escape para separar los tokens siguientes cuando se usan como parte de IDENTIFIER.</span><span class="sxs-lookup"><span data-stu-id="9a772-115">Use the backslash (\\) as an escape character to separate the following tokens when used as part of IDENTIFIER.</span></span>

|<span data-ttu-id="9a772-116">Token</span><span class="sxs-lookup"><span data-stu-id="9a772-116">Token</span></span>|<span data-ttu-id="9a772-117">Significado</span><span class="sxs-lookup"><span data-stu-id="9a772-117">Meaning</span></span>|
|-----------|-------------|
|<span data-ttu-id="9a772-118">\\,</span><span class="sxs-lookup"><span data-stu-id="9a772-118">\\,</span></span>|<span data-ttu-id="9a772-119">Separador de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="9a772-119">Assembly separator.</span></span>|
|\\+|<span data-ttu-id="9a772-120">Separador de tipos anidados.</span><span class="sxs-lookup"><span data-stu-id="9a772-120">Nested type separator.</span></span>|
|\\&|<span data-ttu-id="9a772-121">Tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="9a772-121">Reference type.</span></span>|
|\\*|<span data-ttu-id="9a772-122">Tipo de puntero.</span><span class="sxs-lookup"><span data-stu-id="9a772-122">Pointer type.</span></span>|
|<span data-ttu-id="9a772-123">\\[</span><span class="sxs-lookup"><span data-stu-id="9a772-123">\\[</span></span>|<span data-ttu-id="9a772-124">Delimitador de dimensión de matriz.</span><span class="sxs-lookup"><span data-stu-id="9a772-124">Array dimension delimiter.</span></span>|
|<span data-ttu-id="9a772-125">\\]</span><span class="sxs-lookup"><span data-stu-id="9a772-125">\\]</span></span>|<span data-ttu-id="9a772-126">Delimitador de dimensión de matriz.</span><span class="sxs-lookup"><span data-stu-id="9a772-126">Array dimension delimiter.</span></span>|
|<span data-ttu-id="9a772-127">\\.</span><span class="sxs-lookup"><span data-stu-id="9a772-127">\\.</span></span>|<span data-ttu-id="9a772-128">Use la barra diagonal inversa delante de un punto únicamente si el punto se usa en una especificación de matriz.</span><span class="sxs-lookup"><span data-stu-id="9a772-128">Use the backslash before a period only if the period is used in an array specification.</span></span> <span data-ttu-id="9a772-129">Los puntos de NamespaceSpec no llevan barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="9a772-129">Periods in NamespaceSpec do not take the backslash.</span></span>|
|<span data-ttu-id="9a772-130">\\\|Barra diagonal inversa cuando es necesaria como cadena literal.</span><span class="sxs-lookup"><span data-stu-id="9a772-130">\\\|Backslash when needed as a string literal.</span></span>|

<span data-ttu-id="9a772-131">Tenga en cuenta que los espacios son relevantes en todos los componentes de TypeSpec, salvo en AssemblyNameSpec.</span><span class="sxs-lookup"><span data-stu-id="9a772-131">Note that in all TypeSpec components except AssemblyNameSpec, spaces are relevant.</span></span> <span data-ttu-id="9a772-132">En AssemblyNameSpec, los espacios delante del separador "," son relevantes, pero los espacios detrás del separador "," se omiten.</span><span class="sxs-lookup"><span data-stu-id="9a772-132">In the AssemblyNameSpec, spaces before the ',' separator are relevant, but spaces after the ',' separator are ignored.</span></span>

<span data-ttu-id="9a772-133">Las clases de reflexión, como <xref:System.Type.FullName%2A?displayProperty=nameWithType>, devuelven el nombre alterado para que el nombre devuelto pueda usarse en una llamada a <xref:System.Type.GetType%2A>, como en `MyType.GetType(myType.FullName)`.</span><span class="sxs-lookup"><span data-stu-id="9a772-133">Reflection classes, such as <xref:System.Type.FullName%2A?displayProperty=nameWithType>, return the mangled name so that the returned name can be used in a call to <xref:System.Type.GetType%2A>, as in `MyType.GetType(myType.FullName)`.</span></span>

<span data-ttu-id="9a772-134">Por ejemplo, el nombre completo de un tipo podría ser `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9a772-134">For example, the fully qualified name for a type might be `Ozzy.OutBack.Kangaroo+Wallaby,MyAssembly`.</span></span>

<span data-ttu-id="9a772-135">Si el espacio de nombres fuera `Ozzy.Out+Back`, el signo más debería ir precedido de una barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="9a772-135">If the namespace were `Ozzy.Out+Back`, then the plus sign must be preceded by a backslash.</span></span> <span data-ttu-id="9a772-136">De lo contrario, el analizador lo interpretaría como un separador de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="9a772-136">Otherwise, the parser would interpret it as a nesting separator.</span></span> <span data-ttu-id="9a772-137">La reflexión emite esta cadena como `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span><span class="sxs-lookup"><span data-stu-id="9a772-137">Reflection emits this string as `Ozzy.Out\+Back.Kangaroo+Wallaby,MyAssembly`.</span></span>

## <a name="specifying-assembly-names"></a><span data-ttu-id="9a772-138">Especificación de nombres de ensamblado</span><span class="sxs-lookup"><span data-stu-id="9a772-138">Specifying assembly names</span></span>

<span data-ttu-id="9a772-139">La información mínima necesaria en una especificación de nombre de ensamblado es el nombre textual (IDENTIFIER) del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="9a772-139">The minimum information required in an assembly name specification is the textual name (IDENTIFIER) of the assembly.</span></span> <span data-ttu-id="9a772-140">Puede seguir el IDENTIFIER mediante una lista separada por comas de pares de propiedad-valor, como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9a772-140">You can follow the IDENTIFIER by a comma-separated list of property/value pairs as described in the following table.</span></span> <span data-ttu-id="9a772-141">La nomenclatura de IDENTIFIER debe seguir las reglas de la nomenclatura de archivos.</span><span class="sxs-lookup"><span data-stu-id="9a772-141">IDENTIFIER naming should follow the rules for file naming.</span></span> <span data-ttu-id="9a772-142">IDENTIFIER no distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="9a772-142">The IDENTIFIER is case-insensitive.</span></span>

|<span data-ttu-id="9a772-143">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="9a772-143">Property name</span></span>|<span data-ttu-id="9a772-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a772-144">Description</span></span>|<span data-ttu-id="9a772-145">Valores permitidos</span><span class="sxs-lookup"><span data-stu-id="9a772-145">Allowable values</span></span>|
|-------------------|-----------------|----------------------|
|<span data-ttu-id="9a772-146">**Versión**</span><span class="sxs-lookup"><span data-stu-id="9a772-146">**Version**</span></span>|<span data-ttu-id="9a772-147">Número de versión del ensamblado</span><span class="sxs-lookup"><span data-stu-id="9a772-147">Assembly version number</span></span>|<span data-ttu-id="9a772-148">*Major.Minor.Build.Revision*, donde *Major*, *Minor*, *Build* y *Revision* son números enteros entre 0 y 65535, ambos incluidos.</span><span class="sxs-lookup"><span data-stu-id="9a772-148">*Major.Minor.Build.Revision*, where *Major*, *Minor*, *Build*, and *Revision* are integers between 0 and 65535 inclusive.</span></span>|
|<span data-ttu-id="9a772-149">**PublicKey**</span><span class="sxs-lookup"><span data-stu-id="9a772-149">**PublicKey**</span></span>|<span data-ttu-id="9a772-150">Clave pública completa</span><span class="sxs-lookup"><span data-stu-id="9a772-150">Full public key</span></span>|<span data-ttu-id="9a772-151">Valor de cadena de la clave pública completa en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="9a772-151">String value of full public key in hexadecimal format.</span></span> <span data-ttu-id="9a772-152">Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="9a772-152">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="9a772-153">**PublicKeyToken**</span><span class="sxs-lookup"><span data-stu-id="9a772-153">**PublicKeyToken**</span></span>|<span data-ttu-id="9a772-154">Token de clave pública (hash de 8 bytes de la clave pública completa)</span><span class="sxs-lookup"><span data-stu-id="9a772-154">Public key token (8-byte hash of the full public key)</span></span>|<span data-ttu-id="9a772-155">Valor de cadena del token de clave pública en formato hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="9a772-155">String value of public key token in hexadecimal format.</span></span> <span data-ttu-id="9a772-156">Especifique una referencia nula (**Nothing** en Visual Basic) para indicar explícitamente un ensamblado privado.</span><span class="sxs-lookup"><span data-stu-id="9a772-156">Specify a null reference (**Nothing** in Visual Basic) to explicitly indicate a private assembly.</span></span>|
|<span data-ttu-id="9a772-157">**Referencia cultural**</span><span class="sxs-lookup"><span data-stu-id="9a772-157">**Culture**</span></span>|<span data-ttu-id="9a772-158">Referencia cultural del ensamblado</span><span class="sxs-lookup"><span data-stu-id="9a772-158">Assembly culture</span></span>|<span data-ttu-id="9a772-159">Referencia cultural del ensamblado en formato RFC-1766, o "neutral" para los ensamblados independientes del lenguaje (no satélite).</span><span class="sxs-lookup"><span data-stu-id="9a772-159">Culture of the assembly in RFC-1766 format, or "neutral" for language-independent (nonsatellite) assemblies.</span></span>|
|<span data-ttu-id="9a772-160">**Custom**</span><span class="sxs-lookup"><span data-stu-id="9a772-160">**Custom**</span></span>|<span data-ttu-id="9a772-161">Objeto binario grande personalizado (BLOB).</span><span class="sxs-lookup"><span data-stu-id="9a772-161">Custom binary large object (BLOB).</span></span> <span data-ttu-id="9a772-162">Actualmente esto solo se usa en los ensamblados generados por el [Generador de imágenes nativas (Ngen)](../tools/ngen-exe-native-image-generator.md).</span><span class="sxs-lookup"><span data-stu-id="9a772-162">This is currently used only in assemblies generated by the [Native Image Generator (Ngen)](../tools/ngen-exe-native-image-generator.md).</span></span>|<span data-ttu-id="9a772-163">Cadena personalizada que la herramienta Generador de imágenes nativas usa para notificar a la caché de ensamblados que el ensamblado que se está instalando es una imagen nativa y, por tanto, se tiene que instalar en la caché de imágenes nativas.</span><span class="sxs-lookup"><span data-stu-id="9a772-163">Custom string used by the Native Image Generator tool to notify the assembly cache that the assembly being installed is a native image, and is therefore to be installed in the native image cache.</span></span> <span data-ttu-id="9a772-164">También se denomina cadena ZAP.</span><span class="sxs-lookup"><span data-stu-id="9a772-164">Also called a zap string.</span></span>|

<span data-ttu-id="9a772-165">En el ejemplo siguiente se muestra un **AssemblyName** para un ensamblado de nombre simple con una referencia cultural predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9a772-165">The following example shows an **AssemblyName** for a simply named assembly with default culture.</span></span>

```csharp
com.microsoft.crypto, Culture=""
```

<span data-ttu-id="9a772-166">En el ejemplo siguiente se muestra una referencia completa para un ensamblado con nombre seguro con la referencia cultural "en".</span><span class="sxs-lookup"><span data-stu-id="9a772-166">The following example shows a fully specified reference for a strongly named assembly with culture "en".</span></span>

```csharp
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

<span data-ttu-id="9a772-167">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se puede resolver mediante un ensamblado con un nombre simple o seguro.</span><span class="sxs-lookup"><span data-stu-id="9a772-167">The following examples each show a partially specified **AssemblyName**, which can be satisfied by either a strong or a simply named assembly.</span></span>

```csharp
com.microsoft.crypto
com.microsoft.crypto, Culture=""
com.microsoft.crypto, Culture=en
```

<span data-ttu-id="9a772-168">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre simple.</span><span class="sxs-lookup"><span data-stu-id="9a772-168">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a simply named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=null
com.microsoft.crypto, Culture=en, PublicKeyToken=null
```

<span data-ttu-id="9a772-169">En los ejemplos siguientes se muestra un **AssemblyName** parcialmente especificado, que se debe resolver mediante un ensamblado con un nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="9a772-169">The following examples each show a partially specified **AssemblyName**, which must be satisfied by a strongly named assembly.</span></span>

```csharp
com.microsoft.crypto, Culture="", PublicKeyToken=a5d015c7d5a0b012
com.microsoft.crypto, Culture=en, PublicKeyToken=a5d015c7d5a0b012,
    Version=1.0.0.0
```

## <a name="specifying-generic-types"></a><span data-ttu-id="9a772-170">Especificación de tipos genéricos</span><span class="sxs-lookup"><span data-stu-id="9a772-170">Specifying generic types</span></span>

<span data-ttu-id="9a772-171">SimpleTypeSpec\`NUMBER representa un tipo genérico abierto de 1 a *n* parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="9a772-171">SimpleTypeSpec\`NUMBER represents an open generic type with from 1 to *n* generic type parameters.</span></span> <span data-ttu-id="9a772-172">Por ejemplo, para obtener la referencia al tipo genérico abierto List\<T> o al tipo genérico cerrado List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")``; para obtener una referencia al tipo genérico Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span><span class="sxs-lookup"><span data-stu-id="9a772-172">For example, to get reference to the open generic type List\<T> or the closed generic type List\<String>, use ``Type.GetType("System.Collections.Generic.List`1")`` To get a reference to the generic type Dictionary\<TKey,TValue>, use ``Type.GetType("System.Collections.Generic.Dictionary`2")``.</span></span>

## <a name="specifying-pointers"></a><span data-ttu-id="9a772-173">Especificación de punteros</span><span class="sxs-lookup"><span data-stu-id="9a772-173">Specifying pointers</span></span>

<span data-ttu-id="9a772-174">SimpleTypeSpec\* representa un puntero no administrado.</span><span class="sxs-lookup"><span data-stu-id="9a772-174">SimpleTypeSpec\* represents an unmanaged pointer.</span></span> <span data-ttu-id="9a772-175">Por ejemplo, para obtener un puntero al tipo MyType, use `Type.GetType("MyType*")`.</span><span class="sxs-lookup"><span data-stu-id="9a772-175">For example, to get a pointer to type MyType, use `Type.GetType("MyType*")`.</span></span> <span data-ttu-id="9a772-176">Para obtener un puntero a un puntero al tipo MyType, use `Type.GetType("MyType**")`.</span><span class="sxs-lookup"><span data-stu-id="9a772-176">To get a pointer to a pointer to type MyType, use `Type.GetType("MyType**")`.</span></span>

## <a name="specifying-references"></a><span data-ttu-id="9a772-177">Especificación de referencias</span><span class="sxs-lookup"><span data-stu-id="9a772-177">Specifying references</span></span>

<span data-ttu-id="9a772-178">SimpleTypeSpec & representa un puntero administrado o referencia.</span><span class="sxs-lookup"><span data-stu-id="9a772-178">SimpleTypeSpec & represents a managed pointer or reference.</span></span> <span data-ttu-id="9a772-179">Por ejemplo, para obtener una referencia al tipo MyType, use `Type.GetType("MyType &")`.</span><span class="sxs-lookup"><span data-stu-id="9a772-179">For example, to get a reference to type MyType, use `Type.GetType("MyType &")`.</span></span> <span data-ttu-id="9a772-180">Tenga en cuenta que, a diferencia de los punteros, las referencias están limitadas a un nivel.</span><span class="sxs-lookup"><span data-stu-id="9a772-180">Note that unlike pointers, references are limited to one level.</span></span>

## <a name="specifying-arrays"></a><span data-ttu-id="9a772-181">Especificación de matrices</span><span class="sxs-lookup"><span data-stu-id="9a772-181">Specifying arrays</span></span>

<span data-ttu-id="9a772-182">En la gramática de BNF, ReflectionEmitDimension solo se aplica a las definiciones de tipo incompletas recuperadas mediante <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a772-182">In the BNF Grammar, ReflectionEmitDimension only applies to incomplete type definitions retrieved using <xref:System.Reflection.Emit.ModuleBuilder.GetType%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9a772-183">Las definiciones de tipo incompletas son objetos <xref:System.Reflection.Emit.TypeBuilder> construidos mediante <xref:System.Reflection.Emit?displayProperty=nameWithType>, pero en los que no se ha llamado a <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a772-183">Incomplete type definitions are <xref:System.Reflection.Emit.TypeBuilder> objects constructed using <xref:System.Reflection.Emit?displayProperty=nameWithType> but on which <xref:System.Reflection.Emit.TypeBuilder.CreateType%2A?displayProperty=nameWithType> has not been called.</span></span> <span data-ttu-id="9a772-184">Se puede usar ReflectionDimension para recuperar cualquier definición de tipo que se haya completado, es decir, un tipo que se haya cargado.</span><span class="sxs-lookup"><span data-stu-id="9a772-184">ReflectionDimension can be used to retrieve any type definition that has been completed, that is, a type that has been loaded.</span></span>

<span data-ttu-id="9a772-185">Para obtener acceso a las matrices en la reflexión, se debe especificar el rango de la matriz:</span><span class="sxs-lookup"><span data-stu-id="9a772-185">Arrays are accessed in reflection by specifying the rank of the array:</span></span>

- <span data-ttu-id="9a772-186">`Type.GetType("MyArray[]")` obtiene una matriz unidimensional con límite inferior 0.</span><span class="sxs-lookup"><span data-stu-id="9a772-186">`Type.GetType("MyArray[]")` gets a single-dimension array with 0 lower bound.</span></span>

- <span data-ttu-id="9a772-187">`Type.GetType("MyArray[*]")` obtiene una matriz unidimensional con límite inferior desconocido.</span><span class="sxs-lookup"><span data-stu-id="9a772-187">`Type.GetType("MyArray[*]")` gets a single-dimension array with unknown lower bound.</span></span>
- <span data-ttu-id="9a772-188">`Type.GetType("MyArray[][]")` obtiene una matriz de la matriz bidimensional.</span><span class="sxs-lookup"><span data-stu-id="9a772-188">`Type.GetType("MyArray[][]")` gets a two-dimensional array's array.</span></span>

- <span data-ttu-id="9a772-189">`Type.GetType("MyArray[*,*]")` y `Type.GetType("MyArray[,]")` obtienen una matriz bidimensional rectangular con límites inferiores desconocidos.</span><span class="sxs-lookup"><span data-stu-id="9a772-189">`Type.GetType("MyArray[*,*]")` and `Type.GetType("MyArray[,]")` gets a rectangular two-dimensional array with unknown lower bounds.</span></span>

<span data-ttu-id="9a772-190">Tenga en cuenta que, desde el punto de vista del tiempo de ejecución, `MyArray[] != MyArray[*]`, pero en el caso de las matrices multidimensionales, las dos notaciones son equivalentes.</span><span class="sxs-lookup"><span data-stu-id="9a772-190">Note that from a runtime point of view, `MyArray[] != MyArray[*]`, but for multidimensional arrays, the two notations are equivalent.</span></span> <span data-ttu-id="9a772-191">Es decir, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` se evalúa como **true**.</span><span class="sxs-lookup"><span data-stu-id="9a772-191">That is, `Type.GetType("MyArray [,]") == Type.GetType("MyArray[*,*]")` evaluates to **true**.</span></span>

<span data-ttu-id="9a772-192">Para **ModuleBuilder.GetType**, `MyArray[0..5]` indica una matriz unidimensional de tamaño 6 y límite inferior 0.</span><span class="sxs-lookup"><span data-stu-id="9a772-192">For **ModuleBuilder.GetType**, `MyArray[0..5]` indicates a single-dimension array with size 6, lower bound 0.</span></span> <span data-ttu-id="9a772-193">`MyArray[4…]` indica una matriz unidimensional de tamaño desconocido y límite inferior 4.</span><span class="sxs-lookup"><span data-stu-id="9a772-193">`MyArray[4…]` indicates a single-dimension array of unknown size and lower bound 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="9a772-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a772-194">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- <xref:System.Reflection.Emit.ModuleBuilder>
- <xref:System.Reflection.Emit.TypeBuilder>
- <xref:System.Type.FullName%2A?displayProperty=nameWithType>
- <xref:System.Type.GetType%2A?displayProperty=nameWithType>
- <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9a772-195">Ver información tipos</span><span class="sxs-lookup"><span data-stu-id="9a772-195">Viewing Type Information</span></span>](viewing-type-information.md)
