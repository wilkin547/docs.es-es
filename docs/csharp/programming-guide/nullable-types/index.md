---
title: "Tipos que aceptan valores NULL (Guía de programación de C#)"
ms.date: 2017-05-15
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
caps.latest.revision: 44
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 56e22638457017688ff380f6683b463b47c53a17
ms.contentlocale: es-es
ms.lasthandoff: 09/02/2017

---
# <a name="nullable-types-c-programming-guide"></a><span data-ttu-id="f562d-102">Tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="f562d-102">Nullable Types (C# Programming Guide)</span></span>
<span data-ttu-id="f562d-103">Los tipos que aceptan valores NULL son instancias de la estructura <xref:System.Nullable%601?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f562d-103">Nullable types are instances of the <xref:System.Nullable%601?displayProperty=fullName> struct.</span></span> <span data-ttu-id="f562d-104">Un tipo que acepta valores NULL puede representar el intervalo de valores correcto para su tipo de valor subyacente, además de un valor `null` adicional correcto.</span><span class="sxs-lookup"><span data-stu-id="f562d-104">A nullable type can represent the correct range of values for its underlying value type, plus an additional `null` value.</span></span> <span data-ttu-id="f562d-105">Por ejemplo, a un valor `Nullable<Int32>`, también conocido como "Nullable of Int32", se le puede asignar cualquier valor comprendido entre -2147483648 y 2147483647, o se le puede asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="f562d-105">For example, a `Nullable<Int32>`, pronounced "Nullable of Int32," can be assigned any value from -2147483648 to 2147483647, or it can be assigned the `null` value.</span></span> <span data-ttu-id="f562d-106">A `Nullable<bool>` se le pueden asignar los valores [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) o [null](../../../csharp/language-reference/keywords/null.md).</span><span class="sxs-lookup"><span data-stu-id="f562d-106">A `Nullable<bool>` can be assigned the values [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md), or [null](../../../csharp/language-reference/keywords/null.md).</span></span> <span data-ttu-id="f562d-107">La capacidad de asignar `null` a tipos numéricos y booleanos resulta especialmente útil cuando se trabaja con bases de datos y otros tipos de datos que contienen elementos a los que no se les puede asignar ningún valor.</span><span class="sxs-lookup"><span data-stu-id="f562d-107">The ability to assign `null` to numeric and Boolean types is especially useful when you are dealing with databases and other data types that contain elements that may not be assigned a value.</span></span> <span data-ttu-id="f562d-108">Por ejemplo, un campo booleano en una base de datos puede almacenar los valores `true` o `false`, o puede ser indefinido.</span><span class="sxs-lookup"><span data-stu-id="f562d-108">For example, a Boolean field in a database can store the values `true` or `false`, or it may be undefined.</span></span> 
  
<span data-ttu-id="f562d-109">[!code-cs[tipos que aceptan valores NULL](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f562d-109">[!code-cs[nullable-types](../../../../samples/snippets/csharp/programming-guide/nullable-types/nullable-ex1.cs)]</span></span>  
  
<span data-ttu-id="f562d-110">Para obtener más ejemplos, vea [Utilizar tipos que aceptan valores NULL](../../../csharp/programming-guide/nullable-types/using-nullable-types.md).</span><span class="sxs-lookup"><span data-stu-id="f562d-110">For more examples, see [Using Nullable Types](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)</span></span>  
  
## <a name="nullable-types-overview"></a><span data-ttu-id="f562d-111">Información general sobre tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="f562d-111">Nullable Types Overview</span></span>  
 <span data-ttu-id="f562d-112">Los tipos que aceptan valores NULL tienen la siguientes características:</span><span class="sxs-lookup"><span data-stu-id="f562d-112">Nullable types have the following characteristics:</span></span>  
  
-   <span data-ttu-id="f562d-113">Los tipos que aceptan valores NULL representan variables de tipo de valor a las que se puede asignar el valor `null`.</span><span class="sxs-lookup"><span data-stu-id="f562d-113">Nullable types represent value-type variables that can be assigned the value of `null`.</span></span> <span data-ttu-id="f562d-114">No se puede crear un tipo que acepta valores NULL basado en un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="f562d-114">You cannot create a nullable type based on a reference type.</span></span> <span data-ttu-id="f562d-115">(Los tipos de referencia ya admiten el valor `null`).</span><span class="sxs-lookup"><span data-stu-id="f562d-115">(Reference types already support the `null` value.)</span></span>  
  
-   <span data-ttu-id="f562d-116">La sintaxis `T?` es una abreviatura de <xref:System.Nullable%601>, donde `T` es un tipo de valor.</span><span class="sxs-lookup"><span data-stu-id="f562d-116">The syntax `T?` is shorthand for <xref:System.Nullable%601>, where `T` is a value type.</span></span> <span data-ttu-id="f562d-117">Las dos formas son intercambiables.</span><span class="sxs-lookup"><span data-stu-id="f562d-117">The two forms are interchangeable.</span></span>  
  
-   <span data-ttu-id="f562d-118">Asigne un valor a un tipo que acepta valores NULL tal como lo haría para un tipo de valor normal, por ejemplo `int? x = 10;` o `double? d = 4.108`.</span><span class="sxs-lookup"><span data-stu-id="f562d-118">Assign a value to a nullable type just as you would for an ordinary value type, for example `int? x = 10;` or `double? d = 4.108`.</span></span> <span data-ttu-id="f562d-119">A un tipo que acepta valores NULL también se le puede asignar el valor `null`: `int? x = null.`.</span><span class="sxs-lookup"><span data-stu-id="f562d-119">A nullable type can also be assigned the value `null`: `int? x = null.`</span></span>  
  
-   <span data-ttu-id="f562d-120">Use el método <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> para devolver el valor asignado, o bien el valor predeterminado para el tipo subyacente si el valor es `null`, por ejemplo, `int j = x.GetValueOrDefault();`.</span><span class="sxs-lookup"><span data-stu-id="f562d-120">Use the <xref:System.Nullable%601.GetValueOrDefault%2A?displayProperty=fullName> method to return either the assigned value, or the default value for the underlying type if the value is `null`, for example `int j = x.GetValueOrDefault();`</span></span>  
  
-   <span data-ttu-id="f562d-121">Use las propiedades de solo lectura <xref:System.Nullable%601.HasValue%2A> y <xref:System.Nullable%601.Value%2A> para probar si hay valores NULL y recuperar el valor, como se muestra en el ejemplo siguiente: `if(x.HasValue) j = x.Value;`</span><span class="sxs-lookup"><span data-stu-id="f562d-121">Use the <xref:System.Nullable%601.HasValue%2A> and <xref:System.Nullable%601.Value%2A> read-only properties to test for null and retrieve the value, as shown in the following example: `if(x.HasValue) j = x.Value;`</span></span>  
  
    -   <span data-ttu-id="f562d-122">La propiedad `HasValue` devuelve `true` si la variable contiene un valor, o `false` si es `null`.</span><span class="sxs-lookup"><span data-stu-id="f562d-122">The `HasValue` property returns `true` if the variable contains a value, or `false` if it is `null`.</span></span>  
  
    -   <span data-ttu-id="f562d-123">La propiedad `Value` devuelve un valor si se asigna uno.</span><span class="sxs-lookup"><span data-stu-id="f562d-123">The `Value` property returns a value if one is assigned.</span></span> <span data-ttu-id="f562d-124">De lo contrario, se produce una excepción <xref:System.InvalidOperationException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="f562d-124">Otherwise, a <xref:System.InvalidOperationException?displayProperty=fullName> is thrown.</span></span>  
  
    -   <span data-ttu-id="f562d-125">El valor predeterminado de `HasValue` es `false`.</span><span class="sxs-lookup"><span data-stu-id="f562d-125">The default value for `HasValue` is `false`.</span></span> <span data-ttu-id="f562d-126">La propiedad `Value` no tiene ningún valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="f562d-126">The `Value` property has no default value.</span></span>  
  
    -   <span data-ttu-id="f562d-127">También puede utilizar los operadores `==` y `!=` con un tipo que acepta valores NULL, como se muestra en el ejemplo siguiente: `if (x != null) y = x;`</span><span class="sxs-lookup"><span data-stu-id="f562d-127">You can also use the `==` and `!=` operators with a nullable type, as shown in the following example: `if (x != null) y = x;`</span></span>  
  
-   <span data-ttu-id="f562d-128">Utilice el operador `??` para asignar un valor predeterminado que se aplicará cuando un tipo que acepta valores NULL cuyo valor actual es `null` se asigna a un tipo que no acepta valores NULL, por ejemplo `int? x = null; int y = x ?? -1;`</span><span class="sxs-lookup"><span data-stu-id="f562d-128">Use the `??` operator to assign a default value that will be applied when a nullable type whose current value is `null` is assigned to a non-nullable type, for example `int? x = null; int y = x ?? -1;`</span></span>  
  
-   <span data-ttu-id="f562d-129">No se permiten los tipos anidados que aceptan valores NULL.</span><span class="sxs-lookup"><span data-stu-id="f562d-129">Nested nullable types are not allowed.</span></span> <span data-ttu-id="f562d-130">La línea siguiente no se compilará: `Nullable<Nullable<int>> n;`</span><span class="sxs-lookup"><span data-stu-id="f562d-130">The following line will not compile: `Nullable<Nullable<int>> n;`</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f562d-131">Secciones relacionadas</span><span class="sxs-lookup"><span data-stu-id="f562d-131">Related Sections</span></span>  
 <span data-ttu-id="f562d-132">Para obtener más información:</span><span class="sxs-lookup"><span data-stu-id="f562d-132">For more information:</span></span>  
  
-   [<span data-ttu-id="f562d-133">Utilizar tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="f562d-133">Using Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)  
  
-   [<span data-ttu-id="f562d-134">Aplicar la conversión boxing a tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="f562d-134">Boxing Nullable Types</span></span>](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
  
-   [<span data-ttu-id="f562d-135">Operador ??</span><span class="sxs-lookup"><span data-stu-id="f562d-135">?? Operator</span></span>](../../../csharp/language-reference/operators/null-conditional-operator.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="f562d-136">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f562d-136">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f562d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="f562d-137">See Also</span></span>  
 <span data-ttu-id="f562d-138"><xref:System.Nullable></span><span class="sxs-lookup"><span data-stu-id="f562d-138"><xref:System.Nullable></span></span>   
 <span data-ttu-id="f562d-139">[Guía de programación de C#](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f562d-139">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f562d-140">[C#](../../../csharp/index.md) </span><span class="sxs-lookup"><span data-stu-id="f562d-140">[C#](../../../csharp/index.md) </span></span>  
 <span data-ttu-id="f562d-141">[Referencia de C#](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f562d-141">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="f562d-142">¿Qué significa exactamente "elevado"?</span><span class="sxs-lookup"><span data-stu-id="f562d-142">What exactly does 'lifted' mean?</span></span>](http://go.microsoft.com/fwlink/?LinkId=112382)

