---
title: Novedades de C# 7.3
description: Información general sobre las nuevas características en C# 7.3
ms.date: 05/16/2018
ms.openlocfilehash: 1d1aca2564c26315cf8b3af60a863ea3c70fd385
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827103"
---
# <a name="whats-new-in-c-73"></a><span data-ttu-id="9aa9d-103">Novedades de C# 7.3</span><span class="sxs-lookup"><span data-stu-id="9aa9d-103">What's new in C# 7.3</span></span>

<span data-ttu-id="9aa9d-104">Hay dos temas principales para la versión C# 7.3.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-104">There are two main themes to the C# 7.3 release.</span></span> <span data-ttu-id="9aa9d-105">Un tema proporciona características que permiten al código seguro ser tan eficaz como el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-105">One theme provides features that enable safe code to be as performant as unsafe code.</span></span> <span data-ttu-id="9aa9d-106">El segundo tema proporciona mejoras incrementales en las características existentes.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-106">The second theme provides incremental improvements to existing features.</span></span> <span data-ttu-id="9aa9d-107">Además, se han agregado nuevas opciones de compilador en esta versión.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-107">In addition, new compiler options were added in this release.</span></span>

<span data-ttu-id="9aa9d-108">Las siguientes características nuevas admiten el tema del mejor rendimiento para código seguro:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-108">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="9aa9d-109">Puede tener acceso a campos fijos sin anclar.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-109">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="9aa9d-110">Puede volver a asignar variables locales `ref`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-110">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="9aa9d-111">Puede usar inicializadores en matrices `stackalloc`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-111">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="9aa9d-112">Puede usar instrucciones `fixed` con cualquier tipo que admita un patrón.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-112">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="9aa9d-113">Puede usar restricciones genéricas adicionales.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-113">You can use additional generic constraints.</span></span>

<span data-ttu-id="9aa9d-114">Se hicieron las mejoras siguientes a las características existentes:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-114">The following enhancements were made to existing features:</span></span>

- <span data-ttu-id="9aa9d-115">Puede probar `==` y `!=` con los tipos de tupla.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-115">You can test `==` and `!=` with tuple types.</span></span>
- <span data-ttu-id="9aa9d-116">Puede usar variables de expresión en más ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-116">You can use expression variables in more locations.</span></span>
- <span data-ttu-id="9aa9d-117">Puede asociar atributos al campo de respaldo de las propiedades autoimplementadas.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-117">You may attach attributes to the backing field of auto-implemented properties.</span></span>
- <span data-ttu-id="9aa9d-118">Se ha mejorado la resolución de métodos cuando los argumentos difieren por `in`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-118">Method resolution when arguments differ by `in` has been improved.</span></span>
- <span data-ttu-id="9aa9d-119">Ahora, la resolución de sobrecarga tiene menos casos ambiguos.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-119">Overload resolution now has fewer ambiguous cases.</span></span>

<span data-ttu-id="9aa9d-120">Las nuevas opciones del compilador son:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-120">The new compiler options are:</span></span>

- <span data-ttu-id="9aa9d-121">`-publicsign` para habilitar la firma de ensamblados de software de código abierto (OSS).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-121">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="9aa9d-122">`-pathmap` para proporcionar una asignación para los directorios de origen.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-122">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="9aa9d-123">El resto de este artículo proporciona información detallada y vínculos para obtener más información sobre cada una de las mejoras.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-123">The remainder of this article provides details and links to learn more about each of the improvements.</span></span>

## <a name="enabling-more-performant-safe-code"></a><span data-ttu-id="9aa9d-124">Habilitación de código seguro con mejor rendimiento</span><span class="sxs-lookup"><span data-stu-id="9aa9d-124">Enabling more performant safe code</span></span>

<span data-ttu-id="9aa9d-125">Debería poder escribir código de C# de forma segura que tenga el mismo rendimiento que el código no seguro.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-125">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="9aa9d-126">El código seguro evita clases de errores, como desbordamientos de búfer, punteros perdidos y otros errores de acceso a la memoria.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-126">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="9aa9d-127">Estas nuevas características amplían las capacidades de código seguro comprobable.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-127">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="9aa9d-128">Procure escribir más código utilizando construcciones seguras.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-128">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="9aa9d-129">Estas características lo facilitan en gran medida.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-129">These features make that easier.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="9aa9d-130">Indexación de campos `fixed` sin requerir anclaje</span><span class="sxs-lookup"><span data-stu-id="9aa9d-130">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="9aa9d-131">Considere esta estructura:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-131">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="9aa9d-132">En versiones anteriores de C#, era necesario anclar una variable para acceder a uno de los enteros que forman parte de `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-132">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="9aa9d-133">Ahora, el siguiente código se compila en un contexto seguro:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-133">Now, the following code compiles in a safe context:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="9aa9d-134">La variable `p` tiene acceso a un elemento en `myFixedField`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-134">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="9aa9d-135">No es necesario declarar otra variable `int*` independiente.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-135">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="9aa9d-136">Tenga en cuenta que todavía necesita un contexto `unsafe`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-136">Note that you still need an `unsafe` context.</span></span> <span data-ttu-id="9aa9d-137">En versiones anteriores de C#, es necesario declarar un segundo puntero fijo:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-137">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="9aa9d-138">Para obtener más información, consulte el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-138">Fore more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="ref-local-variables-may-be-reassigned"></a><span data-ttu-id="9aa9d-139">Las variables locales de `ref` se pueden reasignar</span><span class="sxs-lookup"><span data-stu-id="9aa9d-139">`ref` local variables may be reassigned</span></span>

<span data-ttu-id="9aa9d-140">Ahora, las variables locales de `ref` pueden reasignarse para hacer referencia a instancias diferentes después de haberse inicializado.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-140">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="9aa9d-141">El código siguiente ahora compila:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-141">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="9aa9d-142">Para obtener más información, consulte el artículo sobre [valores devueltos `ref` y variables locales de tipo `ref`](../programming-guide/classes-and-structs/ref-returns.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-142">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="9aa9d-143">Las matrices `stackalloc` admiten inicializadores</span><span class="sxs-lookup"><span data-stu-id="9aa9d-143">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="9aa9d-144">Ha podido especificar los valores para los elementos en una matriz cuando la inicializa:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-144">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="9aa9d-145">Ahora, esa misma sintaxis se puede aplicar a las matrices que se declaran con `stackalloc`:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-145">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="9aa9d-146">Para más información, vea el artículo sobre la [instrucción `stackalloc`](../language-reference/keywords/stackalloc.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-146">For more information, see the [`stackalloc` statement](../language-reference/keywords/stackalloc.md) article in the language reference.</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="9aa9d-147">Hay más tipos compatibles con la instrucción `fixed`</span><span class="sxs-lookup"><span data-stu-id="9aa9d-147">More types support the `fixed` statement</span></span>

<span data-ttu-id="9aa9d-148">La instrucción `fixed` admite un conjunto limitado de tipos.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-148">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="9aa9d-149">A partir de C# 7.3, cualquier tipo que contenga un método `GetPinnableReference()` que devuelve un `ref T` o `ref readonly T` puede ser `fixed`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-149">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="9aa9d-150">La adición de esta característica significa que `fixed` puede utilizarse con <xref:System.Span%601?displayProperty=nameWithType> y tipos relacionados.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-150">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="9aa9d-151">Para más información, vea el artículo sobre la [instrucción `fixed`](../language-reference/keywords/fixed-statement.md) en la referencia del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-151">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="9aa9d-152">Restricciones genéricas mejoradas</span><span class="sxs-lookup"><span data-stu-id="9aa9d-152">Enhanced generic constraints</span></span>

<span data-ttu-id="9aa9d-153">Ahora puede especificar el tipo <xref:System.Enum?displayProperty=nameWithType> o <xref:System.Delegate?displayProperty=nameWithType> como restricciones de clase base para un parámetro de tipo.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-153">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="9aa9d-154">También puede usar la nueva restricción `unmanaged` para especificar que el parámetro de tipo debe ser un **tipo no administrado**.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-154">You can also use the new `unmanaged` constraint, to specify that a type parameter must be an **unmanaged type**.</span></span> <span data-ttu-id="9aa9d-155">Un **tipo no administrado** es un tipo que no es un tipo de referencia y no contiene ningún tipo de referencia en ningún nivel de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-155">An **unmanaged type** is a type that isn't a reference type and doesn't contain any reference type at any level of nesting.</span></span>

<span data-ttu-id="9aa9d-156">Para obtener más información, vea los artículos sobre [restricciones genéricas de `where`](../language-reference/keywords/where-generic-type-constraint.md) y [restricciones sobre parámetros de tipo](../programming-guide/generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-156">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

## <a name="make-existing-features-better"></a><span data-ttu-id="9aa9d-157">Mejora de las características existentes</span><span class="sxs-lookup"><span data-stu-id="9aa9d-157">Make existing features better</span></span>

<span data-ttu-id="9aa9d-158">El segundo tema proporciona las mejoras a las características del lenguaje.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-158">The second theme provides improvements to features in the language.</span></span> <span data-ttu-id="9aa9d-159">Estas características mejoran la productividad al escribir C#.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-159">These features improve productivity when writing C#.</span></span>

### <a name="tuples-support--and-"></a><span data-ttu-id="9aa9d-160">Compatibilidad con tuplas `==` y `!=`</span><span class="sxs-lookup"><span data-stu-id="9aa9d-160">Tuples support `==` and `!=`</span></span>

<span data-ttu-id="9aa9d-161">Los tipos de tupla de C# ahora admiten `==` y `!=`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-161">The C# tuple types now support `==` and `!=`.</span></span> <span data-ttu-id="9aa9d-162">Para obtener más información, vea la sección que trata la [igualdad](../tuples.md#equality-and-tuples) en el artículo sobre [tuplas](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-162">Fore more information, see the section covering [equality](../tuples.md#equality-and-tuples) in the article on [tuples](../tuples.md).</span></span>

### <a name="attach-attributes-to-the-backing-fields-for-auto-implemented-properties"></a><span data-ttu-id="9aa9d-163">Asociación de atributos campos de respaldo para las propiedades autoimplementadas</span><span class="sxs-lookup"><span data-stu-id="9aa9d-163">Attach attributes to the backing fields for auto-implemented properties</span></span>

<span data-ttu-id="9aa9d-164">Esta sintaxis ahora se admite:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-164">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="9aa9d-165">El atributo `SomeThingAboutFieldAttribute` se aplica al campo de respaldo generado por el compilador para `SomeProperty`.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-165">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="9aa9d-166">Para obtener más información, vea [atributos](../programming-guide/concepts/attributes/index.md) en la guía de programación de C#.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-166">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

### <a name="in-method-overload-resolution-tiebreaker"></a><span data-ttu-id="9aa9d-167">Factor de desempate de resolución de sobrecargas del método `in`</span><span class="sxs-lookup"><span data-stu-id="9aa9d-167">`in` method overload resolution tiebreaker</span></span>

<span data-ttu-id="9aa9d-168">Cuando se agregó el modificador de argumentos `in`, estos dos métodos causarían una ambigüedad:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-168">When the `in` argument modifier was added, these two methods would cause an ambiguity:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="9aa9d-169">Ahora, la sobrecarga por valor (primera en el ejemplo anterior) es mejor que la de la versión de referencia de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-169">Now, the by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="9aa9d-170">Para llamar a la versión con el argumento de referencia de solo lectura, debe incluir el modificador `in` cuando llame al método.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-170">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

> [!NOTE]
> <span data-ttu-id="9aa9d-171">Esto se implementó como una corrección de errores.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-171">This was implemented as a bug fix.</span></span> <span data-ttu-id="9aa9d-172">Ya no es ambiguo, incluso con la versión de lenguaje establecida en "7.2".</span><span class="sxs-lookup"><span data-stu-id="9aa9d-172">This no longer is ambiguous even with the language version set to "7.2".</span></span>

<span data-ttu-id="9aa9d-173">Para obtener más información, consulte el artículo sobre el [modificador de parámetros`in`](../language-reference/keywords/in-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-173">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="extend-expression-variables-in-initializers"></a><span data-ttu-id="9aa9d-174">Ampliación de variables de la expresión en inicializadores</span><span class="sxs-lookup"><span data-stu-id="9aa9d-174">Extend expression variables in initializers</span></span>

<span data-ttu-id="9aa9d-175">La sintaxis que se agregó en C# 7.0 para permitir declaraciones de variable `out` se ha ampliado para incluir inicializadores de campo, inicializadores de propiedad, inicializadores de constructor y cláusulas de consulta.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-175">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="9aa9d-176">Permite código como el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-176">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : B(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

### <a name="improved-overload-candidates"></a><span data-ttu-id="9aa9d-177">Mejoras en los candidatos de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="9aa9d-177">Improved overload candidates</span></span>

<span data-ttu-id="9aa9d-178">En cada versión, las reglas de resolución de sobrecarga se actualizan para abordar situaciones en las que las invocaciones de métodos ambiguos tienen una opción "obvia".</span><span class="sxs-lookup"><span data-stu-id="9aa9d-178">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="9aa9d-179">Esta versión agrega tres nuevas reglas para ayudar a que el compilador elija la opción obvia:</span><span class="sxs-lookup"><span data-stu-id="9aa9d-179">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="9aa9d-180">Cuando un grupo de métodos contiene tanto miembros de instancia como estáticos, el compilador descarta los miembros de la instancia si el método fue invocado sin un receptor o contexto de instancia.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-180">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="9aa9d-181">El compilador descarta los miembros estáticos si el método se invocó con un receptor de instancia.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-181">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="9aa9d-182">Cuando no hay ningún receptor, el compilador incluye solo miembros estáticos en un contexto estático; de lo contrario, miembros estáticos y de instancia.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-182">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="9aa9d-183">Cuando el receptor es ambiguamente una instancia o un tipo, el compilador incluye ambos.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-183">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="9aa9d-184">Un contexto estático, donde no se puede usar un receptor de instancia `this` implícito, incluye el cuerpo de miembros donde no se define `this`, como miembros estáticos, así como lugares donde `this` no se puede usar, como inicializadores de campo e inicializadores-constructores.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-184">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="9aa9d-185">Cuando un grupo de métodos contiene algunos métodos genéricos cuyos argumentos de tipo no cumplen con sus restricciones, estos miembros se eliminan del conjunto de candidatos.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-185">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="9aa9d-186">En el caso de una conversión de grupo de métodos, los métodos candidatos cuyo tipo de valor devuelto no coincide con el tipo de valor devuelto del delegado se eliminan del conjunto.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-186">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="9aa9d-187">Solo notará este cambio porque encontrará menos errores de compilación para sobrecargas ambiguas de métodos cuando esté seguro de qué método es mejor.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-187">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="9aa9d-188">Nuevas opciones del compilador</span><span class="sxs-lookup"><span data-stu-id="9aa9d-188">New compiler options</span></span>

<span data-ttu-id="9aa9d-189">Las nuevas opciones de compilador admiten nuevos escenarios de DevOps y compilación de programas de C#.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-189">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="9aa9d-190">Firma pública o de código abierto</span><span class="sxs-lookup"><span data-stu-id="9aa9d-190">Public or Open Source signing</span></span>

<span data-ttu-id="9aa9d-191">La opción del compilador `-publicsign` indica al compilador que firme el ensamblado con una clave pública.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-191">The `-publicsign` compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="9aa9d-192">El ensamblado se marca como firmado, pero la firma se toma de la clave pública.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-192">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="9aa9d-193">Esta opción le permite crear ensamblados firmados a partir de proyectos de código abierto utilizando una clave pública.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-193">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="9aa9d-194">Para obtener más información, vea el artículo [-filealign (Opciones del compilador de C#)](../language-reference/compiler-options/publicsign-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-194">For more information, see the [-publicsign compiler option](../language-reference/compiler-options/publicsign-compiler-option.md) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="9aa9d-195">pathmap</span><span class="sxs-lookup"><span data-stu-id="9aa9d-195">pathmap</span></span>

<span data-ttu-id="9aa9d-196">La opción del compilador `-pathmap` indica al compilador que reemplace las rutas de acceso de origen del entorno de compilación por rutas de acceso de origen asignadas.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-196">The `-pathmap` compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="9aa9d-197">La opción `-pathmap` controla la ruta de acceso de origen escrita por el compilador en los archivos PDB o para <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span><span class="sxs-lookup"><span data-stu-id="9aa9d-197">The `-pathmap` option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="9aa9d-198">Para obtener más información, vea el artículo [-pathmap (opciones del compilador de C#)](../language-reference/compiler-options/pathmap-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="9aa9d-198">For more information, see the [-pathmap compiler option](../language-reference/compiler-options/pathmap-compiler-option.md) article.</span></span>
