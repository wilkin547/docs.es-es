---
title: Recolecciones inducidas
description: Recolecciones inducidas
keywords: .NET, .NET Core
author: stevehoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3e09b9dd-a800-4e56-b468-619f910ae22e
translationtype: Human Translation
ms.sourcegitcommit: 213ce098bcc2b5e31c55e759d895254d5ca33caa
ms.openlocfilehash: a10822518f0687dc7bbb06dd0fb77f6d9a3196fb

---

# <a name="induced-collections"></a>Recolecciones inducidas

En la mayoría de los casos, el recolector de elementos no utilizados puede determinar cuál es el mejor momento para realizar una recolección y se debe permitir su ejecución de forma independiente. Hay ocasiones excepcionales en que una recolección forzada puede mejorar el rendimiento de la aplicación. En estos casos, se puede inducir la recolección de elementos no utilizados usando el método [GC.Collect](xref:System.GC.Collect) para forzar una recolección de elementos no utilizados. 

Use el método [Collect](xref:System.GC.Collect) cuando haya una reducción significativa de la cantidad de memoria que se está usando en un punto específico del código de la aplicación. Por ejemplo, si la aplicación usa un cuadro de diálogo complejo que tiene varios controles, llamar a [Collect](xref:System.GC.Collect) cuando se cierra el cuadro de diálogo podría mejorar el rendimiento porque reclama inmediatamente la memoria que usa este. Asegúrese de que la aplicación no induce la recolección de elementos no utilizados con demasiada frecuencia, ya que este hecho puede reducir el rendimiento si el recolector de elementos no utilizados intenta reclamar objetos en el momento inadecuado. Puede proporcionar un valor de enumeración [GCCollectionMode.Optimized](xref:System.GCCollectionMode.Optimized) al método [Collect](xref:System.GC.Collect) para recolectar solo cuando la recolección sea productiva, como se explica en la sección siguiente.

## <a name="gc-collection-mode"></a>Modo de colección de GC

Puede usar una de las sobrecargas del método [GC.Collect](xref:System.GC.Collect), que incluye un valor [GCCollectionMode](xref:System.GCCollectionMode) para especificar el comportamiento de una recolección forzada, como se indica a continuación.

Valor GCCollectionMode | Descripción
---------------------- | ----------- 
[Predetermiado](xref:System.GCCollectionMode.Default) | Usa el valor predeterminado de la recolección de elementos no utilizados para la versión de .NET Framework que se está ejecutando.
[Forzado](xref:System.GCCollectionMode.Forced) | Obliga a que la recolección de elementos no utilizados se produzca inmediatamente. Esto equivale a llamar a la sobrecarga [GC.Collect()](xref:System.GC.Collect). Tiene como consecuencia una recolección completa de bloqueo de todas las generaciones. También puede compactar el montón de objeto grande estableciendo la propiedad [GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode) en [GCLargeObjectHeapCompactionMode.CompactOnce](xref:System.Runtime.GCLargeObjectHeapCompactionMode.CompactOnce) antes de forzar una recolección de elementos no utilizados de bloqueo completa inmediata. 
[Optimizado](xref:System.GCCollectionMode.Optimized) | Permite al recolector de elementos no utilizados determinar si la hora actual es la adecuada para reclamar objetos. El recolector de elementos no utilizados puede determinar que una recolección no esté justificada por su insuficiente productividad, en cuyo caso volverá sin reclamar objetos.
 
## <a name="background-or-blocking-collections"></a>Colecciones de fondo o de bloqueo

Puede llamar a la sobrecarga del método [GC.Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) para especificar si una recolección inducida se está bloqueando o no. El tipo de recolección realizado depende de una combinación de los parámetros *mode* y *blocking* del método. *mode* es miembro de la enumeración [GCCollectionMode](xref:System.GCCollectionMode) y *blocking* es un valor [booleano](xref:System.Boolean). En la tabla siguiente se resume la interacción de los argumentos mode y blocking. 

*mode* | *blocking* = true | *blocking* = false
------ | ----------------- | ------------------
[Forzado](xref:System.GCCollectionMode.Forced) o [predeterminado](xref:System.GCCollectionMode.Default) | Se realiza una recolección de bloqueo lo antes posible. Si una recolección en segundo plano está en curso y la generación es 0 o 1, el método [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) desencadena inmediatamente una recolección de bloqueo y vuelve cuando la recolección finaliza. Si una recolección en segundo plano está en curso y el parámetro de generación es 2, el método espera hasta que finaliza la recolección en segundo plano, desencadena una generación de bloqueo 2 y luego vuelve. | Se realiza una recolección lo antes posible. El método [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) solicita una recolección en segundo plano, pero esto no se garantiza; puede que aún se realice una recolección de bloqueo, dependiendo de las circunstancias. Si una colección en segundo plano ya está en curso, el método vuelve inmediatamente. 
[Optimizado](xref:System.GCCollectionMode.Optimized) | Se puede realizar una recolección de bloqueo, dependiendo del estado del recolector de elementos no utilizados y del parámetro de la generación. El recolector de elementos no utilizados intenta proporcionar un rendimiento óptimo. | Se puede realizar una recolección, según el estado del recolector de elementos no utilizados. El método [Collect(Int32, GCCollectionMode, Boolean)](xref:System.GC.Collect(System.Int32,System.GCCollectionMode,System.Boolean)) solicita una recolección en segundo plano, pero esto no se garantiza; puede que aún se realice una recolección de bloqueo, dependiendo de las circunstancias. El recolector de elementos no utilizados intenta proporcionar un rendimiento óptimo. Si una colección en segundo plano ya está en curso, el método vuelve inmediatamente. 
 
## <a name="see-also"></a>Vea también

[Modos de latencia](latency.md)

[Recolección de elementos no utilizados en .NET](index.md)



<!--HONumber=Nov16_HO1-->


