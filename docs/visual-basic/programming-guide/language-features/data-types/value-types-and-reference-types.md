---
title: Tipos de valor y tipos de referencia
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- reference data types [Visual Basic]
- reference types [Visual Basic]
- value types [Visual Basic]
- value data types [Visual Basic]
- types [Visual Basic]
- data types [Visual Basic], value types
- data types [Visual Basic], reference types
ms.assetid: fc82ce15-5a40-4c5c-a1e1-a556830e7391
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2b54945d27d186771e8b5353e753afd74c56d71b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="value-types-and-reference-types"></a><span data-ttu-id="53471-102">Tipos de valor y tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="53471-102">Value Types and Reference Types</span></span>
<span data-ttu-id="53471-103">En Visual Basic, tipos de datos se implementan según su clasificación.</span><span class="sxs-lookup"><span data-stu-id="53471-103">In Visual Basic, data types are implemented based on their classification.</span></span> <span data-ttu-id="53471-104">El [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] tipos de datos se pueden clasificar según si una variable de un tipo determinado almacena sus propios datos o un puntero a los datos.</span><span class="sxs-lookup"><span data-stu-id="53471-104">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] data types can be classified according to whether a variable of a particular type stores its own data or a pointer to the data.</span></span> <span data-ttu-id="53471-105">Si almacena sus propios datos es un *tipo de valor*; si mantiene un puntero a los datos en otra ubicación en la memoria es un *tipo de referencia*.</span><span class="sxs-lookup"><span data-stu-id="53471-105">If it stores its own data it is a *value type*; if it holds a pointer to data elsewhere in memory it is a *reference type*.</span></span>  
  
## <a name="value-types"></a><span data-ttu-id="53471-106">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="53471-106">Value Types</span></span>  
 <span data-ttu-id="53471-107">Un tipo de datos es un *tipo de valor* si almacena los datos en su propia asignación de memoria.</span><span class="sxs-lookup"><span data-stu-id="53471-107">A data type is a *value type* if it holds the data within its own memory allocation.</span></span> <span data-ttu-id="53471-108">Tipos de valor son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="53471-108">Value types include the following:</span></span>  
  
-   <span data-ttu-id="53471-109">Todos los tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="53471-109">All numeric data types</span></span>  
  
-   <span data-ttu-id="53471-110">`Boolean`, `Char` y `Date`</span><span class="sxs-lookup"><span data-stu-id="53471-110">`Boolean`, `Char`, and `Date`</span></span>  
  
-   <span data-ttu-id="53471-111">Todas las estructuras, incluso si sus miembros son tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="53471-111">All structures, even if their members are reference types</span></span>  
  
-   <span data-ttu-id="53471-112">Las enumeraciones, ya que su tipo subyacente es siempre `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, o`ULong`</span><span class="sxs-lookup"><span data-stu-id="53471-112">Enumerations, since their underlying type is always `SByte`, `Short`, `Integer`, `Long`, `Byte`, `UShort`, `UInteger`, or `ULong`</span></span>  
  
 <span data-ttu-id="53471-113">Cada estructura es un tipo de valor, aunque contenga a los miembros de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="53471-113">Every structure is a value type, even if it contains reference type members.</span></span> <span data-ttu-id="53471-114">Por esta razón, tipos de valor como `Char` y `Integer` se implementan las estructuras de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="53471-114">For this reason, value types such as `Char` and `Integer` are implemented by .NET Framework structures.</span></span>  
  
 <span data-ttu-id="53471-115">Puede declarar un tipo de valor mediante el uso de una palabra clave reservada, por ejemplo, `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="53471-115">You can declare a value type by using the reserved keyword, for example, `Decimal`.</span></span> <span data-ttu-id="53471-116">También puede usar el `New` palabra clave que se va a inicializar un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="53471-116">You can also use the `New` keyword to initialize a value type.</span></span> <span data-ttu-id="53471-117">Esto es especialmente útil si el tipo tiene un constructor que toma parámetros.</span><span class="sxs-lookup"><span data-stu-id="53471-117">This is especially useful if the type has a constructor that takes parameters.</span></span> <span data-ttu-id="53471-118">Un ejemplo de esto es el <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, que compila un nuevo `Decimal` valor de las partes proporcionadas.</span><span class="sxs-lookup"><span data-stu-id="53471-118">An example of this is the <xref:System.Decimal.%23ctor%28System.Int32%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Byte%29> constructor, which builds a new `Decimal` value from the supplied parts.</span></span>  
  
## <a name="reference-types"></a><span data-ttu-id="53471-119">Tipos de referencia</span><span class="sxs-lookup"><span data-stu-id="53471-119">Reference Types</span></span>  
 <span data-ttu-id="53471-120">A *tipo de referencia* contiene un puntero a otra ubicación de memoria que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="53471-120">A *reference type* contains a pointer to another memory location that holds the data.</span></span> <span data-ttu-id="53471-121">Tipos de referencia son los siguientes:</span><span class="sxs-lookup"><span data-stu-id="53471-121">Reference types include the following:</span></span>  
  
-   `String`  
  
-   <span data-ttu-id="53471-122">Todas las matrices, incluso si sus elementos son tipos de valor</span><span class="sxs-lookup"><span data-stu-id="53471-122">All arrays, even if their elements are value types</span></span>  
  
-   <span data-ttu-id="53471-123">Tipos de clase, como<xref:System.Windows.Forms.Form></span><span class="sxs-lookup"><span data-stu-id="53471-123">Class types, such as <xref:System.Windows.Forms.Form></span></span>  
  
-   <span data-ttu-id="53471-124">Delegados</span><span class="sxs-lookup"><span data-stu-id="53471-124">Delegates</span></span>  
  
 <span data-ttu-id="53471-125">Una clase es un *tipo de referencia*.</span><span class="sxs-lookup"><span data-stu-id="53471-125">A class is a *reference type*.</span></span> <span data-ttu-id="53471-126">Por esta razón, tipos de referencia como `Object` y `String` son compatibles con [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] clases.</span><span class="sxs-lookup"><span data-stu-id="53471-126">For this reason, reference types such as `Object` and `String` are supported by [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes.</span></span> <span data-ttu-id="53471-127">Tenga en cuenta que cada matriz es un tipo de referencia, incluso si sus miembros son tipos de valor.</span><span class="sxs-lookup"><span data-stu-id="53471-127">Note that every array is a reference type, even if its members are value types.</span></span>  
  
 <span data-ttu-id="53471-128">Puesto que cada tipo de referencia representa una clase subyacente de .NET Framework, debe utilizar el [New (operador)](../../../../visual-basic/language-reference/operators/new-operator.md) palabra clave al inicializarlo.</span><span class="sxs-lookup"><span data-stu-id="53471-128">Since every reference type represents an underlying .NET Framework class, you must use the [New Operator](../../../../visual-basic/language-reference/operators/new-operator.md) keyword when you initialize it.</span></span> <span data-ttu-id="53471-129">La instrucción siguiente inicializa una matriz.</span><span class="sxs-lookup"><span data-stu-id="53471-129">The following statement initializes an array.</span></span>  
  
```  
Dim totals() As Single = New Single(8) {}  
```  
  
## <a name="elements-that-are-not-types"></a><span data-ttu-id="53471-130">Elementos que no son tipos</span><span class="sxs-lookup"><span data-stu-id="53471-130">Elements That Are Not Types</span></span>  
 <span data-ttu-id="53471-131">Los siguientes elementos de programación no se consideran como tipos, ya que no puede especificar cualquiera de ellos como un tipo de datos para un elemento declarado:</span><span class="sxs-lookup"><span data-stu-id="53471-131">The following programming elements do not qualify as types, because you cannot specify any of them as a data type for a declared element:</span></span>  
  
-   <span data-ttu-id="53471-132">Espacios de nombres</span><span class="sxs-lookup"><span data-stu-id="53471-132">Namespaces</span></span>  
  
-   <span data-ttu-id="53471-133">Módulos</span><span class="sxs-lookup"><span data-stu-id="53471-133">Modules</span></span>  
  
-   <span data-ttu-id="53471-134">Eventos</span><span class="sxs-lookup"><span data-stu-id="53471-134">Events</span></span>  
  
-   <span data-ttu-id="53471-135">Propiedades y procedimientos</span><span class="sxs-lookup"><span data-stu-id="53471-135">Properties and procedures</span></span>  
  
-   <span data-ttu-id="53471-136">Las variables, constantes y campos</span><span class="sxs-lookup"><span data-stu-id="53471-136">Variables, constants, and fields</span></span>  
  
## <a name="working-with-the-object-data-type"></a><span data-ttu-id="53471-137">Trabajar con el tipo de datos de objeto</span><span class="sxs-lookup"><span data-stu-id="53471-137">Working with the Object Data Type</span></span>  
 <span data-ttu-id="53471-138">Puede asignar un tipo de referencia o un tipo de valor a una variable de la `Object` tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="53471-138">You can assign either a reference type or a value type to a variable of the `Object` data type.</span></span> <span data-ttu-id="53471-139">Un `Object` variable siempre contiene un puntero a los datos, nunca los propios datos.</span><span class="sxs-lookup"><span data-stu-id="53471-139">An `Object` variable always holds a pointer to the data, never the data itself.</span></span> <span data-ttu-id="53471-140">Sin embargo, si asigna un tipo de valor a un `Object` variable, se comporta como si contuviera sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="53471-140">However, if you assign a value type to an `Object` variable, it behaves as if it holds its own data.</span></span> <span data-ttu-id="53471-141">Para obtener más información, consulte [tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="53471-141">For more information, see [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md).</span></span>  
  
 <span data-ttu-id="53471-142">Puede averiguar si un `Object` variable está actuando como un tipo de referencia o un tipo de valor y la transfiere a la <xref:Microsoft.VisualBasic.Information.IsReference%2A> método en el <xref:Microsoft.VisualBasic.Information> clase de la <xref:Microsoft.VisualBasic?displayProperty=nameWithType> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="53471-142">You can find out whether an `Object` variable is acting as a reference type or a value type by passing it to the <xref:Microsoft.VisualBasic.Information.IsReference%2A> method in the <xref:Microsoft.VisualBasic.Information> class of the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="53471-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType>Devuelve `True` si el contenido de la `Object` variable representa un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="53471-143"><xref:Microsoft.VisualBasic.Information.IsReference%2A?displayProperty=nameWithType> returns `True` if the content of the `Object` variable represents a reference type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53471-144">Vea también</span><span class="sxs-lookup"><span data-stu-id="53471-144">See Also</span></span>  
 [<span data-ttu-id="53471-145">Tipos de valor que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="53471-145">Nullable Value Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [<span data-ttu-id="53471-146">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="53471-146">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="53471-147">Structure (instrucción)</span><span class="sxs-lookup"><span data-stu-id="53471-147">Structure Statement</span></span>](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [<span data-ttu-id="53471-148">Uso eficiente de tipos de datos</span><span class="sxs-lookup"><span data-stu-id="53471-148">Efficient Use of Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [<span data-ttu-id="53471-149">Tipo de objeto de datos</span><span class="sxs-lookup"><span data-stu-id="53471-149">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [<span data-ttu-id="53471-150">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="53471-150">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
