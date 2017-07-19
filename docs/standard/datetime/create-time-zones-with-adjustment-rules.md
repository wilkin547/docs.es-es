---
title: "C&#243;mo: Crear zonas horarias con reglas de ajuste | Microsoft Docs"
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
  - "regla de ajuste [.NET Framework]"
  - "zonas horarias [.NET Framework], y reglas de ajuste"
  - "zonas horarias [.NET Framework], crear"
ms.assetid: c52ef192-13a9-435f-8015-3b12eae8c47c
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear zonas horarias con reglas de ajuste
La información precisa sobre zonas horarias que necesita una aplicación podría no encontrarse en un sistema concreto por varios motivos:  
  
-   La zona horaria nunca se ha definido en el Registro del sistema local.  
  
-   Se han modificado datos sobre la zona horaria o se han quitado del Registro.  
  
-   La zona horaria no tiene información precisa sobre los ajustes de la zona horaria para un período histórico determinado.  
  
 En estos casos, puede llamar al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> para definir la zona horaria que su aplicación necesita.  Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste.  Si la zona horaria admite el horario de verano, puede definir los ajustes con reglas de ajuste fijas o flotantes. \(Para obtener las definiciones de estos términos, vea la sección "Terminología de zonas horarias" en [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)\).  
  
> [!IMPORTANT]
>  Las zonas horarias personalizadas creadas con una llamada al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> no se agregan al Registro.  Sólo se puede tener acceso a ellas mediante la referencia de objeto devuelta por la llamada al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  
  
 En este tema se muestra cómo crear una zona horaria con reglas de ajuste.  Para crear una zona horaria que no admita las reglas de ajuste del horario de verano, vea [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md).  
  
### Para crear una zona horaria con reglas de ajuste flotantes  
  
1.  Para cada ajuste \(es decir, para cada cambio de horario de verano en un intervalo de tiempo determinado\), haga lo siguiente:  
  
    1.  Defina la hora de comienzo del cambio para el ajuste de la zona horaria.  
  
         Debe llamar al método <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName> y pasarle un valor <xref:System.DateTime> que defina la hora del cambio, un valor entero que defina el mes del cambio, un valor entero que defina la semana en que se produce el cambio y un valor de <xref:System.DayOfWeek> que defina el día de la semana en que se produce el cambio.  Esta llamada al método crea instancias de un objeto <xref:System.TimeZoneInfo.TransitionTime>.  
  
    2.  Defina la hora de finalización del cambio para el ajuste de la zona horaria.  Esto requiere otra llamada al método <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A?displayProperty=fullName>.  Esta llamada al método crea instancias de un segundo objeto <xref:System.TimeZoneInfo.TransitionTime>.  
  
    3.  Llame al método <xref:System.TimeZoneInfo.AdjustmentRule.CreateAdjustmentRule%2A> y pásele las fechas efectivas de inicio y finalización del ajuste, un objeto <xref:System.TimeSpan> que define la cantidad de tiempo del cambio, y los dos objetos <xref:System.TimeZoneInfo.TransitionTime> que definen cuándo se producen los cambios del horario de verano.  Esta llamada al método crea instancias de un objeto <xref:System.TimeZoneInfo.AdjustmentRule>.  
  
    4.  Asigne el objeto <xref:System.TimeZoneInfo.AdjustmentRule> a una matriz de objetos <xref:System.TimeZoneInfo.AdjustmentRule>  
  
2.  Defina el nombre para mostrar de la zona horaria.  El nombre para mostrar sigue un formato estándar: la diferencia de la zona horaria respecto a la hora universal coordinada \(UTC\) se incluye entre paréntesis y le sigue una cadena que identifica la zona horaria, una o varias ciudades de la zona horaria, o uno o varios países o regiones de la zona horaria.  
  
3.  Defina el nombre de la hora estándar de la zona horaria.  Normalmente, esta cadena también se utiliza como identificador de la zona horaria.  
  
4.  Defina el nombre del horario de verano de la zona horaria.  
  
5.  Si desea utilizar un identificador diferente que el nombre estándar de la zona horaria, defina el identificador de zona horaria.  
  
6.  Cree instancias de un objeto <xref:System.TimeSpan> que define la diferencia de la zona horaria respecto a la hora UTC.  Las zonas con horas posteriores a la hora UTC tienen una diferencia positiva.  Las zonas con horas anteriores a la hora UTC tienen una diferencia negativa.  
  
7.  Llame al método [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName> para crear instancias de la nueva zona horaria.  
  
## Ejemplo  
 En el ejemplo siguiente se define una zona Hora estándar del Centro para Estados Unidos que incluye reglas de ajuste para diferentes intervalos de tiempo desde 1918 hasta el momento presente.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#5)]
 [!code-vb[System.TimeZone2.CreateTimeZone#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#5)]  
  
 La zona horaria creada en este ejemplo tiene varias reglas de ajuste.  Hay que prestar atención para asegurarse de que las fechas efectivas de inicio y finalización de las reglas de ajuste no se superpongan con las fechas de otra regla de ajuste.  Si hay una superposición, se produce una excepción <xref:System.InvalidTimeZoneException>.  
  
 Para las reglas de ajuste flotantes, se pasa el valor 5 al parámetro `week` del método <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A> para indicar que el cambio se produce en la última semana de un mes determinado.  
  
 Al crear la matriz de objetos <xref:System.TimeZoneInfo.AdjustmentRule> para utilizar en la llamada al método [TimeZoneInfo.CreateCustomTimeZone\(String, TimeSpan, String, String, String, TimeZoneInfo.AdjustmentRule\<xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%2CSystem.String%2CSystem.TimeZoneInfo.AdjustmentRule%5B%5D%29?displayProperty=fullName>, el código podría inicializar la matriz al tamaño requerido por el número de ajustes que se va a crear para la zona horaria.  En su lugar, este ejemplo de código llama al método <xref:System.Collections.Generic.List%601.Add%2A> para agregar cada regla de ajuste a una colección <xref:System.Collections.Generic.List%601> genérica de objetos <xref:System.TimeZoneInfo.AdjustmentRule>.  Después. el código llama al método <xref:System.Collections.Generic.List%601.CopyTo%2A> para copiar los miembros de esta colección en la matriz.  
  
 En el ejemplo también se utiliza el método <xref:System.TimeZoneInfo.TransitionTime.CreateFixedDateRule%2A> para definir ajustes de fecha fijos.  Esto es similar a llamar al método <xref:System.TimeZoneInfo.TransitionTime.CreateFloatingDateRule%2A>, salvo que solo se requiere la hora, el mes y el día de los parámetros de cambio.  
  
 El ejemplo se puede probar utilizando un código como el siguiente:  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#7)]
 [!code-vb[System.TimeZone2.CreateTimeZone#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#7)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importen los siguientes espacios de nombres:  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)   
 [Cómo: Crear zonas horarias sin reglas de ajuste](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md)