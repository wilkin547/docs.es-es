---
description: 'Más información acerca de: <GCHeapCount> elemento'
title: Elemento GCHeapCount
ms.date: 11/08/2019
helpviewer_keywords:
- gcHeapCount element
- <gcHeapCount> element
ms.openlocfilehash: 9e1e000d647435fe7a8c4b1a8f7549f06c2a3b38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786972"
---
# <a name="gcheapcount-element"></a>Elemento \<GCHeapCount>

Especifica el número de montones o subprocesos que se usarán para la recolección de elementos no utilizados de servidor.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCHeapCount>

## <a name="syntax"></a>Sintaxis

```xml
<GCHeapCount
   enabled="nn"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica el número de montones que se usarán para la recolección de elementos no utilizados de servidor. El número real de montones es el mínimo del número de montones que especifique y el número de procesadores que puede usar el proceso. |

#### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`nn`|El número de montones que se usarán para el GC del servidor.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con su CPU respectiva, de modo que hay un montón de GC, un subproceso de GC de servidor y un subproceso de GC de servidor en segundo plano para cada procesador. A partir de .NET Framework 4.6.2, puede usar el elemento **GCHeapCount** para limitar el número de montones usados por la aplicación para el GC del servidor. Limitar el número de montones usados para el GC del servidor es especialmente útil para los sistemas que ejecutan varias instancias de una aplicación de servidor.

**GCHeapCount** se usa normalmente junto con otras dos marcas:

- [GCNoAffinitize](gcnoaffinitize-element.md), que controla si los subprocesos o montones de GC del servidor se afinidad con con CPU.

- [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que controla la afinidad de los subprocesos o montones de GC con las CPU.

Si se establece **GCHeapCount** y **GCNoAffinitize** está deshabilitado (su configuración predeterminada), existe una afinidad entre los montones o subprocesos de GC de *nn* y *los primeros.* Puede usar el elemento **GCHeapAffinitizeMask** para especificar qué procesadores usan los montones de GC del servidor del proceso. De lo contrario, si se ejecutan varios procesos de servidor en un sistema, el uso del procesador se superpondrá.

Si se establece **GCHeapCount** y **GCNoAffinitize** está habilitado, el recolector de elementos no utilizados limita el número de procesadores que se usan para el GC del servidor, pero no establecer afinidad entre los montones y procesadores de GC.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se indica que una aplicación usa un GC de servidor con 10 subprocesos o montones. Dado que no desea que esos montones se superpongan con montones de otras aplicaciones que se ejecutan en el sistema, use **GCHeapAffinitizeMask** para especificar que el proceso debe utilizar las CPU de 0 a 9.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCHeapAffinitizeMask enabled="1023"/>
   </runtime>
</configuration>
```

En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10.

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCHeapCount enabled="10"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Elemento GCNoAffinitize](gcnoaffinitize-element.md)
- [Elemento GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../standard/garbage-collection/fundamentals.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
