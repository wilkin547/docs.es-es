---
description: 'Más información acerca de: <NetFx45_CultureAwareComparerGetHashCode_LongStrings elemento>'
title: Elemento <NetFx45_CultureAwareComparerGetHashCode_LongStrings>
ms.date: 03/30/2017
helpviewer_keywords:
- NetFx45_CultureAwareComparerGetHashCode_LongStrings element
- <NetFx45_CultureAwareComparerGetHashCode_LongStrings> element
- GetHashCode method
- hash codes, calculating
ms.assetid: 3a5f38d1-ebc8-44de-aaeb-2929f6e6b48f
ms.openlocfilehash: ca4099d3bf812cb25e6a611b9b51b3752b1ad361
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782291"
---
# <a name="netfx45_cultureawarecomparergethashcode_longstrings-element"></a>\<NetFx45_CultureAwareComparerGetHashCode_LongStrings> (Elemento)

Especifica si el runtime usa una cantidad de memoria fija para calcular los códigos hash para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> .

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx45_CultureAwareComparerGetHashCode_LongStrings>**  

## <a name="syntax"></a>Sintaxis

```xml
<NetFx45_CultureAwareComparerGetHashCode_LongStrings enabled="0|1">
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si Common Language Runtime asigna una cantidad de memoria fija al calcular códigos hash.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|Descripción|
|-----------|-----------------|
|0|Common Language Runtime asigna una cantidad de memoria variable para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash. Este es el valor predeterminado.|
|1|Common Language Runtime asigna una cantidad de memoria fija para que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> calcule códigos hash.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Observaciones

De forma predeterminada, Common Language Runtime asigna una cantidad de memoria variable para el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> y puede que se inicie una excepción <xref:System.ArgumentException> cuando el método intenta calcular el código hash de cadenas muy grandes (con millones de caracteres o más). Al agregar este elemento a un archivo de configuración de la aplicación y establecer su atributo `enabled` en "1", puede especificar que el método <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType> use un algoritmo alternativo que asigne una cantidad de memoria fija para el cálculo de códigos hash.

> [!IMPORTANT]
> El `<NetFx45_CultureAwareComparerGetHashCode_LongStrings>` elemento no se utiliza en Windows 8 ni en versiones posteriores.

## <a name="see-also"></a>Vea también

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
