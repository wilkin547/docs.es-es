---
title: Seguridad para subprocesos en expresiones regulares
description: Seguridad para subprocesos en expresiones regulares
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 07/28/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: dc64b681-b3aa-4911-8e30-0764a8b6a852
translationtype: Human Translation
ms.sourcegitcommit: fb00da6505c9edb6a49d2003ae9bcb8e74c11d6c
ms.openlocfilehash: ab71ad5ff9148f00f392fddd3c89acbcab874015

---

# <a name="thread-safety-in-regular-expressions"></a>Seguridad para subprocesos en expresiones regulares

La clase [Regex](xref:System.Text.RegularExpressions.Regex) es en sí misma segura para subprocesos e inmutable (de solo lectura). Es decir, se pueden crear objetos [Regex](xref:System.Text.RegularExpressions.Regex) en cualquier subproceso y compartirlos entre varios subprocesos; los métodos de coincidencia pueden llamarse desde cualquier subproceso y no modifican nunca el estado global.

Pero los objetos de resultado ([Match](xref:System.Text.RegularExpressions.Match) y [MatchCollection)](xref:System.Text.RegularExpressions.MatchCollection) que devuelve [Regex](xref:System.Text.RegularExpressions.Regex) deben usarse en un único subproceso. Aunque muchos de estos objetos son lógicamente inmutables, sus implementaciones pueden retrasar el cálculo de algunos resultados para mejorar el rendimiento y, en consecuencia, los llamadores deben serializar el acceso a ellos.

Si es necesario compartir objetos de resultado de [Regex](xref:System.Text.RegularExpressions.Regex) en varios subprocesos, estos objetos se pueden convertir en instancias seguras para subprocesos llamando a sus métodos sincronizados. A excepción de los enumeradores, todas las clases de expresiones regulares son seguras para subprocesos o pueden convertirse en objetos seguros para subprocesos mediante un método sincronizado.

Los enumeradores son la única excepción. Las aplicaciones debe serializar las llamadas a enumeradores de colecciones. La regla es que, si una colección puede enumerarse simultáneamente en más de un subproceso, se deben sincronizar los métodos de enumerador en el objeto raíz de la colección que recorre el enumerador.

## <a name="see-also"></a>Vea también

[Expresiones regulares de .NET](regular-expressions.md)




<!--HONumber=Nov16_HO3-->


