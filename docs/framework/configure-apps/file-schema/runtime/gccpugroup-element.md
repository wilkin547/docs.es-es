---
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: ae9c96c9d49cf3f6be94da3f77b91423cab12e0b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430481"
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

En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.|

## <a name="enabled-attribute"></a>Atributo enabled

|Valor|Descripción|
|-----------|-----------------|
|`false`|La recolección de elementos no utilizados no admite varios grupos de CPU. Este es el valor predeterminado.|
|`true`|La recolección de elementos no utilizados admite varios grupos de CPU, si está habilitada la recolección de elementos no utilizados de servidor.|

### <a name="child-elements"></a>Elemento secundario

Ninguno.

### <a name="parent-elements"></a>Elemento principal

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el\<elemento de [> gcServer](gcserver-element.md) ), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.

> [!NOTE]
> Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados. Para permitir al motor en tiempo de ejecución distribuir los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el [\<Thread_UseAllCpuGroups >](thread-useallcpugroups-element.md) elemento.

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
- [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../../../standard/garbage-collection/fundamentals.md#workstation-and-server-garbage-collection)
