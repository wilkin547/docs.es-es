---
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 197ab9dbc1ec85bf8961f60bb26496eab788e63f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663699"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup >, elemento

Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.

\<configuration>\
\<> en tiempo de ejecución \
\<> GCCpuGroup

## <a name="syntax"></a>Sintaxis

```xml
<GCCpuGroup
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|DESCRIPCIÓN|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|DESCRIPCIÓN|
|-----------|-----------------|
|`false`|La recolección de elementos no utilizados no admite varios grupos de CPU. Este es el valor predeterminado.|
|`true`|La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el elemento [ \<> gcServer](gcserver-element.md) ), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y toma en cuenta todos los núcleos al crear y montones de equilibrio.

> [!NOTE]
> Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados. Para permitir que el tiempo de ejecución distribuya los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el elemento [ \<> de Thread_UseAllCpuGroups](thread-useallcpugroups-element.md) .

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
- [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../../../../docs/standard/garbage-collection/fundamentals.md#workstation_and_server_garbage_collection)
