---
title: "Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>Almacenamiento local para el subproceso: Campos estáticos relacionados con subproceso y ranuras de datos
Puede usar el almacenamiento local de subprocesos administrados (TLS) para almacenar los datos que sea único en un subproceso y dominio de aplicación. .NET Framework proporciona dos maneras de utilizar TLS administrado: relacionados con subprocesos estáticas campos y ranuras de datos.  
  
-   Usar campos estáticos relacionados con subprocesos (relacionados con subprocesos `Shared` campos en Visual Basic) si puede anticipar sus necesidades exactas en tiempo de compilación. Campos estáticos relacionados con subprocesos proporcionan el mejor rendimiento. También proporcionan las ventajas de la comprobación de tipos en tiempo de compilación.  
  
-   Use las ranuras de datos cuando los requisitos reales pueden detectarse en tiempo de ejecución. Las ranuras de datos son más lento y más difícil de usar que los campos estáticos relacionados con subprocesos y datos se almacenan como tipo <xref:System.Object>, por lo que debe convertir al tipo correcto antes de utilizarla.  
  
 En C++ no administrado, use `TlsAlloc` para asignar ranuras de forma dinámica y `__declspec(thread)` para declarar que una variable debería asignarse en almacenamiento de información relacionados con subprocesos. Las ranuras estáticas de campos y los datos relacionados con subprocesos proporcionan la versión administrada de este comportamiento.  
  
 En el [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar el <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> clase para crear objetos de subprocesos locales que se inicializan de forma diferida cuando primero se consume el objeto. Para obtener más información, vea [Inicialización diferida](../../../docs/framework/performance/lazy-initialization.md).  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>Unicidad de los datos en TLS administrado  
 Si usas los campos estáticos relacionados con subprocesos y ranuras de datos, datos en TLS administrado sean únicos para la combinación de subproceso y dominio de aplicación.  
  
-   Dentro de un dominio de aplicación, un subproceso no puede modificar datos desde otro subproceso, aunque ambos subprocesos utilicen el mismo campo o ranura.  
  
-   Cuando un subproceso tiene acceso el mismo campo o ranura desde varios dominios de aplicación, se mantiene un valor independiente en cada dominio de aplicación.  
  
 Por ejemplo, si un subproceso establece el valor de un campo estático relacionados con subprocesos, entra en otro dominio de aplicación y, a continuación, recupera el valor del campo, el valor recuperado en el segundo dominio de aplicación difiere del valor en el primer dominio de aplicación. Establecer un nuevo valor para el campo en el segundo dominio de aplicación no influye en el valor del campo en el primer dominio de aplicación.  
  
 De forma similar, cuando un subproceso obtiene la misma ranura de datos con nombre en dos dominios de aplicación diferentes, los datos en el primer dominio de aplicación permanecen independientes de los datos en el segundo dominio de aplicación.  
  
## <a name="thread-relative-static-fields"></a>Campos estáticos relacionados con subprocesos  
 Si sabe que un elemento de datos siempre es único para una combinación de dominio de aplicación y un subproceso, aplique el <xref:System.ThreadStaticAttribute> de atributo en el campo estático. Utilice el campo como utilizaría cualquier otro campo estático. Los datos en el campo son únicos para cada subproceso que lo utilice.  
  
 Campos estáticos relacionados con subprocesos proporcionan un rendimiento mejor que las ranuras de datos y tienen la ventaja de comprobación de tipos en tiempo de compilación.  
  
 Tenga en cuenta que cualquier código del constructor de clase se ejecutará en el primer subproceso del primer contexto que tenga acceso al campo. En todos los demás subprocesos o contextos en el mismo dominio de aplicación, los campos se inicializarán en `null` (`Nothing` en Visual Basic) si son tipos de referencia, o en su valor predeterminado valores si son tipos de valor. Por lo tanto, no debe confiar en los constructores de clases para inicializar campos estáticos relacionados con subprocesos. En su lugar, evite inicializar los campos estáticos relacionados con subprocesos y suponga que se hayan inicializado con `null` (`Nothing`) o con sus valores predeterminados.  
  
## <a name="data-slots"></a>Ranuras de datos  
 .NET Framework proporciona las ranuras de datos dinámicos que son únicas en una combinación de subproceso y dominio de aplicación. Hay dos tipos de ranuras de datos: con nombre y sin nombre. Ambos se implementan utilizando la <xref:System.LocalDataStoreSlot> estructura.  
  
-   Para crear una ranura de datos con nombre, use la <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> o <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> método. Para obtener una referencia a una ranura con nombre existente, pase su nombre a la <xref:System.Threading.Thread.GetNamedDataSlot%2A> método.  
  
-   Para crear una ranura de datos sin nombre, use la <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> método.  
  
 Para ambos con y sin nombre ranuras, use la <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> y <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> métodos para establecer y recuperar la información de la ranura. Se trata de métodos estáticos que siempre actúan en los datos para el subproceso que está ejecutando actualmente en ellos.  
  
 Las ranuras con nombre pueden ser conveniente, porque puede recuperar la ranura cuando lo necesite pasando su nombre a la <xref:System.Threading.Thread.GetNamedDataSlot%2A> método, en lugar de mantener una referencia a una ranura sin nombre. Sin embargo, si otro componente usa el mismo nombre para su almacenamiento relacionados con subprocesos y un subproceso ejecuta código desde el componente y el otro componente, los dos componentes podrían dañar los datos de todas las demás. (Este escenario se supone que ambos componentes se ejecutan en el mismo dominio de aplicación y que no están diseñados para compartir los mismos datos).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [Subprocesamiento](../../../docs/standard/threading/index.md)
