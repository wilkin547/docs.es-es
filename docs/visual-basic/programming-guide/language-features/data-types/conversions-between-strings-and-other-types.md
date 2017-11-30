---
title: Conversiones entre cadenas y otros tipos (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 71ece18d4ce33b7b637410110e825b389affcd67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="7a580-102">Conversiones entre cadenas y otros tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7a580-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="7a580-103">Puede convertir un valor numérico, `Boolean`, o fecha y hora valor a un `String`.</span><span class="sxs-lookup"><span data-stu-id="7a580-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="7a580-104">También puede convertir en la dirección inversa, de un valor de cadena en valor numérico, `Boolean`, o `Date` , siempre que el contenido de la cadena se pueda interpretar como un valor válido del tipo de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="7a580-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="7a580-105">Si no es posible, se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7a580-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="7a580-106">Las conversiones de todas estas asignaciones, en ambas direcciones, son conversiones de restricción.</span><span class="sxs-lookup"><span data-stu-id="7a580-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="7a580-107">Debe usar las palabras clave de conversión de tipos (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, y `CType`).</span><span class="sxs-lookup"><span data-stu-id="7a580-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="7a580-108">El <xref:Microsoft.VisualBasic.Strings.Format%2A> y <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones proporcionan un control adicional sobre las conversiones entre cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="7a580-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="7a580-109">Si ha definido una clase o estructura, puede definir operadores de conversión de tipo entre `String` y el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="7a580-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="7a580-110">Para obtener más información, consulte [Cómo: definir un operador de conversión](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7a580-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="7a580-111">Conversión de números en cadenas</span><span class="sxs-lookup"><span data-stu-id="7a580-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="7a580-112">Puede usar el `Format` función para convertir un número en una cadena con formato, que puede incluir no sólo los dígitos adecuados, pero también aplicar formato a los símbolos, como un signo de moneda (como `$`), miles separadores o *agrupación de dígitos símbolos* (como `,`) y un separador decimal (como `.`).</span><span class="sxs-lookup"><span data-stu-id="7a580-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="7a580-113">`Format`usa automáticamente los símbolos adecuados según la **opciones regionales** configuración especificada en las ventanas de **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="7a580-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="7a580-114">Tenga en cuenta que la concatenación (`&`) operador puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="7a580-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="7a580-115">Conversión de cadenas en números</span><span class="sxs-lookup"><span data-stu-id="7a580-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="7a580-116">Puede usar el `Val` función para convertir explícitamente los dígitos de una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="7a580-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="7a580-117">`Val`lee la cadena hasta que encuentra un carácter que no sea un dígito, espacio, ficha, avance de línea o período.</span><span class="sxs-lookup"><span data-stu-id="7a580-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="7a580-118">Las secuencias "& O" y "& H" alteran la base del sistema numérico y finalizan el examen.</span><span class="sxs-lookup"><span data-stu-id="7a580-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="7a580-119">Hasta que finaliza la lectura, `Val` convierte todos los caracteres apropiados en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="7a580-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="7a580-120">Por ejemplo, la siguiente instrucción devuelve el valor `141.825`.</span><span class="sxs-lookup"><span data-stu-id="7a580-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="7a580-121">Cuando [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] convierte una cadena en un valor numérico, usa el **opciones regionales** configuración especificada en las ventanas de **el Panel de Control** para interpretar los miles separador, el separador decimal, y símbolo de divisa.</span><span class="sxs-lookup"><span data-stu-id="7a580-121">When [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="7a580-122">Esto significa que una conversión puede realizarse correctamente bajo una configuración, pero no en otra.</span><span class="sxs-lookup"><span data-stu-id="7a580-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="7a580-123">Por ejemplo, `"$14.20"` es aceptable en la configuración regional Inglés (Estados Unidos), pero no en cualquier configuración regional en francés.</span><span class="sxs-lookup"><span data-stu-id="7a580-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a580-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="7a580-124">See Also</span></span>  
 [<span data-ttu-id="7a580-125">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a580-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="7a580-126">Conversiones de ampliación y de restricción</span><span class="sxs-lookup"><span data-stu-id="7a580-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="7a580-127">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="7a580-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="7a580-128">Cómo: convertir un objeto a otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7a580-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="7a580-129">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="7a580-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="7a580-130">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="7a580-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="7a580-131">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="7a580-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="7a580-132">Introducción a aplicaciones internacionales basadas en .NET Framework</span><span class="sxs-lookup"><span data-stu-id="7a580-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
