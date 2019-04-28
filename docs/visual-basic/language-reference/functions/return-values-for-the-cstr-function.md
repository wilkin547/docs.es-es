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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61801535"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valores devueltos para la función CStr (Visual Basic)
La tabla siguiente describen los valores devueltos para `CStr` para diferentes tipos de datos de `expression`.  
  
|Si `expression` es de tipo|Devoluciones de `CStr`|  
|-----------------------------|--------------------|  
|[Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Una cadena que contiene "True" o "False".|  
|[Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Una cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.|  
|[Tipos de datos numéricos](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Una cadena que representa el número.|  
  
## <a name="cstr-and-date"></a>CStr y Date  
 El `Date` tipo siempre contiene información de fecha y hora. Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) sea un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral para el tiempo. `CStr` no incluye valores neutrales en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha aún está presente en el original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  El `CStr` función realiza su conversión en función de la configuración de la referencia cultural actual para la aplicación. Para obtener la representación de cadena de un número en una referencia cultural determinada, use el número `ToString(IFormatProvider)` método. Por ejemplo, usar <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` a un `String`.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)
