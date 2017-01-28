---
title: "recolección de elementos no utilizados"
description: "recolección de elementos no utilizados"
keywords: .NET, .NET Core
author: richlander
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.devlang: dotnet
ms.assetid: db39a0f5-e363-490f-a7e6-adb9a6ff2a8c
translationtype: Human Translation
ms.sourcegitcommit: ffc0530b2263db0e073f351aac2d539de6701ead
ms.openlocfilehash: 4646a7e8c75315bb1a13bc5fddecd77888f6ae69

---

# <a name="garbage-collection"></a>Recolección de elementos no utilizados

La recolección de elementos no utilizados es una de las características más importantes de la plataforma de código administrado de .NET. El recolector de elementos no utilizados (GC) administra la asignación y liberación de memoria por usted. No necesita asignar y liberar memoria o administrar la duración de los objetos que usan esa memoria. Se realiza una asignación cada vez que tiene un objeto _nuevo_ y se aplica un tipo de valor. Las asignaciones son normalmente muy rápidas. Cuando no hay memoria suficiente para asignar un objeto, el GC debe recopilar y desechar la memoria de elementos no utilizados para que la memoria esté disponible para nuevas asignaciones. Este proceso se denomina "recolección de elementos no utilizados".

El recolector de elementos no utilizados actúa como administrador de memoria automático. Proporciona las siguientes ventajas:

*   Permite desarrollar la aplicación sin tener que liberar memoria.
*   Asigna con eficacia los objetos del montón administrado.
*   Reclama los objetos que ya no se utilizan, borra la memoria correspondiente y mantiene la memoria disponible para asignaciones futuras. Los objetos administrados obtienen automáticamente contenido limpio desde el principio, de modo que sus constructores no tienen que inicializar todos los campos de datos.
*   Proporciona seguridad de memoria, al asegurarse de que un objeto no pueda utilizar el contenido de otro objeto.

El GC de .NET es generacional y tiene 3 generaciones. Cada generación tiene su propio montón que usa para el almacenamiento de objetos asignados. Hay un principio básico que se centra en que la mayoría de los objetos son de corta o larga duración. La generación 0 es donde se asignan primero los objetos. A menudo, los objetos no duran más de la primera generación, puesto que ya no están en uso (fuera de ámbito) en el momento en que se produce la siguiente recolección de elementos no utilizados. La recopilación de la generación 0 es más rápida porque su montón asociado es pequeño. La generación 1 es realmente un espacio de segundas oportunidades. Los objetos con una duración corta, pero que sobreviven a la recolección de la generación 0 (a menudo basada en intervalos fortuita) pasan a la generación 1\. Las recolecciones de la generación 1 son rápidas porque su montón asociado también es pequeño. Los dos primeros montones siguen siendo pequeños porque los objetos se recolectan o se promueven en el siguiente montón de la generación. La generación 2 es donde se encuentran todos los objetos de larga duración. El montón de la generación 2 puede hacerse muy grande, ya que los objetos que contiene pueden sobrevivir mucho tiempo y no hay ningún montón de generación 3 para promover aún más los objetos.

El GC tiene un montón adicional de objetos grandes, denominado el montón de objetos grandes (LOH). Está reservado para objetos de 85 000 bytes o más. Una matriz de bytes (Byte[]) con 85 000 elementos sería un ejemplo de un objeto grande. Los objetos grandes no se asignan a los montones generacionales, sino que se asignan directamente al LOH.

La generación 2 y las recolecciones LOH pueden tardar cierto tiempo en programas que se han ejecutado durante mucho tiempo o pueden operar con grandes cantidades de datos. Los programas de servidor de gran tamaño se distinguen por tener montones que pesan decenas de GB. El GC emplea una variedad de técnicas para reducir la cantidad de tiempo que bloquea la ejecución del programa. El enfoque principal es hacer todo el trabajo de recolección de elementos no utilizados posible en un subproceso en segundo plano, de modo que no interfiera con la ejecución del programa. El GC también expone algunas formas para que los desarrolladores influyan en su comportamiento, lo que puede ser bastante útil para mejorar el rendimiento.

## <a name="related-topics"></a>Temas relacionados

Título | Descripción
----- | ----------- 
[Administración automática de la memoria y recolección de elementos no utilizados](gc.md) | Presenta los conceptos básicos de administración de memoria de .NET
[Fundamentos de la recolección de elementos no utilizados](fundamentals.md) | Describe cómo funciona la recolección de elementos no utilizados, cómo se asignan los objetos en el montón administrado y otros conceptos básicos.
[Colecciones inducidas](induced.md) | Describe cómo hacer que se produzca una recolección de elementos no utilizados.
[Modos de latencia](latency.md) | Describe los modos que determinan la tendencia a la intrusión de la recolección de elementos no utilizados.
[Referencias débiles](weak-references.md) | Describe las características que permiten al recolector de elementos no utilizados recoger un objeto y, mientras tanto, permitir que la aplicación tenga acceso a ese objeto.
 
## <a name="reference"></a>Referencia

[System.GC](xref:System.GC)

[System.GCCollectionMode](xref:System.GCCollectionMode)

[System.Runtime.GCLatencyMode](xref:System.Runtime.GCLatencyMode)

[System.Runtime.GCSettings](xref:System.Runtime.GCSettings)

[GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode)

[Object.Finalize](xref:System.Object.Finalize)

[System.IDisposable](xref:System.IDisposable)

## <a name="see-also"></a>Vea también

[Limpieza de recursos no administrados](unmanaged.md)




<!--HONumber=Jan17_HO3-->


