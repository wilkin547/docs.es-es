---
description: 'Más información acerca de: <gcServer> elemento'
title: Elemento gcServer
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcServer
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcServer
helpviewer_keywords:
- gcServer element
- <gcServer> element
ms.assetid: 8d25b80e-2581-4803-bd87-a59528e3cb03
ms.openlocfilehash: bed347699786682421292392a8d2449b7aac61d0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754542"
---
# <a name="gcserver-element"></a>Elemento \<gcServer>

Especifica si Common Language Runtime ejecuta la recopilación de elementos no utilizados de servidor.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcServer>

## <a name="syntax"></a>Sintaxis

```xml
<gcServer
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados de servidor.|

#### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`false`|No ejecuta la recolección de elementos no utilizados de servidor. Este es el valor predeterminado.|
|`true`|Ejecuta la recolección de elementos no utilizados de servidor.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

Common Language Runtime (CLR) admite dos tipos de recolección de elementos no utilizados: de estación de trabajo, que está disponible en todos los sistemas, y de servidor, que está disponible en sistemas multiprocesador. Use el elemento **gcServer** para controlar el tipo de recolección de elementos no utilizados que CLR realiza. Use la propiedad <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType> para determinar si la recolección de elementos no utilizados de servidor está habilitada.

Para equipos con un solo procesador, la recolección de elementos no utilizados de estación de trabajo predeterminada será la opción más rápida. En los equipos con dos procesadores se puede usar la opción de estación de trabajo o de servidor. La recolección de elementos no utilizados de servidor será la opción más rápida si hay más de dos procesadores. Normalmente, los sistemas de servidor multiprocesador deshabilitan el GC del servidor y usan la instancia de GC de la estación de trabajo cuando muchas instancias de una aplicación de servidor se ejecutan en el mismo equipo.

Este elemento se puede usar solo en el archivo de configuración de la aplicación; se omite si se encuentra en el archivo de configuración del equipo.

> [!NOTE]
> En .NET Framework 4 y versiones anteriores, la recolección de elementos no utilizados simultánea no está disponible si la recolección de elementos no utilizados de servidor está habilitada. A partir de la .NET Framework 4,5, la recolección de elementos no utilizados de servidor es simultánea. Para usar la recolección de elementos no utilizados de servidor no simultánea, establezca el elemento **gcServer** en `true` y el [elemento gcConcurrent](gcconcurrent-element.md) en `false` .

A partir de .NET Framework 4.6.2, también puede usar los siguientes elementos para configurar el GC del servidor:

- [GCNoAffinitize](gcnoaffinitize-element.md), que especifica si existe una afinidad entre los procesadores y los montones de GC del servidor. De forma predeterminada, hay un montón de GC de servidor para cada procesador.

- [GCHeapCount](gcheapcount-element.md), que limita el número de montones utilizados por un proceso.

- [GCHeapAffinitizeMask](gcheapaffinitizemask-element.md), que define la afinidad entre los montones de GC del servidor disponibles y los procesadores individuales.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se habilita la recolección de elementos no utilizados de servidor:

```xml
<configuration>
   <runtime>
      <gcServer enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- <xref:System.Runtime.GCSettings.IsServerGC%2A?displayProperty=nameWithType>
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Para deshabilitar la recolección de elementos no utilizados simultánea](gcconcurrent-element.md#to-disable-background-garbage-collection)
