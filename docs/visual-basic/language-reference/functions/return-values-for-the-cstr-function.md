---
title: Valores devueltos para la función CStr
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
ms.openlocfilehash: 6039ba3f6bd1c364db818807604ee0851bc23d50
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406394"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="2a824-102">Valores devueltos para la función CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a824-102">Return Values for the CStr Function (Visual Basic)</span></span>
<span data-ttu-id="2a824-103">En la tabla siguiente se describen los valores devueltos para `CStr` para distintos tipos de datos de `expression` .</span><span class="sxs-lookup"><span data-stu-id="2a824-103">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="2a824-104">Si el `expression` tipo es</span><span class="sxs-lookup"><span data-stu-id="2a824-104">If `expression` type is</span></span>|<span data-ttu-id="2a824-105">Devoluciones de `CStr`</span><span class="sxs-lookup"><span data-stu-id="2a824-105">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="2a824-106">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="2a824-106">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="2a824-107">Cadena que contiene "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="2a824-107">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="2a824-108">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="2a824-108">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="2a824-109">Cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.</span><span class="sxs-lookup"><span data-stu-id="2a824-109">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="2a824-110">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="2a824-110">Numeric Data Types</span></span>](../../programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="2a824-111">Cadena que representa el número.</span><span class="sxs-lookup"><span data-stu-id="2a824-111">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="2a824-112">CStr y Date</span><span class="sxs-lookup"><span data-stu-id="2a824-112">CStr and Date</span></span>  
 <span data-ttu-id="2a824-113">El `Date` tipo siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="2a824-113">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="2a824-114">A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="2a824-114">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="2a824-115">`CStr`no incluye valores neutros en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="2a824-115">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="2a824-116">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="2a824-116">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="2a824-117">Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="2a824-117">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2a824-118">La `CStr` función realiza su conversión en función de la configuración de la referencia cultural actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a824-118">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="2a824-119">Para obtener la representación en forma de cadena de un número en una referencia cultural determinada, use el método del número `ToString(IFormatProvider)` .</span><span class="sxs-lookup"><span data-stu-id="2a824-119">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="2a824-120">Por ejemplo, <xref:System.Double.ToString%2A?displayProperty=nameWithType> se usa al convertir un valor de tipo `Double` en `String` .</span><span class="sxs-lookup"><span data-stu-id="2a824-120">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a824-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2a824-121">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="2a824-122">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="2a824-122">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="2a824-123">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="2a824-123">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="2a824-124">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="2a824-124">Date Data Type</span></span>](../data-types/date-data-type.md)
