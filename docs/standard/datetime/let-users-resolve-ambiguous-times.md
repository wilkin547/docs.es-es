---
title: "C&#243;mo: Permitir que los usuarios resuelvan horas ambiguas | Microsoft Docs"
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
ms.assetid: bca874ee-5b68-4654-8bbd-3711220ef332
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Permitir que los usuarios resuelvan horas ambiguas
Una hora ambigua es aquella que se asigna a más de una hora universal coordinada \(UTC\).  Se produce al retrasar los relojes, como en el cambio de horario de verano a horario estándar.  Para tratar una hora ambigua, puede elegir una de las siguientes acciones:  
  
-   Si la hora ambigua es un elemento de datos especificado por el usuario, puede dejar que el usuario resuelva la ambigüedad.  
  
-   Haga una suposición sobre cómo se asigna la hora a la hora UTC.  Por ejemplo, puede suponer que una hora ambigua siempre se expresa en la hora estándar de la zona horaria.  
  
 En este tema se muestra cómo permitir a un usuario resolver una hora ambigua.  
  
### Para permitir a un usuario resolver una hora ambigua  
  
1.  Obtenga la entrada de fecha y hora del usuario.  
  
2.  Llame al método <xref:System.TimeZoneInfo.IsAmbiguousTime%2A> para determinar si la hora es ambigua.  
  
3.  Si la hora es ambigua, llame al método <xref:System.TimeZoneInfo.GetAmbiguousTimeOffsets%2A> para recuperar una matriz de objetos <xref:System.TimeSpan>.  Cada elemento de la matriz contiene una diferencia respecto a la hora UTC a la que puede ser asignada la hora ambigua.  
  
4.  Permita al usuario seleccionar la diferencia deseada.  
  
5.  Obtenga la fecha y hora UTC restando a la hora local la diferencia seleccionada por el usuario.  
  
6.  Llame al método <xref:System.DateTime.SpecifyKind%2A> `static` \(`Shared` en Visual Basic .NET\) para establecer la propiedad <xref:System.DateTime.Kind%2A> del valor de fecha y hora UTC en <xref:System.DateTimeKind?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente se pide al usuario que escriba un valor de fecha y hora y, si la hora es ambigua, le permite seleccionar la hora UTC a la que se asignará esta hora ambigua.  
  
 [!code-csharp[System.TimeZone2.Concepts#11](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.TimeZone2.Concepts/CS/TimeZone2Concepts.cs#11)]
 [!code-vb[System.TimeZone2.Concepts#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.TimeZone2.Concepts/VB/TimeZone2Concepts.vb#11)]  
  
 El núcleo del código de ejemplo utiliza una matriz de objetos <xref:System.TimeSpan> para indicar las posibles diferencias de la hora ambigua respecto a la hora UTC.  Sin embargo, probablemente estas diferencias no resultan significativas para el usuario.  Para aclarar el significado de las diferencias, el código también indica si una diferencia representa la hora estándar de la zona horaria local o del horario de verano.  El código determina qué hora es la estándar y cuál pertenece al horario de verano comparando la diferencia con el valor de la propiedad <xref:System.TimeZoneInfo.BaseUtcOffset%2A>.  Esta propiedad indica la diferencia entre la hora UTC y la hora estándar de la zona horaria.  
  
 En este ejemplo, todas las referencias a la zona horaria local se realizan a través de la propiedad <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>; la zona horaria local nunca se asigna a una variable de objeto.  Este es un procedimiento recomendado porque una llamada al método <xref:System.TimeZoneInfo.ClearCachedData%2A?displayProperty=fullName> invalida todos los objetos a los que la zona horaria local está asignada.  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Que se agregue al proyecto una referencia a System.Core.dll.  
  
-   Que se importe el espacio de nombres <xref:System> con la instrucción `using` \(necesaria en código de C\#\).  
  
## Vea también  
 [Fechas, horas y zonas horarias](../../../docs/standard/datetime/index.md)   
 [Cómo: Resolver horas ambiguas](../../../docs/standard/datetime/resolve-ambiguous-times.md)