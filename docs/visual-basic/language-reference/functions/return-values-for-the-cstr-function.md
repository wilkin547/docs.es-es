---
description: 'Más información sobre: valores devueltos para la función CStr (Visual Basic)'
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
ms.openlocfilehash: ce45059db8ff8e926954014a09379ee54f1caf30
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731152"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a><span data-ttu-id="16368-103">Valores devueltos para la función CStr (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16368-103">Return Values for the CStr Function (Visual Basic)</span></span>

<span data-ttu-id="16368-104">En la tabla siguiente se describen los valores devueltos para `CStr` para distintos tipos de datos de `expression` .</span><span class="sxs-lookup"><span data-stu-id="16368-104">The following table describes the return values for `CStr` for different data types of `expression`.</span></span>  
  
|<span data-ttu-id="16368-105">Si el `expression` tipo es</span><span class="sxs-lookup"><span data-stu-id="16368-105">If `expression` type is</span></span>|<span data-ttu-id="16368-106">Devoluciones de `CStr`</span><span class="sxs-lookup"><span data-stu-id="16368-106">`CStr` returns</span></span>|  
|-----------------------------|--------------------|  
|[<span data-ttu-id="16368-107">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="16368-107">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="16368-108">Cadena que contiene "true" o "false".</span><span class="sxs-lookup"><span data-stu-id="16368-108">A string containing "True" or "False".</span></span>|  
|[<span data-ttu-id="16368-109">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="16368-109">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="16368-110">Cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.</span><span class="sxs-lookup"><span data-stu-id="16368-110">A string containing a `Date` value (date and time) in the short date format of your system.</span></span>|  
|[<span data-ttu-id="16368-111">Tipos de datos numéricos</span><span class="sxs-lookup"><span data-stu-id="16368-111">Numeric Data Types</span></span>](../../programming-guide/language-features/data-types/numeric-data-types.md)|<span data-ttu-id="16368-112">Cadena que representa el número.</span><span class="sxs-lookup"><span data-stu-id="16368-112">A string representing the number.</span></span>|  
  
## <a name="cstr-and-date"></a><span data-ttu-id="16368-113">CStr y Date</span><span class="sxs-lookup"><span data-stu-id="16368-113">CStr and Date</span></span>  

 <span data-ttu-id="16368-114">El `Date` tipo siempre contiene información de fecha y hora.</span><span class="sxs-lookup"><span data-stu-id="16368-114">The `Date` type always contains both date and time information.</span></span> <span data-ttu-id="16368-115">A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo.</span><span class="sxs-lookup"><span data-stu-id="16368-115">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="16368-116">`CStr` no incluye valores neutros en la cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="16368-116">`CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="16368-117">Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha.</span><span class="sxs-lookup"><span data-stu-id="16368-117">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="16368-118">Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="16368-118">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16368-119">La `CStr` función realiza su conversión en función de la configuración de la referencia cultural actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="16368-119">The `CStr` function performs its conversion based on the current culture settings for the application.</span></span> <span data-ttu-id="16368-120">Para obtener la representación en forma de cadena de un número en una referencia cultural determinada, use el método del número `ToString(IFormatProvider)` .</span><span class="sxs-lookup"><span data-stu-id="16368-120">To get the string representation of a number in a particular culture, use the number's `ToString(IFormatProvider)` method.</span></span> <span data-ttu-id="16368-121">Por ejemplo, <xref:System.Double.ToString%2A?displayProperty=nameWithType> se usa al convertir un valor de tipo `Double` en `String` .</span><span class="sxs-lookup"><span data-stu-id="16368-121">For example, use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16368-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="16368-122">See also</span></span>

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [<span data-ttu-id="16368-123">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="16368-123">Type Conversion Functions</span></span>](type-conversion-functions.md)
- [<span data-ttu-id="16368-124">Tipo de datos Boolean</span><span class="sxs-lookup"><span data-stu-id="16368-124">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="16368-125">Tipo de datos Date</span><span class="sxs-lookup"><span data-stu-id="16368-125">Date Data Type</span></span>](../data-types/date-data-type.md)
