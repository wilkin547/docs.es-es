---
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
ms.openlocfilehash: 823931f7d6beb8218e8b99d4a8d45716b7214304
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077155"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="dab08-102">Conversiones entre cadenas y otros tipos (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dab08-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>

<span data-ttu-id="dab08-103">Puede convertir un valor numérico, `Boolean` o de fecha y hora en un `String` .</span><span class="sxs-lookup"><span data-stu-id="dab08-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="dab08-104">También puede convertir en la dirección inversa, de un valor de cadena a numérico, `Boolean` o, `Date` siempre que el contenido de la cadena pueda interpretarse como un valor válido del tipo de datos de destino.</span><span class="sxs-lookup"><span data-stu-id="dab08-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="dab08-105">Si no es así, se produce un error en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="dab08-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="dab08-106">Las conversiones de todas estas asignaciones, en cualquier dirección, son conversiones de restricción.</span><span class="sxs-lookup"><span data-stu-id="dab08-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="dab08-107">Debe utilizar las palabras clave de conversión de tipos ( `CBool` , `CByte` , `CDate` , `CDbl` , `CDec` , `CInt` , `CLng` , `CSByte` , `CShort` , `CSng` , `CStr` , `CUInt` ,, `CULng` `CUShort` y `CType` ).</span><span class="sxs-lookup"><span data-stu-id="dab08-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="dab08-108">Las <xref:Microsoft.VisualBasic.Strings.Format%2A> <xref:Microsoft.VisualBasic.Conversion.Val%2A> funciones y proporcionan un control adicional sobre las conversiones entre cadenas y números.</span><span class="sxs-lookup"><span data-stu-id="dab08-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="dab08-109">Si ha definido una clase o estructura, puede definir operadores de conversión de tipos entre `String` y el tipo de la clase o estructura.</span><span class="sxs-lookup"><span data-stu-id="dab08-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="dab08-110">Para obtener más información, consulta [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dab08-110">For more information, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="dab08-111">Conversión de números en cadenas</span><span class="sxs-lookup"><span data-stu-id="dab08-111">Conversion of Numbers to Strings</span></span>  

 <span data-ttu-id="dab08-112">Puede usar la `Format` función para convertir un número en una cadena con formato, que puede incluir no solo los dígitos adecuados, sino también símbolos de formato como un signo de moneda (como `$` ), separadores de miles o *símbolos de agrupación de dígitos* (como `,` ) y un separador decimal (como `.` ).</span><span class="sxs-lookup"><span data-stu-id="dab08-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="dab08-113">`Format` usa automáticamente los símbolos apropiados según la configuración **regional** especificada en el **Panel de control**de Windows.</span><span class="sxs-lookup"><span data-stu-id="dab08-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="dab08-114">Tenga en cuenta que el operador de concatenación ( `&` ) puede convertir un número en una cadena implícitamente, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dab08-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="dab08-115">Conversión de cadenas en números</span><span class="sxs-lookup"><span data-stu-id="dab08-115">Conversion of Strings to Numbers</span></span>  

 <span data-ttu-id="dab08-116">Puede usar la `Val` función para convertir explícitamente los dígitos de una cadena en un número.</span><span class="sxs-lookup"><span data-stu-id="dab08-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="dab08-117">`Val` Lee la cadena hasta que encuentra un carácter que no sea un dígito, un espacio, una tabulación, un salto de línea o un punto.</span><span class="sxs-lookup"><span data-stu-id="dab08-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="dab08-118">Las secuencias "&O" y "&H" modifican la base del sistema numérico y finalizan el análisis.</span><span class="sxs-lookup"><span data-stu-id="dab08-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="dab08-119">Hasta que deje de leerse, `Val` convierte todos los caracteres adecuados en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="dab08-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="dab08-120">Por ejemplo, la siguiente instrucción devuelve el valor `141.825` .</span><span class="sxs-lookup"><span data-stu-id="dab08-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="dab08-121">Cuando Visual Basic convierte una cadena en un valor numérico, usa la configuración de **Opciones regionales** especificada en el panel de **control** de Windows para interpretar el separador de miles, el separador decimal y el símbolo de moneda.</span><span class="sxs-lookup"><span data-stu-id="dab08-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="dab08-122">Esto significa que una conversión podría realizarse con una configuración, pero no con otra.</span><span class="sxs-lookup"><span data-stu-id="dab08-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="dab08-123">Por ejemplo, `"$14.20"` es aceptable en la configuración regional en inglés (Estados Unidos), pero no en la configuración regional en francés.</span><span class="sxs-lookup"><span data-stu-id="dab08-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab08-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab08-124">See also</span></span>

- [<span data-ttu-id="dab08-125">Conversiones de tipos en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dab08-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="dab08-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="dab08-126">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="dab08-127">Conversiones implícitas y explícitas</span><span class="sxs-lookup"><span data-stu-id="dab08-127">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="dab08-128">Cómo: Convertir un objeto en otro tipo en Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dab08-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="dab08-129">Conversiones de matriz</span><span class="sxs-lookup"><span data-stu-id="dab08-129">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="dab08-130">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dab08-130">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="dab08-131">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="dab08-131">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="dab08-132">Desarrollo de aplicaciones localizadas y globalizadas</span><span class="sxs-lookup"><span data-stu-id="dab08-132">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
