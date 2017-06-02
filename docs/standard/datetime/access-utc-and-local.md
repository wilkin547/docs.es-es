---
title: "C&#243;mo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos | Microsoft Docs"
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
  - "acceso a zona horaria local"
  - "zonas horarias predefinidas"
  - "zonas horarias [.NET Framework], locales"
  - "zonas horarias [.NET Framework], recuperar"
  - "zonas horarias [.NET Framework], UTC"
  - "horas UTC, predefinidos"
ms.assetid: 961fb70b-83f0-4dab-a042-cb5fcd817cf5
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Obtener acceso a los objetos de zona horaria local y UTC predefinidos
La clase <xref:System.TimeZoneInfo> proporciona dos propiedades, <xref:System.TimeZoneInfo.Utc%2A> y <xref:System.TimeZoneInfo.Local%2A>, que dan al código acceso a los objetos de zona horaria predefinidos.  En este tema se explica cómo obtener acceso a los objetos <xref:System.TimeZoneInfo> devueltos por esas propiedades.  
  
### Para obtener acceso al objeto TimeZoneInfo de la hora universal coordinada \(UTC\)  
  
1.  Utilice la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> `static` \(`Shared` en Visual Basic\) para obtener acceso a la hora universal coordinada.  
  
2.  En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, continúe obteniendo acceso a la hora universal coordinada a través de la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName>.  
  
### Para obtener acceso a la zona horaria local  
  
1.  Utilice la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> `static` \(`Shared` en Visual Basic\) para obtener acceso a la zona horaria del sistema local.  
  
2.  En lugar de asignar el objeto <xref:System.TimeZoneInfo> devuelto por la propiedad a una variable de objeto, continúe obteniendo acceso a la zona horaria local a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>.  
  
## Ejemplo  
 El código siguiente utiliza las propiedades de <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> y de <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> para convertir una hora de EE.UU. y la zona horaria estándar de canadá, y para mostrar el nombre de la zona horaria en la consola.  
  
 [!code-csharp[System.TimeZone2.Concepts#13](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#13)]
 [!code-vb[System.TimeZone2.Concepts#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#13)]  
  
 Siempre debe obtener acceso a la zona horaria local mediante la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName> en lugar de asignar la zona horaria local a una variable de objeto <xref:System.TimeZoneInfo>.  De igual manera, siempre debe obtener acceso a la hora universal coordinada mediante la propiedad <xref:System.TimeZoneInfo.Utc%2A?displayProperty=fullName> en lugar de asignar la zona UTC a una variable de objeto <xref:System.TimeZoneInfo>.  Así se evita que la variable de objeto <xref:System.TimeZoneInfo> quede invalidada por una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName>.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importe el espacio de nombres <xref:System> con la instrucción `using` \(necesaria en código de C\#\).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Buscar las zonas horarias definidas en un sistema local](../../../docs/standard/datetime/finding-the-time-zones-on-local-system.md)   
 [Cómo: Crear instancias de un objeto TimeZoneInfo](../../../docs/standard/datetime/instantiate-time-zone-info.md)