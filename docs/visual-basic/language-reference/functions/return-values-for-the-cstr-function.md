---
title: "Valores devueltos para la funci&#243;n CStr (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CStr (función)"
  - "Date (tipo de datos), convertir"
  - "fechas [Visual Basic]"
  - "fechas [Visual Basic], valores devueltos para la función CStr"
  - "String (tipo de datos), convertir"
  - "cadenas [Visual Basic], valor devuelto"
  - "horas, valores devueltos para la función CStr"
  - "conversión de tipos"
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Valores devueltos para la funci&#243;n CStr (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

En la tabla siguiente se describen los valores devueltos por la función `CStr` en varios tipos de `expression`.  
  
|Si el tipo de `expression` es|`CStr` devuelve|  
|-----------------------------------|---------------------|  
|[Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Cadena que contiene "True" o "False".|  
|[Date \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/date-data-type.md)|Cadena que contiene un valor `Date` \(fecha y hora\) en el formato de fecha corta del sistema.|  
|[Tipos de datos numéricos](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|Cadena que representa el número.|  
  
## CStr y Date  
 El tipo `Date` siempre contiene información de fecha y hora.  Para la conversión de tipos, Visual Basic considera 1\/1\/0001 \(1 de enero del año 1\) un *valor neutral* de fecha y 00:00:00 \(medianoche\) un valor neutral de hora.  `CStr` no incluye los valores neutros en la cadena resultante.  Por ejemplo, si se convierte `#January 1, 0001 9:30:00#` en una cadena, el resultado sería "9:30:00 a.m.", ya que la información de fecha se omite.  No obstante, la información de fecha sigue estando presente en el valor `Date` original y se puede recuperar mediante funciones como <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>.  
  
> [!NOTE]
>  La función `CStr` realiza su conversión basándose en la configuración de la referencia cultural actual de la aplicación.  Para obtener la representación en forma de cadena de un número en una referencia cultural determinada, utilice el método `ToString(IFormatProvider)` del número.  Por ejemplo, utilice <xref:System.Double.ToString%2A?displayProperty=fullName> al convertir un valor de tipo `Double` en `String`.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Boolean \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/boolean-data-type.md)   
 [Date \(Tipo de datos\)](../../../visual-basic/language-reference/data-types/date-data-type.md)