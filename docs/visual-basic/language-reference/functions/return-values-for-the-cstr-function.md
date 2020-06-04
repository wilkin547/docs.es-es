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
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valores devueltos para la función CStr (Visual Basic)
En la tabla siguiente se describen los valores devueltos para `CStr` para distintos tipos de datos de `expression` .  
  
|Si el `expression` tipo es|Devoluciones de `CStr`|  
|-----------------------------|--------------------|  
|[Tipo de datos Boolean](../data-types/boolean-data-type.md)|Cadena que contiene "true" o "false".|  
|[Tipo de datos Date](../data-types/date-data-type.md)|Cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.|  
|[Tipos de datos numéricos](../../programming-guide/language-features/data-types/numeric-data-types.md)|Cadena que representa el número.|  
  
## <a name="cstr-and-date"></a>CStr y Date  
 El `Date` tipo siempre contiene información de fecha y hora. A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo. `CStr`no incluye valores neutros en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha todavía está presente en el `Date` valor original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .  
  
> [!NOTE]
> La `CStr` función realiza su conversión en función de la configuración de la referencia cultural actual de la aplicación. Para obtener la representación en forma de cadena de un número en una referencia cultural determinada, use el método del número `ToString(IFormatProvider)` . Por ejemplo, <xref:System.Double.ToString%2A?displayProperty=nameWithType> se usa al convertir un valor de tipo `Double` en `String` .  
  
## <a name="see-also"></a>Consulte también

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Type Conversion Functions](type-conversion-functions.md)
- [Tipo de datos Boolean](../data-types/boolean-data-type.md)
- [Tipo de datos Date](../data-types/date-data-type.md)
