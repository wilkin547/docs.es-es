---
description: 'Más información acerca de: <GCNoAffinitize> elemento'
title: Elemento GCNoAffinitize
ms.date: 11/08/2019
helpviewer_keywords:
- gcNoAffinitize element
- <gcNoAffinitize> element
ms.openlocfilehash: 139c0fd9e1ec829a3569b77a85e6526bec765e21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754555"
---
# <a name="gcnoaffinitize-element"></a>Elemento \<GCNoAffinitize>

Especifica si establecer afinidad entre o no los subprocesos de GC del servidor con CPU.

\<configuration>\
&nbsp;&nbsp;\<runtime>\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCNoAffinitize>

## <a name="syntax"></a>Sintaxis

```xml
<GCNoAffinitize
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica si los subprocesos o montones de GC del servidor se afinidad con con los procesadores disponibles en la máquina.|

#### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`false`|Subprocesos de GC del servidor establece con CPU. Este es el valor predeterminado.|
|`true`|No establecer afinidad entre los subprocesos de GC de servidor con CPU.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

De forma predeterminada, los subprocesos de GC de servidor son afinidad cons con sus respectivas CPU. Cada uno de los procesadores disponibles del sistema tiene su propio subproceso y montón de GC. Esta suele ser la configuración preferida, ya que optimiza el uso de la memoria caché. A partir de .NET Framework 4.6.2, al establecer el atributo del elemento **GCNoAffinitize** `enabled` en `true` , se puede especificar que los subprocesos de GC del servidor y las CPU no deben estar estrechamente acoplados.

Puede especificar el elemento de configuración **GCNoAffinitize** solo para los subprocesos de GC del servidor de establecer afinidad entre con CPU. También puede utilizarlo junto con el elemento [GCHeapCount](gcheapcount-element.md) para controlar el número de subprocesos y montones de GC utilizados por una aplicación.

Si el `enabled` atributo del elemento **GCNoAffinitize** es `false` (su valor predeterminado), también puede usar el elemento [GCHeapCount](gcheapcount-element.md) para especificar el número de subprocesos y montones de GC, junto con el elemento [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md) para especificar los procesadores en los que los subprocesos de GC y los montones están afinidad con.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
      <GCNoAffinitize enabled="true"/>
   </runtime>
</configuration>
```

En el ejemplo siguiente no se establecer afinidad entre los subprocesos de GC del servidor y se limita el número de subprocesos o montones de GC a 10:

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
- [Elemento GCHeapAffinitizeMask](gcheapaffinitizemask-element.md)
- [Elemento GCHeapCount](gcheapcount-element.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../standard/garbage-collection/fundamentals.md)
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
