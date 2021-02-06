---
description: 'Más información acerca de: <performanceCounters> elemento'
title: <performanceCounters> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 3a9a6c42575be3fc7fb5c5d80ffecd940894e164
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639580"
---
# <a name="performancecounters-element"></a>\<performanceCounters> (Elemento)

Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.

[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<performanceCounters>**  

## <a name="syntax"></a>Sintaxis

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|filemappingsize|Atributo necesario.<br /><br /> Especifica el tamaño (en bytes) de la memoria global compartida por los contadores de rendimiento. El valor predeterminado es 524288.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|

## <a name="remarks"></a>Observaciones

Los contadores de rendimiento usan un archivo asignado a la memoria, o la memoria compartida, para publicar datos de rendimiento.  El tamaño de la memoria compartida determina el número de instancias que se pueden usar a la vez.  Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.  Todas las categorías de contadores de rendimiento que se instalan con las .NET Framework versiones 1,0 o 1,1 utilizan la memoria compartida global.  Las categorías de contadores de rendimiento instaladas con la .NET Framework versión 2,0 usan una memoria compartida independiente, y cada categoría de contador de rendimiento tiene su propia memoria.

El tamaño de la memoria compartida global solo se puede establecer con un archivo de configuración.  El tamaño predeterminado es 524.288 BSÍ, el tamaño máximo es de 33.554.432 bytes y el tamaño mínimo es de 32.768 bytes.  Dado que todos los procesos y las categorías comparten la memoria compartida global, el primer creador especifica el tamaño.  Si define el tamaño en el archivo de configuración de la aplicación, ese tamaño solo se utiliza si la aplicación es la primera aplicación que hace que se ejecuten los contadores de rendimiento.  Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo de Machine.config.  Los contadores de rendimiento individuales no pueden liberar memoria en la memoria compartida global, por lo que finalmente se agota la memoria compartida global si se crea un gran número de instancias de contador de rendimiento con nombres diferentes.

Para el tamaño de la memoria compartida independiente, primero se hace referencia al valor DWORD FileMappingSize en la clave del registro HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\ *\<category name>* \Performance, seguido del valor especificado para la memoria compartida global en el archivo de configuración. Si el valor FileMappingSize no existe, el tamaño de la memoria compartida independiente se establece en un cuarto (1/4) la configuración global del archivo de configuración.

## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
