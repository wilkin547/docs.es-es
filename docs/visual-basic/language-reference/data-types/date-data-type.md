---
title: "Date (Tipo de datos, Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Date"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "# (especificador para literales Date)"
  - "tipos de datos [Visual Basic], asignar"
  - "valores de datos"
  - "Date (tipo de datos)"
  - "Date (literales)"
  - "fechas, Date (tipo de datos)"
  - "fechas, tipos de datos de Visual Basic"
  - "literales, Date"
  - "horas, Date (tipo de datos)"
  - "horas, tipos de datos de Visual Basic"
ms.assetid: d9edf5b0-e85e-438b-a1cf-1f321e7c831b
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Date (Tipo de datos, Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Contiene los valores IEEE de 64 bits \(8 bytes\) que representan fechas comprendidas entre el 1 de enero del año 0001 hasta el 31 de diciembre del año 9999, y las horas comprendidas entre las 00:00:00 \(medianoche\) y las 23:59:59.9999999.  Cada incremento representa 100 nanosegundos de tiempo transcurrido desde el comienzo del 1 de enero del año 1 del calendario gregoriano.  El valor máximo representa 100 nanosegundos antes del comienzo del 1 de enero del año 10000.  
  
## Comentarios  
 Utilice el tipo de datos `Date` para contener valores de fecha, valores de hora o valores de fecha y hora.  
  
 El valor predeterminado de `Date` es 0:00:00 \(medianoche\) del 1 de enero de 0001.  
  
 Puede obtener la fecha y hora actuales desde la clase <xref:Microsoft.VisualBasic.DateAndTime>.  
  
## Requisitos de formato  
 Debe delimitar cualquier literal `Date` con signos de número \(`# #`\).  Debe especificar el valor de fecha en el formato M\/d\/aaaa, por ejemplo `#5/31/1993#`, o aaaa\-MM\-dd, por ejemplo `#1993-5-31#`.  Puede usar barras diagonales al especificar el año en primer lugar.  Este requisito es independiente de la configuración regional y de la configuración de formato de fecha y hora del equipo.  
  
 El motivo de esta restricción es que el significado del código nunca debe cambiar en función de la configuración regional en que se ejecuta la aplicación.  Suponga que codifica un literal `Date` de `#3/4/1998#` con la intención de que signifique el 4 de marzo de 1998.  En una configuración regional que use el formato mm\/dd\/aaaa, 3\/4\/1998 se compila tal como desea.  Pero suponga que implementa la aplicación en varios países.  En una configuración regional que use el formato dd\/mm\/aaaa, el literal incluido en el código se compilará como 3 de abril de 1998.  En una configuración local que utilice el formato aaaa\/mm\/dd, el literal no sería válido \(1998 de abril de 0003\) y generaría un error de compilación.  
  
## Soluciones  
 Para convertir un literal `Date` al formato de la configuración regional o a un formato personalizado, proporcione el literal a la función <xref:Microsoft.VisualBasic.Strings.Format%2A> especificando un formato de fecha predefinido o uno especificado por el usuario.  En el siguiente ejemplo se muestra cómo hacerlo.  
  
```  
MsgBox("The formatted date is " & Format(#5/31/1993#, "dddd, d MMM yyyy"))  
```  
  
 Si lo desea, también puede utilizar uno de los constructores sobrecargados de la estructura <xref:System.DateTime> para ensamblar un valor de fecha y hora.  En el ejemplo siguiente se crea un valor para representar 31 de mayo de 1993 a las 12:14 del mediodía.  
  
```  
Dim dateInMay As New System.DateTime(1993, 5, 31, 12, 14, 0)   
```  
  
## Formato de hora  
 Puede especificar el valor de hora en formato de 12 horas o de 24 horas, por ejemplo, `#1:15:30 PM#` o `#13:15:30#`.  Sin embargo, si no especifica los minutos o los segundos, debe especificar AM o PM.  
  
## Valores predeterminados de fecha y hora  
 Si no incluye una fecha en un literal de fecha y hora, Visual Basic establece la parte de fecha del valor en el 1 de enero de 0001.  Si no incluye una hora en un literal de fecha y hora, Visual Basic establece la parte de hora del valor en el inicio del día, es decir, medianoche \(0:00:00\).  
  
## Conversiones de tipos  
 Si convierte un valor `Date` al tipo `String`, Visual Basic representa la fecha en función del formato corto de fecha especificado por la configuración regional en tiempo de ejecución y representa la hora de acuerdo con el formato de hora \(12 o 24 horas\) especificado por la configuración regional en tiempo de ejecución.  
  
## Sugerencias de programación  
  
-   **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para .NET Framework, por ejemplo, objetos de automatización o COM, tenga presente que los tipos de fecha y hora definidos en otros entornos no son compatibles con el tipo `Date` de Visual Basic.  Al pasar un argumento de fecha y hora a esos componentes, declárelo en el código de Visual Basic como `Double` en lugar de como `Date`, y use los métodos de conversión <xref:System.DateTime.FromOADate%2A?displayProperty=fullName> y <xref:System.DateTime.ToOADate%2A?displayProperty=fullName>.  
  
-   **Caracteres de tipo.** `Date` no tiene caracteres de tipo literal ni caracteres de tipo identificador.  Sin embargo, el compilador trata los literales incluidos entre caracteres de signo de número \(`# #`\) como `Date`.  
  
-   **Tipo de Framework.** El tipo correspondiente en .NET Framework es la estructura <xref:System.DateTime?displayProperty=fullName>.  
  
## Ejemplo  
 Una variable o constante del tipo de datos `Date` contiene la fecha y la hora.  Esto se ilustra en el siguiente ejemplo:  
  
```  
Dim someDateAndTime As Date = #8/13/2002 12:14 PM#  
```  
  
## Vea también  
 <xref:System.DateTime?displayProperty=fullName>   
 [Tipos de datos](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Cadenas con formato de fecha y hora estándar](../Topic/Standard%20Date%20and%20Time%20Format%20Strings.md)   
 [Cadenas con formato de fecha y hora personalizado](../Topic/Custom%20Date%20and%20Time%20Format%20Strings.md)   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Resumen de conversión](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Uso eficiente de tipos de datos](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)