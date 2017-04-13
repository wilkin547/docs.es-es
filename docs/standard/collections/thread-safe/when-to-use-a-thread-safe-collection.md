---
title: "Cu&#225;ndo usar una colecci&#243;n segura para subprocesos | Microsoft Docs"
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
  - "colecciones seguras para subprocesos, cuándo usar"
ms.assetid: a9babe97-e457-4ff3-b528-a1bc940d5320
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Cu&#225;ndo usar una colecci&#243;n segura para subprocesos
[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] introduce cinco nuevos tipos de colección que están especialmente diseñados para admitir operaciones multiproceso de agregar y quitar.  Para lograr seguridad para subprocesos, estos nuevos tipos utilizan varios tipos de mecanismos eficaces de sincronización de bloqueo y sin bloqueos.  La sincronización agrega sobrecarga a una operación.  La cantidad de sobrecarga depende del tipo de sincronización que se utiliza, el tipo de operaciones que se realiza y otros factores como el número de subprocesos que están intentando tener acceso a la colección simultáneamente.  
  
 En algunos escenarios, la sobrecarga de sincronización es insignificante y permite que el tipo multiproceso funcione de un modo notablemente más rápido y escale mucho mejor que su equivalente no seguro para subprocesos cuando está protegido por un bloqueo externo.  En otros escenarios, la sobrecarga puede hacer que el tipo seguro para subprocesos funcione y escale del mismo modo o aún más despacio que la versión del tipo no segura para subprocesos y bloqueada externamente.  
  
 En las siguientes secciones se proporciona una orientación general sobre cuándo utilizar una colección segura para subprocesos frente a su equivalente no seguro para subprocesos que tiene un bloqueo proporcionado por usuario en torno a sus operaciones de lectura y escritura.  Como el rendimiento puede variar en función de numerosos factores, la orientación no es específica y no es necesariamente válida en todas las circunstancias.  Si el rendimiento es muy importante, entonces la manera mejor de determinar qué tipo de colección se puede utilizar es medir el rendimiento basándose en las configuraciones y cargas representativas del equipo.  En este documento se utilizan los términos siguientes:  
  
 *Escenario puro de consumidor\-productor*  
 Cualquier subproceso determinado agrega o quita elementos, pero no ambos.  
  
 *Escenario mixto de consumidor\-productor*  
 Cualquier subproceso determinado agrega y quita elementos.  
  
 *Velocidad*  
 Un rendimiento algorítmico más rápido en relación con otro tipo en el mismo escenario.  
  
 *Escalabilidad*  
 Aumento del rendimiento proporcional al número de núcleos del equipo.  Un algoritmo que escala funciona de un modo más rápido en ocho núcleos que en dos.  
  
## ConcurrentQueue \(T\) con la cola \(T\)  
 En escenarios puros de consumidor\-productor, cuando el tiempo de proceso para cada elemento es muy corto \(algunas instrucciones\), <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName> puede proporcionar unas ventajas de rendimiento modestas sobre <xref:System.Collections.Generic.Queue%601?displayProperty=fullName> que tiene un bloqueo externo.  En este escenario, <xref:System.Collections.Concurrent.ConcurrentQueue%601> funciona mejor cuando un subproceso dedicado está esperando en la cola y un subproceso dedicado se está quitando de la cola.  Si no se aplica esta regla, <xref:System.Collections.Generic.Queue%601> puede incluso funcionar algo más rápido que <xref:System.Collections.Concurrent.ConcurrentQueue%601> en equipos que tengan varios núcleos.  
  
 Cuando el tiempo de proceso es de unos 500 FLOPS \(operaciones de punto flotante\) o más, la regla de dos subprocesos no se aplica a <xref:System.Collections.Concurrent.ConcurrentQueue%601>, que tiene una escalabilidad muy buena.  <xref:System.Collections.Generic.Queue%601> no escala correctamente en este escenario.  
  
 En escenarios mixtos de consumidor\-productor, cuando el tiempo de proceso es muy corto, <xref:System.Collections.Generic.Queue%601> que tiene un bloqueo externo escala mejor que <xref:System.Collections.Concurrent.ConcurrentQueue%601>.  Sin embargo, cuando el tiempo de proceso es de unos 500 FLOPS o más, <xref:System.Collections.Concurrent.ConcurrentQueue%601> escala mejor.  
  
## ConcurrentStack frente pila  
 En escenarios puros de consumidor\-productor, cuando el tiempo de proceso es muy corto, <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName> y <xref:System.Collections.Generic.Stack%601?displayProperty=fullName> que tiene un bloqueo externo funcionarán probablemente del mismo modo con un subproceso de inserción dedicado y un subproceso de extracción dedicado.  Sin embargo, al ir aumentando el número de subprocesos, ambos tipos se ralentizan debido a una mayor contención y <xref:System.Collections.Generic.Stack%601> puede funcionar mejor que <xref:System.Collections.Concurrent.ConcurrentStack%601>.  Cuando el tiempo de proceso es de unos 500 FLOPS o más, ambos tipos escalan a una tasa aproximadamente igual.  
  
 En escenarios mixtos de consumidor\-productor, <xref:System.Collections.Concurrent.ConcurrentStack%601> es más rápido tanto para cargas de trabajo pequeñas como grandes.  
  
 El uso de <xref:System.Collections.Concurrent.ConcurrentStack%601.PushRange%2A> y <xref:System.Collections.Concurrent.ConcurrentStack%601.TryPopRange%2A> pueden acelerar considerablemente los tiempos de acceso.  
  
## ConcurrentDictionary frente al diccionario  
 En general, utilice <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> en cualquier escenario donde agregue y actualice claves o valores de varios subprocesos simultáneamente.  En escenarios que implican actualizaciones frecuentes y relativamente pocas lecturas, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> proporciona en general unas ventajas modestas.  En escenarios que implican numerosas lecturas y actualizaciones, <xref:System.Collections.Concurrent.ConcurrentDictionary%602> es significativamente más rápido, en general, en los equipos que tienen cualquier número de núcleos.  
  
 En escenarios que implican actualizaciones frecuentes, puede aumentar el grado de simultaneidad en <xref:System.Collections.Concurrent.ConcurrentDictionary%602> y realizar una medición para ver si el rendimiento aumenta en los equipos que tienen más núcleos.  Si cambia el nivel de simultaneidad, evite las operaciones globales en la medida de lo posible.  
  
 Si solo está leyendo claves o valores, <xref:System.Collections.Generic.Dictionary%602> es más rápido porque no se requiere sincronización alguna si no hay ningún subproceso que modifique el diccionario.  
  
## ConcurrentBag  
 En escenarios puros de consumidor\-productor, <xref:System.Collections.Concurrent.ConcurrentBag%601?displayProperty=fullName> funcionará probablemente más despacio que los demás tipos de colección simultáneos.  
  
 En escenarios mixtos de consumidor\-productor, <xref:System.Collections.Concurrent.ConcurrentBag%601> es generalmente mucho más rápido y escalable que cualquier otro tipo de colección simultáneo tanto para cargas de trabajo grandes como pequeñas.  
  
## BlockingCollection  
 Cuando se requiere semántica de límite y bloqueo, <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> funcionará probablemente más rápido que cualquier implementación personalizada.  También admite cancelación, enumeración y control de excepciones complejos.  
  
## Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)   
 [Parallel Programming](../../../../docs/standard/parallel-programming/index.md)