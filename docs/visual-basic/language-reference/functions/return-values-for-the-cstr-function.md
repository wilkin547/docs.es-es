---
title: "Valores devueltos para la función CStr (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b498c9b1b7916467c96ed2c645c7131192a5e8b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>Valores devueltos para la función CStr (Visual Basic)
La tabla siguiente describen los valores devueltos por `CStr` para distintos tipos de datos de `expression`.  
  
|Si `expression` es de tipo|`CStr`Devuelve|  
|-----------------------------|--------------------|  
|[Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Una cadena que contiene "True" o "False".|  
|[Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Una cadena que contiene un `Date` valor (fecha y hora) en el formato de fecha corta del sistema.|  
|[Tipos de datos numéricos](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Una cadena que representa el número.|  
  
## <a name="cstr-and-date"></a>CStr y Date  
 El `Date` tipo siempre contiene información de fecha y hora. Para fines de conversión de tipos, Visual Basic considera 1/1/0001 (del 1 de enero del año 1) como un *valor neutral* de fecha y 00:00:00 (medianoche) un valor neutral por vez. `CStr`no incluye valores neutrales en la cadena resultante. Por ejemplo, si convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado es "9:30:00 AM"; se suprime la información de fecha. Sin embargo, la información de fecha aún está presente en la versión original `Date` valor y se pueden recuperar con funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  El `CStr` función realiza su conversión basándose en la configuración de referencia cultural actual para la aplicación. Para obtener la representación de cadena de un número en una referencia cultural determinada, use el número `ToString(IFormatProvider)` método. Por ejemplo, utilice <xref:System.Double.ToString%2A?displayProperty=nameWithType> al convertir un valor de tipo `Double` a una `String`.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>  
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Boolean (tipo de datos)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)  
 [Date (tipo de datos)](../../../visual-basic/language-reference/data-types/date-data-type.md)
