---
title: "C&#243;mo: Crear zonas horarias sin reglas de ajuste | Microsoft Docs"
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
  - "zonas horarias [.NET Framework], regla de ajuste"
  - "zonas horarias [.NET Framework], crear"
ms.assetid: a6af8647-7893-4f29-95a9-d94c65a6e8dd
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear zonas horarias sin reglas de ajuste
La información precisa sobre zonas horarias que necesita una aplicación podría no encontrarse en un sistema concreto por varios motivos:  
  
-   La zona horaria nunca se ha definido en el Registro del sistema local.  
  
-   Se han modificado datos sobre la zona horaria o se han quitado del Registro.  
  
-   La zona horaria existe pero no tiene información precisa sobre los ajustes de la zona horaria para un período histórico determinado.  
  
 En estos casos, puede llamar al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> para definir la zona horaria que su aplicación necesita.  Puede utilizar las sobrecargas de este método para crear una zona horaria con o sin reglas de ajuste.  Si la zona horaria admite el horario de verano, puede definir los ajustes con reglas de ajuste fijas o flotantes. \(Para obtener las definiciones de estos términos, vea la sección "Terminología de zonas horarias" en [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)\).  
  
> [!IMPORTANT]
>  Las zonas horarias personalizadas creadas con una llamada al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> no se agregan al Registro.  Sólo se puede tener acceso a ellas mediante la referencia de objeto devuelta por la llamada al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A>.  
  
 En este tema se muestra cómo crear una zona horaria sin reglas de ajuste.  Para crear una zona horaria que admita las reglas de ajuste del horario de verano, vea [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md).  
  
### Para crear una zona horaria sin reglas de ajuste  
  
1.  Defina el nombre para mostrar de la zona horaria.  
  
     El nombre para mostrar sigue un formato estándar: la diferencia de la zona horaria respecto a la hora universal coordinada \(UTC\) se incluye entre paréntesis y le sigue una cadena que identifica la zona horaria, una o varias ciudades de la zona horaria, o uno o varios países o regiones de la zona horaria.  
  
2.  Defina el nombre de la hora estándar de la zona horaria.  Normalmente, esta cadena también se utiliza como identificador de la zona horaria.  
  
3.  Si desea utilizar un identificador diferente que el nombre estándar de la zona horaria, defina el identificador de zona horaria.  
  
4.  Cree instancias de un objeto <xref:System.TimeSpan> que define la diferencia de la zona horaria respecto a la hora UTC.  Las zonas con horas posteriores a la hora UTC tienen una diferencia positiva.  Las zonas con horas anteriores a la hora UTC tienen una diferencia negativa.  
  
5.  Llame al método <xref:System.TimeZoneInfo.CreateCustomTimeZone%28System.String%2CSystem.TimeSpan%2CSystem.String%2CSystem.String%29?displayProperty=fullName> para crear instancias de la nueva zona horaria.  
  
## Ejemplo  
 En el ejemplo siguiente se define una zona horaria personalizada para Mawson, Antártida, que no tiene ninguna regla de ajuste.  
  
 [!code-csharp[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#1)]
 [!code-vb[System.TimeZone2.CreateTimeZone#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#1)]  
  
 La cadena asignada a la propiedad <xref:System.TimeZoneInfo.DisplayName%2A> sigue un formato estándar en el que la diferencia respecto a la hora UTC va seguida de una descripción breve y fácil de comprender de la zona horaria.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importen los siguientes espacios de nombres:  
  
     [!code-csharp[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/cs/System.TimeZone2.CreateTimeZone.cs#6)]
     [!code-vb[System.TimeZone2.CreateTimeZone#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.CreateTimeZone/vb/System.TimeZone2.CreateTimeZone.vb#6)]  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Información general sobre zonas horarias](../../../docs/standard/datetime/time-zone-overview.md)   
 [Cómo: Crear zonas horarias con reglas de ajuste](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)