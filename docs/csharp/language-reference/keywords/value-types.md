---
title: Tipos de valor (Referencia de C#)
ms.date: 07/20/2015
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 3bbaea9247d975c27ed6f49dedb749312f675296
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2018
ms.locfileid: "43487070"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="89fed-102">Tipos de valor (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="89fed-102">Value Types (C# Reference)</span></span>
<span data-ttu-id="89fed-103">Los tipos de valor constan de dos categorías principales:</span><span class="sxs-lookup"><span data-stu-id="89fed-103">The value types consist of two main categories:</span></span>  
  
-   [<span data-ttu-id="89fed-104">Structs</span><span class="sxs-lookup"><span data-stu-id="89fed-104">Structs</span></span>](../../../csharp/language-reference/keywords/struct.md)  
  
-   [<span data-ttu-id="89fed-105">Enumeraciones</span><span class="sxs-lookup"><span data-stu-id="89fed-105">Enumerations</span></span>](../../../csharp/language-reference/keywords/enum.md)  
  
 <span data-ttu-id="89fed-106">Los structs se dividen en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="89fed-106">Structs fall into these categories:</span></span>  
  
-   <span data-ttu-id="89fed-107">Tipos numéricos</span><span class="sxs-lookup"><span data-stu-id="89fed-107">Numeric types</span></span>  
  
    -   [<span data-ttu-id="89fed-108">Tipos enteros</span><span class="sxs-lookup"><span data-stu-id="89fed-108">Integral types</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
  
    -   [<span data-ttu-id="89fed-109">Tipos de punto flotante</span><span class="sxs-lookup"><span data-stu-id="89fed-109">Floating-point types</span></span>](../../../csharp/language-reference/keywords/floating-point-types-table.md)  
  
-   [<span data-ttu-id="89fed-110">bool</span><span class="sxs-lookup"><span data-stu-id="89fed-110">bool</span></span>](../../../csharp/language-reference/keywords/bool.md)  
  
-   <span data-ttu-id="89fed-111">Structs definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="89fed-111">User defined structs.</span></span>  
  
## <a name="main-features-of-value-types"></a><span data-ttu-id="89fed-112">Características principales de los tipos de valor</span><span class="sxs-lookup"><span data-stu-id="89fed-112">Main Features of Value Types</span></span>  
 <span data-ttu-id="89fed-113">Las variables que se basan en tipos de valor directamente contienen valores.</span><span class="sxs-lookup"><span data-stu-id="89fed-113">Variables that are based on value types directly contain values.</span></span> <span data-ttu-id="89fed-114">Asignar una variable de tipo de valor a otra copia el valor incluido.</span><span class="sxs-lookup"><span data-stu-id="89fed-114">Assigning one value type variable to another copies the contained value.</span></span> <span data-ttu-id="89fed-115">Esto difiere de la asignación de variables de tipo de referencia, que copia una referencia al objeto pero no el propio objeto.</span><span class="sxs-lookup"><span data-stu-id="89fed-115">This differs from the assignment of reference type variables, which copies a reference to the object but not the object itself.</span></span>  
  
 <span data-ttu-id="89fed-116">Todos los tipos de valor se derivan implícitamente de <xref:System.ValueType?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89fed-116">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="89fed-117">A diferencia de los tipos de referencia, no puede derivar un tipo nuevo de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="89fed-117">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="89fed-118">En cambio, como los tipos de referencia, los structs pueden implementar interfaces.</span><span class="sxs-lookup"><span data-stu-id="89fed-118">However, like reference types, structs can implement interfaces.</span></span>  
  
 <span data-ttu-id="89fed-119">A diferencia de los tipos de referencia, un tipo de valor no puede contener el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="89fed-119">Unlike reference types, a value type cannot contain the `null` value.</span></span> <span data-ttu-id="89fed-120">En cambio, la característica [tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/index.md) se permite para los tipos de valor que se van a asignar a `null`.</span><span class="sxs-lookup"><span data-stu-id="89fed-120">However, the [nullable types](../../../csharp/programming-guide/nullable-types/index.md) feature does allow for value types to be assigned to `null`.</span></span>  
  
 <span data-ttu-id="89fed-121">Cada tipo de valor tiene un constructor predeterminado implícito que inicializa el valor predeterminado de ese tipo.</span><span class="sxs-lookup"><span data-stu-id="89fed-121">Each value type has an implicit default constructor that initializes the default value of that type.</span></span> <span data-ttu-id="89fed-122">Para obtener información sobre los valores predeterminados de los tipos de valor, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="89fed-122">For information about default values of value types, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
## <a name="main-features-of-simple-types"></a><span data-ttu-id="89fed-123">Características principales de los tipos simples</span><span class="sxs-lookup"><span data-stu-id="89fed-123">Main Features of Simple Types</span></span>  
 <span data-ttu-id="89fed-124">Todos los tipos simples, integrales del lenguaje de C#, son alias de los tipos de sistema de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="89fed-124">All of the simple types -- those integral to the C# language -- are aliases of the .NET Framework System types.</span></span> <span data-ttu-id="89fed-125">Por ejemplo, [int](../../../csharp/language-reference/keywords/int.md) es un alias de <xref:System.Int32?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="89fed-125">For example, [int](../../../csharp/language-reference/keywords/int.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="89fed-126">Para obtener una lista completa de los alias, vea [Tabla de tipos integrados](../../../csharp/language-reference/keywords/built-in-types-table.md).</span><span class="sxs-lookup"><span data-stu-id="89fed-126">For a complete list of aliases, see [Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md).</span></span>  
  
 <span data-ttu-id="89fed-127">Las expresiones constantes, cuyos operandos son todos constantes de tipo simple, se evalúan en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="89fed-127">Constant expressions, whose operands are all simple type constants, are evaluated at compilation time.</span></span>  
  
 <span data-ttu-id="89fed-128">Los tipos simples pueden inicializarse mediante el uso de literales.</span><span class="sxs-lookup"><span data-stu-id="89fed-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="89fed-129">Por ejemplo, "A" es un literal del tipo `char` y 2001 es un literal del tipo `int`.</span><span class="sxs-lookup"><span data-stu-id="89fed-129">For example, 'A' is a literal of the type `char` and 2001 is a literal of the type `int`.</span></span>  
  
## <a name="initializing-value-types"></a><span data-ttu-id="89fed-130">Inicializar tipos de valor</span><span class="sxs-lookup"><span data-stu-id="89fed-130">Initializing Value Types</span></span>  
 <span data-ttu-id="89fed-131">Las variables locales en C# deben inicializarse antes de usarse.</span><span class="sxs-lookup"><span data-stu-id="89fed-131">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="89fed-132">Por ejemplo, puede declarar una variable local sin inicialización como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="89fed-132">For example, you might declare a local variable without initialization as in the following example:</span></span>  
  
```csharp  
int myInt;  
```  
  
 <span data-ttu-id="89fed-133">No puede usarla antes de inicializarla.</span><span class="sxs-lookup"><span data-stu-id="89fed-133">You cannot use it before you initialize it.</span></span> <span data-ttu-id="89fed-134">Puede inicializarla con la siguiente instrucción:</span><span class="sxs-lookup"><span data-stu-id="89fed-134">You can initialize it using the following statement:</span></span>  
  
```csharp  
myInt = new int();  // Invoke default constructor for int type.  
```  
  
 <span data-ttu-id="89fed-135">Esta instrucción es equivalente a la instrucción siguiente:</span><span class="sxs-lookup"><span data-stu-id="89fed-135">This statement is equivalent to the following statement:</span></span>  
  
```csharp  
myInt = 0;         // Assign an initial value, 0 in this example.  
```  
  
 <span data-ttu-id="89fed-136">Por supuesto, puede tener la declaración y la inicialización en la misma instrucción como en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="89fed-136">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>  
  
```csharp  
int myInt = new int();  
```  
  
 <span data-ttu-id="89fed-137">-O bien-</span><span class="sxs-lookup"><span data-stu-id="89fed-137">–or–</span></span>  
  
```csharp  
int myInt = 0;  
```  
  
 <span data-ttu-id="89fed-138">Con el operador [new](../../../csharp/language-reference/keywords/new.md) se llama al constructor predeterminado del tipo específico y asigna el valor predeterminado a la variable.</span><span class="sxs-lookup"><span data-stu-id="89fed-138">Using the [new](../../../csharp/language-reference/keywords/new.md) operator calls the default constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="89fed-139">En el ejemplo anterior, el constructor predeterminado ha asignado el valor `0` a `myInt`.</span><span class="sxs-lookup"><span data-stu-id="89fed-139">In the preceding example, the default constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="89fed-140">Para obtener más información sobre los valores que se han asignado llamando a los constructores predeterminados, vea [Tabla de valores predeterminados](../../../csharp/language-reference/keywords/default-values-table.md).</span><span class="sxs-lookup"><span data-stu-id="89fed-140">For more information about values assigned by calling default constructors, see [Default Values Table](../../../csharp/language-reference/keywords/default-values-table.md).</span></span>  
  
 <span data-ttu-id="89fed-141">Con los tipos definidos por el usuario, use [new](../../../csharp/language-reference/keywords/new.md) para invocar al constructor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="89fed-141">With user-defined types, use [new](../../../csharp/language-reference/keywords/new.md) to invoke the default constructor.</span></span> <span data-ttu-id="89fed-142">Por ejemplo, la siguiente instrucción invoca al constructor predeterminado del struct `Point`:</span><span class="sxs-lookup"><span data-stu-id="89fed-142">For example, the following statement invokes the default constructor of the `Point` struct:</span></span>  
  
```csharp  
Point p = new Point(); // Invoke default constructor for the struct.  
```  
  
 <span data-ttu-id="89fed-143">Después de esta llamada, el struct se considera asignado definitivamente; es decir, todos sus miembros se inicializan a sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="89fed-143">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>  
  
 <span data-ttu-id="89fed-144">Para obtener más información sobre el operador new, vea [new](../../../csharp/language-reference/keywords/new.md).</span><span class="sxs-lookup"><span data-stu-id="89fed-144">For more information about the new operator, see [new](../../../csharp/language-reference/keywords/new.md).</span></span>  
  
 <span data-ttu-id="89fed-145">Para obtener información sobre cómo aplicar formato al resultado de los tipos numéricos, vea [Tabla de formatos de presentación para valores numéricos](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span><span class="sxs-lookup"><span data-stu-id="89fed-145">For information about formatting the output of numeric types, see [Formatting Numeric Results Table](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89fed-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="89fed-146">See Also</span></span>

- [<span data-ttu-id="89fed-147">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="89fed-147">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="89fed-148">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="89fed-148">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="89fed-149">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="89fed-149">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="89fed-150">Tipos</span><span class="sxs-lookup"><span data-stu-id="89fed-150">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="89fed-151">Tablas de referencia para tipos</span><span class="sxs-lookup"><span data-stu-id="89fed-151">Reference Tables for Types</span></span>](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
- [<span data-ttu-id="89fed-152">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="89fed-152">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- <span data-ttu-id="89fed-153">[Nullable types](../../programming-guide/nullable-types/index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="89fed-153">[Nullable types](../../programming-guide/nullable-types/index.md)</span></span>  
