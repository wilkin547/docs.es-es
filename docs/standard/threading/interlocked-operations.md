---
title: Operaciones de bloqueo
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6f96286da84e41e79fb0b6253d6f20eea89da21a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2018
ms.locfileid: "50201362"
---
# <a name="interlocked-operations"></a>Operaciones de bloqueo

La clase <xref:System.Threading.Interlocked?displayProperty=nameWithType> proporciona métodos que sincronizan el acceso a una variable que comparten varios subprocesos. Los subprocesos de distintos procesos pueden usar este mecanismo si la variable está en una memoria compartida. Las operaciones de bloqueo son atómicas, es decir, toda la operación es una unidad que no se puede interrumpir por otra operación en la misma variable. Esto es importante en los sistemas operativos con multithreading preferente, donde se puede suspender un subproceso después de cargar un valor desde una dirección de memoria, pero antes de tener la oportunidad de alterarlo y almacenarlo.  
  
 La clase <xref:System.Threading.Interlocked> proporciona las siguientes operaciones:  
  
-   El método <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType> agrega un valor entero a una variable y devuelve el valor nuevo de la variable.  
  
-   El método <xref:System.Threading.Interlocked.Read%2A?displayProperty=nameWithType> lee un valor entero de 64 bits como una operación atómica. Esto resulta útil en los sistemas operativos de 32 bits, en los que leer un entero de 64 bits no es habitualmente una operación atómica.  
  
-   Los métodos <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType> y <xref:System.Threading.Interlocked.Decrement%2A?displayProperty=nameWithType> incrementan o disminuyen una variable y devuelven el valor resultante.  
  
-   El método <xref:System.Threading.Interlocked.Exchange%2A?displayProperty=nameWithType> realiza un intercambio atómico del valor en una variable especificada, devolviendo ese valor y reemplazándolo por un valor nuevo. Use una sobrecarga <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29> genérica de este método para realizar el intercambio en una variable de cualquier tipo de referencia.  
  
-   El método <xref:System.Threading.Interlocked.CompareExchange%2A?displayProperty=nameWithType> también intercambia dos valores, pero en función del resultado de una comparación. Use una sobrecarga <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29> genérica de este método para realizar el intercambio en una variable de cualquier tipo de referencia.  
  
 En los procesadores modernos, los métodos de la clase <xref:System.Threading.Interlocked> habitualmente se pueden implementar con una sola instrucción. De este modo, proporcionan una sincronización de rendimiento muy elevado y se pueden usar para crear mecanismos de sincronización de nivel superior, como bloqueos de giro.  
  
 Para consultar un ejemplo que usa las clases <xref:System.Threading.Monitor> y <xref:System.Threading.Interlocked> de forma combinada, vea <xref:System.Threading.Monitor>.  
  
## <a name="compareexchange-example"></a>Ejemplo de CompareExchange

 El método <xref:System.Threading.Interlocked.CompareExchange%2A> se puede usar para proteger cálculos más complicados que un simple incremento y decremento. El ejemplo siguiente muestra un método seguro para subprocesos que se agrega a un total acumulado almacenado como número de punto flotante. (Para números enteros, el método <xref:System.Threading.Interlocked.Add%2A> es una solución más sencilla). Para obtener ejemplos de código completos, vea las sobrecargas de <xref:System.Threading.Interlocked.CompareExchange%2A> que adoptan argumentos de punto flotante de precisión simple y doble precisión (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> y <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Sobrecargas de Exchange y CompareExchange sin tipo

 Los métodos <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> tienen sobrecargas que adoptan argumentos de tipo <xref:System.Object>. El primer argumento de cada una de estas sobrecargas es `ref Object` (`ByRef … As Object` en Visual Basic) y la seguridad de tipos requiere que la variable que se transmite a este argumento tenga estrictamente el tipo <xref:System.Object>; no puede simplemente transformar el primer argumento al tipo <xref:System.Object> cuando se llama a estos métodos.  
  
> [!NOTE]
>  En .NET Framework 2.0 y versiones posteriores, use las sobrecargas genéricas de los métodos <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> para intercambiar variables fuertemente tipadas.  
  
 El ejemplo de código siguiente muestra una propiedad de tipo`ClassA` que solo se puede establecer una vez, tal como se podría implementar en la versión 1.0 o 1.1 de .NET Framework.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Threading.Interlocked?displayProperty=nameWithType>  
- <xref:System.Threading.Monitor?displayProperty=nameWithType>  
- [Subprocesamiento](index.md)  
- [Objetos y características de subprocesos](threading-objects-and-features.md)
