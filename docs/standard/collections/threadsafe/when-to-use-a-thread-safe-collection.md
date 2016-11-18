---
title: "Cuándo usar una colección segura para subprocesos"
description: "Cuándo usar una colección segura para subprocesos"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: a2a42d44-f6a5-4f16-9000-026221d66349
translationtype: Human Translation
ms.sourcegitcommit: e07788926a995b41571be276379ad9285747951d
ms.openlocfilehash: 05f692a1a58c0c653e14993cafd61a0711ebf9f8

---

# <a name="when-to-use-a-threadsafe-collection"></a>Cuándo usar una colección segura para subprocesos

Los tipos de colección `ConcurrentQueue`, `ConcurrentStack`, `ConcurrentDictionary`, `ConcurrentBag` y `BlockingCollection` están especialmente diseñados para admitir operaciones multiproceso de agregar y quitar. Para obtener seguridad para los subprocesos, estos nuevos tipos usan diversas clases de mecanismos de sincronización eficientes con bloqueo y sin bloqueo. La sincronización agrega sobrecarga a las operaciones. La cantidad de sobrecarga depende del tipo de sincronización que se use, el tipo de operaciones que se realicen y otros factores, como el número de subprocesos que intentan obtener acceso simultáneamente a la colección.

En algunos escenarios, la sobrecarga de la sincronización es insignificante y permite que el tipo multiproceso funcione mucho más rápido y aumente de tamaño mucho mejor que su equivalente no seguro para subprocesos cuando está protegido por un bloqueo externo. En otros escenarios, la sobrecarga puede hacer que el tipo seguro para subprocesos funcione y aumente de tamaño más o menos igual o incluso más lentamente que la versión del tipo no segura para subprocesos bloqueada externamente.

Las secciones siguientes proporcionan instrucciones generales acerca de cuándo usar una colección segura para subprocesos frente a su equivalente no seguro para subprocesos que tiene un bloqueo para la lectura y escritura proporcionado por el usuario. Dado que el rendimiento puede variar según muchos factores, las instrucciones no son específicas y tampoco son necesariamente válidas en todas las circunstancias. Si el rendimiento es muy importante, la mejor manera de determinar qué tipo de colección debe usar es medir el rendimiento en función de cargas y configuraciones de equipo representativas. Este documento usa los términos siguientes:

*Escenario puro de productor-consumidor:* cualquier subproceso dado agrega o quita elementos, pero no realiza ambas operaciones.

*Escenario mixto de productor-consumidor:* cualquier subproceso dado agrega y quita elementos.

*Aceleración:* rendimiento algorítmico más rápido con respecto a otro tipo en el mismo escenario.

*Escalabilidad:* aumento del rendimiento que es proporcional al número de núcleos del equipo. Un algoritmo que escala funciona más rápido con ocho núcleos que con dos núcleos.

## <a name="concurrentqueuelttgt-vs-queuelttgt"></a>ConcurrentQueue&lt;T&gt; frente a Queue&lt;T&gt;

En escenarios productor-consumidor puros, cuando el tiempo de procesamiento de cada elemento es muy pequeño (pocas instrucciones), [System.Collections.Concurrent.ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) puede ofrecer modestas ventajas de rendimiento sobre [System.Collections.Generic.Queue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Queue-1) con un bloqueo externo. En este escenario, `ConcurrentQueue<T>` funciona mejor cuando un subproceso dedicado se está poniendo en cola y un subproceso dedicado se está quitando de la cola. Si no se aplica esta regla, `Queue<T>` podría funcionar incluso algo más rápido que `ConcurrentQueue<T>` en equipos con varios núcleos. 

Cuando el tiempo de procesamiento es de unos 500 FLOPS (operaciones de punto flotante) o más, la regla de dos subprocesos no se aplica a `ConcurrentQueue<T>`, que en ese caso tiene muy buena escalabilidad. `Queue<T>` no escala bien en este escenario.

En escenarios productor-consumidor mixtos, cuando el tiempo de procesamiento es muy pequeño, `Queue<T>` con un bloqueo externo escala mejor que `ConcurrentQueue<T>`. Pero cuando el tiempo de procesamiento es de unos 500 FLOPS o más, `ConcurrentQueue<T>` escala mejor.

## <a name="concurrentstack-vs-stack"></a>ConcurrentStack frente a Pila

En escenarios productor-consumidor puros, cuando el tiempo de procesamiento es muy pequeño, [System.Collections.Concurrent.ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1) y [System.Collections.Generic.Stack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Stack-1) con un bloqueo externo probablemente funcionarán más o menos igual con un subproceso dedicado que se inserta y un subproceso dedicado que se extrae. Pero a medida que aumenta el número de subprocesos, ambos tipos se ralentizan debido a una mayor contención y `Stack<T>` podría funcionar mejor que `ConcurrentStack<T>`. Cuando el tiempo de procesamiento es de unos 500 FLOPS o más, ambos tipos escalan con una velocidad similar. 

En escenarios productor-consumidor mixtos, `ConcurrentStack<T>` es más rápido para cargas de trabajo grandes y pequeñas.

El uso de `PushRange` y `TryPopRange` puede acelerar considerablemente el tiempo de acceso.

## <a name="concurrentdictionary-vs-dictionary"></a>ConcurrentDictionary frente a Dictionary

En general, use [System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) en cualquier escenario en el que agregue y actualice claves o valores simultáneamente desde varios subprocesos. En escenarios que implican actualizaciones frecuentes y relativamente pocas lecturas, `ConcurrentDictionary<TKey, TValue>` suele ofrecer ventajas modestas. En escenarios que implican numerosas lecturas y actualizaciones, `ConcurrentDictionary<TKey, TValue>` suele ser considerablemente más rápido en equipos con cualquier número de núcleos.

En escenarios que implican actualizaciones frecuentes, puede aumentar el grado de simultaneidad en `ConcurrentDictionary<TKey, TValue>` y medir el rendimiento para ver si aumenta en equipos que tienen más núcleos. Si cambia el nivel de simultaneidad, evite las operaciones globales tanto como pueda.

Si solo va a leer claves o valores, [System.Collections.Generic.Dictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Generic.Dictionary-2) es más rápido porque no se necesita ninguna sincronización cuando no hay ningún subproceso que modifique el diccionario.

## <a name="concurrentbag"></a>ConcurrentBag

En escenarios productor-consumidor puros, [System.Collections.Concurrent.ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) probablemente será más lento que los otros tipos de colección simultánea.

En escenarios productor-consumidor mixtos, `ConcurrentBag<T>` es generalmente mucho más rápido y más escalable que cualquier otro tipo de colección simultánea para cargas de trabajo grandes y pequeñas.

## <a name="blockingcollection"></a>BlockingCollection

Cuando se necesita una semántica de límite y bloqueo, [System.Collections.Concurrent.BlockingCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) probablemente funcionará más rápido que cualquier implementación personalizada. Además, admite tareas avanzadas de cancelación, enumeración y control de excepciones.

## <a name="see-also"></a>Vea también

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Colecciones seguras para subprocesos](index.md)



<!--HONumber=Nov16_HO3-->


