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
# <a name="object-data-type"></a><span data-ttu-id="57260-102">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="57260-102">Object Data Type</span></span>

<span data-ttu-id="57260-103">Contiene direcciones que hacen referencia a objetos.</span><span class="sxs-lookup"><span data-stu-id="57260-103">Holds addresses that refer to objects.</span></span> <span data-ttu-id="57260-104">Puede asignar cualquier tipo de referencia (cadena, matriz, clase o interfaz) a una variable de `Object`.</span><span class="sxs-lookup"><span data-stu-id="57260-104">You can assign any reference type (string, array, class, or interface) to an `Object` variable.</span></span> <span data-ttu-id="57260-105">Una variable `Object` también puede hacer referencia a datos de cualquier tipo de valor (Numeric, `Boolean`, `Char`, `Date`, Structure o Enumeration).</span><span class="sxs-lookup"><span data-stu-id="57260-105">An `Object` variable can also refer to data of any value type (numeric, `Boolean`, `Char`, `Date`, structure, or enumeration).</span></span>

## <a name="remarks"></a><span data-ttu-id="57260-106">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57260-106">Remarks</span></span>

<span data-ttu-id="57260-107">El tipo de datos `Object` puede apuntar a datos de cualquier tipo de datos, incluida cualquier instancia de objeto que la aplicación reconozca.</span><span class="sxs-lookup"><span data-stu-id="57260-107">The `Object` data type can point to data of any data type, including any object instance your application recognizes.</span></span> <span data-ttu-id="57260-108">Use `Object` cuando no conozca en tiempo de compilación a qué tipo de datos puede apuntar la variable.</span><span class="sxs-lookup"><span data-stu-id="57260-108">Use `Object` when you do not know at compile time what data type the variable might point to.</span></span>

<span data-ttu-id="57260-109">El valor predeterminado de `Object` es `Nothing` (una referencia nula).</span><span class="sxs-lookup"><span data-stu-id="57260-109">The default value of `Object` is `Nothing` (a null reference).</span></span>

## <a name="data-types"></a><span data-ttu-id="57260-110">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="57260-110">Data Types</span></span>

<span data-ttu-id="57260-111">Puede asignar una variable, una constante o una expresión de cualquier tipo de datos a una variable de `Object`.</span><span class="sxs-lookup"><span data-stu-id="57260-111">You can assign a variable, constant, or expression of any data type to an `Object` variable.</span></span> <span data-ttu-id="57260-112">Para determinar el tipo de datos al que hace referencia una variable `Object` actualmente, puede usar el método <xref:System.Type.GetTypeCode%2A> de la clase <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57260-112">To determine the data type an `Object` variable currently refers to, you can use the <xref:System.Type.GetTypeCode%2A> method of the <xref:System.Type?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="57260-113">En el ejemplo siguiente se ilustra esto.</span><span class="sxs-lookup"><span data-stu-id="57260-113">The following example illustrates this.</span></span>

```vb
Dim myObject As Object
' Suppose myObject has now had something assigned to it.
Dim datTyp As Integer
datTyp = Type.GetTypeCode(myObject.GetType())
```

<span data-ttu-id="57260-114">El tipo de datos `Object` es un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="57260-114">The `Object` data type is a reference type.</span></span> <span data-ttu-id="57260-115">Sin embargo, Visual Basic trata una variable `Object` como un tipo de valor cuando hace referencia a los datos de un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="57260-115">However, Visual Basic treats an `Object` variable as a value type when it refers to data of a value type.</span></span>

## <a name="storage"></a><span data-ttu-id="57260-116">Almacenamiento</span><span class="sxs-lookup"><span data-stu-id="57260-116">Storage</span></span>

<span data-ttu-id="57260-117">Sea cual sea el tipo de datos al que haga referencia, una variable `Object` no contenga el propio valor de datos, sino un puntero al valor.</span><span class="sxs-lookup"><span data-stu-id="57260-117">Whatever data type it refers to, an `Object` variable does not contain the data value itself, but rather a pointer to the value.</span></span> <span data-ttu-id="57260-118">Siempre usa cuatro bytes en la memoria del equipo, pero no incluye el almacenamiento de los datos que representan el valor de la variable.</span><span class="sxs-lookup"><span data-stu-id="57260-118">It always uses four bytes in computer memory, but this does not include the storage for the data representing the value of the variable.</span></span> <span data-ttu-id="57260-119">Debido al código que usa el puntero para ubicar los datos, `Object` variables que contienen tipos de valor son ligeramente más lentas de tener acceso que las variables de tipo explícito.</span><span class="sxs-lookup"><span data-stu-id="57260-119">Because of the code that uses the pointer to locate the data, `Object` variables holding value types are slightly slower to access than explicitly typed variables.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="57260-120">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="57260-120">Programming Tips</span></span>

- <span data-ttu-id="57260-121">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="57260-121">**Interop Considerations.**</span></span> <span data-ttu-id="57260-122">Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos de puntero en otros entornos no son compatibles con el tipo de `Object` Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="57260-122">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that pointer types in other environments are not compatible with the Visual Basic `Object` type.</span></span>

- <span data-ttu-id="57260-123">**Rendimiento.**</span><span class="sxs-lookup"><span data-stu-id="57260-123">**Performance.**</span></span> <span data-ttu-id="57260-124">Una variable que se declara con el tipo `Object` es lo suficientemente flexible como para contener una referencia a cualquier objeto.</span><span class="sxs-lookup"><span data-stu-id="57260-124">A variable you declare with the `Object` type is flexible enough to contain a reference to any object.</span></span> <span data-ttu-id="57260-125">Sin embargo, cuando se invoca un método o una propiedad en este tipo de variable, siempre se incurre en el *enlace* en tiempo de ejecución (en tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="57260-125">However, when you invoke a method or property on such a variable, you always incur *late binding* (at run time).</span></span> <span data-ttu-id="57260-126">Para forzar el *enlace anticipado* (en tiempo de compilación) y un mejor rendimiento, declare la variable con un nombre de clase específico o conviértala en el tipo de datos específico.</span><span class="sxs-lookup"><span data-stu-id="57260-126">To force *early binding* (at compile time) and better performance, declare the variable with a specific class name, or cast it to the specific data type.</span></span>

  <span data-ttu-id="57260-127">Al declarar una variable de objeto, intente usar un tipo de clase concreto, por ejemplo <xref:System.OperatingSystem>, en lugar del tipo de `Object` generalizado.</span><span class="sxs-lookup"><span data-stu-id="57260-127">When you declare an object variable, try to use a specific class type, for example <xref:System.OperatingSystem>, instead of the generalized `Object` type.</span></span> <span data-ttu-id="57260-128">También debe utilizar la clase más específica disponible, como <xref:System.Windows.Forms.TextBox> en lugar de <xref:System.Windows.Forms.Control>, de modo que pueda tener acceso a sus propiedades y métodos.</span><span class="sxs-lookup"><span data-stu-id="57260-128">You should also use the most specific class available, such as <xref:System.Windows.Forms.TextBox> instead of <xref:System.Windows.Forms.Control>, so that you can access its properties and methods.</span></span> <span data-ttu-id="57260-129">Normalmente, puede usar la lista **clases** de la **Examinador de objetos** para buscar los nombres de clase disponibles.</span><span class="sxs-lookup"><span data-stu-id="57260-129">You can usually use the **Classes** list in the **Object Browser** to find available class names.</span></span>

- <span data-ttu-id="57260-130">**Ampliación.**</span><span class="sxs-lookup"><span data-stu-id="57260-130">**Widening.**</span></span> <span data-ttu-id="57260-131">Todos los tipos de datos y todos los tipos de referencia se amplían al tipo de datos `Object`.</span><span class="sxs-lookup"><span data-stu-id="57260-131">All data types and all reference types widen to the `Object` data type.</span></span> <span data-ttu-id="57260-132">Esto significa que puede convertir cualquier tipo en `Object` sin encontrar un error de <xref:System.OverflowException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57260-132">This means you can convert any type to `Object` without encountering a <xref:System.OverflowException?displayProperty=nameWithType> error.</span></span>

  <span data-ttu-id="57260-133">Sin embargo, si se convierte entre tipos de valor y `Object`, Visual Basic realiza operaciones denominadas *conversión boxing y conversión* *unboxing*, lo que ralentiza la ejecución.</span><span class="sxs-lookup"><span data-stu-id="57260-133">However, if you convert between value types and `Object`, Visual Basic performs operations called *boxing* and *unboxing*, which make execution slower.</span></span>

- <span data-ttu-id="57260-134">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="57260-134">**Type Characters.**</span></span> <span data-ttu-id="57260-135">`Object` no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="57260-135">`Object` has no literal type character or identifier type character.</span></span>

- <span data-ttu-id="57260-136">**Tipo de marco.**</span><span class="sxs-lookup"><span data-stu-id="57260-136">**Framework Type.**</span></span> <span data-ttu-id="57260-137">El tipo correspondiente en el .NET Framework es la clase <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="57260-137">The corresponding type in the .NET Framework is the <xref:System.Object?displayProperty=nameWithType> class.</span></span>

## <a name="example"></a><span data-ttu-id="57260-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="57260-138">Example</span></span>

<span data-ttu-id="57260-139">En el ejemplo siguiente se muestra una variable de `Object` que apunta a una instancia de objeto.</span><span class="sxs-lookup"><span data-stu-id="57260-139">The following example illustrates an `Object` variable pointing to an object instance.</span></span>

```vb
Dim objDb As Object
Dim myCollection As New Collection()
' Suppose myCollection has now been populated.
objDb = myCollection.Item(1)
```

## <a name="see-also"></a><span data-ttu-id="57260-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="57260-140">See also</span></span>

- <xref:System.Object>
- [<span data-ttu-id="57260-141">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="57260-141">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="57260-142">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="57260-142">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="57260-143">Resumen de conversión</span><span class="sxs-lookup"><span data-stu-id="57260-143">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="57260-144">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="57260-144">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="57260-145">Determinar si dos objetos están relacionados</span><span class="sxs-lookup"><span data-stu-id="57260-145">How to: Determine Whether Two Objects Are Related</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)
- [<span data-ttu-id="57260-146">Determinar si dos objetos son idénticos</span><span class="sxs-lookup"><span data-stu-id="57260-146">How to: Determine Whether Two Objects Are Identical</span></span>](../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)
