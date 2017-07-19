---
title: "C&#243;mo: Resolver horas ambiguas | Microsoft Docs"
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
  - "hora ambigua [.NET Framework]"
  - "zonas horarias [.NET Framework], hora ambigua"
ms.assetid: 2cf5fb25-492c-4875-9245-98cac8348e97
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Resolver horas ambiguas
Una hora ambigua es aquella que se asigna a más de una hora universal coordinada \(UTC\).  Se produce al retrasar los relojes, como en el cambio de horario de verano a horario estándar.  Para tratar una hora ambigua, puede elegir una de las siguientes acciones:  
  
-   Haga una suposición sobre cómo se asigna la hora a la hora UTC.  Por ejemplo, puede suponer que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.  
  
-   Si la hora ambigua es un elemento de datos especificado por el usuario, puede dejar que el usuario resuelva la ambigüedad.  
  
 En este tema se muestra cómo resolver una hora ambigua suponiendo que representa la hora estándar de la zona horaria.  
  
### Para asignar una hora ambigua a una hora estándar de la zona horaria  
  
1.  Llame al método <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> para determinar si la hora es ambigua.  
  
2.  Si la hora es ambigua, reste la hora del objeto <xref:System.TimeSpan> devuelto por la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria.  
  
3.  Llame al método `static` \(`Shared` en Visual Basic .NET\) <xref:System.DateTime.SpecifyKind%2A> para establecer la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora UTC en <xref:System.DateTimeKind?displayProperty=fullName>.  
  
## Ejemplo  
 El ejemplo siguiente muestra cómo convertir una hora ambigua en una hora UTC suponiendo que representa la hora estándar de la zona horaria local.  
  
 [!code-csharp[System.TimeZone2.Concepts#10](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#10)]
 [!code-vb[System.TimeZone2.Concepts#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#10)]  
  
 El ejemplo está compuesto por un método denominado `ResolveAmbiguousTime`, que determina si el valor de <xref:System.DateTime> que se le ha pasado es ambiguo.  Si el valor es ambiguo, el método devuelve un valor de <xref:System.DateTime> que representa la hora UTC correspondiente.  El método trata esta conversión restando a la hora local el valor de la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> de la zona horaria local.  
  
 Normalmente, una hora ambigua se trata llamando al método <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> para recuperar una matriz de objetos <xref:System.TimeSpan> que contienen la posible diferencia de la hora ambigua respecto a la hora UTC.  Sin embargo, en este ejemplo se supone que una hora ambigua siempre se debe asignar a la hora estándar de la zona horaria.  La propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A> devuelve la diferencia entre la hora UTC y la hora estándar de la zona horaria.  
  
 En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>; la zona horaria local nunca se asigna a una variable de objeto.  Este es un procedimiento recomendado porque una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName> invalida todos los objetos a los que la zona horaria local está asignada.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importe el espacio de nombres <xref:System> con la instrucción `using` \(necesaria en código de C\#\).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Cómo: Permitir que los usuarios resuelvan horas ambiguas](../../../docs/standard/datetime/let-users-resolve-ambiguous-times.md)