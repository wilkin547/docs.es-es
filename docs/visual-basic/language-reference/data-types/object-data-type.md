---
title: Object Data Type
ms.date: 07/20/2015
f1_keywords:
- vb.Object
- vb.Variant
helpviewer_keywords:
- object variables [Visual Basic], Object type
- data types [Visual Basic], assigning
- Object data type
- Object data type [Visual Basic], reference
ms.assetid: 61ea4a7c-3b3d-48d4-adc4-eacfa91779b2
ms.openlocfilehash: 2ccb9b69b865c259d078ed9642d63c7f83514756
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343963"
---
# <a name="object-data-type"></a><span data-ttu-id="8dde4-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="8dde4-102">Object Data Type</span></span>

<span data-ttu-id="8dde4-103">Holds addresses that refer to objects.</span><span class="sxs-lookup"><span data-stu-id="8dde4-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="8dde4-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="8dde4-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="8dde4-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span><span class="sxs-lookup"><span data-stu-id="8dde4-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="8dde4-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8dde4-106">Remarks</span></span>

<span data-ttu-id="8dde4-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span><span class="sxs-lookup"><span data-stu-id="8dde4-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="8dde4-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span><span class="sxs-lookup"><span data-stu-id="8dde4-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="8dde4-109">The default value of `Object` is `Nothing` (a null reference).</span><span class="sxs-lookup"><span data-stu-id="8dde4-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="8dde4-110">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8dde4-110">Data Types</span></span>

<span data-ttu-id="8dde4-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span><span class="sxs-lookup"><span data-stu-id="8dde4-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="8dde4-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span><span class="sxs-lookup"><span data-stu-id="8dde4-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="8dde4-113">Esto se ilustra en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8dde4-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="8dde4-114">The `Object` data type is a reference type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="8dde4-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="8dde4-116">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="8dde4-116">Storage</span></span>

<span data-ttu-id="8dde4-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span><span class="sxs-lookup"><span data-stu-id="8dde4-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="8dde4-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span><span class="sxs-lookup"><span data-stu-id="8dde4-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="8dde4-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span><span class="sxs-lookup"><span data-stu-id="8dde4-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="8dde4-120">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="8dde4-120">Programming Tips</span></span>

- <span data-ttu-id="8dde4-121">**Interop Considerations.**</span><span class="sxs-lookup"><span data-stu-id="8dde4-121">**Interop Considerations.**</span></span> <span data-ttu-id="8dde4-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="8dde4-123">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="8dde4-123">**Performance.**</span></span> <span data-ttu-id="8dde4-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span><span class="sxs-lookup"><span data-stu-id="8dde4-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="8dde4-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span><span class="sxs-lookup"><span data-stu-id="8dde4-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="8dde4-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="8dde4-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="8dde4-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span><span class="sxs-lookup"><span data-stu-id="8dde4-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="8dde4-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span><span class="sxs-lookup"><span data-stu-id="8dde4-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="8dde4-130">**Widening.**</span><span class="sxs-lookup"><span data-stu-id="8dde4-130">**Widening.**</span></span> <span data-ttu-id="8dde4-131">All data types and all reference types widen to the `Object` data type.</span><span class="sxs-lookup"><span data-stu-id="8dde4-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="8dde4-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span><span class="sxs-lookup"><span data-stu-id="8dde4-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="8dde4-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span><span class="sxs-lookup"><span data-stu-id="8dde4-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="8dde4-134">**Type Characters.**</span><span class="sxs-lookup"><span data-stu-id="8dde4-134">**Type Characters.**</span></span> <span data-ttu-id="8dde4-135">`Object` has no literal type character or identifier type character.</span><span class="sxs-lookup"><span data-stu-id="8dde4-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="8dde4-136">**Framework Type.**</span><span class="sxs-lookup"><span data-stu-id="8dde4-136">**Framework Type.**</span></span> <span data-ttu-id="8dde4-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span><span class="sxs-lookup"><span data-stu-id="8dde4-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="8dde4-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8dde4-138">Example</span></span>

<span data-ttu-id="8dde4-139">The following example illustrates an `Object` variable pointing to an object instance.</span><span class="sxs-lookup"><span data-stu-id="8dde4-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="8dde4-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="8dde4-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="8dde4-141">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8dde4-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8dde4-142">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="8dde4-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8dde4-143">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="8dde4-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8dde4-144">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="8dde4-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="8dde4-145">Determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="8dde4-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="8dde4-146">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="8dde4-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
