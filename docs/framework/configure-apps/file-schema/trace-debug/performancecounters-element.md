---
title: <performanceCounters> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/performanceCounters
- http://schemas.microsoft.com/.NetConfiguration/v2.0#performanceCounters
helpviewer_keywords:
- performanceCounters element
- <performanceCounters> element
ms.assetid: a71f605b-c7d9-4501-a5c3-abcbb964a43f
ms.openlocfilehash: 6144bcbda69b2ba799e87c3e7fa2118fbe4d9bf6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673750"
---
# <a name="performancecounters-element"></a>\<performanceCounters > elemento

Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.

 \<configuration>\
\<system.diagnostics>\
\<performanceCounters>

## <a name="syntax"></a>Sintaxis

```xml
<performanceCounters filemappingsize="524288" />
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|filemappingsize|Atributo necesario.<br /><br /> Especifica el tamaño, en bytes, de la memoria global compartida por los contadores de rendimiento. El valor predeterminado es 524288.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`Configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`system.diagnostics`|Especifica el elemento raíz de la sección de configuración de ASP.NET.|

## <a name="remarks"></a>Comentarios

Contadores de rendimiento de usar un archivo asignado en memoria, o memoria compartida, para publicar datos de rendimiento.  El tamaño de la memoria compartida determina cuántas instancias se pueden usar a la vez.  Hay dos tipos de memoria compartida: memoria compartida global y memoria compartida independiente.  Se utiliza la memoria global compartida por todas las categorías de contador de rendimiento instaladas con las versiones de .NET Framework 1.0 o 1.1.  Categorías de contador de rendimiento instaladas con la versión 2.0 de .NET Framework usa memoria compartida independiente, con cada categoría de contador de rendimiento tiene su propia memoria.

Solo con un archivo de configuración se puede establecer el tamaño de memoria compartida global.  El tamaño predeterminado es 524.288 bytes, el tamaño máximo es 33 554 432 bytes y el tamaño mínimo es de 32.768 bytes.  Puesto que todos los procesos y categorías comparten la memoria compartida global, el creador del primer especifica el tamaño.  Si define el tamaño del archivo de configuración de aplicación, sólo se utiliza ese tamaño si la primera aplicación que hace que los contadores de rendimiento ejecutar la aplicación.  Por lo tanto, la ubicación correcta para especificar el `filemappingsize` valor es el archivo Machine.config.  No se puede liberar memoria en la memoria global compartida por los contadores de rendimiento individuales, por lo que finalmente se agota la memoria compartida global si se crea un gran número de instancias de contador de rendimiento con nombres diferentes.

El tamaño de memoria compartida independiente, el valor de DWORD FileMappingSize en el registro de clave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\\*\<nombre de categoría >* \Performance se hace referencia en primer lugar, seguido por el valor especificado para la memoria compartida global en el archivo de configuración. Si el valor de FileMappingSize no existe, se establece el tamaño de memoria compartida independiente a un cuarto (1/4) la configuración global en el archivo de configuración.

## <a name="see-also"></a>Vea también

- <xref:System.Diagnostics.PerformanceCounter>
- <xref:System.Diagnostics.PerformanceCounterCategory>
- <xref:System.Diagnostics.PerformanceCounter.InstanceLifetime%2A>
- <xref:System.Diagnostics.PerformanceCounterInstanceLifetime>
