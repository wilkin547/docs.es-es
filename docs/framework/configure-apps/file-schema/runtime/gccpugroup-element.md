---
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: 352890519c1a227d664d877c3123866e5e4e1657
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73116831"
---
# <a name="gccpugroup-element"></a>\<elemento > GCCpuGroup

Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.

[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<en tiempo de ejecución >** ](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp; **\<GCCpuGroup >**  

## <a name="syntax"></a>Sintaxis

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|

## <a name="enabled-attribute"></a>Atributo enabled

|Valor|Descripción|
|-----------|-----------------|
|`false`|La recolección de elementos no utilizados no admite varios grupos de CPU. Este es el valor predeterminado.|
|`true`|La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el\<elemento de [> gcServer](gcserver-element.md) ), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y montones de equilibrio.

> [!NOTE]
> Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados. Para permitir que el motor en tiempo de ejecución distribuya los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el elemento [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) .

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo habilitar la recolección de elementos no utilizados para varios grupos de CPU.

```xml
<configuration>
   <runtime>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Para deshabilitar la recolección de elementos no utilizados simultánea](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../../../standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
