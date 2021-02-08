---
description: 'Más información acerca de: <Thread_UseAllCpuGroups elemento>'
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
ms.openlocfilehash: 3f11ba6855caab25bd261de71c80c78232f2690f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802416"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups> (Elemento)

Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Thread_UseAllCpuGroups>**  

## <a name="syntax"></a>Sintaxis

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|Descripción|
|-----------|-----------------|
|`false`|El runtime no distribuye los subprocesos administrados entre varios grupos de CPU. Este es el valor predeterminado.|
|`true`|El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [\<GCCpuGroup>](gccpugroup-element.md) elemento está habilitado.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU. Para usar esta característica, también debe habilitar el [\<GCCpuGroup>](gccpugroup-element.md) elemento, que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones. Para habilitar el elemento, es [\<GCCpuGroup>](gccpugroup-element.md) necesario habilitar el [\<gcServer>](gcserver-element.md) elemento. Si estos elementos no están habilitados, la habilitación del `<Thread_UseAllCpuGroups>` elemento no tiene ningún efecto.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo habilitar la compatibilidad con varios grupos de CPU.

```xml
<configuration>
   <runtime>
      <Thread_UseAllCpuGroups enabled="true"/>
      <GCCpuGroup enabled="true"/>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Elemento \<GCCpuGroup>](gccpugroup-element.md)
