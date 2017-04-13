---
title: "C&#243;mo: Agregar y quitar elementos de ConcurrentDictionary | Microsoft Docs"
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
  - "colecciones seguras para subprocesos, diccionario simultáneo"
ms.assetid: 81b64b95-13f7-4532-9249-ab532f629598
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar y quitar elementos de ConcurrentDictionary
En este ejemplo se muestra cómo agregar, recuperar, actualizar y quitar elementos de <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>.  Esta clase de colección es una implementación segura para subprocesos.  Recomendamos utilizarla cada vez que varios subprocesos intenten tener acceso a los elementos simultáneamente.  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> proporciona varios métodos útiles que hacen innecesario que el código compruebe primero si existe una clave antes de intentar agregar o quitar datos.  La siguiente tabla enumera estos métodos útiles y describe cuándo utilizarlos.  
  
|Método|Se utiliza cuando…|  
|------------|------------------------|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>|Desea agregar un nuevo valor para una clave especificada y, si la clave ya existe, desea reemplazar su valor.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>|Desea recuperar el valor existente para una clave especificada y, si la clave no existe, desea especificar un par clave\-valor.|  
|<xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryAdd%2A>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryGetValue%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryUpdate%2A> , <xref:System.Collections.Concurrent.ConcurrentDictionary%602.TryRemove%2A>|Desea agregar, obtener, actualizar o quitar un par clave\-valor y, si la clave ya existe o se produce un error en el intento por cualquier otra razón, desea realizar alguna acción alternativa.|  
  
## Ejemplo  
 En el siguiente ejemplo se utilizan dos instancias <xref:System.Threading.Tasks.Task> para agregar algunos elementos a <xref:System.Collections.Concurrent.ConcurrentDictionary%602> simultáneamente y a continuación, se genera todo el contenido para mostrar que los elementos se agregaron correctamente.  El ejemplo también se muestra cómo utilizar <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>, <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>, y los métodos de <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> para agregar, actualizar, y recuperar elementos de la colección.  
  
 [!code-csharp[CDS#16](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds_dictionaryhowto.cs#16)]
 [!code-vb[CDS#16](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/cds_concdict.vb#16)]  
  
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> está diseñado para escenarios multiproceso.  No necesita utilizar bloqueos en el código para agregar o quitar elementos de la colección.  Sin embargo, siempre es posible que un subproceso recupere un valor y otro subproceso actualice de inmediato la colección dando un nuevo valor a la misma clave.  
  
 Además, aunque todos los métodos <xref:System.Collections.Concurrent.ConcurrentDictionary%602> son seguros para subprocesos, no todos los métodos son atómicos, concretamente <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> y <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  El delegado de usuario que se pasa a estos métodos se invoca fuera del bloqueo interno del diccionario. \(Esto se hace para evitar que código desconocido bloquee todos los subprocesos.\) Por tanto, es posible que se produzca esta secuencia de eventos:  
  
 1\) el subproceso A llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A>, no encuentra ningún elemento y crea un nuevo elemento para agregar invocando el delegado valueFactory.  
  
 2\) el subproceso B llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> simultáneamente, se invoca su delegado valueFactory y este llega al bloqueo interno antes que el subproceso A, por lo que su nuevo par clave\-valor se agrega al diccionario.  
  
 3\) el delegado de usuario del subproceso A se completa y el subproceso llega al bloqueo, pero ahora ve que el elemento ya existe.  
  
 4\) el subproceso A realiza un "Get" y devuelve los datos agregados previamente por el subproceso B.  
  
 Por tanto, no se garantiza que los datos devueltos por <xref:System.Collections.Concurrent.ConcurrentDictionary%602.GetOrAdd%2A> sean los mismos que creó el delegado valueFactory del subproceso.  Puede ocurrir una secuencia de eventos similar cuando se llama a <xref:System.Collections.Concurrent.ConcurrentDictionary%602.AddOrUpdate%2A>.  
  
## Vea también  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)