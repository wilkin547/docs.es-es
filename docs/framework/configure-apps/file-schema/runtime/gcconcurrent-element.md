---
title: Elemento gcConcurrent
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/gcConcurrent
- http://schemas.microsoft.com/.NetConfiguration/v2.0#gcConcurrent
helpviewer_keywords:
- container tags, <gcConcurrent> element
- gcConcurrent element
- <gcConcurrent> element
ms.assetid: 503f55ba-26ed-45ac-a2ea-caf994da04cd
ms.openlocfilehash: 249518ae7477d284d50f9010757db83b7752c657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "82102923"
---
# <a name="gcconcurrent-element"></a>Elemento \<gcConcurrent>

Especifica si Common Language Runtime ejecuta la recolección de elementos no utilizados en un subproceso independiente.

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<gcConcurrent>

## <a name="syntax"></a>Sintaxis

```xml
<gcConcurrent
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica si CLR ejecuta la recolección de elementos no utilizados simultáneamente.|

#### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`false`|No ejecuta la recolección de elementos no utilizados simultáneamente.|
|`true`|Ejecuta la recolección de elementos no utilizados simultáneamente. Este es el valor predeterminado.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Comentarios

Antes de .NET Framework 4, la recolección de elementos no utilizados de estación de trabajo admitía la recolección de elementos no utilizados simultánea, que realizaba la recolección de elementos no utilizados en segundo plano en otro subproceso. En .NET Framework 4, la recolección de elementos no utilizados simultánea se ha reemplazado por GC de fondo, que también realiza la recolección de elementos no utilizados en segundo plano en un subproceso independiente. A partir de .NET Framework 4,5, la recolección en segundo plano estuvo disponible en la recolección de elementos no utilizados de servidor. El elemento **gcConcurrent** controla si el motor en tiempo de ejecución realiza la recolección de elementos no utilizados simultánea o en segundo plano, si está disponible, o si realiza la recolección de elementos no utilizados en primer plano.

### <a name="to-disable-background-garbage-collection"></a>Para deshabilitar la recolección de elementos no utilizados en segundo plano

> [!WARNING]
> A partir de .NET Framework 4, la recolección de elementos no utilizados en segundo plano reemplaza la recolección simultánea de elementos no utilizados. Los términos *simultáneos* y de *fondo* se usan indistintamente en la documentación de .NET Framework. Para deshabilitar la recolección de elementos no utilizados en segundo plano, use el elemento **gcConcurrent** , como se describe en este artículo.

De forma predeterminada, CLR usa la recolección de elementos no utilizados simultánea, que está optimizada para la latencia. Si la aplicación requiere mucha interacción por parte del usuario, deje habilitada la recolección de elementos no utilizados simultánea para minimizar el tiempo que la aplicación debe parar para realizar la recolección de elementos no utilizados. Si establece el `enabled` atributo del elemento **gcConcurrent** en `false` , el Runtime usa la recolección de elementos no utilizados no simultánea, que está optimizada para el rendimiento.

El siguiente archivo de configuración deshabilita la recolección de elementos no utilizados en segundo plano:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="false"/>
   </runtime>
</configuration>
```

Si hay un valor de **gcConcurrentSetting** en el archivo de configuración del equipo, define el valor predeterminado para todas las aplicaciones .NET Framework. El archivo de configuración del equipo reemplaza el archivo de configuración de la aplicación.

Para obtener más información sobre la recolección de elementos no utilizados simultánea y en segundo plano, consulte recolección de [elementos no utilizados en segundo plano](../../../../standard/garbage-collection/background-gc.md).

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se habilita la recolección de elementos no utilizados en segundo plano:

```xml
<configuration>
   <runtime>
      <gcConcurrent enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../standard/garbage-collection/fundamentals.md)
