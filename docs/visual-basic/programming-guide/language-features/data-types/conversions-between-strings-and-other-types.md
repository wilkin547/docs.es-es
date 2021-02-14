---
description: 'Más información sobre: conversiones entre cadenas y otros tipos (Visual Basic)'
title: Conversiones entre cadenas y otros tipos
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: c0f7f7637d173d039d58b2516fba41ae55b990ac
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100477221"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="57106-103">Conversiones entre cadenas y otros tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57106-103">Conversions Between Strings and Other Types (Visual Basic)</span></span>

<span data-ttu-id="57106-104">Puede convertir un valor numérico, `Boolean` o de fecha y hora en un `String` .</span><span class="sxs-lookup"><span data-stu-id="57106-104">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="57106-105">También puede convertir en la dirección inversa, de un valor de cadena a numérico, `Boolean` o, `Date` siempre que el contenido de la cadena pueda interpretarse como un valor válido del tipo de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="57106-105">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="57106-106">Si no es así, se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="57106-106">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="57106-107">Las conversiones de todas estas asignaciones, en cualquier dirección, son conversiones de restricción.</span><span class="sxs-lookup"><span data-stu-id="57106-107">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="57106-108">Debe utilizar las palabras clave de conversión de tipos ( `CBool` , `CByte` , `CDate` , `CDbl` , `CDec` , `CInt` , `CLng` , `CSByte` , `CShort` , `CSng` , `CStr` , `CUInt` ,, `CULng` `CUShort` y `CType` ).</span><span class="sxs-lookup"><span data-stu-id="57106-108">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="57106-109">Las <xref:Microsoft.VisualBasic.Strings.Format%2A> <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones y proporcionan un control adicional sobre las conversiones entre cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="57106-109">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="57106-110">Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="57106-110">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="57106-111">Para obtener más información, consulta [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="57106-111">For more information, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="57106-112">Conversión de números en cadenas</span><span class="sxs-lookup"><span data-stu-id="57106-112">Conversion of Numbers to Strings</span></span>  

 <span data-ttu-id="57106-113">Puede usar la `Format` función para convertir un número en una cadena con formato, que puede incluir no solo los dígitos adecuados, sino también símbolos de formato como un signo de moneda (como `$` ), separadores de miles o *símbolos de agrupación de dígitos* (como `,` ) y un separador decimal (como `.` ).</span><span class="sxs-lookup"><span data-stu-id="57106-113">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="57106-114">`Format` usa automáticamente los símbolos apropiados según la configuración **regional** especificada en el **Panel de control** de Windows.</span><span class="sxs-lookup"><span data-stu-id="57106-114">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="57106-115">Tenga en cuenta que el operador de concatenación ( `&` ) puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="57106-115">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="57106-116">Conversión de cadenas en números</span><span class="sxs-lookup"><span data-stu-id="57106-116">Conversion of Strings to Numbers</span></span>  

 <span data-ttu-id="57106-117">Puede usar la `Val` función para convertir explícitamente los dígitos de una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="57106-117">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="57106-118">`Val` Lee la cadena hasta que encuentra un carácter que no sea un dígito, un espacio, una tabulación, un salto de línea o un punto.</span><span class="sxs-lookup"><span data-stu-id="57106-118">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="57106-119">Las secuencias "&O" y "&H" modifican la base del sistema numérico y finalizan el análisis.</span><span class="sxs-lookup"><span data-stu-id="57106-119">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="57106-120">Hasta que deje de leerse, `Val` convierte todos los caracteres adecuados en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="57106-120">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="57106-121">Por ejemplo, la siguiente instrucción devuelve el valor `141.825` .</span><span class="sxs-lookup"><span data-stu-id="57106-121">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="57106-122">Cuando Visual Basic convierte una cadena en un valor numérico, usa la configuración de **Opciones regionales** especificada en el panel de **control** de Windows para interpretar el separador de miles, el separador decimal y el símbolo de moneda.</span><span class="sxs-lookup"><span data-stu-id="57106-122">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="57106-123">Esto significa que una conversión podría realizarse con una configuración, pero no con otra.</span><span class="sxs-lookup"><span data-stu-id="57106-123">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="57106-124">Por ejemplo, `"$14.20"` es aceptable en la configuración regional en inglés (Estados Unidos), pero no en la configuración regional en francés.</span><span class="sxs-lookup"><span data-stu-id="57106-124">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57106-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57106-125">See also</span></span>

- [<span data-ttu-id="57106-126">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57106-126">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="57106-127">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="57106-127">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="57106-128">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="57106-128">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="57106-129">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="57106-129">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="57106-130">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="57106-130">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="57106-131">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="57106-131">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="57106-132">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="57106-132">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="57106-133">Desarrollo de aplicaciones localizadas y globalizadas</span><span class="sxs-lookup"><span data-stu-id="57106-133">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
