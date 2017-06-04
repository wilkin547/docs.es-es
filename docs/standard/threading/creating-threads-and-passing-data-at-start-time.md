---
title: "Creating Threads and Passing Data at Start Time | Microsoft Docs"
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
  - "threading [.NET Framework], creating"
  - "threading [.NET Framework], passing data to threads"
  - "threading [.NET Framework], retrieving data from threads"
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Creating Threads and Passing Data at Start Time
Al crear un proceso del sistema operativo, éste introduce un subproceso para ejecutar el código de dicho proceso, incluido cualquier dominio de aplicación original.  A partir de ese punto, pueden crearse y destruirse dominios de aplicación sin que necesariamente se cree o destruya ningún subproceso del sistema operativo.  Si el código que se ejecuta es administrado, puede obtenerse un objeto <xref:System.Threading.Thread> para el subproceso que se ejecuta en el dominio de aplicación actual si se recupera la propiedad estática <xref:System.Threading.Thread.CurrentThread%2A> de tipo <xref:System.Threading.Thread>.  En este tema se describe la creación de subprocesos y se analizan las alternativas para pasar datos al procedimiento de subproceso.  
  
## Crear un subproceso  
 Al crear un nuevo objeto <xref:System.Threading.Thread> se crea un nuevo subproceso administrado.  La clase <xref:System.Threading.Thread> dispone de constructores que toman un delegado <xref:System.Threading.ThreadStart> o <xref:System.Threading.ParameterizedThreadStart>; el delegado contiene el método al que invoca el nuevo subproceso cuando se llama al método <xref:System.Threading.Thread.Start%2A>.  Si se llama a <xref:System.Threading.Thread.Start%2A> más de una vez, se produce una excepción <xref:System.Threading.ThreadStateException>.  
  
 El método <xref:System.Threading.Thread.Start%2A> devuelve un resultado inmediatamente, con frecuencia antes de que el nuevo subproceso se haya iniciado realmente.  Puede utilizar las propiedades <xref:System.Threading.Thread.ThreadState%2A> y <xref:System.Threading.Thread.IsAlive%2A> para determinar el estado del subproceso en cualquier momento, pero estas propiedades no deben utilizarse nunca para sincronizar las actividades de los subprocesos.  
  
> [!NOTE]
>  Una vez iniciado un subproceso, no es necesario conservar una referencia al objeto <xref:System.Threading.Thread>.  El subproceso se continúa ejecutando hasta que el procedimiento del mismo finaliza.  
  
 En el ejemplo de código siguiente se crean dos subprocesos nuevos para llamar a métodos estáticos y una instancia de otro objeto.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## Pasar datos a subprocesos y recuperar datos de subprocesos  
 En la versión 2.0 de .NET Framework, el delegado <xref:System.Threading.ParameterizedThreadStart> proporciona una forma sencilla de pasar un objeto que contiene datos a un subproceso cuando se llama a la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>.  Vea <xref:System.Threading.ParameterizedThreadStart> para obtener un ejemplo de código.  
  
 El uso del delegado <xref:System.Threading.ParameterizedThreadStart> no constituye un modo con seguridad de tipos para pasar los datos, dado que la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=fullName> acepta cualquier objeto.  Una alternativa consiste en encapsular el procedimiento de subproceso y los datos en una clase auxiliar y utilizar el delegado <xref:System.Threading.ThreadStart> para ejecutar el procedimiento de subproceso.  Esta técnica se muestra en los dos ejemplos de código siguientes.  
  
 Ninguno de estos delegados presenta un valor devuelto, porque no hay ningún lugar donde devolver los datos de una llamada asincrónica.  Para recuperar los resultados de un método de subproceso, puede utilizar un método de respuesta, como se muestra en el segundo ejemplo de código.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### Recuperar datos con métodos de devolución de llamada  
 En el siguiente ejemplo se muestra un método de respuesta que recupera datos de un subproceso.  El constructor de la clase que contiene los datos y el método del subproceso también acepta un delegado que representa el método de devolución de llamada; antes de finalizar, el método del subproceso invoca al delegado de devolución de llamada.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## Vea también  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadStart>   
 <xref:System.Threading.ParameterizedThreadStart>   
 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)