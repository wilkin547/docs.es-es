---
title: "Fundamentos de la recolección de elementos no utilizados"
description: "Fundamentos de la recolección de elementos no utilizados"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
manager: wpickett
ms.date: 08/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 9d5fce64-95a4-4609-8eee-b0ac70078cdb
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 78a2d593329f0703c71df2462cfea30b02adff85

---

# <a name="fundamentals-of-garbage-collection"></a>Fundamentos de la recolección de elementos no utilizados

En el Common Language Runtime (CLR), el recolector de elementos no utilizados actúa como administrador de memoria automático. Proporciona las siguientes ventajas:

* Permite desarrollar la aplicación sin tener que liberar memoria. 

* Asigna con eficacia los objetos del montón administrado. 

* Reclama los objetos que ya no se utilizan, borra la memoria correspondiente y mantiene la memoria disponible para asignaciones futuras. Los objetos administrados obtienen automáticamente contenido limpio desde el principio, de modo que sus constructores no tienen que inicializar todos los campos de datos.

* Proporciona seguridad de memoria, al asegurarse de que un objeto no pueda utilizar el contenido de otro objeto.


En este tema se describen los conceptos básicos de la recolección de elementos no utilizados. Contiene las siguientes secciones:

* [Fundamentos de memoria](#fundamentals-of-memory)

* [Condiciones para la recolección de elementos no utilizados](#conditions-for-a-garbage-collection)

* [Montón administrado](#the-managed-heap)

* [Generaciones](#generations)

* [Lo que sucede durante la recolección de elementos no utilizados](#what-happens-during-a-garbage-collection)

* [Manipular recursos no administrados](#manipulating-unmanaged-resources)

## <a name="fundamentals-of-memory"></a>Fundamentos de memoria

En la lista siguiente se resumen los conceptos importantes de memoria de CLR.

* Cada proceso tiene propio espacio de direcciones virtuales independiente. Todos los procesos del equipo comparten la misma memoria física y comparten el archivo de paginación si hay alguno.

* De forma predeterminada, en los equipos de 32 bits, cada proceso tiene un espacio de direcciones virtuales en modo usuario de 2 GB.

* Como desarrollador de aplicaciones, solo trabaja con el espacio de direcciones virtuales y nunca manipula la memoria física directamente. El recolector de elementos no utilizados asigna y libera memoria virtual en el montón administrado.

* La memoria virtual puede estar en tres estados: 

    * Libre. El bloque de memoria no tiene ninguna referencia a ella y está disponible para su asignación.

    * Reservado. El bloque de memoria está disponible para su uso y no se puede emplear para ninguna otra solicitud de asignación. Sin embargo, no puede almacenar datos en este bloque de memoria hasta que se confirme. 

    * Confirmado. El bloque de memoria se asigna al almacenamiento físico.

* El espacio de direcciones virtuales puede llegar a fragmentarse. Esto significa que hay bloques libres, también conocidos como marcadores, en el espacio de direcciones. Cuando se solicita una asignación de memoria virtual, el administrador de memoria virtual tiene que encontrar un único bloque libre que sea suficientemente grande para satisfacer esa solicitud de asignación. Aunque tenga 2 GB de espacio disponible, la asignación que necesita 2 GB será incorrecta a menos que todo ese espacio esté en un único bloque de direcciones.

* Puede quedarse sin memoria si no tiene espacio de direcciones virtuales para reservar o espacio físico para confirmar.

El archivo de paginación se usa aunque haya poca necesidad de memoria física (es decir, demanda de memoria física). La primera vez que se necesita mucha memoria física, el sistema operativo debe hacer sitio en la memoria física para almacenar los datos y hace una copia de seguridad en el archivo de paginación de algunos datos que están en la memoria física. Esos datos no se paginan hasta que no se necesitan, por lo que es posible encontrar paginación en situaciones donde haya muy poca necesidad de memoria física.

## <a name="conditions-for-a-garbage-collection"></a>Condiciones para la recolección de elementos no utilizados

La recolección de elementos no utilizados se produce cuando se cumple alguna de las siguientes condiciones:

* El sistema tiene poca memoria física.

* La memoria que utilizan los objetos asignados del montón administrado supera un umbral aceptable. Este umbral se ajusta continuamente a medida que se ejecuta el proceso.

* Se llama al método [GC.Collect](xref:System.GC.Collect). En casi todos casos, no es necesario llamar a este método, porque el recolector de elementos no utilizados se ejecuta continuamente. Este método se utiliza principalmente para pruebas y situaciones singulares. 

## <a name="the-managed-heap"></a>Montón administrado

Una vez que el CLR inicializa el recolector de elementos no utilizados, asigna un segmento de memoria para almacenar y administrar objetos. Esta memoria se denomina montón administrado, y se diferencia del montón nativo del sistema operativo. 

Hay un montón administrado para cada proceso administrado. Todos los subprocesos del proceso asignan memoria a los objetos del mismo montón.

> [!IMPORTANT]
> El tamaño de los segmentos asignados por el recolector de elementos no utilizados es específico de la implementación y está sujeto a cambios en cualquier momento, incluso en las actualizaciones periódicas. La aplicación nunca debe realizar suposiciones sobre el tamaño de un sector determinado ni depender de él, y tampoco debe intentar configurar la cantidad de memoria disponible para las asignaciones de segmentos. 
 
Cuantos menos objetos se asignen al montón, menos trabajo tendrá que hacer el recolector de elementos no utilizados. Al asignar objetos, no use valores redondeados que superen sus necesidades; por ejemplo, no asigne una matriz de 32 bytes si solo necesita 15 bytes. 

Cuando se desencadena una recolección de elementos no utilizados, el recolector de elementos no utilizados reclama la memoria ocupada por objetos muertos. El proceso de reclamación compacta los objetos activos para moverlos juntos, y el espacio muerto se quita, para reducir el montón. De este modo, se asegura de que los objetos que se asignan juntos permanezcan juntos en el montón administrado, a fin de conservar su situación.

La tendencia a la intrusión (frecuencia y duración) de las recolecciones de elementos no utilizados es el resultado del volumen de asignaciones y la cantidad de memoria que sobrevivió en el montón administrado. 

El montón considerarse una acumulación de dos montones: el montón de objetos grandes y el montón de objetos pequeños. 

El montón de objetos grandes contiene objetos muy grandes de 85.000 bytes o más. Los objetos del montón de objetos grandes suelen ser matrices. Es raro que un objeto de instancia sea sumamente grande. 

## <a name="generations"></a>Generaciones

El montón se organiza en generaciones, para poder administrar objetos de larga y corta duración. La recolección de elementos no utilizados se produce principalmente con la reclamación de objetos de corta duración que suelen ocupar solamente una parte reducida del montón. Hay tres generaciones de objetos en el montón: 

* **Generación 0.** Es la generación más joven y contiene los objetos de corta duración. Un ejemplo de objeto de corta duración es una variable temporal. La recolección de elementos no utilizados se produce con mayor frecuencia en esta generación. 

  Los objetos recién asignados constituyen una nueva generación de objetos e implícitamente son recolecciones de generación 0, a menos que sean objetos grandes, en cuyo caso entran en el montón de objetos grandes en una recolección de la generación 2.

  La mayoría de los objetos se reclaman para la recolección de elementos no utilizados en la generación 0 y no sobreviven a la generación siguiente. 

* **Generación 1.** Esta generación contiene objetos de corta duración y sirve como búfer entre los objetos de corta y larga duración. 

* **Generación 2.** Esta generación contiene los objetos de larga duración. Un ejemplo de objeto de larga duración es un objeto de una aplicación de servidor que contiene datos estáticos que están activos mientras dura el proceso.

Las recolecciones de elementos no utilizados se producen en generaciones concretas según lo permitan las condiciones. La recolección de una generación significa recolectar los objetos de esa generación y de todas las generaciones anteriores. Una recolección de elementos no utilizados de la generación 2 se denomina también recolección de elementos no utilizados completa, porque reclama todos los objetos de todas las generaciones (es decir, todos los objetos del montón administrado).

### <a name="survival-and-promotions"></a>Supervivencia y promociones

Los objetos que no se reclaman en una recolección de elementos no utilizados se denominan supervivientes y se promueven a la generación siguiente. Los objetos que sobreviven a una recolección de elementos no utilizados de la generación 0 se promueven a la generación 1; los que sobreviven a una recolección de elementos no utilizados de la generación 1 se promueven a la generación 2; y los que sobreviven a una recolección de elementos no utilizados de la generación 2 permanecen en esa misma generación.

Cuando el recolector de elementos no utilizados detecta que la tasa de supervivencia es alta en una generación, aumenta el umbral de asignaciones para esa generación, de modo que la recolección siguiente obtenga un tamaño sustancial de memoria reclamada. El CLR equilibra continuamente dos prioridades: no permitir que el espacio de trabajo de una aplicación adquiera un tamaño excesivo y no permitir que la recolección de elementos no utilizados tarde demasiado tiempo.

### <a name="ephemeral-generations-and-segments"></a>Generaciones y segmentos efímeros

Dado que los objetos de las generaciones 0 y 1 son de corta duración, estas generaciones se denominan generaciones efímeras. 

Las generaciones efímeras se deben asignar en el segmento de memoria denominado segmento efímero. Cada nuevo segmento adquirido por el recolector de elementos no utilizados se convierte en el nuevo segmento efímero y contiene los objetos que sobrevivieron a una recolección de elementos no utilizados de la generación 0. El segmento efímero anterior se convierte en el nuevo segmento de la generación 2. 


El segmento efímero puede incluir objetos de la generación 2. Los objetos de la generación 2 pueden utilizar varios segmentos (tantos como necesite el proceso y la memoria permita). 

La cantidad de memoria liberada como consecuencia de una recolección de elementos no utilizados efímera se limita al tamaño del segmento efímero. La cantidad de memoria que se libera es proporcional al espacio que ocupaban los objetos muertos.

## <a name="what-happens-during-a-garbage-collection"></a>Lo que sucede durante la recolección de elementos no utilizados

Una recolección de elementos no utilizados tiene las siguientes fases: 

* Una fase de marcado que busca y crea una lista de todos los objetos activos.

* Una fase de reubicación, que actualiza las referencias a los objetos que se van a compactar. 

* Una fase de compactación, que reclama el espacio ocupado por los objetos muertos y compacta los objetos supervivientes. En la fase de compactación se mueven los objetos que han sobrevivido a una recolección de elementos no utilizados hacia el extremo más antiguo del segmento. 

Debido a que las recolecciones de la generación 2 pueden ocupar varios segmentos, los objetos que se promueven a la generación 2 se pueden mover a un segmento anterior. Los supervivientes de las generaciones 1 y 2 se pueden mover a un segmento diferente, porque se promueven a la generación 2. 

Normalmente, el montón de objetos grandes no se compacta, porque al copiar objetos grandes se reduce el rendimiento. Pero puede usar la propiedad [GCSettings.LargeObjectHeapCompactionMode](xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode) para compactar el montón de objetos grandes a petición. 

El recolector de elementos no utilizados utiliza la siguiente información para determinar si los objetos están activos: 

* **Raíces de la pila.** Variables de pila proporcionadas por el compilador Just-In-Time (JIT) y el rastreador de pila.

* **Identificadores de recolección de elementos no utilizados.** Identificadores que señalan a objetos administrados y que se pueden asignar mediante código de usuario o mediante Common Language Runtime.

* **Datos estáticos.** Objetos estáticos de dominios de aplicación que podrían hacer referencia a otros objetos. Cada dominio de aplicación realiza el seguimiento de sus objetos estáticos.

Antes de que iniciarse una recolección de elementos no utilizados, todos los subprocesos administrados se suspenden salvo el subproceso que activó la recolección de elementos no utilizados.

En la ilustración siguiente se muestra un subproceso que desencadena una recolección de elementos no utilizados, lo que provoca la suspensión de los demás subprocesos.

![Cuando un subproceso activa una recolección de elementos no utilizados](./media/fundamentals/393001.png)

Subproceso que desencadena una recolección de elementos no utilizados

## <a name="manipulating-unmanaged-resources"></a>Manipular recursos no administrados

Si los objetos administrados hacen referencia a objetos no administrados mediante sus identificadores de archivos nativos, es necesario liberar explícitamente los objetos no administrados, ya que el recolector de elementos no utilizados únicamente realiza el seguimiento de la memoria del montón administrado.

Los usuarios de su objeto administrado podrían no disponer de los recursos nativos utilizados por el objeto. Para realizar la limpieza, puede hacer que su objeto administrado sea susceptible de finalización. La finalización está compuesta de acciones de limpieza que el usuario ejecuta cuando el objeto ya no se utiliza. Cuando el objeto administrados muere, realiza acciones de limpieza que se especifican en su método finalizador.

Cuando se detecta que un objeto susceptible de finalización está muerto, su finalizador se coloca en una cola para que se ejecuten sus acciones de limpieza, pero el objeto en sí se promueve a la generación siguiente. Por tanto, tendrá que esperar hasta la siguiente recolección de elementos no utilizados que se produzca en esa generación (y que no tiene por qué ser necesariamente la próxima recolección de elementos no utilizados) para determinar si se ha recuperado el objeto.

## <a name="see-also"></a>Vea también

[Recolección de elementos no utilizados en .NET](gc.md)



<!--HONumber=Nov16_HO3-->


