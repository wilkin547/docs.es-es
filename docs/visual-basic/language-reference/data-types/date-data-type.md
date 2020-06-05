---
title: Tipo de datos Date
ms.date: 07/20/2015
f1_keywords:
- vb.Date
helpviewer_keywords:
- Date data type
- dates [Visual Basic], Visual Basic data types
- times [Visual Basic], Date data type
- Date literals [Visual Basic]
- data values [Visual Basic]
- times [Visual Basic], Visual Basic data types
- dates [Visual Basic], Date data type
- data types [Visual Basic], assigning
- literals [Visual Basic], Date
- '# specifier for Date literals'
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
ms.openlocfilehash: 46c25e14db56d4cc3c6d59ec7649b37c35676e2e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387431"
---
# <a name="date-data-type-visual-basic"></a><span data-ttu-id="fd7f7-102">Date (Tipo de datos, Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fd7f7-102">Date Data Type (Visual Basic)</span></span>

<span data-ttu-id="fd7f7-103">Contiene los valores IEEE de 64 bits (8 bytes) que representan fechas comprendidas entre el 1 de enero del año 0001 hasta el 31 de diciembre del año 9999, y las horas comprendidas entre las 00:00:00 (medianoche) y las 23:59:59.9999999.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-103">Holds IEEE 64-bit (8-byte) values that represent dates ranging from January 1 of the year 0001 through December 31 of the year 9999, and times from 12:00:00 AM (midnight) through 11:59:59.9999999 PM.</span></span> <span data-ttu-id="fd7f7-104">Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el comienzo del 1 de enero del año 1 del calendario gregoriano.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-104">Each increment represents 100 nanoseconds of elapsed time since the beginning of January 1 of the year 1 in the Gregorian calendar.</span></span> <span data-ttu-id="fd7f7-105">El valor máximo representa 100 nanosegundos antes del comienzo del 1 de enero del año 10000.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-105">The maximum value represents 100 nanoseconds before the beginning of January 1 of the year 10000.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd7f7-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fd7f7-106">Remarks</span></span>

<span data-ttu-id="fd7f7-107">Utilice el tipo de datos `Date` para contener valores de fecha, valores de hora o valores de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-107">Use the `Date` data type to contain date values, time values, or date and time values.</span></span>

<span data-ttu-id="fd7f7-108">El valor predeterminado de `Date` es 0:00:00 (medianoche) del 1 de enero de 0001.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-108">The default value of `Date` is 0:00:00 (midnight) on January 1, 0001.</span></span>

<span data-ttu-id="fd7f7-109">Puede obtener la fecha y hora actuales desde la clase <xref:Microsoft.VisualBasic.DateAndTime>.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-109">You can get the current date and time from the <xref:Microsoft.VisualBasic.DateAndTime> class.</span></span>

## <a name="format-requirements"></a><span data-ttu-id="fd7f7-110">Requisitos de formato</span><span class="sxs-lookup"><span data-stu-id="fd7f7-110">Format Requirements</span></span>

<span data-ttu-id="fd7f7-111">Debe delimitar cualquier literal `Date` con signos de número (`# #`).</span><span class="sxs-lookup"><span data-stu-id="fd7f7-111">You must enclose a `Date` literal within number signs (`# #`).</span></span> <span data-ttu-id="fd7f7-112">Debe especificar el valor de fecha en el formato M/d/aaaa, por ejemplo `#5/31/1993#`, o aaaa-MM-dd, por ejemplo `#1993-5-31#`.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-112">You must specify the date value in the format M/d/yyyy, for example `#5/31/1993#`, or yyyy-MM-dd, for example `#1993-5-31#`.</span></span> <span data-ttu-id="fd7f7-113">Puede usar barras diagonales al especificar el año en primer lugar.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-113">You can use slashes when specifying the year first.</span></span>  <span data-ttu-id="fd7f7-114">Este requisito es independiente de la configuración regional y de la configuración de formato de fecha y hora del equipo.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-114">This requirement is independent of your locale and your computer's date and time format settings.</span></span>

<span data-ttu-id="fd7f7-115">El motivo de esta restricción es que el significado del código nunca debe cambiar en función de la configuración regional en que se ejecuta la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-115">The reason for this restriction is that the meaning of your code should never change depending on the locale in which your application is running.</span></span> <span data-ttu-id="fd7f7-116">Suponga que codifica un literal `Date` de `#3/4/1998#` con la intención de que signifique el 4 de marzo de 1998.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-116">Suppose you hard-code a `Date` literal of `#3/4/1998#` and intend it to mean March 4, 1998.</span></span> <span data-ttu-id="fd7f7-117">En una configuración regional que use el formato mm/dd/aaaa, 3/4/1998 se compila tal como desea.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-117">In a locale that uses mm/dd/yyyy, 3/4/1998 compiles as you intend.</span></span> <span data-ttu-id="fd7f7-118">Pero supongamos que implementa la aplicación en muchos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-118">But suppose you deploy your application in many countries/regions.</span></span> <span data-ttu-id="fd7f7-119">En una configuración regional que use el formato dd/mm/aaaa, el literal incluido en el código se compilará como 3 de abril de 1998.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-119">In a locale that uses dd/mm/yyyy, your hard-coded literal would compile to April 3, 1998.</span></span> <span data-ttu-id="fd7f7-120">En una configuración local que utilice el formato aaaa/mm/dd, el literal no sería válido (1998 de abril de 0003) y generaría un error de compilación.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-120">In a locale that uses yyyy/mm/dd, the literal would be invalid (April 1998, 0003) and cause a compiler error.</span></span>

## <a name="workarounds"></a><span data-ttu-id="fd7f7-121">Soluciones alternativas</span><span class="sxs-lookup"><span data-stu-id="fd7f7-121">Workarounds</span></span>

<span data-ttu-id="fd7f7-122">Para convertir un literal `Date` al formato de la configuración regional o a un formato personalizado, proporcione el literal a la función <xref:Microsoft.VisualBasic.Strings.Format%2A> especificando un formato de fecha predefinido o uno especificado por el usuario.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-122">To convert a `Date` literal to the format of your locale, or to a custom format, supply the literal to the <xref:Microsoft.VisualBasic.Strings.Format%2A> function, specifying either a predefined or user-defined date format.</span></span> <span data-ttu-id="fd7f7-123">El ejemplo siguiente demuestra este patrón.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-123">The following example demonstrates this.</span></span>

```vb
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))
```

<span data-ttu-id="fd7f7-124">Si lo desea, también puede utilizar uno de los constructores sobrecargados de la estructura <xref:System.DateTime> para ensamblar un valor de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-124">Alternatively, you can use one of the overloaded constructors of the <xref:System.DateTime> structure to assemble a date and time value.</span></span> <span data-ttu-id="fd7f7-125">En el ejemplo siguiente se crea un valor para representar 31 de mayo de 1993 a las 12:14 del mediodía.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-125">The following example creates a value to represent May 31, 1993 at 12:14 in the afternoon.</span></span>

```vb
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)
```

## <a name="hour-format"></a><span data-ttu-id="fd7f7-126">Formato de hora</span><span class="sxs-lookup"><span data-stu-id="fd7f7-126">Hour Format</span></span>

<span data-ttu-id="fd7f7-127">Puede especificar el valor de hora en formato de 12 horas o de 24 horas, por ejemplo, `#1:15:30 PM#` o `#13:15:30#`.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-127">You can specify the time value in either 12-hour or 24-hour format, for example `#1:15:30 PM#` or `#13:15:30#`.</span></span> <span data-ttu-id="fd7f7-128">Sin embargo, si no especifica los minutos o los segundos, debe especificar AM o PM.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-128">However, if you do not specify either the minutes or the seconds, you must specify AM or PM.</span></span>

## <a name="date-and-time-defaults"></a><span data-ttu-id="fd7f7-129">Valores predeterminados de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="fd7f7-129">Date and Time Defaults</span></span>

<span data-ttu-id="fd7f7-130">Si no incluye una fecha en un literal de fecha y hora, Visual Basic establece la parte de fecha del valor en el 1 de enero de 0001.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-130">If you do not include a date in a date/time literal, Visual Basic sets the date part of the value to January 1, 0001.</span></span> <span data-ttu-id="fd7f7-131">Si no incluye una hora en un literal de fecha y hora, Visual Basic establece la parte de hora del valor en el inicio del día, es decir, medianoche (0:00:00).</span><span class="sxs-lookup"><span data-stu-id="fd7f7-131">If you do not include a time in a date/time literal, Visual Basic sets the time part of the value to the start of the day, that is, midnight (0:00:00).</span></span>

## <a name="type-conversions"></a><span data-ttu-id="fd7f7-132">Conversiones de tipos</span><span class="sxs-lookup"><span data-stu-id="fd7f7-132">Type Conversions</span></span>

<span data-ttu-id="fd7f7-133">Si convierte un valor `Date` al tipo `String`, Visual Basic representa la fecha en función del formato corto de fecha especificado por la configuración regional en tiempo de ejecución y representa la hora de acuerdo con el formato de hora (12 o 24 horas) especificado por la configuración regional en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-133">If you convert a `Date` value to the `String` type, Visual Basic renders the date according to the short date format specified by the run-time locale, and it renders the time according to the time format (either 12-hour or 24-hour) specified by the run-time locale.</span></span>

## <a name="programming-tips"></a><span data-ttu-id="fd7f7-134">Sugerencias de programación</span><span class="sxs-lookup"><span data-stu-id="fd7f7-134">Programming Tips</span></span>

- <span data-ttu-id="fd7f7-135">**Consideraciones de interoperabilidad.**</span><span class="sxs-lookup"><span data-stu-id="fd7f7-135">**Interop Considerations.**</span></span> <span data-ttu-id="fd7f7-136">Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo, objetos de automatización o COM, tenga presente que los tipos de fecha y hora definidos en otros entornos no son compatibles con el tipo `Date` de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, keep in mind that date/time types in other environments are not compatible with the Visual Basic `Date` type.</span></span> <span data-ttu-id="fd7f7-137">Al pasar un argumento de fecha y hora a esos componentes, declárelo en el código de Visual Basic como `Double` en lugar de como `Date`, y use los métodos de conversión <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> y <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-137">If you are passing a date/time argument to such a component, declare it as `Double` instead of `Date` in your new Visual Basic code, and use the conversion methods <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> and <xref:System.DateTime.ToOADate%2A?displayProperty=nameWithType>.</span></span>

- <span data-ttu-id="fd7f7-138">**Caracteres de tipo.**</span><span class="sxs-lookup"><span data-stu-id="fd7f7-138">**Type Characters.**</span></span> <span data-ttu-id="fd7f7-139">`Date`no tiene un carácter de tipo literal o un carácter de tipo de identificador.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-139">`Date` has no literal type character or identifier type character.</span></span> <span data-ttu-id="fd7f7-140">Sin embargo, el compilador trata los literales incluidos entre caracteres de signo de número (`# #`) como `Date`.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-140">However, the compiler treats literals enclosed within number signs (`# #`) as `Date`.</span></span>

- <span data-ttu-id="fd7f7-141">**Tipo de Framework.**</span><span class="sxs-lookup"><span data-stu-id="fd7f7-141">**Framework Type.**</span></span> <span data-ttu-id="fd7f7-142">El tipo correspondiente en .NET Framework es la estructura <xref:System.DateTime?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-142">The corresponding type in the .NET Framework is the <xref:System.DateTime?displayProperty=nameWithType> structure.</span></span>

## <a name="example"></a><span data-ttu-id="fd7f7-143">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fd7f7-143">Example</span></span>

<span data-ttu-id="fd7f7-144">Una variable o constante del tipo de datos `Date` contiene la fecha y la hora.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-144">A variable or constant of the `Date` data type holds both the date and the time.</span></span> <span data-ttu-id="fd7f7-145">Esto se ilustra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="fd7f7-145">The following example illustrates this.</span></span>

```vb
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#
```

## <a name="see-also"></a><span data-ttu-id="fd7f7-146">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fd7f7-146">See also</span></span>

- <xref:System.DateTime?displayProperty=nameWithType>
- [<span data-ttu-id="fd7f7-147">Tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fd7f7-147">Data Types</span></span>](index.md)
- [<span data-ttu-id="fd7f7-148">Cadenas con formato de fecha y hora estándar</span><span class="sxs-lookup"><span data-stu-id="fd7f7-148">Standard Date and Time Format Strings</span></span>](../../../standard/base-types/standard-date-and-time-format-strings.md)
- [<span data-ttu-id="fd7f7-149">Cadenas con formato de fecha y hora personalizado</span><span class="sxs-lookup"><span data-stu-id="fd7f7-149">Custom Date and Time Format Strings</span></span>](../../../standard/base-types/custom-date-and-time-format-strings.md)
- [<span data-ttu-id="fd7f7-150">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="fd7f7-150">Type Conversion Functions</span></span>](../functions/type-conversion-functions.md)
- [<span data-ttu-id="fd7f7-151">Resumen de las conversiones</span><span class="sxs-lookup"><span data-stu-id="fd7f7-151">Conversion Summary</span></span>](../keywords/conversion-summary.md)
- [<span data-ttu-id="fd7f7-152">Uso eficiente de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="fd7f7-152">Efficient Use of Data Types</span></span>](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
