---
title: "Efectuar operaciones aritm&#233;ticas con fechas y horas | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "operaciones aritméticas [.NET Framework], fechas y horas"
  - "fechas [.NET Framework], operaciones aritméticas"
  - "fechas [.NET Framework], comparar"
  - "DateTime (estructura), operaciones aritméticas"
  - "DateTimeOffset (estructura), operaciones aritméticas"
  - "zonas horarias [.NET Framework], operaciones aritméticas"
  - "horas [.NET Framework], operaciones aritméticas"
ms.assetid: 87c7ddf2-f15e-48af-8602-b3642237e6d0
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Efectuar operaciones aritm&#233;ticas con fechas y horas
Aunque tanto las estructuras <xref:System.DateTime> como <xref:System.DateTimeOffset> proporcionan miembros que efectúan operaciones aritméticas con sus valores, los resultados que arrojan estas operaciones son muy diferentes.  En este tema se estudian esas diferencias, se relacionan con los grados de conocimiento de la zona horaria en los datos de fecha y hora, y se explica cómo realizar operaciones con conocimiento pleno de la zona horaria utilizando datos de fecha y hora.  
  
## Operaciones comparativas y aritméticas con valores de DateTime  
 A partir de la versión 2.0 de .NET Framework, los valores de <xref:System.DateTime> poseen un grado limitado de conocimiento de la zona horaria.  La propiedad <xref:System.DateTime.Kind%2A?displayProperty=fullName> permite asignar un valor de <xref:System.DateTimeKind> a la fecha y la hora para indicar si representa la hora local, la hora universal coordinada \(UTC\) o la hora de una zona horaria no especificada.  Sin embargo, esta información de zona horaria limitada se omite al efectuar comparaciones u operaciones aritméticas de fecha y hora con valores de <xref:System.DateTime>.  En el ejemplo siguiente, donde se compara la hora local actual con la hora UTC actual, se ilustra este punto.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual2.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual2.vb#2)]  
  
 Los informes del método de <xref:System.DateTime.CompareTo%28System.DateTime%29> que la hora local es anterior a \(o menor que\) la hora UTC, y la operación de resta indica que la diferencia entre la hora utc y la hora local para un sistema de la zona horaria estándar del Pacífico de EE.UU. es siete horas.  Sin embargo, debido a que estos dos valores proporcionan representaciones diferentes de un mismo punto de tiempo, en este caso está claro que este intervalo de tiempo es totalmente atribuible a la diferencia entre la zona horaria local con respecto a la hora UTC.  
  
 De modo más general, la propiedad <xref:System.DateTime.Kind%2A?displayProperty=fullName> no afecta a los resultados devueltos por la comparación <xref:System.DateTime> ni a los métodos aritméticos \(tal como lo indica la comparación de dos puntos de tiempo idénticos\), aunque puede afectar a la interpretación de esos resultados.  Por ejemplo:  
  
-   El resultado de cualquier operación aritmética efectuada con dos valores de fecha y hora cuyas propiedades <xref:System.DateTime.Kind%2A?displayProperty=fullName> sean iguales a <xref:System.DateTimeKind> en ambos casos, refleja el intervalo de tiempo real entre los dos valores.  De igual forma, la comparación de dos valores de fecha y hora de este tipo refleja con precisión la relación entre ambas horas.  
  
-   El resultado de cualquier operación aritmética o comparativa realizada con dos valores de fecha y hora cuyas propiedades <xref:System.DateTime.Kind%2A?displayProperty=fullName> sean <xref:System.DateTimeKind> en ambos casos o con dos valores de fecha y hora que tengan valores de propiedad <xref:System.DateTime.Kind%2A?displayProperty=fullName> diferentes refleja la diferencia de la hora que marca el reloj entre los dos valores.  
  
-   Las operaciones aritméticas o comparativas con valores de fecha y hora locales no tienen en cuenta si un valor concreto es ambiguo o no válido, ni tampoco el efecto de ninguna regla de ajuste resultante de la transición de la zona horaria local al horario de verano o de invierno.  
  
-   Cualquier operación que compara o calcula la diferencia entre la hora UTC y una hora local incluye en el resultado un intervalo de tiempo igual a la diferencia de la zona horaria local con respecto a la hora UTC.  
  
-   Cualquier operación que compare o calcule la diferencia entre una hora no especificada y la hora UTC o la hora local refleja simplemente la hora del reloj.  Las diferencias de zonas horarias no se tienen en cuenta y el resultado no refleja la aplicación de reglas de ajuste de la zona horaria.  
  
-   Cualquier operación que compare o calcule la diferencia entre dos horas no especificadas puede incluir un intervalo desconocido que refleje las diferencias horarias en dos zonas horarias diferentes.  
  
 Hay muchos escenarios en los que las diferencias de zona horaria no afectan a los cálculos de fecha y hora \(para obtener una explicación de algunos de ellos, consulte [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md)\) o en los que el contexto de los datos de fecha y hora define el significado de las operaciones comparativas o aritméticas.  
  
## Operaciones comparativas y aritméticas con valores de DateTimeOffset  
 Un valor de <xref:System.DateTimeOffset> incluye no sólo una fecha y hora, sino también una diferencia que define sin ambigüedad esa fecha y hora con respecto a la hora UTC.  Esto permite definir la igualdad de un modo diferente que para los valores de <xref:System.DateTime>.  Mientras que los valores de <xref:System.DateTime> son iguales si tienen el mismo valor de fecha y hora, los valores de <xref:System.DateTimeOffset> son iguales si ambos hacen referencia al mismo punto temporal.  Esto hace que un valor de <xref:System.DateTimeOffset> sea más preciso y su interpretación menos necesaria cuando se utiliza en comparaciones y en la mayoría de las operaciones aritméticas que determinan el intervalo entre dos fechas y horas.  En el ejemplo siguiente, que es el equivalente de <xref:System.DateTimeOffset> al ejemplo anterior en el que se comparaban los valores de <xref:System.DateTime> local y UTC, se muestra esta diferencia de comportamiento.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual3.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual3.vb#3)]  
  
 En este ejemplo, el método <xref:System.DateTimeOffset.CompareTo%2A> indica que la hora local y la hora UTC actuales son iguales, y la resta de los valores de <xref:System.DateTimeOffset> indica que la diferencia entre las dos horas es <xref:System.TimeSpan.Zero?displayProperty=fullName>.  
  
 La limitación principal de utilizar valores de <xref:System.DateTimeOffset> en las operaciones aritméticas con valores de fecha y hora reside en que, si bien los valores de <xref:System.DateTimeOffset> tienen algún conocimiento de la zona horaria, no tienen conocimiento pleno de ella.  Aunque la diferencia del valor de <xref:System.DateTimeOffset> refleja la diferencia de una zona horaria con respecto a la hora UTC cuando se asigna un valor por primera vez a una variable <xref:System.DateTimeOffset>, en lo sucesivo deja de estar asociada a la zona horaria.  Al no seguir estando directamente asociada con una hora identificable, la adición y resta de intervalos de fecha y hora no tiene en cuenta las reglas de ajuste de la zona horaria.  
  
 Para mostrar, la transición al horario de verano en la zona horaria estándar de EE.UU. Central aparece a las 2:00 a.m. el 9 de marzo de 2008.  Esto significa que agregando dos y un intervalo de media hora a una hora estándar Central de 1:30 a.m. el 9 de marzo de 2008, debe generar una fecha y hora de 5:00 a.m. el 9 de marzo de 2008.  Sin embargo, como se muestra en el ejemplo siguiente, el resultado de la suma es 4:00 a.m. el 9 de marzo de 2008.  Tenga en cuenta que este último resultado de la operación sí representa el punto de tiempo correcto, aunque no sea la hora correcta en la zona horaria que nos interesa \(es decir, no tiene la diferencia esperada de la zona horaria\).  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual4.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual4.vb#4)]  
  
## Operaciones aritméticas con horas en zonas horarias  
 La clase <xref:System.TimeZoneInfo> incluye varios métodos de conversión que aplican ajustes automáticamente cuando convierten las horas de una zona horaria en otra.  Entre ellos, se incluyen los siguientes:  
  
-   Los métodos <xref:System.TimeZoneInfo.ConvertTime%2A> y <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>, que convierten las horas entre dos zonas horarias.  
  
-   Los métodos <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A> y <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>, que convierten la hora de una zona horaria concreta en la hora UTC, y viceversa.  
  
 Para obtener información detallada, vea [Convertir horas entre zonas horarias](../../../docs/standard/datetime/converting-between-time-zones.md).  
  
 La clase <xref:System.TimeZoneInfo> no proporciona ningún método que aplique automáticamente reglas de ajuste cuando se realizan operaciones aritméticas con valores de fecha y hora.  Sin embargo, para hacerlo basta con convertir la hora de una zona horaria en la hora UTC, realizar la operación aritmética y, a continuación, volver a convertir la hora UTC en la hora correspondiente de la zona horaria.  Para obtener información detallada, vea [Cómo: Utilizar zonas horarias en aritmética de fecha y hora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md).  
  
 Por ejemplo, el código siguiente es similar al código anterior en el que se sumaban dos horas y media a las 2:00 a.m. el 9 de marzo de 2008.  Sin embargo, como convierte la hora CST en hora UTC antes de realizar la operación aritmética y, a continuación, vuelve a convertir el resultado de la hora UTC en la hora CST, la hora resultante sí refleja la transición de la zona horaria CST al horario de verano.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual5.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual5.vb#5)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Cómo: Utilizar zonas horarias en aritmética de fecha y hora](../../../docs/standard/datetime/use-time-zones-in-arithmetic.md)