---
title: Montón de objetos grandes en Windows
ms.date: 05/02/2018
helpviewer_keywords:
- large object heap (LOH)"
- LOH
- garbage collection, large object heap
- GC [.NET ], large object heap
ms.openlocfilehash: ab9beca58b3d6118bc0f5121b6f5dec71a9f9f36
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102273"
---
# <a name="the-large-object-heap-on-windows-systems"></a>Montón de objetos grandes en sistemas Windows

El recolector de elementos no utilizados de .NET divide los objetos en pequeños y grandes. Cuando un objeto es grande, algunos de sus atributos son más importantes que si fuera pequeño. Por ejemplo, su compactación (es decir, copiarlo en memoria en cualquier parte del montón) puede resultar cara. Por este motivo, el recolector de elementos no utilizados de .NET coloca los objetos grandes en el montón de objetos grandes. En este artículo nos centraremos en qué caracteriza a un objeto como objeto grande, cómo se recolectan objetos grandes y qué tipo de implicaciones de rendimiento conllevan los objetos grandes.

> [!IMPORTANT]
> También hablaremos del montón de objetos grandes en .NET Framework y .NET Core solo cuando se ejecutan en sistemas Windows. No se aborda el montón de objetos grandes en implementaciones de .NET en otras plataformas.

## <a name="how-an-object-ends-up-on-the-loh"></a>Cómo termina un objeto en el montón de objetos grandes

Si un objeto tiene un tamaño mayor o igual que 85 000 bytes, se considera un objeto grande. Este número venía determinado por el ajuste de rendimiento. Cuando una solicitud de asignación de objeto es de 85 000 o más bytes, el tiempo de ejecución la asigna al montón de objetos grandes.

Para entender lo que esto significa, viene bien examinar algunos conceptos básicos relativos al recolector de elementos no utilizados.

El recolector de elementos no utilizados es un recolector generacional; es decir, tiene tres generaciones: generación 0, generación 1 y generación 2. El motivo para tener tres generaciones reside en que, en una aplicación bien ajustada, la mayoría de los objetos no pasa de la generación 0. Por ejemplo, en una aplicación de servidor, las asignaciones asociadas a cada solicitud deben agotarse después de que la solicitud finalice. Las solicitudes de asignación al vuelo pasarán a la generación 1 y allí dejarán de estar activas. Básicamente, la generación 1 actúa de búfer entre las áreas de objetos jóvenes y las áreas de objetos de larga vida.

Los objetos pequeños siempre se asignan en la generación 0 y, según cuál sea su duración, pueden subir a la generación 1 o a la generación 2. Los objetos grandes siempre se asignan a la generación 2.

Los objetos grandes pertenecen a la generación 2 porque se recolectan únicamente durante una recolección de generación 2. Cuando una generación se recolecta, también se recolectan todas sus generaciones más jóvenes. Por ejemplo, cuando se produce una recolección de elementos no utilizados de generación 1, se recolectan las generaciones 1 y 0, mientras que, cuando se produce una de generación 2, se recolecta todo el montón. Este es el motivo por el que las recolecciones de elementos no utilizados de generación 2 también se conocen como *recolecciones de elementos no utilizados completas*. En este artículo hablaremos de recolecciones de elementos no utilizados de generación 2 en lugar completas, si bien ambas son indistintas.

Las generaciones proporcionan una vista lógica del montón del recolector de elementos no utilizados. Físicamente, los objetos se encuentran en segmentos de montón administrado. Un *segmento de montón administrado* es un fragmento de memoria que el recolector de elementos no utilizados reserva del sistema operativo, para lo cual llama a la [función VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) en nombre del código administrado. Cuando el CLR se carga, el recolector de elementos no utilizados asigna dos segmentos de montón iniciales: uno para objetos pequeños (montón de objetos pequeños) y otro para objetos grandes (montón de objetos grandes).

Tras ello, las solicitudes de asignación se cumplen colocando objetos administrados en cualquiera de estos dos segmentos de montón administrados. Si el objeto tiene un tamaño inferior a 85 000 bytes, se coloca en el segmento de montón de objetos pequeños y, si no, se coloca en el segmento de montón de objetos grandes. Los segmentos se confirman (en fragmentos menores) a medida que más y más objetos se asignan a ellos.
En el montón de objetos pequeños, aquellos objetos que sobrevivan a una recolección de elementos no utilizados se promueven a la siguiente generación. Los objetos que sobrevivan a una recolección de generación 0 pasarán a considerarse objetos de la generación 1, y así sucesivamente. En cambio, los objetos que sobrevivan a la generación más antigua se seguirán considerando pertenecientes a ella. Es decir, los supervivientes de la generación 2 son objetos de la generación 2 y los supervivientes del montón de objeto grande serán objetos de montón de objeto grande (que se recolectan con la generación 2).

El código de usuario solo puede realizar la asignación en la generación 0 (objetos pequeños) o el montón de objetos grandes (objetos grandes). El recolector de elementos no utilizados es el único que puede "asignar" objetos en la generación 1 (promoviendo los supervivientes de la generación 0) y en la generación 2 (promoviendo los supervivientes de las generaciones 1 y 2).

Cuando se activa una recolección de elementos no utilizados, el recolector de elementos no utilizados realiza el seguimiento de los objetos activos y los compacta. Pero, dado que la compactación resulta cara, el recolector de elementos no utilizados *barre* el montón de objetos grandes; dicho de otro modo, confecciona una lista de los objetos inactivos que se puedan reutilizar más adelante para satisfacer las solicitudes de asignación de objetos grandes. Los objetos inactivos adyacentes se convierten en un objeto libre.

.NET Core y .NET Framework (a partir de .NET Framework 4.5.1) incluyen la propiedad <xref:System.Runtime.GCSettings.LargeObjectHeapCompactionMode?displayProperty=nameWithType>, con la que los usuarios pueden especificar que el montón de objetos grandes se compacte durante la siguiente recolección de elementos no utilizados de bloqueo completo. En un futuro próximo, cabrá la posibilidad de que .NET decida compactar el montón de objetos grandes automáticamente. Esto significa que, si asigna objetos grandes y quiere asegurarse de que no se mueven, deberá fijarlos.

En la figura 1 se ilustra un escenario en el que el recolector de elementos no utilizados crea la generación 1 después de la primera recolección de elementos no utilizados de generación 0, donde `Obj1` y `Obj3` están inactivos, y crea la generación 2 después de la primera recolección de elementos no utilizados de generación 1, donde `Obj2` y `Obj5` están inactivos. Cabe mencionar que tanto esta como las demás figuras se muestran a título meramente ilustrativo; contienen muy pocos objetos para mostrar de mejor forma lo que sucede en el montón. En realidad, en una recolección de elementos no utilizados suele haber muchos más objetos.

![Figura 1: recolecciones de elementos no utilizados de generación 0 y de generación 1](media/loh/loh-figure-1.jpg)\
Figura 1: recolecciones de elementos no utilizados de generación 0 y de generación 1.

En la figura 2 se muestra que, después de una recolección de elementos no utilizados de generación 2 en la que se apreciaba que `Obj1` y `Obj2` estaban inactivos, el recolector de elementos no utilizados libera el espacio en memoria que solía estar ocupado por `Obj1` y `Obj2`, que pasa a usarse para cumplir una solicitud de asignación de `Obj4`. El espacio que hay después del último objeto, `Obj3`, hasta el final del segmento se puede usar también para cumplir solicitudes de asignación.

![Figura 2: Después de una recolección de elementos no utilizados de generación 2](media/loh/loh-figure-2.jpg)\
Figura 2: Después de una recolección de elementos no utilizados de generación 2

Si no existe suficiente espacio libre para las solicitudes de asignación de objeto grande, el recolector de elementos no utilizados intenta primero adquirir más segmentos del sistema operativo. Si esto no sirve, activa una recolección de elementos no utilizados de generación 2 con la esperanza de liberar algo de espacio.

Durante una recolección de elementos no utilizados de generación 1 o de generación 2, el recolector de elementos no utilizados libera los segmentos que no tengan objetos activos para el sistema operativo (llamando a la función [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree)). De este modo, se anula la confirmación del espacio tras el último objeto activo hasta el final del segmento (excepto en el segmento efímero de las generaciones 0 y 1, donde el recolector de elementos no utilizados mantiene confirmado algo de espacio, ya que es posible que la aplicación lo asigne inmediatamente). Además, los espacios libres se quedan confirmados aunque se restablezcan, lo que significa que el sistema operativo no necesita escribir los datos que contienen al disco.

Como el montón de objetos grandes solo se recopila durante las recolecciones de elementos no utilizados de generación 2, el segmento del montón de objetos grandes solo se puede liberar durante una recolección de este tipo. En la figura 3 se ilustra un escenario en el que el recolector de elementos no utilizados libera un segmento (segmento 2) para el sistema operativo y anula la confirmación de más espacio en los segmentos restantes. Si necesitara usar el espacio que no está confirmado al final del segmento para cumplir asignaciones de objetos grandes, confirmará la memoria de nuevo. Para obtener una explicación sobre cómo confirmar/anular confirmaciones, vea la documentación de [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc).

![Figura 3: Montón de objetos grandes después de una recolección de elementos no utilizados de generación 2](media/loh/loh-figure-3.jpg)\
Figura 3: Montón de objetos grandes después de una recolección de elementos no utilizados de generación 2

## <a name="when-is-a-large-object-collected"></a>¿Cuándo se recolecta un objeto grande?

Por lo general, una recolección de elementos no utilizados tiene lugar bajo una de las tres condiciones siguientes:

- La asignación supera el umbral de la generación 0 o de objeto grande.

  El umbral es una propiedad de una generación. El umbral de una generación se establece cuando el recolector de elementos no utilizados asigna objetos a esa generación. Cuando el umbral se supera, se activa una recolección de elementos no utilizados en dicha generación. Cuando se asignan objetos pequeños o grandes, se consumen los umbrales de la generación 0 y del montón de objeto grande respectivamente. Cuando el recolector de elementos no utilizados realiza la asignación en las generaciones 1 y 2, consume sus umbrales correspondientes. Estos umbrales se optimizan dinámicamente a medida que se ejecuta el programa.

  Esto es lo habitual; la mayoría de las recolecciones de elementos no utilizados ocurren debido a las asignaciones del montón administrado.

- Se llama al método <xref:System.GC.Collect%2A?displayProperty=nameWithType> .

  Si se llama al método sin parámetros <xref:System.GC.Collect?displayProperty=nameWithType> o se pasa otra sobrecarga <xref:System.GC.MaxGeneration?displayProperty=nameWithType> como argumento, el montón de objetos grandes se recopilará junto con el resto del montón administrado.

- El sistema está en situación de memoria insuficiente.

  Esto sucede cuando el recolector de elementos no utilizados recibe una notificación de memoria alta del sistema operativo. Si el recolector de elementos no utilizados considera que llevar a cabo una recolección de elementos no utilizados de generación 2 va a ser productivo, activa una.

## <a name="loh-performance-implications"></a>Implicaciones de rendimiento del montón de objetos grandes

Las asignaciones del montón de objetos grandes afectan al rendimiento de las siguientes formas.

- Costo de la asignación.

  El CLR garantiza que se borra la memoria de cada nuevo objeto que envío. Esto significa que el costo de la asignación de un objeto grande está dominado por el borrado de la memoria (a menos que active una recolección de elementos no utilizados). Si se tardan dos ciclos en borrar un byte, se tardarán 170 000 ciclos en borrar el objeto grande más pequeño. Borrar la memoria de un objeto de 16 MB en un equipo a 2 GHz tarda 16 ms aproximadamente. Se trata de un costo bastante grande.

- Costo de la colección.

  Dado que el montón de objetos grandes y la generación 2 se recopilan juntos, si el umbral de uno de ellos se supera, se activa una recolección de generación 2. Si se activa una colección de generación 2 debido al montón de objetos grandes, dicha generación no será necesariamente mucho menor después de la recolección de elementos no utilizados. Si no hay muchos datos en la generación 2, el impacto será mínimo, pero si es grande, podría provocar problemas de rendimiento si se activan muchas recolecciones de elementos no utilizados de generación 2. Si se asignan numerosos objetos grandes muy de vez en cuando y tiene un montón de objetos grandes muy voluminoso, podría estar dedicando demasiado tiempo a las recolecciones de elementos no utilizados. Además, el costo de la asignación puede subir tremendamente si sigue asignando y liberando objetos muy grandes.

- Elementos de matriz con tipos de referencia.

  Por lo general, los objetos muy grandes en el montón de objeto grande son matrices (es muy poco habitual tener un objeto de instancia que sea realmente grande). Si los elementos de una matriz contienen cuantiosas referencias, se incurrirá en un costo que no se produce cuando no existen tantas referencias en los elementos. Si el elemento no contiene ninguna referencia, el recolector de elementos no utilizados no necesitará recorrer la matriz en absoluto. Por ejemplo, si usa una matriz para almacenar nodos en un árbol binario, una forma de implementarlo es hacer referencia al nodo derecho e izquierdo de un nodo por medio de los nodos reales:

  ```csharp
  class Node
  {
     Data d;
     Node left;
     Node right;
  };

  Node[] binary_tr = new Node [num_nodes];
  ```

  Si `num_nodes` es grande, el recolector de elementos no utilizados debe recorrer al menos dos referencias por elemento. Un método alternativo consiste en almacenar el índice de los nodos derecho e izquierdo:

  ```csharp
  class Node
  {
     Data d;
     uint left_index;
     uint right_index;
  } ;
  ```

  En lugar de hacer referencia a los datos del nodo izquierdo como `left.d`, haremos referencia a ellos como `binary_tr[left_index].d`. Así, el recolector de elementos no utilizados no tiene que buscar el nodo izquierdo y el derecho en ninguna referencia.

De estos tres factores, los dos primeros suelen ser más importantes que el tercero. En consecuencia, se recomienda asignar un grupo de objetos grandes y reutilizarlos en vez de asignar temporales.

## <a name="collect-performance-data-for-the-loh"></a>Recolección de datos de rendimiento para el montón de objetos grandes

Antes de recopilar datos de rendimiento para un área específica, conviene haber hecho ya lo siguiente:

1. Haber encontrado pruebas de que se debe buscar en esta área.

2. Haber agotado otras áreas que conozca sin haber hallado una explicación al problema de rendimiento que ha visto.

Vea el blog [Understand the problem before you try to find a solution](https://devblogs.microsoft.com/dotnet/understand-the-problem-before-you-try-to-find-a-solution/) (Conocer el problema antes de intentar buscar una solución) para más información sobre los conceptos básicos de memoria y la CPU.

Puede usar las siguientes herramientas para recopilar datos sobre el rendimiento del montón de objetos grandes:

- [Contadores de rendimiento de memoria de .NET CLR](#net-clr-memory-performance-counters)

- [Eventos ETW](#etw-events)

- [Un depurador](#a-debugger)

### <a name="net-clr-memory-performance-counters"></a>Contadores de rendimiento de memoria de .NET CLR

Estos contadores de rendimiento suelen ser un buen punto de partida para investigar los problemas de rendimiento (aunque se recomienda usar [eventos ETW](#etw-events)). Para configurar el Monitor de rendimiento, hay que agregar los contadores que se quiera, como se muestra en la figura 4. Los que son relevantes para el montón de objetos grandes son:

- **Número de colecciones de gen. 2**

   Muestra el número de veces que se han producido recolecciones de elementos no utilizados de generación 2 desde que se inició el proceso. Este contador se incrementa al final de una recolección de elementos no utilizados de generación 2 (también llamada recolección completa de elementos no utilizados). Este contador muestra el último valor observado.

- **Tamaño del montón del objeto grande**

   Muestra el tamaño actual en bytes (espacio libre incluido) del montón de objetos grandes. Este contador se actualiza al final de una recolección de elementos no utilizados, no durante cada asignación.

Una forma habitual de examinar los contadores de rendimiento es a través del Monitor de rendimiento (perfmon.exe). Use "Agregar contadores" para agregar los contadores de interés relativos a los procesos que le preocupen. Puede guardar los datos de contador de rendimiento en un archivo de registro, tal y como muestra la figura 4.

![Captura de pantalla que muestra cómo agregar contadores de rendimiento.](media/large-object-heap/add-performance-counter.png)
Figura 4: Montón de objetos grandes después de una recolección de elementos no utilizados de generación 2

Los contadores de rendimiento también se pueden consultar mediante programación. Muchas personas los recolectan de esta forma como parte de su proceso rutinario de pruebas. Al detectar contadores con valores que no son normales, usan otros medios para obtener más detalles que ayuden en la investigación.

> [!NOTE]
> El uso de eventos ETW es preferible al de los contadores de rendimiento, ya que ETW proporciona información mucho más completa.

### <a name="etw-events"></a>eventos ETW

El recolector de elementos no utilizados proporciona un amplio conjunto de eventos ETW que sirven para entender qué hace el montón y por qué. En las siguientes entradas de blog se explica cómo recopilar y entender los eventos de recolección de elementos no utilizados con ETW:

- [GC ETW Events - 1 ](https://devblogs.microsoft.com/dotnet/gc-etw-events-1/) (Eventos ETW de recolección de elementos no utilizados, 1)

- [GC ETW Events - 2 ](https://devblogs.microsoft.com/dotnet/gc-etw-events-2/) (Eventos ETW de recolección de elementos no utilizados, 2)

- [GC ETW Events - 3 ](https://devblogs.microsoft.com/dotnet/gc-etw-events-3/) (Eventos ETW de recolección de elementos no utilizados, 3)

- [GC ETW Events - 4 ](https://devblogs.microsoft.com/dotnet/gc-etw-events-4/) (Eventos ETW de recolección de elementos no utilizados, 4)

Para identificar los excesos de recolecciones de elementos no utilizados de generación 2 provocados por las asignaciones temporales del montón de objetos grandes, busque en la columna Razón del desencadenador de las recolecciones. Para realizar una sencilla prueba en la que solo se asignan objetos grandes temporales, puede recopilar información sobre los eventos ETW con la siguiente línea de comandos de [PerfView](https://www.microsoft.com/download/details.aspx?id=28567):

```console
perfview /GCCollectOnly /AcceptEULA /nogui collect
```

El resultado es similar al siguiente:

![Captura de pantalla que muestra los eventos ETW en PerfView.](media/large-object-heap/event-tracing-windows-perfview.png)
Figura 5: Eventos ETW con PerfView

Como se puede ver, todas las recolecciones de elementos no utilizados pertenecen a la generación 2 y todas ellas se han activado por medio de AllocLarge, lo que significa que esta recolección de elementos no utilizados se ha activado a raíz de la asignación de un objeto grande. Sabemos que estas asignaciones son temporales porque la columna **LOH Survival Rate %** (% de tasa de supervivencia del montón de objetos grandes) muestra 1%.

Se pueden recopilar más eventos ETW que indican quién ha asignado estos objetos grandes. La siguiente línea de comandos:

```console
perfview /GCOnly /AcceptEULA /nogui collect
```

recopila un evento AllocationTick que se activa aproximadamente con cada asignación con un volumen de 100 000. Dicho de otro modo, se activa un evento cada vez que se asigna un objeto grande. Así, puede consultar una de las vistas de asignación del montón de recolección de elementos no utilizados, en las que se muestran las pilas de llamadas que han asignado objetos grandes:

![Captura de pantalla que muestra una vista de recolector de elementos no utilizados del montón.](media/large-object-heap/garbage-collector-heap.png)
Figura 6: Vista de asignación del montón de recolección de elementos no utilizados

Como se puede ver, se trata de una prueba muy sencilla que simplemente asigna objetos grandes desde el método `Main`.

### <a name="a-debugger"></a>Un depurador

Si todo lo que tiene es un volcado de memoria y necesita examinar los objetos que realmente hay en el montón de objetos grandes, puede usar la [extensión de depurador SoS](../../../docs/framework/tools/sos-dll-sos-debugging-extension.md) proporcionada por .NET.

> [!NOTE]
> Los comandos de depuración que se mencionan en esta sección son válidos con los [depuradores de Windows](https://www.microsoft.com/whdc/devtools/debugging/default.mspx).

Aquí se muestra la salida de ejemplo resultante de analizar el montón de objetos grandes:

```console
0:003> .loadby sos mscorwks
0:003> !eeheap -gc
Number of GC Heaps: 1
generation 0 starts at 0x013e35ec
sdgeneration 1 starts at 0x013e1b6c
generation 2 starts at 0x013e1000
ephemeral segment allocation context: none
segment   begin allocated     size
0018f2d0 790d5588 790f4b38 0x0001f5b0(128432)
013e0000 013e1000 013e35f8 0x000025f8(9720)
Large object heap starts at 0x023e1000
segment   begin allocated     size
023e0000 023e1000 033db630 0x00ffa630(16754224)
033e0000 033e1000 043cdf98 0x00fecf98(16699288)
043e0000 043e1000 05368b58 0x00f87b58(16284504)
Total Size 0x2f90cc8(49876168)
------------------------------
GC Heap Size 0x2f90cc8(49876168)
0:003> !dumpheap -stat 023e1000 033db630
total 133 objects
Statistics:
MT   Count   TotalSize Class Name
001521d0       66     2081792     Free
7912273c       63     6663696 System.Byte[]
7912254c       4     8008736 System.Object[]
Total 133 objects
```

El tamaño del montón de objetos grandes es (16 754 224 + 16 699 288 + 16 284 504) = 49 738 016 bytes. Entre las direcciones 023e1000 y 033db630, 8 008 736 bytes están ocupados por una matriz de objetos <xref:System.Object?displayProperty=nameWithType>; 6 663 696 bytes, por una matriz de objetos <xref:System.Byte?displayProperty=nameWithType>, y 2 081 792 bytes, por espacio libre.

En ocasiones, el depurador señala que el tamaño total del montón de objetos grandes es inferior a 85 000 bytes. Esto sucede porque el propio módulo de tiempo de ejecución usa el montón de objetos grandes para asignar objetos con un tamaño menor que un objeto grande.

Como el montón de objetos grandes no se compacta, a veces se considera que dicho montón es un origen de fragmentación. La fragmentación significa:

- Fragmentación del montón administrado, que viene indicado por la cantidad de espacio libre entre los objetos administrados. En SoS, el comando `!dumpheap –type Free` muestra la cantidad de espacio libre entre los objetos administrados.

- Fragmentación del espacio de direcciones de memoria virtual (VM), que es la memoria marcada como `MEM_FREE`. Se puede obtener usando varios comandos de depurador en windbg.

   En el siguiente ejemplo se muestra la fragmentación en el espacio de memoria virtual:

   ```console
   0:000> !address
   00000000 : 00000000 - 00010000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   00010000 : 00010000 - 00002000
   Type     00020000 MEM_PRIVATE
   Protect 00000004 PAGE_READWRITE
   State   00001000 MEM_COMMIT
   Usage   RegionUsageEnvironmentBlock
   00012000 : 00012000 - 0000e000
   Type     00000000
   Protect 00000001 PAGE_NOACCESS
   State   00010000 MEM_FREE
   Usage   RegionUsageFree
   … [omitted]
   -------------------- Usage SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Pct(Busy)   Usage
   701000 (   7172) : 00.34%   20.69%   : RegionUsageIsVAD
   7de15000 ( 2062420) : 98.35%   00.00%   : RegionUsageFree
   1452000 (   20808) : 00.99%   60.02%   : RegionUsageImage
   300000 (   3072) : 00.15%   08.86%   : RegionUsageStack
   3000 (     12) : 00.00%   00.03%   : RegionUsageTeb
   381000 (   3588) : 00.17%   10.35%   : RegionUsageHeap
   0 (       0) : 00.00%   00.00%   : RegionUsagePageHeap
   1000 (       4) : 00.00%   00.01%   : RegionUsagePeb
   1000 (       4) : 00.00%   00.01%   : RegionUsageProcessParametrs
   2000 (       8) : 00.00%   00.02%   : RegionUsageEnvironmentBlock
   Tot: 7fff0000 (2097088 KB) Busy: 021db000 (34668 KB)

   -------------------- Type SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   7de15000 ( 2062420) : 98.35%   : <free>
   1452000 (   20808) : 00.99%   : MEM_IMAGE
   69f000 (   6780) : 00.32%   : MEM_MAPPED
   6ea000 (   7080) : 00.34%   : MEM_PRIVATE

   -------------------- State SUMMARY --------------------------
   TotSize (     KB)   Pct(Tots) Usage
   1a58000 (   26976) : 01.29%   : MEM_COMMIT
   7de15000 ( 2062420) : 98.35%   : MEM_FREE
   783000 (   7692) : 00.37%   : MEM_RESERVE

   Largest free region: Base 01432000 - Size 707ee000 (1843128 KB)
   ```

Es más habitual ver fragmentación de la memoria virtual provocada por objetos grandes temporales que requieren que el recolector de elementos no utilizados adquiera frecuentemente nuevos segmentos de montón administrados del sistema operativo y liberar los vacíos para el sistema operativo.

Para comprobar si el montón de objetos grandes provoca fragmentación de la memoria virtual, puede establecer un punto de ruptura en [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) y [VirtualFree](/windows/desktop/api/memoryapi/nf-memoryapi-virtualfree), y ver quién los llama. Por ejemplo, para ver quién ha intentado asignar fragmentos de memoria virtual superiores a 8 MB desde el sistema operativo, podemos establecer un punto de ruptura como el siguiente:

```console
bp kernel32!virtualalloc "j (dwo(@esp+8)>800000) 'kb';'g'"
```

Este comando entra en el depurador y muestra la pila de llamadas solo si se llama a [VirtualAlloc](/windows/desktop/api/memoryapi/nf-memoryapi-virtualalloc) con un tamaño de asignación superior a 8 MB (0x800000).

En CLR 2.0 se ha incluido una característica denominada *acumulación de memoria virtual* que puede resultar útil si se encuentra en una situación en la que los segmentos (incluidos los de los montones de objetos pequeños y de objetos grandes) se adquieren y liberan con frecuencia. Para establecer un valor de acumulación de memoria virtual, hay que especificar una marca de inicio denominada `STARTUP_HOARD_GC_VM` a través de la API de hospedaje. En vez de liberar los segmentos vacíos para el sistema operativo, CLR anula la confirmación de la memoria de estos segmentos y los coloca en una lista en espera (cabe decir que CLR no lleva esto a cabo en segmentos que son demasiado grandes). Más adelante, CLR usa esos segmentos para cumplir nuevas solicitudes de segmento. La próxima vez que la aplicación necesite un nuevo segmento, CLR usará uno de esta lista en espera (si encuentra uno lo suficientemente grande).

La acumulación de memoria virtual también es útil en aplicaciones que quieren retener los segmentos ya adquiridos; es el caso, por ejemplo, de algunas aplicaciones de servidor que son aplicaciones dominantes que se ejecutan en el sistema, para evitar que se produzcan excepciones por memoria insuficiente.

Se recomienda encarecidamente tener cuidado al usar esta característica en la aplicación y garantizar que esta tiene un uso de memoria bastante estable.
