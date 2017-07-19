---
title: "Merge Options in PLINQ | Microsoft Docs"
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
  - "PLINQ queries, merge options"
ms.assetid: e8f7be3b-88de-4f33-ab14-dc008e76c1ba
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Merge Options in PLINQ
Cuando una consulta se ejecuta en paralelo, PLINQ crea particiones en la secuencia de origen para que varios subprocesos puedan funcionar simultáneamente en diferentes partes, por lo general en subprocesos independientes.  Si los resultados se van a usar en un subproceso, por ejemplo, en un bucle `foreach` \(`For Each` en [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]\), los resultados de cada subproceso deben volver a combinarse en una secuencia.  El tipo de combinación que PLINQ realiza depende de los operadores que se encuentran en la consulta.  Por ejemplo, los operadores que imponen un nuevo orden en los resultados deben almacenar en búfer todos los elementos de todos los subprocesos.  Desde el punto de vista del subproceso utilizado \(qué también es el del usuario de la aplicación\), una consulta totalmente almacenada en búfer podría ejecutarse durante un período notable de tiempo antes de generar su primer resultado.  Otros operadores se almacenan parcialmente en búfer de forma predeterminada; producen sus resultados en lotes.  Un operador <xref:System.Linq.ParallelEnumerable.ForAll%2A> no se almacena en búfer de forma predeterminada.  Produce inmediatamente todos los elementos de todos los subprocesos.  
  
 Como se muestra en el siguiente ejemplo, con el método <xref:System.Linq.ParallelEnumerable.WithMergeOptions%2A>, puede proporcionar a PLINQ una sugerencia que indica el tipo de combinación que se va a realizar.  
  
 [!code-csharp[PLINQ#26](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqsamples.cs#26)]
 [!code-vb[PLINQ#26](../../../samples/snippets/visualbasic/VS_Snippets_Misc/plinq/vb/plinq2_vb.vb#26)]  
  
 Para obtener el ejemplo completo, vea [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md).  
  
 Si la consulta determinada no puede admitir la opción solicitada, esta se omitirá.  En la mayoría de los casos, no tiene que especificar una opción de combinación para una consulta PLINQ.  Sin embargo, en algunos casos puede encontrar mediante pruebas y mediciones que una consulta se ejecuta mejor en un modo no predeterminado.  Un uso común de esta opción es forzar a un operador de combinación de fragmentos a transmitir en secuencias sus resultados para proporcionar una interfaz de usuario más sensible.  
  
## ParallelMergeOptions  
 La enumeración <xref:System.Linq.ParallelMergeOptions> incluye las siguientes opciones que especifican, para las formas de la consulta compatibles, cómo se proporciona el resultado final de la consulta cuando se usan los resultados en un subproceso:  
  
-   `Not Buffered`  
  
     La opción <xref:System.Linq.ParallelMergeOptions> hace que cada subproceso devuelva cada elemento procesado en cuanto se genere.  Este comportamiento es análogo a la "transmisión por secuencias" del resultado.  Si el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> se encuentra en la consulta, `NotBuffered` conserva el orden de los elementos de origen.  Aunque `NotBuffered` empieza a proporcionar los resultados en cuanto están disponibles, el tiempo total para generar todos los resultados podría ser aún más prolongado que al usar una de las otras opciones de combinación.  
  
-   `Auto Buffered`  
  
     La opción de <xref:System.Linq.ParallelMergeOptions> hace la consulta para obtener elementos en un búfer y después para provocar periódicamente el contenido del búfer de una vez en el subproceso utilizado.  Esto es análogo a proporcionar los datos de origen en "fragmentos" en lugar de usar el comportamiento de "transmisión por secuencias" de `NotBuffered`.  `AutoBuffered` puede llevar mucho más tiempo que `NotBuffered` para hacer que el primer elemento esté disponible en el subproceso utilizado.  El tamaño del búfer y el comportamiento productivo exacto no se puede configurar y puede variar, en función de varios factores relacionados con la consulta.  
  
-   `FullyBuffered`  
  
     La opción <xref:System.Linq.ParallelMergeOptions> hace que el resultado de la consulta completa se almacene en búfer antes de que se proporcione cualquiera de los elementos.  Cuando se usa esta opción, puede llevar mucho más tiempo que el primer elemento esté disponible en el subproceso utilizado, pero los resultados completos se podrían generar aún más rápidamente que al usar las otras opciones.  
  
## Operadores de consulta que admiten opciones de combinación  
 En la siguiente tabla se hace una lista de los operadores que admiten todos los modos de opción de combinación, sujetos a las restricciones especificadas.  
  
|operador ??|Restricciones|  
|-----------------|-------------------|  
|<xref:System.Linq.ParallelEnumerable.AsEnumerable%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Cast%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Concat%2A>|Consultas no ordenadas que solo tienen un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.DefaultIfEmpty%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.OfType%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Reverse%2A>|Consultas no ordenadas que solo tienen un origen de matriz o lista.|  
|<xref:System.Linq.ParallelEnumerable.Select%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.SelectMany%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Skip%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Take%2A>|None|  
|<xref:System.Linq.ParallelEnumerable.Where%2A>|None|  
  
 Todos los demás operadores de consulta PLINQ podrían omitir las opciones de combinación proporcionadas por el usuario.  Algunos operadores de consulta, por ejemplo, <xref:System.Linq.ParallelEnumerable.Reverse%2A> y <xref:System.Linq.ParallelEnumerable.OrderBy%2A>, no pueden proporcionar ningún elemento hasta que todos se hayan generado y reordenado.  Por consiguiente, cuando se usa <xref:System.Linq.ParallelMergeOptions> en una consulta que también contiene a operador como <xref:System.Linq.ParallelEnumerable.Reverse%2A>, el comportamiento de combinación no se aplicará en la consulta hasta que ese operador haya generado sus resultados.  
  
 La capacidad de algunos operadores para controlar las opciones de combinación depende del tipo de la secuencia de origen y de si el operador <xref:System.Linq.ParallelEnumerable.AsOrdered%2A> se usó anteriormente en la consulta.  <xref:System.Linq.ParallelEnumerable.ForAll%2A> siempre es <xref:System.Linq.ParallelMergeOptions>; proporciona sus elementos inmediatamente.  <xref:System.Linq.ParallelEnumerable.OrderBy%2A> siempre es <xref:System.Linq.ParallelMergeOptions>; debe ordenar la lista completa antes de proporcionar resultados.  
  
## Vea también  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)   
 [How to: Specify Merge Options in PLINQ](../../../docs/standard/parallel-programming/how-to-specify-merge-options-in-plinq.md)