---
title: Elemento <Thread_UseAllCpuGroups>
ms.date: 03/30/2017
ms.assetid: d30fe7c5-8469-46e2-b804-e3eec7b24256
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e9ee6bdb7094ea2bc9e283e331c0f6ad9b68e4f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663422"
---
# <a name="thread_useallcpugroups-element"></a>\<Thread_UseAllCpuGroups >, elemento

Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.

\<configuration>\
\<> en tiempo de ejecución \
\<> Thread_UseAllCpuGroups

## <a name="syntax"></a>Sintaxis

```xml
<Thread_UseAllCpuGroups
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|DESCRIPCIÓN|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si el runtime distribuye subprocesos administrados en todos los grupos de CPU.|

## <a name="enabled-attribute"></a>Atributo enabled

|Valor|DESCRIPCIÓN|
|-----------|-----------------|
|`false`|El runtime no distribuye los subprocesos administrados entre varios grupos de CPU. Este es el valor predeterminado.|
|`true`|El motor en tiempo de ejecución distribuye los subprocesos administrados entre varios grupos de CPU, si el equipo tiene varios grupos de CPU y el [ \<elemento > GCCpuGroup](gccpugroup-element.md) está habilitado.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

Cuando un equipo tiene varios grupos de CPU, la habilitación de este elemento hace que el tiempo de ejecución distribuya los subprocesos administrados en todos los grupos de CPU. Para usar esta característica, también debe habilitar el elemento [ \<> de GCCpuGroup](gccpugroup-element.md) , que extiende la recolección de elementos no utilizados a todos los grupos de CPU y tiene en cuenta todos los núcleos al crear y equilibrar los montones. Para habilitar el [ \<elemento > GCCpuGroup](gccpugroup-element.md) es necesario habilitar el [ \<elemento gcServer >](gcserver-element.md) . Si estos elementos no están habilitados, la `<Thread_UseAllCpuGroups>` habilitación del elemento no tiene ningún efecto.

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
- [\<GCCpuGroup >, elemento](gccpugroup-element.md)
