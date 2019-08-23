---
title: Elemento <TimeSpan_LegacyFormatMode>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <TimeSpan_LegacyFormatMode> element
- TimeSpan_LegacyFormatMode element
ms.assetid: 865e7207-d050-4442-b574-57ea29d5e2d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f16a2bbd2470b4aec9e95ab67ccb0e736c4c6d02
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920686"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode >, elemento

Determina si el tiempo de ejecución conserva el comportamiento heredado en operaciones <xref:System.TimeSpan?displayProperty=nameWithType> de formato con valores.

\<configuration>\
\<> en tiempo de ejecución \
\<TimeSpan_LegacyFormatMode>

## <a name="syntax"></a>Sintaxis

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|DESCRIPCIÓN|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si el Runtime usa el comportamiento de formato <xref:System.TimeSpan?displayProperty=nameWithType> heredado con valores.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|DESCRIPCIÓN|
|-----------|-----------------|
|`false`|El motor en tiempo de ejecución no restaura el comportamiento de formato heredado.|
|`true`|El motor en tiempo de ejecución restaura el comportamiento de formato heredado.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|DESCRIPCIÓN|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Comentarios

A partir de la .NET Framework 4, <xref:System.TimeSpan?displayProperty=nameWithType> la estructura implementa la <xref:System.IFormattable> interfaz y admite operaciones de formato con cadenas de formato estándar y personalizadas. Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce una <xref:System.FormatException>excepción.

En versiones anteriores del .NET Framework, la <xref:System.TimeSpan> estructura no implementaba <xref:System.IFormattable> y no admitía cadenas de formato. Sin embargo, muchos desarrolladores suponían erróneamente que <xref:System.TimeSpan> admiten un conjunto de cadenas de formato y las usaban en operaciones de [formato compuesto](../../../../standard/base-types/composite-formatting.md) <xref:System.String.Format%2A?displayProperty=nameWithType>con métodos como. Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con cadenas de formato no admitidas normalmente producen una <xref:System.FormatException>excepción. Sin embargo, <xref:System.TimeSpan> dado que no <xref:System.IFormattable>implementó, el tiempo de ejecución omitió la cadena de <xref:System.TimeSpan.ToString?displayProperty=nameWithType> formato y, en su lugar, llamó al método. Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no da <xref:System.FormatException>como resultado una.

En los casos en que el código heredado pasa un método de formato compuesto y una cadena de formato no válida, y ese código no se puede `<TimeSpan_LegacyFormatMode>` volver a compilar <xref:System.TimeSpan> , puede usar el elemento para restaurar el comportamiento heredado. Al establecer `enabled` el atributo de este elemento en <xref:System.TimeSpan.ToString?displayProperty=nameWithType> `true`, el método de formato compuesto produce una llamada a en lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>, y no <xref:System.FormatException> se produce una excepción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se <xref:System.TimeSpan> <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> crea una instancia de un objeto y se intenta dar formato al método mediante una cadena de formato estándar no compatible.

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Al ejecutar el ejemplo en el .NET Framework 3,5 o en una versión anterior, se muestra el siguiente resultado:

```
12:30:45
```

Esto difiere notablemente de la salida si ejecuta el ejemplo en el .NET Framework 4 o una versión posterior:

```
Invalid Format
```

Sin embargo, si agrega el archivo de configuración siguiente al directorio del ejemplo y, a continuación, ejecuta el ejemplo en el .NET Framework 4 o una versión posterior, la salida es idéntica a la generada por el ejemplo cuando se ejecuta en .NET Framework 3,5.

```xml
<?xml version ="1.0"?>
<configuration>
   <runtime>
      <TimeSpan_LegacyFormatMode enabled="true"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
