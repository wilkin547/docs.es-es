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
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349991"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valores devueltos para la función CStr (Visual Basic)
En la tabla siguiente se describen los valores devueltos para `CStr` para diferentes tipos de datos de `expression`.  
  
|Si `expression` tipo es|Devoluciones de `CStr`|  
|-----------------------------|--------------------|  
|[Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cadena que contiene "true" o "false".|  
|[Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Cadena que contiene un valor de `Date` (fecha y hora) en el formato de fecha corta del sistema.|  
|[Tipos de datos numéricos](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Cadena que representa el número.|  
  
## <a name="cstr-and-date"></a>CStr y Date  
 El tipo de `Date` siempre contiene información de fecha y hora. A efectos de la conversión de tipos, Visual Basic considera 1/1/0001 (1 de enero del año 1) para que sea un *valor neutro* para la fecha y 00:00:00 (medianoche) como valor neutro para el tiempo. `CStr` no incluye valores neutros en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha todavía está presente en el valor de `Date` original y se puede recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
> La función `CStr` realiza su conversión en función de la configuración de la referencia cultural actual de la aplicación. Para obtener la representación en forma de cadena de un número en una referencia cultural determinada, use el método `ToString(IFormatProvider)` del número. Por ejemplo, utilice <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` en un `String`.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)
