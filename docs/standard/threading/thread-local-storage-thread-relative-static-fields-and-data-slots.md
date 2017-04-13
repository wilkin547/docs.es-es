---
title: "Thread Local Storage: Thread-Relative Static Fields and Data Slots | Microsoft Docs"
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
  - "threading [.NET Framework], local storage"
  - "threading [.NET Framework], thread-relative static fields"
  - "local thread storage"
  - "TLS"
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Thread Local Storage: Thread-Relative Static Fields and Data Slots
Puede usar TSL \(Thread Local Storage, almacenamiento local de subprocesos\) para almacenar datos que sean exclusivos de un subproceso y dominio de aplicación.  .NET Framework permite utilizar TLS administrado de dos maneras: campos estáticos relacionados con subprocesos y ranuras de datos.  
  
-   Si puede anticipar sus necesidades exactas en el momento de la compilación, utilice campos estáticos relacionados con subprocesos \(campos `Shared` relacionados con subprocesos en Visual Basic\).  Los campos estáticos relacionados con subprocesos proporcionan el máximo rendimiento.  También ofrecen las ventajas de la comprobación de tipos en tiempo de compilación.  
  
-   Utilice ranuras de datos cuando las necesidades reales sólo se puedan detectar en tiempo de ejecución.  Las ranuras de datos son más lentas y tediosas de usar que los campos estáticos relacionados con subprocesos, y los datos se almacenan con el tipo <xref:System.Object>, por lo que debe convertirlos al tipo correcto antes de utilizarlos.  
  
 En C\+\+ no administrado, se utiliza `TlsAlloc` para asignar ranuras de forma dinámica y `__declspec(thread)` para declarar que una variable debe asignarse a un almacenamiento relacionado con subprocesos.  Los campos estáticos relacionados con subprocesos y las ranuras de datos ofrecen la versión administrada de este comportamiento.  
  
 En [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], puede usar la clase <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> para crear objetos de subprocesos locales que se inicializan de forma diferida la primera vez que se consume el objeto.  Para obtener más información, vea [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).  
  
## Exclusividad de los datos en TLS administrado  
 Tanto si utiliza campos estáticos relacionados con subprocesos o ranuras de datos, los datos de TLS administrado son exclusivos de la combinación de subproceso y dominio de aplicación.  
  
-   En un dominio de aplicación, un subproceso no puede modificar los datos de otro subproceso, aunque ambos subprocesos utilicen el mismo campo o ranura.  
  
-   Cuando un subproceso tiene acceso al mismo campo o ranura de varios dominios de aplicación, se mantiene un valor independiente en cada dominio de aplicación.  
  
 Por ejemplo, si un subproceso establece el valor de un campo estático relacionado con subprocesos, entra en otro dominio de aplicación y, a continuación, recupera el valor del campo, el valor recuperado en el segundo dominio de aplicación difiere del valor en el primer dominio de aplicación.  Establecer un nuevo valor para el campo en el segundo dominio de aplicación no afecta al valor del campo en el primer dominio de aplicación.  
  
 De igual forma, cuando un subproceso obtiene la misma ranura de datos con nombre en dos dominios de aplicación diferentes, los datos del primer dominio de aplicación son independientes de los datos del segundo dominio de aplicación.  
  
## Campos estáticos relacionados con subprocesos  
 Si sabe que un dato siempre es exclusivo de una combinación de subproceso y dominio de aplicación, aplique el atributo <xref:System.ThreadStaticAttribute> al campo estático.  Utilice el campo igual que cualquier otro campo estático.  Los datos del campo son exclusivos de cada subproceso que los utiliza.  
  
 Los campos estáticos relacionados con subprocesos proporcionan un rendimiento mejor que las ranuras de datos y tienen la ventaja de que comprueban los tipos en tiempo de compilación.  
  
 Tenga en cuenta que cualquier código constructor de clases se ejecutará en el primer subproceso del primer contexto que tenga acceso al campo.  En todos los demás subprocesos o contextos del mismo dominio de aplicación, los campos se inicializarán en `null` \(`Nothing` en Visual Basic\) si son tipos de referencia, o en sus valores predeterminados si son tipos de valor.  Por consiguiente, no debe confiar en los constructores de clases para inicializar campos estáticos relacionados con subprocesos.  En su lugar, evite inicializar los campos estáticos relacionados con subprocesos y asuma que se inicializan en `null` \(`Nothing`\) o en sus valores predeterminados.  
  
## Ranuras de datos  
 .NET Framework proporciona ranuras de datos dinámicos que son exclusivas de una combinación de dominio de aplicación y subproceso.  Hay dos tipos de ranuras de datos: con nombre y sin nombre.  Ambas se implementan mediante la estructura <xref:System.LocalDataStoreSlot>.  
  
-   Para crear una ranura de datos con nombre, utilice el método <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=fullName> o <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName>.  Para obtener una referencia a una ranura con nombre existente, pase su nombre al método <xref:System.Threading.Thread.GetNamedDataSlot%2A>.  
  
-   Para crear una ranura de datos sin nombre, utilice el método <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=fullName>.  
  
 Para las ranuras con nombre y sin nombre, utilice los métodos <xref:System.Threading.Thread.SetData%2A?displayProperty=fullName> y <xref:System.Threading.Thread.GetData%2A?displayProperty=fullName> para establecer y recuperar la información de la ranura.  Éstos son métodos estáticos que siempre representan los datos del subproceso que los está ejecutando.  
  
 Las ranuras con nombre pueden resultar cómodas, porque puede recuperar la ranura cuando lo necesite pasando su nombre al método <xref:System.Threading.Thread.GetNamedDataSlot%2A>, en lugar de mantener una referencia a una ranura sin nombre.  Sin embargo, si otro componente usa el mismo nombre para su propio almacenamiento relacionado con subprocesos y un subproceso ejecuta código tanto de su componente como del otro, ambos componentes podrían dañar los datos del otro. \(En este escenario se supone que ambos componentes se están ejecutando en el mismo dominio de aplicación y que no están diseñados para compartir los mismos datos.\)  
  
## Vea también  
 <xref:System.ContextStaticAttribute>   
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName>   
 <xref:System.ThreadStaticAttribute>   
 <xref:System.Runtime.Remoting.Messaging.CallContext>   
 [Threading](../../../docs/standard/threading/index.md)