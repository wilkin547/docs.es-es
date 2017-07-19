---
title: "Interlocked Operations | Microsoft Docs"
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
  - "Interlocked class, about Interlocked class"
  - "threading [.NET Framework], Interlocked class"
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Interlocked Operations
La clase <xref:System.Threading.Interlocked> proporciona métodos que sincronizan el acceso a una variable compartida por varios subprocesos.  Los subprocesos de diferentes procesos pueden utilizar este mecanismo si la variable está en la memoria compartida.  Las operaciones de bloqueo son atómicas, es decir, el conjunto de la operación constituye una unidad que ninguna otra operación de bloqueo puede interrumpir en la misma variable.  Esto último tiene importancia en sistemas operativos con multithreading preferente, donde se puede suspender un subproceso después de cargar un valor desde una dirección de memoria, pero antes de tener oportunidad de alterarlo y almacenarlo.  
  
 La clase <xref:System.Threading.Interlocked> proporciona las siguientes operaciones:  
  
-   En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.Add%2A> agrega un valor entero a una variable y devuelve el nuevo valor de la variable.  
  
-   En la versión 2.0 de .NET Framework, el método <xref:System.Threading.Interlocked.Read%2A> lee un valor entero de 64 bits como una operación atómica.  Esto resulta útil en sistemas operativos de 32 bits, donde leer un entero de 64 bits no constituye habitualmente una operación atómica.  
  
-   Los métodos <xref:System.Threading.Interlocked.Increment%2A> y <xref:System.Threading.Interlocked.Decrement%2A> incrementan o decrementan una variable y devuelven el valor resultante.  
  
-   El método <xref:System.Threading.Interlocked.Exchange%2A> realiza un intercambio atómico del valor en la variable especificada, devolviendo dicho valor y reemplazándolo por un valor nuevo.  En la versión 2.0 de .NET Framework, puede utilizarse una sobrecarga genérica de este método para realizar este intercambio en una variable con cualquier tipo de referencia.  Vea <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   El método <xref:System.Threading.Interlocked.CompareExchange%2A> también intercambia dos valores, pero en función del resultado de una comparación.  En la versión 2.0 de .NET Framework, puede utilizarse una sobrecarga genérica de este método para realizar este intercambio en una variable con cualquier tipo de referencia.  Vea <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 En los procesadores modernos, los métodos de la clase <xref:System.Threading.Interlocked> a menudo pueden implementarse mediante una única instrucción.  Así, proporcionan una sincronización con un rendimiento muy elevado y pueden utilizarse para compilar mecanismos de sincronización de nivel superior, como bloqueos circulares.  
  
 Para obtener un ejemplo que utiliza las clases <xref:System.Threading.Monitor> y <xref:System.Threading.Interlocked> en combinación, vea [Monitores](../Topic/Monitors.md).  
  
## Ejemplo de CompareExchange  
 El método <xref:System.Threading.Interlocked.CompareExchange%2A> se puede utilizar para proteger cálculos más complicados que un simple incremento y decremento.  En el siguiente ejemplo se muestra un método seguro para subprocesos que se agrega a un total actualizado almacenado como un número de punto flotante. \(En el caso de los números enteros, el método <xref:System.Threading.Interlocked.Add%2A> constituye una solución más sencilla.\) Para obtener ejemplos de código completos, vea las sobrecargas de <xref:System.Threading.Interlocked.CompareExchange%2A> que toma argumentos de punto flotante de precisión sencilla y doble \(<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> y <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>\).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## Sobrecargas sin tipo de Exchange y CompareExchange  
 Los métodos <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> disponen de sobrecargas que aceptan argumentos de tipo <xref:System.Object>.  El primer argumento de cada una de estas sobrecargas es `ref Object` \(`ByRef … As Object` en Visual Basic\) y la seguridad de tipos requiere que se pase la variable a este argumento para que sea estrictamente de tipo <xref:System.Object>; no se puede transformar simplemente el primer argumento a tipo <xref:System.Object> cuando se realiza la llamada a estos métodos.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, utilice las sobrecargas genéricas de los métodos <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> para intercambiar variables fuertemente tipadas.  
  
 En el siguiente ejemplo de código se muestra una propiedad de tipo `ClassA` que sólo puede establecerse una vez, ya que debería implementarse en la versión 1.0 o 1.1 de .NET Framework.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## Vea también  
 <xref:System.Threading.Interlocked>   
 <xref:System.Threading.Monitor>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)