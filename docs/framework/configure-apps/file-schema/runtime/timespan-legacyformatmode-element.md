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
ms.openlocfilehash: 9d9eedf52f5d711412e4549e39e6ea23abb68ff3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "73968904"
---
# <a name="timespan_legacyformatmode-element"></a>\<TimeSpan_LegacyFormatMode> (Elemento)

Determina si el tiempo de ejecución conserva el comportamiento heredado en operaciones de formato con <xref:System.TimeSpan?displayProperty=nameWithType> valores.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<TimeSpan_LegacyFormatMode>**  

## <a name="syntax"></a>Sintaxis

```xml
<TimeSpan_LegacyFormatMode
   enabled="true|false"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si el Runtime usa el comportamiento de formato heredado con <xref:System.TimeSpan?displayProperty=nameWithType> valores.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|Descripción|
|-----------|-----------------|
|`false`|El motor en tiempo de ejecución no restaura el comportamiento de formato heredado.|
|`true`|El motor en tiempo de ejecución restaura el comportamiento de formato heredado.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Comentarios

A partir de la .NET Framework 4, la <xref:System.TimeSpan?displayProperty=nameWithType> estructura implementa la <xref:System.IFormattable> interfaz y admite operaciones de formato con cadenas de formato estándar y personalizadas. Si un método de análisis encuentra un especificador de formato no compatible o una cadena de formato, produce una excepción <xref:System.FormatException> .

En versiones anteriores del .NET Framework, la <xref:System.TimeSpan> estructura no implementaba <xref:System.IFormattable> y no admitía cadenas de formato. Sin embargo, muchos desarrolladores suponían erróneamente que <xref:System.TimeSpan> admiten un conjunto de cadenas de formato y las usaban en [operaciones de formato compuesto](../../../../standard/base-types/composite-formatting.md) con métodos como <xref:System.String.Format%2A?displayProperty=nameWithType> . Normalmente, si un tipo implementa <xref:System.IFormattable> y admite cadenas de formato, las llamadas a métodos de formato con cadenas de formato no admitidas normalmente producen una excepción <xref:System.FormatException> . Sin embargo, dado <xref:System.TimeSpan> que no implementó <xref:System.IFormattable> , el tiempo de ejecución omitió la cadena de formato y, en su lugar, llamó al <xref:System.TimeSpan.ToString?displayProperty=nameWithType> método. Esto significa que, aunque las cadenas de formato no tenían ningún efecto en la operación de formato, su presencia no da como resultado una <xref:System.FormatException> .

En los casos en que el código heredado pasa un método de formato compuesto y una cadena de formato no válida, y ese código no se puede volver a compilar, puede usar el `<TimeSpan_LegacyFormatMode>` elemento para restaurar el comportamiento heredado <xref:System.TimeSpan> . Al establecer el `enabled` atributo de este elemento en `true` , el método de formato compuesto produce una llamada a en <xref:System.TimeSpan.ToString?displayProperty=nameWithType> lugar de <xref:System.TimeSpan.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType> , y <xref:System.FormatException> no se produce una excepción.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crea una instancia de un <xref:System.TimeSpan> objeto y se intenta dar formato al <xref:System.String.Format%28System.String%2CSystem.Object%29?displayProperty=nameWithType> método mediante una cadena de formato estándar no compatible.

[!code-csharp[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/timespan.breakingchanges/cs/legacyformatmode1.cs#1)]
[!code-vb[TimeSpan.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/timespan.breakingchanges/vb/legacyformatmode1.vb#1)]

Al ejecutar el ejemplo en el .NET Framework 3,5 o en una versión anterior, se muestra el siguiente resultado:

```console
12:30:45
```

Esto difiere notablemente de la salida si ejecuta el ejemplo en el .NET Framework 4 o una versión posterior:

```console
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

## <a name="see-also"></a>Consulte también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
