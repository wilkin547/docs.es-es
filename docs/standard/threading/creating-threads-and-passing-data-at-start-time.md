---
title: Creación de subprocesos y análisis los datos en el inicio
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
ms.openlocfilehash: a628cbb4c9ec8e1c9ccd9fd73e72a82ecf2b2836
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73138100"
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Creación de subprocesos y análisis los datos en el inicio

Cuando se crea un proceso de sistema operativo, el sistema operativo inserta un subproceso para ejecutar el código en dicho proceso, incluido cualquier dominio de aplicación original. Desde ese momento, los dominios de aplicación se pueden crear y destruir sin que se cree o destruya necesariamente ningún subproceso del sistema operativo. Si el código ejecutado es código administrado, se puede obtener un objeto <xref:System.Threading.Thread> para el subproceso que se ejecuta en el dominio de aplicación actual mediante la recuperación de la propiedad <xref:System.Threading.Thread.CurrentThread%2A> estática de tipo <xref:System.Threading.Thread>. En este tema se describe la creación de subprocesos y se analizan las alternativas para pasar datos al procedimiento de los subprocesos.  
  
## <a name="creating-a-thread"></a>Creación de un subproceso

 Al crear un objeto <xref:System.Threading.Thread>, se crea un subproceso administrado. La clase <xref:System.Threading.Thread> tiene constructores que adoptan un delegado <xref:System.Threading.ThreadStart> o un delegado <xref:System.Threading.ParameterizedThreadStart>; el delegado ajusta el método invocado por el nuevo subproceso cuando llama al método <xref:System.Threading.Thread.Start%2A>. Al llamar a <xref:System.Threading.Thread.Start%2A> más de una vez, se inicia <xref:System.Threading.ThreadStateException>.  
  
 El método <xref:System.Threading.Thread.Start%2A> se devuelve inmediatamente, a menudo antes de que se haya iniciado realmente el nuevo subproceso. Puede usar las propiedades <xref:System.Threading.Thread.ThreadState%2A> y <xref:System.Threading.Thread.IsAlive%2A> para determinar el estado del subproceso en cualquier momento, pero estas propiedades nunca deben utilizarse para sincronizar las actividades de los subprocesos.  
  
> [!NOTE]
> Una vez que se inicia un subproceso, no es necesario conservar una referencia al objeto <xref:System.Threading.Thread>. El subproceso continúa ejecutándose hasta que finaliza el procedimiento del subproceso.  
  
 En el ejemplo de código siguiente se crean dos subprocesos para llamar a métodos estáticos e instancias en otro objeto.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads"></a>Paso de datos a subprocesos

 En .NET Framework 2.0, el delegado <xref:System.Threading.ParameterizedThreadStart> ofrece una forma sencilla de pasar un objeto que contiene datos a un subproceso al llamar a la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>. Vea <xref:System.Threading.ParameterizedThreadStart> para obtener código muestra.  
  
 El uso del delegado <xref:System.Threading.ParameterizedThreadStart> no es una forma con seguridad de tipos de pasar datos, porque la sobrecarga del método <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> acepta cualquier objeto. Una alternativa consiste en encapsular el procedimiento de subprocesos y los datos en una clase del asistente y utilizar el delegado <xref:System.Threading.ThreadStart> para ejecutar el procedimiento de subprocesos. En el siguiente ejemplo se muestra esta técnica:

 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  

Ninguno de estos delegados, <xref:System.Threading.ThreadStart> ni <xref:System.Threading.ParameterizedThreadStart>, tiene un valor devuelto, porque no hay ningún lugar para devolver los datos de una llamada asincrónica. Para recuperar los resultados de un método de subproceso, puede utilizar un método de devolución de llamada, como se muestra en la siguiente sección.
  
## <a name="retrieving-data-from-threads-with-callback-methods"></a>Recuperación de datos de subprocesos con métodos de devolución de llamada

 En el ejemplo siguiente se muestra un método de devolución de llamada que recupera datos de un subproceso. El constructor de la clase que contiene los datos y el método del subproceso también acepta a un delegado que representa el método de devolución de llamada; antes de que finalice el método del subproceso, invoca al delegado de devolución de llamada.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Thread>
- <xref:System.Threading.ThreadStart>
- <xref:System.Threading.ParameterizedThreadStart>
- <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>
- [Subprocesamiento](index.md)
- [Usar subprocesos y subprocesamiento](using-threads-and-threading.md)
