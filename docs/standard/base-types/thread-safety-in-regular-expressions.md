---
title: "Seguridad para subprocesos en expresiones regulares | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "expresiones regulares de .NET Framework, subprocesos"
  - "analizar texto con expresiones regulares, subprocesos"
  - "coincidencia de patrones con expresiones regulares, subprocesos"
  - "expresiones regulares, subprocesos"
  - "buscar con expresiones regulares, subprocesos"
ms.assetid: 7c4a167b-5236-4cde-a2ca-58646230730f
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Seguridad para subprocesos en expresiones regulares
La clase <xref:System.Text.RegularExpressions.Regex> en sí es segura para la ejecución de subprocesos e inmutable \(de sólo lectura\).  Es decir, se pueden crear objetos **Regex** en un subproceso cualquiera y pueden compartirse entre varios subprocesos; se puede llamar a los métodos de búsqueda de coincidencias desde un subproceso cualquiera, y no modificar nunca ningún estado global.  
  
 No obstante, los objetos de resultados \(**Match** y **MatchCollection**\) devueltos por **Regex** deben utilizarse en un único subproceso.  Aunque muchos de estos objetos son lógicamente inmutables, sus implementaciones pueden retrasar el cálculo de algunos resultados para mejorar el rendimiento y, en consecuencia, los llamadores deberán serializar el acceso a ellos.  
  
 Si es necesario que varios subprocesos compartan los objetos de resultados de **Regex**, estos objetos pueden convertirse en instancias seguras para la ejecución de subprocesos llamando a sus métodos sincronizados.  A excepción de los enumeradores, todas las clases de expresiones regulares son seguras para la ejecución de subprocesos o pueden convertirse en objetos seguros para la ejecución de subprocesos mediante un método sincronizado.  
  
 Los enumeradores son la única excepción.  Una aplicación debe serializar las llamadas a enumeradores de colecciones.  La regla establece que si una colección puede enumerarse simultáneamente en más de un subproceso, los métodos de los enumeradores deben sincronizarse en el objeto raíz de la colección que recorre el enumerador.  
  
## Vea también  
 [Expresiones regulares de .NET Framework](../../../docs/standard/base-types/regular-expressions.md)