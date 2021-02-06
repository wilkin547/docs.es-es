---
description: 'Más información sobre: elemento GCLOHThreshold'
title: Elemento GCLOHThreshold
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: 5d4ef4e6aaf44642c2307dc27ac2e99e966d3ad0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652814"
---
# <a name="gclohthreshold-element"></a>Elemento GCLOHThreshold

Especifica el tamaño del umbral, en bytes, que hace que el recolector de elementos no utilizados coloque objetos en el montón de objetos grandes (montón).

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<runtime>](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold>

## <a name="syntax"></a>Sintaxis

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br />Especifica el tamaño del umbral que hace que los objetos se dirijan al montón de objetos grandes.|

### <a name="enabled-attribute"></a>atributo Enabled

|Value|Descripción|
|-----------|-----------------|
|`nnnn`|Tamaño del umbral, en bytes, que hace que los objetos vayan al montón de objetos grandes.|

## <a name="child-elements"></a>Elementos secundarios

Ninguno.

## <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información del enlace del ensamblado y de la recolección de elementos no utilizados.|

## <a name="remarks"></a>Observaciones

Esta configuración se presentó en .NET Framework 4,8.

## <a name="see-also"></a>Vea también

- [Esquema de configuración de tiempo de ejecución](index.md)
- [Esquema del archivo de configuración](../index.md)
- [Fundamentos de la recolección de elementos no utilizados](../../../../standard/garbage-collection/fundamentals.md)
- [Opciones de configuración de tiempo de ejecución de .net Core para GC](../../../../core/run-time-config/garbage-collector.md)
