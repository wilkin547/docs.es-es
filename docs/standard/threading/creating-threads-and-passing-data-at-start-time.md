---
title: Crear subprocesos y analizar los datos en el inicio
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
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Crear subprocesos y analizar los datos en el inicio
Cuando se crea un proceso de sistema operativo, el sistema operativo inserta un subproceso para ejecutar el código en dicho proceso, incluido cualquier dominio de aplicación original. Desde ese momento, los dominios de aplicación se pueden crear y destruir sin ningún subproceso del sistema operativo necesariamente que se crea o se destruye. Si se administra el código que se ejecuta código, un <xref:System.Threading.Thread> objeto para el subproceso que se ejecuta en el dominio de aplicación actual se puede obtener mediante la recuperación estático <xref:System.Threading.Thread.CurrentThread%2A> propiedad de tipo <xref:System.Threading.Thread>. En este tema se describe la creación de subprocesos y se analiza las alternativas para pasar datos al procedimiento de subproceso.  
  
## <a name="creating-a-thread"></a>Crear un subproceso  
 Crear un nuevo <xref:System.Threading.Thread> objeto crea un nuevo subproceso administrado. El <xref:System.Threading.Thread> clase tiene constructores que toman un <xref:System.Threading.ThreadStart> delegar o un <xref:System.Threading.ParameterizedThreadStart> delegar; el delegado ajusta el método que se invoca el nuevo subproceso cuando se llama a la <xref:System.Threading.Thread.Start%2A> método. Al llamar a <xref:System.Threading.Thread.Start%2A> hace más de una vez un <xref:System.Threading.ThreadStateException> que se produzca.  
  
 El <xref:System.Threading.Thread.Start%2A> método devuelve inmediatamente, a menudo antes de que se haya iniciado realmente el nuevo subproceso. Puede usar el <xref:System.Threading.Thread.ThreadState%2A> y <xref:System.Threading.Thread.IsAlive%2A> las propiedades para determinar el estado del subproceso en cualquier momento, pero estas propiedades nunca deben utilizarse para sincronizar las actividades de subprocesos.  
  
> [!NOTE]
>  Una vez que se inicia un subproceso, no es necesario conservar una referencia a la <xref:System.Threading.Thread> objeto. El subproceso continúa ejecutándose hasta que finaliza el procedimiento de subproceso.  
  
 En el ejemplo de código siguiente se crea dos subprocesos nuevos para llamar a métodos estáticos e instancia en otro objeto.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a>Pasar datos a subprocesos y recuperar datos de subprocesos  
 En .NET Framework versión 2.0, el <xref:System.Threading.ParameterizedThreadStart> delegado proporciona una manera sencilla para pasar un objeto que contiene datos a un subproceso cuando se llama a la <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> sobrecarga del método. Vea <xref:System.Threading.ParameterizedThreadStart> para obtener código muestra.  
  
 Mediante el <xref:System.Threading.ParameterizedThreadStart> delegado no es una forma de seguridad de tipos para pasar datos, porque el <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> sobrecarga del método acepta cualquier objeto. Una alternativa consiste en encapsular el procedimiento de subproceso y los datos en una clase auxiliar y utilizar el <xref:System.Threading.ThreadStart> delegado para ejecutar el procedimiento de subproceso. Esta técnica se muestra en los dos ejemplos de código siguientes.  
  
 Ninguno de estos delegados tiene un valor devuelto, porque no hay ningún lugar para devolver los datos de una llamada asincrónica. Para recuperar los resultados de un método de subproceso, puede utilizar un método de devolución de llamada, como se muestra en el segundo ejemplo de código.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a>Recuperar datos con métodos de devolución de llamada  
 En el ejemplo siguiente se muestra un método de devolución de llamada que recupera datos de un subproceso. El constructor de la clase que contiene los datos y el método del subproceso también acepta a un delegado que representa el método de devolución de llamada; antes de que finalice el método del subproceso, invoca al delegado de devolución de llamada.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Usar subprocesos y subprocesamiento](../../../docs/standard/threading/using-threads-and-threading.md)
