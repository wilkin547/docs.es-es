---
title: Operaciones de bloqueo
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
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>Operaciones de bloqueo
La <xref:System.Threading.Interlocked> clase proporciona métodos que sincronización el acceso a una variable compartida por varios subprocesos. Los subprocesos de distintos procesos pueden usar este mecanismo si la variable está en una memoria compartida. Las operaciones de bloqueo son atómicas, es decir, toda la operación es una unidad que no se puede interrumpir por otra operación de bloqueo en la misma variable. Esto es importante en los sistemas operativos con multithreading preferente, donde se puede suspender un subproceso después de cargar un valor desde una dirección de memoria, pero antes de tener la oportunidad de alterarlo y almacenarlo.  
  
 La <xref:System.Threading.Interlocked> clase proporciona las siguientes operaciones:  
  
-   En .NET Framework versión 2.0, el <xref:System.Threading.Interlocked.Add%2A> método agrega un valor entero a una variable y devuelve el nuevo valor de la variable.  
  
-   En .NET Framework versión 2.0, el <xref:System.Threading.Interlocked.Read%2A> método lee un valor entero de 64 bits como una operación atómica. Esto resulta útil en los sistemas operativos de 32 bits, en los que leer un entero de 64 bits no es habitualmente una operación atómica.  
  
-   El <xref:System.Threading.Interlocked.Increment%2A> y <xref:System.Threading.Interlocked.Decrement%2A> métodos incrementar o disminuir una variable y devuelven el valor resultante.  
  
-   El <xref:System.Threading.Interlocked.Exchange%2A> método realiza un intercambio atómico del valor en una variable especificada, que no devuelve ese valor y reemplazarlo con un nuevo valor. En la versión 2.0 de .NET Framework, se puede usar una sobrecarga genérica de este método para realizar este intercambio en una variable de cualquier tipo de referencia. Consulta <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   El <xref:System.Threading.Interlocked.CompareExchange%2A> método también intercambia dos valores, pero el resultado de una comparación. En la versión 2.0 de .NET Framework, se puede usar una sobrecarga genérica de este método para realizar este intercambio en una variable de cualquier tipo de referencia. Consulta <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 En los procesadores modernos, los métodos de la <xref:System.Threading.Interlocked> clase a menudo puede implementarse mediante una única instrucción. De este modo, proporcionan una sincronización de rendimiento muy elevado y se pueden usar para crear mecanismos de sincronización de nivel superior, como bloqueos de giro.  
  
 Para obtener un ejemplo que usa el <xref:System.Threading.Monitor> y <xref:System.Threading.Interlocked> clases de combinación, vea el artículo [monitores](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>Ejemplo de CompareExchange  
 El <xref:System.Threading.Interlocked.CompareExchange%2A> método se puede utilizar para proteger cálculos que son más complicados que simple incremento y decremento. El ejemplo siguiente muestra un método seguro para subprocesos que se agrega a un total acumulado almacenado como número de punto flotante. (Para números enteros, el <xref:System.Threading.Interlocked.Add%2A> método es una solución más sencilla.) Para obtener ejemplos de código completo, vea las sobrecargas de <xref:System.Threading.Interlocked.CompareExchange%2A> que toman argumentos de punto flotante de precisión simple y doble precisión (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> y <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Sobrecargas de Exchange y CompareExchange sin tipo  
 El <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> métodos tienen sobrecargas que toman argumentos de tipo <xref:System.Object>. El primer argumento de cada una de estas sobrecargas es `ref Object` (`ByRef … As Object` en Visual Basic), y seguridad de tipos requiere que la variable que se pasa a este argumento para que sea estrictamente de tipo como <xref:System.Object>; simplemente no se puede convertir el primer argumento de tipo <xref:System.Object> Cuando se llama a estos métodos.  
  
> [!NOTE]
>  En la versión 2.0 de .NET Framework, use las sobrecargas genéricas de la <xref:System.Threading.Interlocked.Exchange%2A> y <xref:System.Threading.Interlocked.CompareExchange%2A> métodos para intercambiar fuertemente tipados variables.  
  
 El ejemplo de código siguiente muestra una propiedad de tipo`ClassA` que solo se puede establecer una vez, tal como se podría implementar en la versión 1.0 o 1.1 de .NET Framework.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)  
 [Objetos y características de subprocesos](../../../docs/standard/threading/threading-objects-and-features.md)
