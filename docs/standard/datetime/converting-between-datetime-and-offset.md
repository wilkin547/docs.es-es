---
title: "Convertir entre DateTime y DateTimeOffset | Microsoft Docs"
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
  - "convertir valores de DateTimeOffset y DateTime"
  - "convertir horas"
  - "Date (tipo de datos), convertir"
  - "fechas [.NET Framework], convertir"
  - "DateTime (estructura), convertir"
  - "DateTimeOffset (estructura), convertir"
  - "conversiones de hora local"
  - "zonas horarias [.NET Framework], conversiones"
  - "horas UTC, convertir"
ms.assetid: b605ff97-0c45-4c24-833f-4c6a3e8be64c
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Convertir entre DateTime y DateTimeOffset
Aunque la estructura de <xref:System.DateTimeOffset> permite un grado mayor de reconocimiento de la zona horaria que la estructura <xref:System.DateTime>, los parámetros <xref:System.DateTime> se utilizan con más frecuencia en llamadas a métodos.  Por este motivo, la capacidad para convertir valores <xref:System.DateTimeOffset> en valores <xref:System.DateTime> y viceversa es especialmente importante.  En este tema se muestra cómo realizar estas conversiones de manera que se conserve toda la información posible de la zona horaria.  
  
> [!NOTE]
>  Los tipos <xref:System.DateTime> y <xref:System.DateTimeOffset> tienen algunas limitaciones para representar las horas de las zonas horarias.  Con su propiedad <xref:System.DateTime.Kind%2A>, <xref:System.DateTime>, solo puede reflejar la hora universal coordinada \(UTC\) y la zona horaria local del sistema.  <xref:System.DateTimeOffset> refleja la diferencia horaria respecto a la hora UTC, pero no refleja la zona horaria real a la que pertenece esa diferencia horaria.  Para obtener información detallada acerca de los valores de tiempo y la compatibilidad para zonas horarias, vea [Elegir entre DateTime, DateTimeOffset, TimeSpan y TimeZoneInfo](../../../docs/standard/datetime/choosing-between-datetime.md).  
  
## Conversiones de DateTime a DateTimeOffset  
 La estructura <xref:System.DateTimeOffset> ofrece dos maneras equivalentes de realizar conversiones de <xref:System.DateTime> a <xref:System.DateTimeOffset> apropiadas para la mayoría de las conversiones:  
  
-   El constructor <xref:System.DateTimeOffset.%23ctor%2A>, que crea un nuevo objeto <xref:System.DateTimeOffset> basado en un valor <xref:System.DateTime>.  
  
-   El operador de conversión implícito, que permite asignar un valor <xref:System.DateTime> a un objeto <xref:System.DateTimeOffset>.  
  
 Para los valores <xref:System.DateTime> UTC y locales, la propiedad <xref:System.DateTimeOffset.Offset%2A> del valor <xref:System.DateTimeOffset> resultante refleja con precisión la hora UTC o la diferencia horaria de la zona horaria local.  Por ejemplo, el código siguiente convierte una hora UTC en su valor <xref:System.DateTimeOffset> equivalente.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#1)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#1)]  
  
 En este caso, la diferencia horaria de la variable `utcTime2` es 00:00.  De igual forma, el código siguiente convierte una hora local en su valor <xref:System.DateTimeOffset> equivalente.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#2)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#2)]  
  
 Sin embargo, para los valores <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind?displayProperty=fullName>, estos dos métodos de conversión generan un valor <xref:System.DateTimeOffset> cuya diferencia horaria es la de la zona horaria local.  Esto se muestra en el siguiente ejemplo, que se ejecuta en la zona horaria estándar del Pacífico de EE.UU.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#3)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#3)]  
  
 Si el valor <xref:System.DateTime> refleja una fecha y hora que no corresponde a la zona horaria local ni a la hora UTC, puede convertirlo en un valor <xref:System.DateTimeOffset> y conservar la información de su zona horaria llamando al constructor <xref:System.DateTimeOffset.%23ctor%2A> sobrecargado.  El ejemplo siguiente crea instancias de un objeto <xref:System.DateTimeOffset> que refleja el horario central estándar.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#4)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#4)]  
  
 El segundo parámetro de esta sobrecarga del constructor, un objeto <xref:System.TimeSpan> que representa la diferencia horaria respecto a UTC, debería recuperarse mediante una llamada al método <xref:System.TimeZoneInfo.GetUtcOffset%28System.DateTime%29?displayProperty=fullName> de la zona horaria correspondiente a la hora.  El único parámetro del método es el valor <xref:System.DateTime> que representa la fecha y hora que se va a convertir.  Si la zona horaria admite el horario de verano, este parámetro permite al método determinar la diferencia horaria adecuada para esa fecha y hora concreta.  
  
## Conversiones de DateTimeOffset a DateTime  
 La propiedad <xref:System.DateTimeOffset.DateTime%2A> se utiliza más habitualmente para realizar la conversión de <xref:System.DateTimeOffset> a <xref:System.DateTime>.  Sin embargo, devuelve un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind>, como muestra el ejemplo siguiente.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#5)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#5)]  
  
 Esto significa que la conversión pierde toda la información sobre la relación del valor <xref:System.DateTimeOffset> con la hora UTC cuando se utiliza la propiedad <xref:System.DateTimeOffset.DateTime%2A>.  Esto afecta a los valores <xref:System.DateTimeOffset> que corresponden a la hora UTC o a la hora local del sistema porque la estructura <xref:System.DateTimeOffset.DateTime%2A> sólo refleja esas dos zonas horarias en su propiedad <xref:System.DateTime.Kind%2A>.  
  
 Para conservar toda la información posible acerca de la zona horaria al convertir un valor <xref:System.DateTimeOffset> en un valor <xref:System.DateTime>, puede utilizar las propiedades <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> y <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>.  
  
### Convertir una hora UTC  
 Para indicar que un valor <xref:System.DateTimeOffset.DateTime%2A> convertido es la hora UTC, puede recuperar el valor de la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName>.  Difiere de la propiedad <xref:System.DateTimeOffset.DateTime%2A> en dos aspectos:  
  
-   Devuelve un valor <xref:System.DateTime> cuya propiedad <xref:System.DateTime.Kind%2A> es <xref:System.DateTimeKind>.  
  
-   Si el valor de propiedad <xref:System.DateTimeOffset.Offset%2A> no es igual a <xref:System.TimeSpan.Zero?displayProperty=fullName>, convierte la hora en hora UTC.  
  
> [!NOTE]
>  Si su aplicación requiere que los valores <xref:System.DateTime> convertidos identifiquen inequívocamente un único punto del tiempo, debería considerar la utilización de la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A?displayProperty=fullName> para administrar todas las conversiones de <xref:System.DateTimeOffset> a <xref:System.DateTime>.  
  
 El código siguiente utiliza la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A> para convertir un valor <xref:System.DateTimeOffset>, cuya diferencia horaria es igual a <xref:System.TimeSpan.Zero?displayProperty=fullName>, en un valor <xref:System.DateTime>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#6)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#6)]  
  
 El código siguiente utiliza la propiedad <xref:System.DateTimeOffset.UtcDateTime%2A> para realizar una conversión de la zona horaria y una conversión de tipos en un valor <xref:System.DateTimeOffset>.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#12)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#12)]  
  
### Convertir una hora local  
 Para indicar que un valor <xref:System.DateTimeOffset> representa la hora local, puede pasar el valor <xref:System.DateTime> devuelto por la propiedad <xref:System.DateTimeOffset.DateTime%2A?displayProperty=fullName> \(`Shared` en Visual Basic\) al método `static` <xref:System.DateTime.SpecifyKind%2A>.  El método devuelve la fecha y la hora que le pasaron como su primer parámetro, pero establece la propiedad <xref:System.DateTime.Kind%2A> en el valor especificado por su segundo parámetro.  El código siguiente utiliza el método <xref:System.DateTime.SpecifyKind%2A> para convertir un valor <xref:System.DateTimeOffset> cuya diferencia horaria es la de la zona horaria local.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#7)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#7)]  
  
 También puede utilizar la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> para convertir un valor <xref:System.DateTimeOffset> en un valor <xref:System.DateTime> local.  La propiedad <xref:System.DateTime.Kind%2A> del valor <xref:System.DateTime> devuelto es <xref:System.DateTimeKind>.  El código siguiente utiliza la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> para convertir un valor <xref:System.DateTimeOffset> cuya diferencia horaria es la de la zona horaria local.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#10)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#10)]  
  
 Cuando se recupera un valor <xref:System.DateTime> mediante la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName>, el descriptor de acceso `get` de la propiedad convierte primero el valor <xref:System.DateTimeOffset> en una hora UTC; a continuación, lo convierte en una hora local mediante una llamada al método <xref:System.DateTimeOffset.ToLocalTime%2A>.  Esto significa que puede recuperar un valor de la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> para realizar una conversión de la zona horaria al mismo tiempo que realiza una conversión de tipos.  También significa que se aplicarán las reglas de ajuste de la zona horaria local para realizar la conversión.  El código siguiente muestra el uso de la propiedad <xref:System.DateTimeOffset.LocalDateTime%2A?displayProperty=fullName> para realizar una conversión de tipos y de zona horaria.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#11)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#11)]  
  
### Método general de conversión  
 El ejemplo siguiente define un método denominado `ConvertFromDateTimeOffset` que convierte valores <xref:System.DateTimeOffset> en valores <xref:System.DateTime>.  En función de la diferencia horaria, determina si el valor <xref:System.DateTimeOffset> es una hora UTC, una hora local u otra hora, y define la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora devuelto.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#8)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#8)]  
  
 El siguiente ejemplo llama al método de `ConvertFromDateTimeOffset` para convertir los valores de <xref:System.DateTimeOffset> que representan una hora UTC, una hora local, y una hora de la zona horaria del estándar de EE.UU. Central.  
  
 [!code-csharp[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/cs/Conversions.cs#9)]
 [!code-vb[System.DateTimeOffset.Conceptual.Conversions#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTimeOffset.Conceptual.Conversions/vb/Conversions.vb#9)]  
  
 Observe que este código hace dos suposiciones que, en función de la aplicación y del origen de sus valores de fecha y hora, podrían no ser siempre válidas:  
  
-   Supone que un valor de fecha y hora cuya diferencia horaria es <xref:System.TimeSpan.Zero?displayProperty=fullName>, representa una hora UTC.  De hecho, la hora UTC no es una hora de una zona horaria determinada, sino la hora respecto a la cual se normalizan las horas de las zonas horarias del mundo.  Las zonas horarias también pueden tener una diferencia horaria de <xref:System.TimeSpan.Zero>.  
  
-   Supone que una fecha y hora, cuya diferencia horaria es la de la zona horaria local, representa la zona horaria local.  Debido a que los valores de fecha y hora no está asociados a su zona horaria original, esto no podría darse; la fecha y hora puede haberse originado en otra zona horaria con la misma diferencia horaria.  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)