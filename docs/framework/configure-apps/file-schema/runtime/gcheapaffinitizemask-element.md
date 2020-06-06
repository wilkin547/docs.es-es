---
title: Elemento GCHeapAffinitizeMask
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 09d6523fb10692dd3617a3827d5bccf112bc632b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73978424"
---
# <a name="gcheapaffinitizemask-element"></a>Elemento \<GCHeapAffinitizeMask>

Define la afinidad entre los montones de GC y los procesadores individuales.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapAffinitizeMask>

## <a name="syntax"></a>Sintaxis

```xml
<GCHeapAffinitizeMask
   enabled="nnnn"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica la afinidad entre los montones de GC y los procesadores individuales. |

#### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`nnnn`|Un valor decimal que constituye una máscara de máscara que define la afinidad entre los montones de GC del servidor y los procesadores individuales. |

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador. A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapAffinitizeMask** para controlar la afinidad entre los montones y los procesadores de GC del servidor cuando el número de montones está limitado por el elemento **GCHeapCount** .

**GCHeapAffinitizeMask** se usa normalmente junto con otras dos marcas:

- [GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU. El `enabled` atributo del elemento [GCNoAffinitize](gcnoaffinitize-element.md) debe ser `false` (su valor predeterminado) para que se use el valor **GCHeapAffinitizeMask** .

- [GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por el proceso para el GC del servidor. De forma predeterminada, hay un montón para cada procesador.

**nnnn** es una máscara de bits expresada como un valor decimal. El bit 0 de byte 0 representa el procesador 0, bit 1 de byte 0 representa el procesador 1, etc. Por ejemplo:

```xml
<GCHeapAffinitizeMask enabled="1023"/>
```

Un valor de 1023 es 0x3FF o 0011 1111 1111b. El proceso utiliza 10 procesadores, desde el procesador 0 hasta el procesador 9.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones. Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe usar las CPU de 0 a 9.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Consulte también

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Elemento GCNoAffinitize](gcnoaffinitize-element.md)
- [Elemento GCHeapCount](gcheapcount-element.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../standard/garbage-collection/fundamentals.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
