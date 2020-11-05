---
title: 'Almacenamiento local de subprocesos: Campos estáticos relacionados con subprocesos y ranuras de datos'
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET], local storage
- threading [.NET], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
ms.openlocfilehash: f80cc09d87116d3daff8047c1d1398c5e6104178
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188164"
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Almacenamiento local de subprocesos: Campos estáticos relacionados con subprocesos y ranuras de datos

Puede usar el almacenamiento local para el subproceso (TLS) administrado a fin de almacenar los datos que sean exclusivos de un subproceso y un dominio de la aplicación. .NET proporciona dos maneras de usar el TLS administrado: ranuras para datos y campos estáticos relacionados con subprocesos.  
  
- Use campos estáticos relacionados con subprocesos (campos `Shared` relacionados con subprocesos en Visual Basic) si puede anticipar las necesidades exactas en tiempo de compilación. Los campos estáticos relacionados con subprocesos proporcionan el mejor rendimiento. También proporcionan las ventajas de la comprobación de tipos en tiempo de compilación.  
  
- Use las ranuras de datos si se pueden detectar los requisitos reales solo en tiempo de ejecución. Las ranuras de datos son más lentas y más difíciles de usar que los campos estáticos relacionados con subprocesos, y los datos se almacenan como tipos <xref:System.Object>, por lo que debe convertirlos al tipo correcto antes de utilizarlos.  
  
 En C++ no administrado, use `TlsAlloc` para asignar ranuras de forma dinámica y `__declspec(thread)` para declarar que una variable debería asignarse en el almacenamiento relacionado con los subprocesos. Los campos estáticos y las ranuras para datos relacionados con los subprocesos proporcionan la versión administrada de este comportamiento.  
  
Puede usar la clase <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> para crear objetos locales de subprocesos que se inicializan de forma diferida la primera vez que se usa el objeto. Para obtener más información, vea [Inicialización diferida](../../framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Unicidad de los datos en la TLS administrada  
 Si usa los campos estáticos o las ranuras para datos relacionados con subprocesos, los datos de la TLS administrada son exclusivos de la combinación de subproceso y dominio de aplicación.  
  
- Dentro de un dominio de aplicación, un subproceso no puede modificar datos de otro subproceso, aunque ambos subprocesos utilicen el mismo campo o ranura.  
  
- Cuando un subproceso accede al mismo campo o ranura desde varios dominios de aplicación, se mantiene un valor independiente en cada dominio de aplicación.  
  
 Por ejemplo, si un subproceso establece el valor de un campo estático relacionado con el subproceso, escribe otro dominio de aplicación y luego recupera el valor del campo, entonces el valor recuperado en el segundo dominio de aplicación difiere del valor del primer dominio de aplicación. Establecer un nuevo valor para el campo del segundo dominio de aplicación no influye en el valor del campo del primer dominio de aplicación.  
  
 De forma similar, si un subproceso obtiene la ranura para datos con el mismo nombre en dos dominios de aplicación distintos, los datos del primer dominio de aplicación son independientes de los datos del segundo dominio de aplicación.  
  
## <a name="thread-relative-static-fields"></a>Campos estáticos relacionados con subprocesos  
 Si sabe que un elemento de datos siempre es exclusivo para una combinación de dominio de aplicación y subproceso, aplique el atributo <xref:System.ThreadStaticAttribute> al campo estático. Utilice el campo como utilizaría cualquier otro campo estático. Los datos del campo son exclusivos para cada subproceso que los use.  
  
 Los campos estáticos relacionados con subprocesos ofrecen mayor rendimiento que las ranuras para datos y, además, tienen la ventaja de la comprobación de tipos en tiempo de compilación.  
  
 Tenga en cuenta que cualquier código del constructor de clase se ejecutará en el primer subproceso del primer contexto que acceda al campo. En todos los demás subprocesos o contextos del mismo dominio de aplicación, los campos se inicializarán como `null` (`Nothing` en Visual Basic) si son tipos de referencia o como valores predeterminados si son tipos de valor. Por lo tanto, no debe basarse en los constructores de clase para inicializar campos estáticos relacionados con subprocesos. En su lugar, evite inicializar los campos estáticos relacionados con subprocesos y suponga que se han inicializado como `null` (`Nothing`) o con sus valores predeterminados.  
  
## <a name="data-slots"></a>Ranuras para datos  

.NET proporciona ranuras para datos dinámicos exclusivas para la combinación de subproceso y dominio de la aplicación. Hay dos tipos de ranuras para datos: ranuras con nombre y ranuras sin nombre. Ambos tipos se implementan mediante la estructura <xref:System.LocalDataStoreSlot>.  
  
- Para crear una ranura de datos con nombre, use los métodos <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> o <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>. Para obtener una referencia a una ranura con nombre existente, pase su nombre al método <xref:System.Threading.Thread.GetNamedDataSlot%2A>.  
  
- Para crear una ranura para datos sin nombre, use el método <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType>.  
  
 Para las ranuras con nombre y sin nombre, use los métodos <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> y <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> para establecer y recuperar la información en la ranura. Se trata de métodos estáticos que siempre actúan en los datos para el subproceso que los ejecuta actualmente.  
  
 Las ranuras con nombre pueden ser prácticas, porque puede recuperar la ranura cuando lo necesite pasando su nombre al método <xref:System.Threading.Thread.GetNamedDataSlot%2A>, en lugar de mantener una referencia a una ranura sin nombre. Sin embargo, si otro componente usa el mismo nombre para su almacenamiento relacionado con subprocesos y un subproceso ejecuta código desde el componente y el otro componente, los dos componentes podrían dañar los datos del otro. (En este escenario se supone que ambos componentes se ejecutan en el mismo dominio de aplicación y que no están diseñados para compartir los mismos datos).  
  
## <a name="see-also"></a>Vea también

- <xref:System.ContextStaticAttribute>
- <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>
- <xref:System.ThreadStaticAttribute>
- <xref:System.Runtime.Remoting.Messaging.CallContext>
- [Subprocesamiento](index.md)
