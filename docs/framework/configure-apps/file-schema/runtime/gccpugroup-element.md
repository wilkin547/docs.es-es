---
description: 'Más información acerca de: <GCCpuGroup> elemento'
title: <GCCpuGroup> (Elemento)
ms.date: 03/30/2017
helpviewer_keywords:
- GCCpuGroup element
- <GCCpuGroup> element
ms.assetid: c1fc7d6c-7220-475c-a312-5b8b201f66e0
ms.openlocfilehash: d4b3aa7084cbc2cb23b273bea95ffaec6e3a74d6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786998"
---
# <a name="gccpugroup-element"></a>\<GCCpuGroup> (Elemento)

Especifica si la recolección de elementos no utilizados admite varios grupos de CPU.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<GCCpuGroup>**

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

|Value|Descripción|
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

## <a name="remarks"></a>Observaciones

Cuando un equipo tiene varios grupos de CPU y la recolección de elementos no utilizados de servidor está habilitada (vea el [\<gcServer>](gcserver-element.md) elemento), la habilitación de este elemento extiende la recolección de elementos no utilizados en todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones.

> [!NOTE]
> Este elemento solo se aplica a los subprocesos de recolección de elementos no utilizados. Para permitir que el tiempo de ejecución distribuya los subprocesos de usuario en todos los grupos de CPU, también debe habilitar el [\<Thread_UseAllCpuGroups>](thread-useallcpugroups-element.md) elemento.

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
- [Deshabilitar la recolección de elementos no utilizados simultánea](gcconcurrent-element.md#to-disable-background-garbage-collection)
- [Recolección de elementos no utilizados de estación de trabajo y de servidor](../../../../standard/garbage-collection/workstation-server-gc.md)
