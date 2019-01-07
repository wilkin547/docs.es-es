---
title: Tipos de valor - Referencia de C#
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 77aed78e7822e06b3b1e6c48b07790d93e09559c
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612730"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="3fec9-102">Tipos de valor (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="3fec9-102">Value types (C# Reference)</span></span>

<span data-ttu-id="3fec9-103">Existen dos clases de tipos de valor:</span><span class="sxs-lookup"><span data-stu-id="3fec9-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="3fec9-104">Structs</span><span class="sxs-lookup"><span data-stu-id="3fec9-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="3fec9-105">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="3fec9-105">Enumerations</span></span>](enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="3fec9-106">Características principales de los tipos de valor</span><span class="sxs-lookup"><span data-stu-id="3fec9-106">Main features of value types</span></span>

<span data-ttu-id="3fec9-107">Una variable de un tipo de valor contiene un valor del tipo.</span><span class="sxs-lookup"><span data-stu-id="3fec9-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="3fec9-108">Por ejemplo, una variable del tipo `int` podría contener el valor `42`.</span><span class="sxs-lookup"><span data-stu-id="3fec9-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="3fec9-109">Esto difiere de una variable de un tipo de referencia, que contiene una referencia a una instancia del tipo y que también se conoce como un objeto.</span><span class="sxs-lookup"><span data-stu-id="3fec9-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="3fec9-110">Al asignar un nuevo valor a una variable de un tipo de valor, se copia ese valor.</span><span class="sxs-lookup"><span data-stu-id="3fec9-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="3fec9-111">Al asignar un nuevo valor a una variable de un tipo de referencia, se copia la referencia, no el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="3fec9-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="3fec9-112">Todos los tipos de valor se derivan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3fec9-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="3fec9-113">A diferencia de los tipos de referencia, no puede derivar un tipo nuevo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="3fec9-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="3fec9-114">En cambio, como los tipos de referencia, los structs pueden implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="3fec9-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="3fec9-115">Las variables de tipo de valor no pueden ser `null` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3fec9-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="3fec9-116">Sin embargo, las variables de los [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) correspondientes pueden ser `null`.</span><span class="sxs-lookup"><span data-stu-id="3fec9-116">However, variables of the corresponding [nullable types](../../../csharp/programming-guide/nullable-types/index.md) can be `null`.</span></span>

<span data-ttu-id="3fec9-117">Cada tipo de valor tiene un constructor predeterminado implícito que inicializa el valor predeterminado de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="3fec9-117">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="3fec9-118">Para información sobre los valores predeterminados de los tipos de valor, vea [Tabla de valores predeterminados](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="3fec9-119">Tipos simples</span><span class="sxs-lookup"><span data-stu-id="3fec9-119">Simple types</span></span>

<span data-ttu-id="3fec9-120">Los *tipos simples* son un conjunto de tipos struct predefinidos proporcionados por C# y comprenden los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="3fec9-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="3fec9-121">[Tipos enteros](integral-types-table.md): tipos numéricos enteros y tipo [char](char.md)</span><span class="sxs-lookup"><span data-stu-id="3fec9-121">[Integral types](integral-types-table.md): integer numeric types and the [char](char.md) type</span></span>
- [<span data-ttu-id="3fec9-122">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="3fec9-122">Floating-point types</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="3fec9-123">bool</span><span class="sxs-lookup"><span data-stu-id="3fec9-123">bool</span></span>](bool.md)

<span data-ttu-id="3fec9-124">Los tipos simples se identifican mediante palabras clave, pero estas palabras clave son simplemente los alias para tipos struct predefinidos en el espacio de nombres <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="3fec9-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="3fec9-125">Por ejemplo, [int](int.md) es un alias de <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="3fec9-125">For example, [int](int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="3fec9-126">Para una lista completa de alias, vea [Tabla de tipos integrados](built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="3fec9-127">Los tipos simples se diferencian de otros tipos struct en que permiten determinadas operaciones adicionales:</span><span class="sxs-lookup"><span data-stu-id="3fec9-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="3fec9-128">Los tipos simples pueden inicializarse mediante el uso de literales.</span><span class="sxs-lookup"><span data-stu-id="3fec9-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="3fec9-129">Por ejemplo, `'A'` es un literal del tipo `char` y `2001` es un literal del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="3fec9-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="3fec9-130">Puede declarar constantes de los tipos simples con la palabra clave [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="3fec9-131">No es posible tener constantes de otros tipos struct.</span><span class="sxs-lookup"><span data-stu-id="3fec9-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="3fec9-132">Las expresiones constantes, cuyos operandos son todas constantes de tipo simple, se evalúan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="3fec9-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="3fec9-133">Para más información, vea la sección [Tipos simples](~/_csharplang/spec/types.md#simple-types) de la [Especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="3fec9-134">Inicialización de tipos de valor</span><span class="sxs-lookup"><span data-stu-id="3fec9-134">Initializing value types</span></span>

<span data-ttu-id="3fec9-135">Las variables locales en C# deben inicializarse antes de usarse.</span><span class="sxs-lookup"><span data-stu-id="3fec9-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="3fec9-136">Por ejemplo, puede declarar una variable local sin inicialización como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3fec9-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="3fec9-137">No puede usarla antes de inicializarla.</span><span class="sxs-lookup"><span data-stu-id="3fec9-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="3fec9-138">Puede inicializarla con la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="3fec9-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke default constructor for int type.
```

<span data-ttu-id="3fec9-139">Esta instrucción es equivalente a la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="3fec9-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="3fec9-140">Por supuesto, puede tener la declaración y la inicialización en la misma instrucción como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="3fec9-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="3fec9-141">-O bien-</span><span class="sxs-lookup"><span data-stu-id="3fec9-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="3fec9-142">Con el operador [new](new.md) se llama al constructor predeterminado del tipo específico y asigna el valor predeterminado a la variable.</span><span class="sxs-lookup"><span data-stu-id="3fec9-142">Using the [new](new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="3fec9-143">En el ejemplo anterior, el constructor predeterminado ha asignado el valor `0` a `myInt`.</span><span class="sxs-lookup"><span data-stu-id="3fec9-143">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="3fec9-144">Para más información sobre los valores que se han asignado llamando a los constructores predeterminados, vea [Tabla de valores predeterminados](default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-144">For more information about values assigned by calling default constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="3fec9-145">Con los tipos definidos por el usuario, use [new](new.md) para invocar al constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3fec9-145">With user-defined types, use [new](new.md) to invoke the default constructor.</span></span> <span data-ttu-id="3fec9-146">Por ejemplo, la siguiente instrucción invoca al constructor predeterminado del struct `Point`:</span><span class="sxs-lookup"><span data-stu-id="3fec9-146">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>

```csharp
Point p = new Point(); // Invoke default constructor for the struct.
```

<span data-ttu-id="3fec9-147">Después de esta llamada, el struct se considera asignado definitivamente; es decir, todos sus miembros se inicializan a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="3fec9-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="3fec9-148">Para obtener más información acerca del operador `new`, vea [new](new.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-148">For more information about the `new` operator, see [new](new.md).</span></span>

<span data-ttu-id="3fec9-149">Para información sobre cómo aplicar formato al resultado de los tipos numéricos, vea [Tabla de formatos de presentación para valores numéricos](formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="3fec9-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3fec9-150">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fec9-150">See also</span></span>

- [<span data-ttu-id="3fec9-151">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="3fec9-151">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3fec9-152">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="3fec9-152">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3fec9-153">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="3fec9-153">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3fec9-154">Tipos</span><span class="sxs-lookup"><span data-stu-id="3fec9-154">Types</span></span>](types.md)
- [<span data-ttu-id="3fec9-155">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="3fec9-155">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="3fec9-156">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="3fec9-156">Reference Types</span></span>](reference-types.md)
- <span data-ttu-id="3fec9-157">[Nullable types](../../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="3fec9-157">[Nullable types](../../programming-guide/nullable-types/index.md)</span></span>