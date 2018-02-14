---
title: "Cómo: Agregar y quitar elementos de ConcurrentDictionary"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- thread-safe collections, concurrent dictionary
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 4ef7c8050b26cffeed03cc394193116f8f6797a9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Cómo: Agregar y quitar elementos de ConcurrentDictionary
En este ejemplo se muestra cómo agregar, recuperar, actualizar y quitar elementos de <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=nameWithType>. Esta clase de colección es una implementación segura para subprocesos. Es recomendable que la use cada vez que varios subprocesos puedan intentar tener acceso a los elementos de forma simultánea.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> proporciona varios métodos útiles que requieren que el código compruebe primero si existe una clave antes de intentar agregar o quitar datos. En la tabla siguiente se enumeran estos métodos útiles y se describe cuándo se deben usar.  
  
|Método|Cuándo se usa…|  
|------------|---------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Quiere agregar un nuevo valor para una clave especificada y, si la clave ya existe, quiere reemplazar su valor.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Quiere recuperar el valor existente de una clave especificada y, si la clave no existe, quiere especificar un par de clave/valor.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Quiere agregar, obtener, actualizar o quitar un par de clave/valor y, si la clave ya existe o se produce un error en el intento por cualquier otra razón, quiere realizar alguna acción alternativa.|  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan dos instancias de <xref:System.Threading.Tasks.Task> para agregar algunos elementos a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> de manera simultánea y, después, se genera todo el contenido para mostrar que los elementos se han agregado correctamente. En el ejemplo también se muestra cómo usar los métodos <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> para agregar, actualizar y recuperar elementos en la colección.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> está diseñado para escenarios multiproceso. No es necesario usar bloqueos en el código para agregar o quitar elementos de la colección. Pero siempre es posible que un subproceso recupere un valor y otro subproceso actualice inmediatamente la colección asignándole un nuevo valor a la misma clave.  
  
 Además, aunque todos los métodos de <xref:System.Collections.Concurrent.ConcurrentDictionary%602> son seguros para subprocesos, no todos los métodos son atómicos, específicamente <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>. Se invoca el delegado del usuario que se pasa a estos métodos fuera del bloqueo interno del diccionario. (Esto se hace para evitar que el código desconocido bloquee todos los subprocesos). Por tanto, es posible que se produzca esta secuencia de eventos:  
  
 1\) El subproceso A llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, no encuentra ningún elemento y crea un nuevo elemento para agregar mediante la invocación del delegado valueFactory.  
  
 2\) Al mismo tiempo, el subproceso B llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, se invoca a su delegado valueFactory y llega al bloqueo interno antes que el subproceso A. Por tanto, su nuevo par clave-valor se agrega al diccionario.  
  
 3\)El delegado de usuario del subproceso A se completa, y el subproceso llega al bloqueo, pero ahora se ve que el elemento ya existe.  
  
 4\) El subproceso A realiza una operación "Get" y devuelve los datos que había agregado anteriormente el subproceso B.  
  
 Por tanto, no está garantizado que los datos devueltos por <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> sean los mismos que los creados por valueFactory del subproceso. Puede producirse una secuencia similar de eventos cuando se llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Collections.Concurrent?displayProperty=nameWithType>  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)
