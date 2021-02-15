---
description: 'Más información sobre: tipos de valor y tipos de referencia'
title: Tipos de valor y tipos de referencia
ms.date: 07/20/2015
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
ms.openlocfilehash: 22cce68260955545e810f6fefe645b5ad6a37ca5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100462144"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="11d64-103">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="11d64-103">Value Types and Reference Types</span></span>

<span data-ttu-id="11d64-104">Hay dos tipos de tipos en Visual Basic: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="11d64-104">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="11d64-105">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="11d64-105">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="11d64-106">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="11d64-106">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="11d64-107">Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso del [modificador ByRef en parámetros](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="11d64-107">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="11d64-108">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="11d64-108">Value Types</span></span>  

 <span data-ttu-id="11d64-109">Un tipo de datos es un *tipo de valor* si contiene los datos dentro de su propia asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="11d64-109">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="11d64-110">Entre los tipos de valor se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="11d64-110">Value types include the following:</span></span>  
  
- <span data-ttu-id="11d64-111">Todos los tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="11d64-111">All numeric data types</span></span>  
  
- <span data-ttu-id="11d64-112">`Boolean`, `Char` y `Date`</span><span class="sxs-lookup"><span data-stu-id="11d64-112">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="11d64-113">Todas las estructuras, incluso si sus miembros son tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="11d64-113">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="11d64-114">Enumeraciones, ya que su tipo subyacente siempre es `SByte` , `Short` , `Integer` , `Long` , `Byte` , `UShort` , `UInteger` o. `ULong`</span><span class="sxs-lookup"><span data-stu-id="11d64-114">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="11d64-115">Cada estructura es un tipo de valor, incluso si contiene miembros de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="11d64-115">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="11d64-116">Por esta razón, los tipos de valor como `Char` y `Integer` se implementan mediante .NET Framework estructuras.</span><span class="sxs-lookup"><span data-stu-id="11d64-116">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="11d64-117">Puede declarar un tipo de valor mediante la palabra clave Reserved, por ejemplo, `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="11d64-117">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="11d64-118">También puede usar la `New` palabra clave para inicializar un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="11d64-118">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="11d64-119">Esto es especialmente útil si el tipo tiene un constructor que toma parámetros.</span><span class="sxs-lookup"><span data-stu-id="11d64-119">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="11d64-120">Un ejemplo de esto es el <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, que genera un nuevo `Decimal` valor a partir de los elementos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="11d64-120">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="11d64-121">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="11d64-121">Reference Types</span></span>  

 <span data-ttu-id="11d64-122">Un *tipo de referencia* almacena una referencia a sus datos.</span><span class="sxs-lookup"><span data-stu-id="11d64-122">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="11d64-123">Entre los tipos de referencia se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="11d64-123">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="11d64-124">Todas las matrices, incluso si sus elementos son tipos de valor</span><span class="sxs-lookup"><span data-stu-id="11d64-124">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="11d64-125">Tipos de clase, como <xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="11d64-125">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="11d64-126">Delegados</span><span class="sxs-lookup"><span data-stu-id="11d64-126">Delegates</span></span>  
  
 <span data-ttu-id="11d64-127">Una clase es un *tipo de referencia*.</span><span class="sxs-lookup"><span data-stu-id="11d64-127">A class is a *reference type*.</span></span> <span data-ttu-id="11d64-128">Tenga en cuenta que cada matriz es un tipo de referencia, incluso si sus miembros son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="11d64-128">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="11d64-129">Puesto que cada tipo de referencia representa una clase de .NET Framework subyacente, debe usar la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) al inicializarla.</span><span class="sxs-lookup"><span data-stu-id="11d64-129">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="11d64-130">La siguiente instrucción Inicializa una matriz.</span><span class="sxs-lookup"><span data-stu-id="11d64-130">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="11d64-131">Elementos que no son tipos</span><span class="sxs-lookup"><span data-stu-id="11d64-131">Elements That Are Not Types</span></span>  

 <span data-ttu-id="11d64-132">Los elementos de programación siguientes no se califican como tipos, ya que no se puede especificar ninguno de ellos como un tipo de datos para un elemento declarado:</span><span class="sxs-lookup"><span data-stu-id="11d64-132">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="11d64-133">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="11d64-133">Namespaces</span></span>  
  
- <span data-ttu-id="11d64-134">Módulos</span><span class="sxs-lookup"><span data-stu-id="11d64-134">Modules</span></span>  
  
- <span data-ttu-id="11d64-135">Eventos</span><span class="sxs-lookup"><span data-stu-id="11d64-135">Events</span></span>  
  
- <span data-ttu-id="11d64-136">Propiedades y procedimientos</span><span class="sxs-lookup"><span data-stu-id="11d64-136">Properties and procedures</span></span>  
  
- <span data-ttu-id="11d64-137">Variables, constantes y campos</span><span class="sxs-lookup"><span data-stu-id="11d64-137">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="11d64-138">Trabajar con el tipo de datos Object</span><span class="sxs-lookup"><span data-stu-id="11d64-138">Working with the Object Data Type</span></span>  

 <span data-ttu-id="11d64-139">Puede asignar un tipo de referencia o un tipo de valor a una variable del `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="11d64-139">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="11d64-140">Una `Object` variable siempre contiene una referencia a los datos, nunca los propios datos.</span><span class="sxs-lookup"><span data-stu-id="11d64-140">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="11d64-141">Sin embargo, si asigna un tipo de valor a una `Object` variable, se comporta como si tuviera sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="11d64-141">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="11d64-142">Para obtener más información, vea [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="11d64-142">For more information, see [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="11d64-143">Puede averiguar si una `Object` variable actúa como un tipo de referencia o un tipo de valor pasándola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> método en la <xref:Microsoft.VisualBasic.Information> clase del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="11d64-143">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="11d64-144"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> Devuelve `True` si el contenido de la `Object` variable representa un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="11d64-144"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d64-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="11d64-145">See also</span></span>

- [<span data-ttu-id="11d64-146">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="11d64-146">Nullable Value Types</span></span>](nullable-value-types.md)
- [<span data-ttu-id="11d64-147">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="11d64-147">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="11d64-148">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="11d64-148">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="11d64-149">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="11d64-149">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
- [<span data-ttu-id="11d64-150">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="11d64-150">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="11d64-151">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="11d64-151">Data Types</span></span>](index.md)
