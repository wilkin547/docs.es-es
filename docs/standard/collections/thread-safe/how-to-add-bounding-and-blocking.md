---
title: "C&#243;mo: Agregar la funcionalidad de l&#237;mite y bloqueo a una colecci&#243;n | Microsoft Docs"
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
  - "colecciones seguras para subprocesos, colecciones de bloqueo personalizadas"
ms.assetid: 4c2492de-3876-4873-b5a1-000bb404d770
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Agregar la funcionalidad de l&#237;mite y bloqueo a una colecci&#243;n
En este ejemplo se muestra cómo agregar la funcionalidad de límite y bloqueo a una clase de colección personalizada implementando la interfaz <xref:System.Collections.Concurrent.IProducerConsumerCollection%601?displayProperty=fullName> en la clase y utilizando una instancia de clase como mecanismo de almacenamiento interno para <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName>.  Para obtener más información sobre cómo limitar y bloquear, vea [Información general sobre BlockingCollection](../../../../docs/standard/collections/thread-safe/blockingcollection-overview.md).  
  
## Ejemplo  
 La clase de colección personalizada es una cola de prioridad básica en la que los niveles de prioridad se representan como una matriz de objetos <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  No se realiza ninguna clasificación adicional dentro de cada cola.  
  
 En el código de cliente, se inician tres tareas.  La primera tarea se limita a buscar pulsaciones de teclado para habilitar la cancelación en cualquier punto durante la ejecución.  La segunda tarea es el subproceso del productor; agrega nuevos elementos a la colección de bloqueo y proporciona a cada elemento una prioridad basándose en un valor aleatorio.  La tercera tarea quita los elementos de la colección cuando se vuelven disponibles.  
  
 Puede ajustar el comportamiento de la aplicación haciendo que uno de los subprocesos se ejecute de una manera más rápida que el otro.  Si el productor se ejecuta más rápidamente, observará la funcionalidad de límite al evitar la colección de bloqueo que se agreguen elementos si ya contiene el número de elementos que se especifica en el constructor.  Si el consumidor se ejecuta más rápidamente, observará la funcionalidad de bloqueo mientras el consumidor espera que se agregue un nuevo elemento.  
  
 [!code-csharp[CDS_BlockingCollection#06](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/prodcon.cs#06)]  
  
 De forma predeterminada, el almacenamiento de <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> es <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=fullName>.  
  
## Vea también  
 [Colecciones seguras para subprocesos](../../../../docs/standard/collections/thread-safe/index.md)