---
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
ms.openlocfilehash: 3a1de120f5f97ba93939f332f121d70cd3091216
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392979"
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="d1c36-102">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="d1c36-102">Value Types and Reference Types</span></span>
<span data-ttu-id="d1c36-103">Hay dos tipos de tipos en Visual Basic: tipos de referencia y tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="d1c36-103">There are two kinds of types in Visual Basic: reference types and value types.</span></span> <span data-ttu-id="d1c36-104">Las variables de tipos de referencia almacenan referencias en sus datos (objetos), mientras que las variables de tipos de valor contienen directamente los datos.</span><span class="sxs-lookup"><span data-stu-id="d1c36-104">Variables of reference types store references to their data (objects), while variables of value types directly contain their data.</span></span> <span data-ttu-id="d1c36-105">Con los tipos de referencia, dos variables pueden hacer referencia al mismo objeto y, por lo tanto, las operaciones en una variable pueden afectar al objeto al que hace referencia la otra variable.</span><span class="sxs-lookup"><span data-stu-id="d1c36-105">With reference types, two variables can reference the same object; therefore, operations on one variable can affect the object referenced by the other variable.</span></span> <span data-ttu-id="d1c36-106">Con los tipos de valor, cada variable tiene su propia copia de los datos y no es posible que las operaciones en una variable afecten a la otra (excepto en el caso del [modificador ByRef en parámetros](../../../language-reference/modifiers/byref.md)).</span><span class="sxs-lookup"><span data-stu-id="d1c36-106">With value types, each variable has its own copy of the data, and it is not possible for operations on one variable to affect the other (except in the case of the [ByRef modifier on parameters](../../../language-reference/modifiers/byref.md)).</span></span>
  
## <a name="value-types"></a><span data-ttu-id="d1c36-107">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="d1c36-107">Value Types</span></span>  
 <span data-ttu-id="d1c36-108">Un tipo de datos es un *tipo de valor* si contiene los datos dentro de su propia asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="d1c36-108">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="d1c36-109">Entre los tipos de valor se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1c36-109">Value types include the following:</span></span>  
  
- <span data-ttu-id="d1c36-110">Todos los tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="d1c36-110">All numeric data types</span></span>  
  
- <span data-ttu-id="d1c36-111">`Boolean`, `Char` y `Date`</span><span class="sxs-lookup"><span data-stu-id="d1c36-111">`Boolean`, `Char`, and `Date`</span></span>  
  
- <span data-ttu-id="d1c36-112">Todas las estructuras, incluso si sus miembros son tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="d1c36-112">All structures, even if their members are reference types</span></span>  
  
- <span data-ttu-id="d1c36-113">Enumeraciones, ya que su tipo subyacente siempre es `SByte` , `Short` , `Integer` , `Long` , `Byte` , `UShort` , `UInteger` o.`ULong`</span><span class="sxs-lookup"><span data-stu-id="d1c36-113">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="d1c36-114">Cada estructura es un tipo de valor, incluso si contiene miembros de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="d1c36-114">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="d1c36-115">Por esta razón, los tipos de valor como `Char` y `Integer` se implementan mediante .NET Framework estructuras.</span><span class="sxs-lookup"><span data-stu-id="d1c36-115">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="d1c36-116">Puede declarar un tipo de valor mediante la palabra clave Reserved, por ejemplo, `Decimal` .</span><span class="sxs-lookup"><span data-stu-id="d1c36-116">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="d1c36-117">También puede usar la `New` palabra clave para inicializar un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="d1c36-117">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="d1c36-118">Esto es especialmente útil si el tipo tiene un constructor que toma parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1c36-118">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="d1c36-119">Un ejemplo de esto es el <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, que genera un nuevo `Decimal` valor a partir de los elementos proporcionados.</span><span class="sxs-lookup"><span data-stu-id="d1c36-119">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="d1c36-120">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="d1c36-120">Reference Types</span></span>  
 <span data-ttu-id="d1c36-121">Un *tipo de referencia* almacena una referencia a sus datos.</span><span class="sxs-lookup"><span data-stu-id="d1c36-121">A *reference type* stores a reference to its data.</span></span> <span data-ttu-id="d1c36-122">Entre los tipos de referencia se incluyen los siguientes:</span><span class="sxs-lookup"><span data-stu-id="d1c36-122">Reference types include the following:</span></span>  
  
- `String`  
  
- <span data-ttu-id="d1c36-123">Todas las matrices, incluso si sus elementos son tipos de valor</span><span class="sxs-lookup"><span data-stu-id="d1c36-123">All arrays, even if their elements are value types</span></span>  
  
- <span data-ttu-id="d1c36-124">Tipos de clase, como<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="d1c36-124">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
- <span data-ttu-id="d1c36-125">Delegados</span><span class="sxs-lookup"><span data-stu-id="d1c36-125">Delegates</span></span>  
  
 <span data-ttu-id="d1c36-126">Una clase es un *tipo de referencia*.</span><span class="sxs-lookup"><span data-stu-id="d1c36-126">A class is a *reference type*.</span></span> <span data-ttu-id="d1c36-127">Tenga en cuenta que cada matriz es un tipo de referencia, incluso si sus miembros son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="d1c36-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="d1c36-128">Puesto que cada tipo de referencia representa una clase de .NET Framework subyacente, debe usar la palabra clave [New Operator](../../../language-reference/operators/new-operator.md) al inicializarla.</span><span class="sxs-lookup"><span data-stu-id="d1c36-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="d1c36-129">La siguiente instrucción Inicializa una matriz.</span><span class="sxs-lookup"><span data-stu-id="d1c36-129">The following statement initializes an array.</span></span>  
  
```vb  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="d1c36-130">Elementos que no son tipos</span><span class="sxs-lookup"><span data-stu-id="d1c36-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="d1c36-131">Los elementos de programación siguientes no se califican como tipos, ya que no se puede especificar ninguno de ellos como un tipo de datos para un elemento declarado:</span><span class="sxs-lookup"><span data-stu-id="d1c36-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
- <span data-ttu-id="d1c36-132">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="d1c36-132">Namespaces</span></span>  
  
- <span data-ttu-id="d1c36-133">Módulos</span><span class="sxs-lookup"><span data-stu-id="d1c36-133">Modules</span></span>  
  
- <span data-ttu-id="d1c36-134">Eventos</span><span class="sxs-lookup"><span data-stu-id="d1c36-134">Events</span></span>  
  
- <span data-ttu-id="d1c36-135">Propiedades y procedimientos</span><span class="sxs-lookup"><span data-stu-id="d1c36-135">Properties and procedures</span></span>  
  
- <span data-ttu-id="d1c36-136">Variables, constantes y campos</span><span class="sxs-lookup"><span data-stu-id="d1c36-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="d1c36-137">Trabajar con el tipo de datos Object</span><span class="sxs-lookup"><span data-stu-id="d1c36-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="d1c36-138">Puede asignar un tipo de referencia o un tipo de valor a una variable del `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="d1c36-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="d1c36-139">Una `Object` variable siempre contiene una referencia a los datos, nunca los propios datos.</span><span class="sxs-lookup"><span data-stu-id="d1c36-139">An `Object` variable always holds a reference to the data, never the data itself.</span></span> <span data-ttu-id="d1c36-140">Sin embargo, si asigna un tipo de valor a una `Object` variable, se comporta como si tuviera sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="d1c36-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="d1c36-141">Para obtener más información, vea [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="d1c36-141">For more information, see [Object Data Type](../../../language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="d1c36-142">Puede averiguar si una `Object` variable actúa como un tipo de referencia o un tipo de valor pasándola al <xref:Microsoft.VisualBasic.Information.IsReference%2A> método en la <xref:Microsoft.VisualBasic.Information> clase del <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="d1c36-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="d1c36-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Devuelve `True` si el contenido de la `Object` variable representa un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="d1c36-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1c36-144">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1c36-144">See also</span></span>

- [<span data-ttu-id="d1c36-145">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="d1c36-145">Nullable Value Types</span></span>](nullable-value-types.md)
- [<span data-ttu-id="d1c36-146">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d1c36-146">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="d1c36-147">Structure (Instrucción)</span><span class="sxs-lookup"><span data-stu-id="d1c36-147">Structure Statement</span></span>](../../../language-reference/statements/structure-statement.md)
- [<span data-ttu-id="d1c36-148">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1c36-148">Efficient Use of Data Types</span></span>](efficient-use-of-data-types.md)
- [<span data-ttu-id="d1c36-149">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="d1c36-149">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="d1c36-150">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="d1c36-150">Data Types</span></span>](index.md)
