---
title: Valores devueltos para la función CStr (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: 3653194c7e48533e664ac7513ca7f4f48d1c69f7
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819520"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="c7898-102">Valores devueltos para la función CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7898-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="c7898-103">La tabla siguiente describen los valores devueltos para `CStr` para diferentes tipos de datos de `expression`.</span><span class="sxs-lookup"><span data-stu-id="c7898-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="c7898-104">Si `expression` es de tipo</span><span class="sxs-lookup"><span data-stu-id="c7898-104">If `expression` type is</span></span>|<span data-ttu-id="c7898-105">Devoluciones de `CStr`</span><span class="sxs-lookup"><span data-stu-id="c7898-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="c7898-106">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c7898-106">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="c7898-107">Una cadena que contiene "True" o "False".</span><span class="sxs-lookup"><span data-stu-id="c7898-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="c7898-108">Date (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c7898-108">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="c7898-109">Una cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.</span><span class="sxs-lookup"><span data-stu-id="c7898-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="c7898-110">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="c7898-110">Numeric Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="c7898-111">Una cadena que representa el número.</span><span class="sxs-lookup"><span data-stu-id="c7898-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="c7898-112">CStr y Date</span><span class="sxs-lookup"><span data-stu-id="c7898-112">CStr and Date</span></span>  
 <span data-ttu-id="c7898-113">El `Date` tipo siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="c7898-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="c7898-114">Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) sea un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="c7898-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="c7898-115">`CStr` no incluye valores neutrales en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="c7898-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="c7898-116">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="c7898-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="c7898-117">Sin embargo, la información de fecha aún está presente en el original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span><span class="sxs-lookup"><span data-stu-id="c7898-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7898-118">El `CStr` función realiza su conversión en función de la configuración de la referencia cultural actual para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c7898-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="c7898-119">Para obtener la representación de cadena de un número en una referencia cultural determinada, use el número `ToString(IFormatProvider)` método.</span><span class="sxs-lookup"><span data-stu-id="c7898-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="c7898-120">Por ejemplo, usar <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` a un `String`.</span><span class="sxs-lookup"><span data-stu-id="c7898-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7898-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="c7898-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="c7898-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="c7898-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c7898-123">Boolean (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c7898-123">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="c7898-124">Date (tipo de datos)</span><span class="sxs-lookup"><span data-stu-id="c7898-124">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)
