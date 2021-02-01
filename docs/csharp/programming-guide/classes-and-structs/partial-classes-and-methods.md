---
title: 'Clases y métodos parciales: Guía de programación de C#'
description: En C#, las clases y métodos parciales dividen la definición de una clase, una estructura, una interfaz o un método en dos o más archivos de código fuente.
ms.date: 07/20/2015
helpviewer_keywords:
- partial methods [C#]
- partial classes [C#]
- C# language, partial classes and methods
ms.assetid: 804cecb7-62db-4f97-a99f-60975bd59fa1
ms.openlocfilehash: cfda3b89bfd9dc046274dfa53d62a0789d4d597e
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899105"
---
# <a name="partial-classes-and-methods-c-programming-guide"></a><span data-ttu-id="5faaf-103">Clases y métodos parciales (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="5faaf-103">Partial Classes and Methods (C# Programming Guide)</span></span>

<span data-ttu-id="5faaf-104">Es posible dividir la definición de una [clase](../../language-reference/keywords/class.md), un [struct](../../language-reference/builtin-types/struct.md), una [interfaz](../../language-reference/keywords/interface.md) o un método en dos o más archivos de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5faaf-104">It is possible to split the definition of a [class](../../language-reference/keywords/class.md), a [struct](../../language-reference/builtin-types/struct.md), an [interface](../../language-reference/keywords/interface.md) or a method over two or more source files.</span></span> <span data-ttu-id="5faaf-105">Cada archivo de código fuente contiene una sección de la definición de tipo o método, y todos los elementos se combinan cuando se compila la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-105">Each source file contains a section of the type or method definition, and all parts are combined when the application is compiled.</span></span>

## <a name="partial-classes"></a><span data-ttu-id="5faaf-106">Clases parciales</span><span class="sxs-lookup"><span data-stu-id="5faaf-106">Partial Classes</span></span>

<span data-ttu-id="5faaf-107">Es recomendable dividir una definición de clase en varias situaciones:</span><span class="sxs-lookup"><span data-stu-id="5faaf-107">There are several situations when splitting a class definition is desirable:</span></span>

- <span data-ttu-id="5faaf-108">Cuando se trabaja con proyectos grandes, el hecho de repartir una clase entre archivos independientes permite que varios programadores trabajen en ella al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5faaf-108">When working on large projects, spreading a class over separate files enables multiple programmers to work on it at the same time.</span></span>

- <span data-ttu-id="5faaf-109">Cuando se trabaja con código fuente generado automáticamente, se puede agregar código a la clase sin tener que volver a crear el archivo de código fuente.</span><span class="sxs-lookup"><span data-stu-id="5faaf-109">When working with automatically generated source, code can be added to the class without having to recreate the source file.</span></span> <span data-ttu-id="5faaf-110">Visual Studio usa este enfoque al crear formularios Windows Forms, código de contenedor de servicio Web, etc.</span><span class="sxs-lookup"><span data-stu-id="5faaf-110">Visual Studio uses this approach when it creates Windows Forms, Web service wrapper code, and so on.</span></span> <span data-ttu-id="5faaf-111">Puede crear código que use estas clases sin necesidad de modificar el archivo creado por Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5faaf-111">You can create code that uses these classes without having to modify the file created by Visual Studio.</span></span>

- <span data-ttu-id="5faaf-112">Para dividir una definición de clase, use el modificador de palabra clave [partial](../../language-reference/keywords/partial-type.md), como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="5faaf-112">To split a class definition, use the [partial](../../language-reference/keywords/partial-type.md) keyword modifier, as shown here:</span></span>

  [!code-csharp[EmployeeExample#1](snippets/partial-classes-and-methods/Program.cs#1)]

<span data-ttu-id="5faaf-113">La palabra clave `partial` indica que se pueden definir en el espacio de nombres otros elementos de la clase, la estructura o la interfaz.</span><span class="sxs-lookup"><span data-stu-id="5faaf-113">The `partial` keyword indicates that other parts of the class, struct, or interface can be defined in the namespace.</span></span> <span data-ttu-id="5faaf-114">Todos los elementos deben usar la palabra clave `partial`.</span><span class="sxs-lookup"><span data-stu-id="5faaf-114">All the parts must use the `partial` keyword.</span></span> <span data-ttu-id="5faaf-115">Todos los elementos deben estar disponibles en tiempo de compilación para formar el tipo final.</span><span class="sxs-lookup"><span data-stu-id="5faaf-115">All the parts must be available at compile time to form the final type.</span></span> <span data-ttu-id="5faaf-116">Todos los elementos deben tener la misma accesibilidad, como `public`, `private`, etc.</span><span class="sxs-lookup"><span data-stu-id="5faaf-116">All the parts must have the same accessibility, such as `public`, `private`, and so on.</span></span>

<span data-ttu-id="5faaf-117">Si algún elemento se declara abstracto, todo el tipo se considera abstracto.</span><span class="sxs-lookup"><span data-stu-id="5faaf-117">If any part is declared abstract, then the whole type is considered abstract.</span></span> <span data-ttu-id="5faaf-118">Si algún elemento se declara sellado, todo el tipo se considera sellado.</span><span class="sxs-lookup"><span data-stu-id="5faaf-118">If any part is declared sealed, then the whole type is considered sealed.</span></span> <span data-ttu-id="5faaf-119">Si algún elemento declara un tipo base, todo el tipo hereda esa clase.</span><span class="sxs-lookup"><span data-stu-id="5faaf-119">If any part declares a base type, then the whole type inherits that class.</span></span>

<span data-ttu-id="5faaf-120">Todos los elementos que especifiquen una clase base deben coincidir, pero los elementos que omitan una clase base heredan igualmente el tipo base.</span><span class="sxs-lookup"><span data-stu-id="5faaf-120">All the parts that specify a base class must agree, but parts that omit a base class still inherit the base type.</span></span> <span data-ttu-id="5faaf-121">Los elementos pueden especificar diferentes interfaces base, y el tipo final implementa todas las interfaces enumeradas por todas las declaraciones parciales.</span><span class="sxs-lookup"><span data-stu-id="5faaf-121">Parts can specify different base interfaces, and the final type implements all the interfaces listed by all the partial declarations.</span></span> <span data-ttu-id="5faaf-122">Todas las clases, structs o miembros de interfaz declarados en una definición parcial están disponibles para todos los demás elementos.</span><span class="sxs-lookup"><span data-stu-id="5faaf-122">Any class, struct, or interface members declared in a partial definition are available to all the other parts.</span></span> <span data-ttu-id="5faaf-123">El tipo final es la combinación de todos los elementos en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-123">The final type is the combination of all the parts at compile time.</span></span>

> [!NOTE]
> <span data-ttu-id="5faaf-124">El modificador `partial` no está disponible en declaraciones de delegado o enumeración.</span><span class="sxs-lookup"><span data-stu-id="5faaf-124">The `partial` modifier is not available on delegate or enumeration declarations.</span></span>

<span data-ttu-id="5faaf-125">En el ejemplo siguiente se muestra que los tipos anidados pueden ser parciales, incluso si el tipo en el que están anidados no es parcial.</span><span class="sxs-lookup"><span data-stu-id="5faaf-125">The following example shows that nested types can be partial, even if the type they are nested within is not partial itself.</span></span>

[!code-csharp[NestedPartialTypes#2](snippets/partial-classes-and-methods/Program.cs#2)]

<span data-ttu-id="5faaf-126">En tiempo de compilación, se combinan los atributos de definiciones de tipo parcial.</span><span class="sxs-lookup"><span data-stu-id="5faaf-126">At compile time, attributes of partial-type definitions are merged.</span></span> <span data-ttu-id="5faaf-127">Por ejemplo, consideremos las siguientes declaraciones:</span><span class="sxs-lookup"><span data-stu-id="5faaf-127">For example, consider the following declarations:</span></span>

[!code-csharp[PartialMoonDeclarations#3](snippets/partial-classes-and-methods/Program.cs#3)]

<span data-ttu-id="5faaf-128">Son equivalentes a las declaraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5faaf-128">They are equivalent to the following declarations:</span></span>

[!code-csharp[SingleMoonDeclaration#4](snippets/partial-classes-and-methods/Program.cs#4)]

<span data-ttu-id="5faaf-129">A continuación se indican los elementos que se combinan de todas las definiciones de tipo parcial:</span><span class="sxs-lookup"><span data-stu-id="5faaf-129">The following are merged from all the partial-type definitions:</span></span>

- <span data-ttu-id="5faaf-130">comentarios XML</span><span class="sxs-lookup"><span data-stu-id="5faaf-130">XML comments</span></span>

- <span data-ttu-id="5faaf-131">interfaces</span><span class="sxs-lookup"><span data-stu-id="5faaf-131">interfaces</span></span>

- <span data-ttu-id="5faaf-132">atributos de parámetro de tipo genérico</span><span class="sxs-lookup"><span data-stu-id="5faaf-132">generic-type parameter attributes</span></span>

- <span data-ttu-id="5faaf-133">class (atributos)</span><span class="sxs-lookup"><span data-stu-id="5faaf-133">class attributes</span></span>

- <span data-ttu-id="5faaf-134">miembros</span><span class="sxs-lookup"><span data-stu-id="5faaf-134">members</span></span>

<span data-ttu-id="5faaf-135">Por ejemplo, consideremos las siguientes declaraciones:</span><span class="sxs-lookup"><span data-stu-id="5faaf-135">For example, consider the following declarations:</span></span>

[!code-csharp[PartialEarthDeclarations#5](snippets/partial-classes-and-methods/Program.cs#5)]

<span data-ttu-id="5faaf-136">Son equivalentes a las declaraciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5faaf-136">They are equivalent to the following declarations:</span></span>

[!code-csharp[SingleEarthDeclaration#6](snippets/partial-classes-and-methods/Program.cs#6)]

### <a name="restrictions"></a><span data-ttu-id="5faaf-137">Restricciones</span><span class="sxs-lookup"><span data-stu-id="5faaf-137">Restrictions</span></span>

<span data-ttu-id="5faaf-138">Debe seguir varias reglas al trabajar con definiciones de clase parcial:</span><span class="sxs-lookup"><span data-stu-id="5faaf-138">There are several rules to follow when you are working with partial class definitions:</span></span>

- <span data-ttu-id="5faaf-139">Todas las definiciones de tipo parcial que van a formar parte del mismo tipo deben modificarse con `partial`.</span><span class="sxs-lookup"><span data-stu-id="5faaf-139">All partial-type definitions meant to be parts of the same type must be modified with `partial`.</span></span> <span data-ttu-id="5faaf-140">Por ejemplo, las declaraciones de clase siguientes generan un error:</span><span class="sxs-lookup"><span data-stu-id="5faaf-140">For example, the following class declarations generate an error:</span></span>

  [!code-csharp[AllDefinitionsMustBePartials#7](snippets/partial-classes-and-methods/Program.cs#7)]

- <span data-ttu-id="5faaf-141">El modificador `partial` solo puede aparecer inmediatamente antes de las palabras clave `class`, `struct` o `interface`.</span><span class="sxs-lookup"><span data-stu-id="5faaf-141">The `partial` modifier can only appear immediately before the keywords `class`, `struct`, or `interface`.</span></span>

- <span data-ttu-id="5faaf-142">Se permiten tipos parciales anidados en definiciones de tipo parcial, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5faaf-142">Nested partial types are allowed in partial-type definitions as illustrated in the following example:</span></span>

  [!code-csharp[NestedPartialTypes#8](snippets/partial-classes-and-methods/Program.cs#8)]

- <span data-ttu-id="5faaf-143">Todas las definiciones de tipo parcial que van a formar parte del mismo tipo deben definirse en el mismo ensamblado y en el mismo módulo (archivo .exe o .dll).</span><span class="sxs-lookup"><span data-stu-id="5faaf-143">All partial-type definitions meant to be parts of the same type must be defined in the same assembly and the same module (.exe or .dll file).</span></span> <span data-ttu-id="5faaf-144">Las definiciones parciales no pueden abarcar varios módulos.</span><span class="sxs-lookup"><span data-stu-id="5faaf-144">Partial definitions cannot span multiple modules.</span></span>

- <span data-ttu-id="5faaf-145">El nombre de clase y los parámetros de tipo genérico deben coincidir en todas las definiciones de tipo parcial.</span><span class="sxs-lookup"><span data-stu-id="5faaf-145">The class name and generic-type parameters must match on all partial-type definitions.</span></span> <span data-ttu-id="5faaf-146">Los tipos genéricos pueden ser parciales.</span><span class="sxs-lookup"><span data-stu-id="5faaf-146">Generic types can be partial.</span></span> <span data-ttu-id="5faaf-147">Cada declaración parcial debe usar los mismos nombres de parámetro en el mismo orden.</span><span class="sxs-lookup"><span data-stu-id="5faaf-147">Each partial declaration must use the same parameter names in the same order.</span></span>

- <span data-ttu-id="5faaf-148">Las siguientes palabras clave son opcionales en una definición de tipo parcial, pero si están presentes la definición, no pueden entrar en conflicto con las palabras clave especificadas en otra definición parcial para el mismo tipo:</span><span class="sxs-lookup"><span data-stu-id="5faaf-148">The following keywords on a partial-type definition are optional, but if present on one partial-type definition, cannot conflict with the keywords specified on another partial definition for the same type:</span></span>

  - [<span data-ttu-id="5faaf-149">public</span><span class="sxs-lookup"><span data-stu-id="5faaf-149">public</span></span>](../../language-reference/keywords/public.md)

  - [<span data-ttu-id="5faaf-150">private</span><span class="sxs-lookup"><span data-stu-id="5faaf-150">private</span></span>](../../language-reference/keywords/private.md)

  - [<span data-ttu-id="5faaf-151">protected</span><span class="sxs-lookup"><span data-stu-id="5faaf-151">protected</span></span>](../../language-reference/keywords/protected.md)

  - [<span data-ttu-id="5faaf-152">internal</span><span class="sxs-lookup"><span data-stu-id="5faaf-152">internal</span></span>](../../language-reference/keywords/internal.md)

  - [<span data-ttu-id="5faaf-153">abstract</span><span class="sxs-lookup"><span data-stu-id="5faaf-153">abstract</span></span>](../../language-reference/keywords/abstract.md)

  - [<span data-ttu-id="5faaf-154">sealed</span><span class="sxs-lookup"><span data-stu-id="5faaf-154">sealed</span></span>](../../language-reference/keywords/sealed.md)

  - <span data-ttu-id="5faaf-155">clase base</span><span class="sxs-lookup"><span data-stu-id="5faaf-155">base class</span></span>

  - <span data-ttu-id="5faaf-156">modificador [new](../../language-reference/keywords/new-modifier.md) (elementos anidados)</span><span class="sxs-lookup"><span data-stu-id="5faaf-156">[new](../../language-reference/keywords/new-modifier.md) modifier (nested parts)</span></span>

  - <span data-ttu-id="5faaf-157">restricciones genéricas</span><span class="sxs-lookup"><span data-stu-id="5faaf-157">generic constraints</span></span>

<span data-ttu-id="5faaf-158">Para obtener más información, vea [Restricciones de tipos de parámetros](../generics/constraints-on-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="5faaf-158">For more information, see [Constraints on Type Parameters](../generics/constraints-on-type-parameters.md).</span></span>

## <a name="example-1"></a><span data-ttu-id="5faaf-159">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5faaf-159">Example 1</span></span>

### <a name="description"></a><span data-ttu-id="5faaf-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="5faaf-160">Description</span></span>

<span data-ttu-id="5faaf-161">En el ejemplo siguiente, los campos y el constructor de la clase, `Coords`, se declaran en una definición de clase parcial y el miembro `PrintCoords` se declara en otra definición de clase parcial.</span><span class="sxs-lookup"><span data-stu-id="5faaf-161">In the following example, the fields and the constructor of the class, `Coords`, are declared in one partial class definition, and the member, `PrintCoords`, is declared in another partial class definition.</span></span>

### <a name="code"></a><span data-ttu-id="5faaf-162">Código</span><span class="sxs-lookup"><span data-stu-id="5faaf-162">Code</span></span>

[!code-csharp[CoordsExample#9](snippets/partial-classes-and-methods/Program.cs#9)]

## <a name="example-2"></a><span data-ttu-id="5faaf-163">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="5faaf-163">Example 2</span></span>

### <a name="description"></a><span data-ttu-id="5faaf-164">Descripción</span><span class="sxs-lookup"><span data-stu-id="5faaf-164">Description</span></span>

<span data-ttu-id="5faaf-165">En el ejemplo siguiente se muestra que también se pueden desarrollar structs e interfaces parciales.</span><span class="sxs-lookup"><span data-stu-id="5faaf-165">The following example shows that you can also develop partial structs and interfaces.</span></span>

### <a name="code"></a><span data-ttu-id="5faaf-166">Código</span><span class="sxs-lookup"><span data-stu-id="5faaf-166">Code</span></span>

[!code-csharp[PartialStructsAndInterfaces#10](snippets/partial-classes-and-methods/Program.cs#10)]

## <a name="partial-methods"></a><span data-ttu-id="5faaf-167">Métodos Partial</span><span class="sxs-lookup"><span data-stu-id="5faaf-167">Partial Methods</span></span>

<span data-ttu-id="5faaf-168">Una clase o struct parcial puede contener un método parcial.</span><span class="sxs-lookup"><span data-stu-id="5faaf-168">A partial class or struct may contain a partial method.</span></span> <span data-ttu-id="5faaf-169">Un elemento de la clase contiene la firma del método.</span><span class="sxs-lookup"><span data-stu-id="5faaf-169">One part of the class contains the signature of the method.</span></span> <span data-ttu-id="5faaf-170">Se puede definir una implementación opcional en el mismo elemento o en otro.</span><span class="sxs-lookup"><span data-stu-id="5faaf-170">An optional implementation may be defined in the same part or another part.</span></span> <span data-ttu-id="5faaf-171">Si no se proporciona la implementación, el método y todas las llamadas al método se quitan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-171">If the implementation is not supplied, then the method and all calls to the method are removed at compile time.</span></span>

<span data-ttu-id="5faaf-172">Los métodos parciales permiten que el implementador de un elemento de una clase defina un método, similar a un evento.</span><span class="sxs-lookup"><span data-stu-id="5faaf-172">Partial methods enable the implementer of one part of a class to define a method, similar to an event.</span></span> <span data-ttu-id="5faaf-173">El implementador del otro elemento de la clase puede decidir si quiere implementar el método o no.</span><span class="sxs-lookup"><span data-stu-id="5faaf-173">The implementer of the other part of the class can decide whether to implement the method or not.</span></span> <span data-ttu-id="5faaf-174">Si el método no se implementa, el compilador quita la firma del método y todas las llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="5faaf-174">If the method is not implemented, then the compiler removes the method signature and all calls to the method.</span></span> <span data-ttu-id="5faaf-175">Las llamadas al método, incluidos los resultados que se producirían por la evaluación de los argumentos de las llamadas, no tienen efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5faaf-175">The calls to the method, including any results that would occur from evaluation of arguments in the calls, have no effect at run time.</span></span> <span data-ttu-id="5faaf-176">Por lo tanto, el código de la clase parcial puede usar libremente un método parcial, incluso si no se proporciona la implementación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-176">Therefore, any code in the partial class can freely use a partial method, even if the implementation is not supplied.</span></span> <span data-ttu-id="5faaf-177">No se producirá ningún error en tiempo de compilación o en tiempo de ejecución si se llama al método pero no se implementa.</span><span class="sxs-lookup"><span data-stu-id="5faaf-177">No compile-time or run-time errors will result if the method is called but not implemented.</span></span>

<span data-ttu-id="5faaf-178">Los métodos parciales son especialmente útiles para personalizar el código generado.</span><span class="sxs-lookup"><span data-stu-id="5faaf-178">Partial methods are especially useful as a way to customize generated code.</span></span> <span data-ttu-id="5faaf-179">Permiten reservar un nombre y firma de método de modo que el código generado pueda llamar al método, pero el desarrollador decide si se implementa el método.</span><span class="sxs-lookup"><span data-stu-id="5faaf-179">They allow for a method name and signature to be reserved, so that generated code can call the method but the developer can decide whether to implement the method.</span></span> <span data-ttu-id="5faaf-180">De manera muy similar a como hacen las clases parciales, los métodos parciales permiten que el código creado por un generador de código y el código creado por un desarrollador humano funcionen juntos sin costos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5faaf-180">Much like partial classes, partial methods enable code created by a code generator and code created by a human developer to work together without run-time costs.</span></span>

<span data-ttu-id="5faaf-181">Una declaración de método parcial consta de dos elementos: la definición y la implementación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-181">A partial method declaration consists of two parts: the definition, and the implementation.</span></span> <span data-ttu-id="5faaf-182">Pueden encontrarse en elementos independientes de una clase parcial o en el mismo elemento.</span><span class="sxs-lookup"><span data-stu-id="5faaf-182">These may be in separate parts of a partial class, or in the same part.</span></span> <span data-ttu-id="5faaf-183">Si no hay ninguna declaración de implementación, el compilador optimiza tanto la declaración de definición como todas las llamadas al método.</span><span class="sxs-lookup"><span data-stu-id="5faaf-183">If there is no implementation declaration, then the compiler optimizes away both the defining declaration and all calls to the method.</span></span>

```csharp
// Definition in file1.cs
partial void onNameChanged();

// Implementation in file2.cs
partial void onNameChanged()
{
  // method body
}
```

- <span data-ttu-id="5faaf-184">Las declaraciones de método parcial deben comenzar con la palabra clave contextual [partial](../../language-reference/keywords/partial-type.md) y el método debe devolver [void](../../language-reference/builtin-types/void.md).</span><span class="sxs-lookup"><span data-stu-id="5faaf-184">Partial method declarations must begin with the contextual keyword [partial](../../language-reference/keywords/partial-type.md) and the method must return [void](../../language-reference/builtin-types/void.md).</span></span>

- <span data-ttu-id="5faaf-185">Los métodos parciales pueden tener parámetros [in](../../language-reference/keywords/in-parameter-modifier.md) o [ref](../../language-reference/keywords/ref.md), pero no parámetros [out](../../language-reference/keywords/out-parameter-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="5faaf-185">Partial methods can have [in](../../language-reference/keywords/in-parameter-modifier.md) or [ref](../../language-reference/keywords/ref.md) but not [out](../../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>

- <span data-ttu-id="5faaf-186">Los métodos parciales son implícitamente [private](../../language-reference/keywords/private.md) y, por tanto, no pueden ser [virtual](../../language-reference/keywords/virtual.md).</span><span class="sxs-lookup"><span data-stu-id="5faaf-186">Partial methods are implicitly [private](../../language-reference/keywords/private.md), and therefore they cannot be [virtual](../../language-reference/keywords/virtual.md).</span></span>

- <span data-ttu-id="5faaf-187">Los métodos parciales no pueden ser [extern](../../language-reference/keywords/extern.md), ya que la presencia del cuerpo determina si son de definición o de implementación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-187">Partial methods cannot be [extern](../../language-reference/keywords/extern.md), because the presence of the body determines whether they are defining or implementing.</span></span>

- <span data-ttu-id="5faaf-188">Los métodos parciales pueden tener modificadores [static](../../language-reference/keywords/static.md) y [unsafe](../../language-reference/keywords/unsafe.md).</span><span class="sxs-lookup"><span data-stu-id="5faaf-188">Partial methods can have [static](../../language-reference/keywords/static.md) and [unsafe](../../language-reference/keywords/unsafe.md) modifiers.</span></span>

- <span data-ttu-id="5faaf-189">Los métodos parciales pueden ser genéricos.</span><span class="sxs-lookup"><span data-stu-id="5faaf-189">Partial methods can be generic.</span></span> <span data-ttu-id="5faaf-190">Las restricciones se colocan en la declaración de método parcial de definición y opcionalmente pueden repetirse en el de implementación.</span><span class="sxs-lookup"><span data-stu-id="5faaf-190">Constraints are put on the defining partial method declaration, and may optionally be repeated on the implementing one.</span></span> <span data-ttu-id="5faaf-191">Los nombres del parámetro y del parámetro de tipo no tienen que ser iguales en la declaración de implementación y en la declaración de definición.</span><span class="sxs-lookup"><span data-stu-id="5faaf-191">Parameter and type parameter names do not have to be the same in the implementing declaration as in the defining one.</span></span>

- <span data-ttu-id="5faaf-192">Puede crear un [delegado](../../language-reference/builtin-types/reference-types.md) para un método parcial que se ha definido e implementado, pero no para un método parcial que solo se ha definido.</span><span class="sxs-lookup"><span data-stu-id="5faaf-192">You can make a [delegate](../../language-reference/builtin-types/reference-types.md) to a partial method that has been defined and implemented, but not to a partial method that has only been defined.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="5faaf-193">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="5faaf-193">C# Language Specification</span></span>

<span data-ttu-id="5faaf-194">Para obtener más información, vea la sección [Tipos parciales](~/_csharplang/spec/classes.md#partial-types) de la [Especificación del lenguaje C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="5faaf-194">For more information, see [Partial types](~/_csharplang/spec/classes.md#partial-types) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="5faaf-195">La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.</span><span class="sxs-lookup"><span data-stu-id="5faaf-195">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="5faaf-196">Vea también</span><span class="sxs-lookup"><span data-stu-id="5faaf-196">See also</span></span>

- [<span data-ttu-id="5faaf-197">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="5faaf-197">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5faaf-198">Clases</span><span class="sxs-lookup"><span data-stu-id="5faaf-198">Classes</span></span>](./classes.md)
- [<span data-ttu-id="5faaf-199">Tipos de estructura</span><span class="sxs-lookup"><span data-stu-id="5faaf-199">Structure types</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="5faaf-200">Interfaces</span><span class="sxs-lookup"><span data-stu-id="5faaf-200">Interfaces</span></span>](../interfaces/index.md)
- [<span data-ttu-id="5faaf-201">partial (Tipos)</span><span class="sxs-lookup"><span data-stu-id="5faaf-201">partial (Type)</span></span>](../../language-reference/keywords/partial-type.md)
