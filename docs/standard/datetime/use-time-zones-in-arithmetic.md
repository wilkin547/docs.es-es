---
title: "C&#243;mo: Utilizar zonas horarias en aritm&#233;tica de fecha y hora | Microsoft Docs"
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
  - "fechas [.NET Framework], agregar y sustraer"
  - "zonas horarias [.NET Framework], operaciones aritméticas"
ms.assetid: 83dd898d-1338-415d-8cd6-445377ab7871
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Utilizar zonas horarias en aritm&#233;tica de fecha y hora
Normalmente, cuando se realizan operaciones aritméticas de fecha y hora mediante valores <xref:System.DateTime> o <xref:System.DateTimeOffset>, el resultado no refleja las reglas de ajuste de la zona horaria.  Esto es así incluso cuando la zona horaria del valor de fecha y hora es claramente identificable \(por ejemplo, cuando la propiedad <xref:System.DateTime.Kind%2A> está establecida en <xref:System.DateTimeKind>\).  En este tema se muestra cómo realizar operaciones aritméticas en valores de fecha y hora que pertenecen a una zona horaria determinada.  Los resultados de las operaciones aritméticas reflejarán las reglas de ajuste de la zona horaria.  
  
### Para aplicar reglas de ajuste a operaciones aritméticas de fecha y hora  
  
1.  Implemente algún método para relacionar un valor de fecha y hora con la zona horaria a la que pertenece.  Por ejemplo, declare una estructura que incluya los valores de fecha y hora y su zona horaria.  En el ejemplo siguiente se utiliza este enfoque para vincular un valor de <xref:System.DateTime> con su zona horaria.  
  
     [!code-csharp[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#6)]
     [!code-vb[System.DateTimeOffset.Conceptual#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#6)]  
  
2.  Convierta una hora en hora UTC mediante una llamada a los métodos <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A> o <xref:System.TimeZoneInfo.ConvertTime%2A>.  
  
3.  Realice la operación aritmética en la hora UTC.  
  
4.  Convierta la hora UTC a la zona horaria asociada a la hora original mediante una llamada al método <xref:System.TimeZoneInfo.ConvertTime%28System.DateTime%2CSystem.TimeZoneInfo%29?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente se agregan dos horas y treinta minutos al 9 de marzo de 2008, a la 1:30 a.m. horario central estándar.  La transición de la zona horaria al horario de verano produce treinta minutos después, a las 2:00 a.m. el 9 de marzo de 2008.  Dado que el ejemplo se siguen los cuatro pasos enumerados en la sección anterior, se notifica correctamente la hora resultante como 5:00 a.m. el 9 de marzo de 2008.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual8.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual8.vb#8)]  
  
 Los valores de <xref:System.DateTime> y <xref:System.DateTimeOffset> están disociados de cualquier zona horaria a la que pudieran pertenecer.  Para realizar operaciones aritméticas de fecha y hora de manera que apliquen automáticamente reglas de ajuste de una zona horaria, la zona horaria a la que pertenece cualquier valor de fecha y hora debe ser identificable de forma inmediata.  Esto significa que se debe relacionar estrechamente un valor de fecha y hora con su zona horaria asociada.  Hay varias maneras de hacerlo, entre ellas:  
  
-   Suponer que todas las horas utilizadas en una aplicación pertenecen a una zona horaria determinada.  Aunque es adecuado en algunos casos, este enfoque es poco flexible y es posible que limite la portabilidad.  
  
-   Definir un tipo que relacione estrechamente un valor de fecha y hora con su zona horaria asociada, incluyendo ambos como campos del tipo.  Este es el enfoque utilizado en el código de ejemplo, que define una estructura para almacenar el valor de fecha y hora y la zona horaria en dos campos de miembro.  
  
 En el ejemplo se muestra cómo realizar operaciones aritméticas en valores de <xref:System.DateTime> para aplicar las reglas de ajuste de la zona horaria al resultado.  Sin embargo, los valores de <xref:System.DateTimeOffset> se pueden usar fácilmente.  En el ejemplo siguiente se muestra cómo el código del ejemplo original puede adaptarse para utilizar <xref:System.DateTimeOffset> en lugar de valores de <xref:System.DateTime>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/cs/Conceptual6.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual/vb/Conceptual6.vb#7)]  
  
 Tenga en cuenta que si esta suma se realiza simplemente en el valor de <xref:System.DateTimeOffset> sin convertirlo primero a hora UTC, el resultado reflejará el punto en el tiempo correcto pero su diferencia no reflejará la de la zona horaria designada para esa hora.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importe el espacio de nombres <xref:System> con la instrucción `using` \(necesaria en código de C\#\).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Efectuar operaciones aritméticas con fechas y horas](../../../docs/standard/datetime/performing-arithmetic-operations.md)