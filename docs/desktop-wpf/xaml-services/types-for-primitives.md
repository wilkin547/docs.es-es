---
title: Tipos integrados para primitivas comunes en el lenguaje XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML language primitives [XAML Services]
- XAML [XAML Services], built-in types
- x:String [XAML Services]
- x:TimeSpan [XAML Services]
- x:Byte [XAML Services]
- x:Double [XAML Services]
- XAML [XAML Services], types
- x:Uri [XAML Services]
- XAML built-in types [XAML Services]
- x:Int64 [XAML Services]
- x:Single [XAML Services]
- x:Int32 [XAML Services]
ms.assetid: 11de2f08-5b95-4989-b5ec-5178eb968184
ms.openlocfilehash: 3bd486ee66c5f9a32621416638bb7575025f7dee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433059"
---
# <a name="built-in-types-for-common-xaml-language-primitives"></a>Tipos integrados para primitivas de lenguaje XAML comunes

XAML 2009 presenta la compatibilidad de nivel de lenguaje XAML con varios tipos de datos que son primitivas usadas con frecuencia en Common Language Runtime (CLR) y otros lenguajes de programación. XAML 2009 agrega compatibilidad con estas primitivas: `x:Object`, `x:Boolean`, `x:Char`, `x:String`, `x:Decimal`, `x:Single`, `x:Double`, `x:Int16`, `x:Int32`, `x:Int64`, `x:TimeSpan`, `x:Uri`, `x:Byte`y `x:Array`

## <a name="previous-techniques-for-language-primitives-in-xaml-markup"></a>Técnicas anteriores para las primitivas del lenguaje en el marcado XAML

 En XAML para versiones anteriores de WPF, se podía hacer referencia a las primitivas del lenguaje CLR si se asignaba el ensamblado y el espacio de nombres que contenían una clase de definición de primitiva CLR para .NET Framework. La mayoría se encuentra en el ensamblado mscorlib y el espacio de nombres <xref:System> . Por ejemplo, para usar <xref:System.Int32>, podría declarar la siguiente asignación (con un uso de ejemplo mostrado a continuación):

```xaml
<Application xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
xmlns:sys="clr-namespace:System;assembly=mscorlib">
  <Application.Resources>
    <sys:Int32 x:Key="intMeaning">42</sys:Int32>
  </Application.Resources>
</Application>
```

## <a name="xaml-2009-language-primitives"></a>Primitivas del lenguaje XAML 2009

Por convención, se muestran las primitivas del lenguaje para XAML y todos los demás elementos del lenguaje XAML, incluido el prefijo `x:` . Así es como se usan normalmente los elementos del lenguaje XAML en el marcado del mundo real. Esta convención se sigue en la documentación conceptual de XAML en WPF y también en la especificación XAML.

### <a name="xobject"></a>x:Object

En copias de seguridad de CLR, la primitiva `x:Object` corresponde a <xref:System.Object>.

Esta primitiva no se usa normalmente en el marcado de aplicaciones, pero puede resultar útil en algunos escenarios como la comprobación de la capacidad de asignación en un sistema de tipos XAML.

### <a name="xboolean"></a>x:Boolean

En copias de seguridad de CLR, la primitiva `x:Boolean` corresponde a <xref:System.Boolean>.

XAML analiza los valores de `x:Boolean` como si no distinguieran entre mayúsculas y minúsculas. Tenga en cuenta que `x:Bool` no es una alternativa aceptada. Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.17 y 5.4.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xchar"></a>x:Char

En copias de seguridad de CLR, la primitiva `x:Char` corresponde a <xref:System.Char>.

Los tipos de cadena y carácter tienen interacción con la codificación general del archivo en el nivel XML. Para obtener la definición de especificación del lenguaje XAML, vea [ \[Las secciones 5.2.7 y 5.4.1 de MS-XAML.\] ](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))

### <a name="xstring"></a>x:String

En copias de seguridad de CLR, la primitiva `x:String` corresponde a <xref:System.String>.

Los tipos de cadena y carácter tienen interacción con la codificación general del archivo en el nivel XML. Para obtener la definición de especificación del lenguaje XAML, vea [ \[Secciones\] 5.2.6 de MS-XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xdecimal"></a>x:Decimal

En copias de seguridad de CLR, la primitiva `x:Decimal` corresponde a <xref:System.Decimal>.

El análisis XAML se `en-US` realiza intrínsecamente en la referencia cultural. En la referencia cultural `en-US` , el separador correcto de los componentes de un decimal es siempre un punto (`.`) independientemente de la configuración de referencia cultural del entorno de desarrollo o del destino de cliente final donde se carga XAML en tiempo de ejecución.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.14 y 5.4.8](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xsingle"></a>x:Single

En copias de seguridad de CLR, la primitiva `x:Single` corresponde a <xref:System.Single>.

Además de los valores numéricos, la sintaxis de texto de `x:Single` también permite los tokens `Infinity`, `-Infinity`y `NaN`. En los tokens se distinguen mayúsculas de minúsculas.

`x:Single` puede admitir valores en formato de notación científica si el primer carácter de la sintaxis de texto es `e` o `E`.

Para obtener la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.8 y 5.4.2](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xdouble"></a>x:Double

En copias de seguridad de CLR, la primitiva `x:Double` corresponde a <xref:System.Double>.

Además de los valores numéricos, la sintaxis de texto de `x:Double` permite los tokens `Infinity`, `-Infinity`y `NaN`. En los tokens se distinguen mayúsculas de minúsculas.

`x:Double` puede admitir valores en formato de notación científica. Use el carácter `e` o `E` para presentar la parte del exponente.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.9 y 5.4.3](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint16"></a>x:Int16

En copias de seguridad de CLR, la primitiva `x:Int16` corresponde a <xref:System.Int16> y `x:Int16` se trata como un valor con signo. En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.11 y 5.4.5](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint32"></a>x:Int32

En copias de seguridad de CLR, la primitiva `x:Int32` corresponde a <xref:System.Int32>. `x:Int32` se trata como un valor con signo. En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.12 y 5.4.6](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xint64"></a>x:Int64

En copias de seguridad de CLR, la primitiva `x:Int64` corresponde a <xref:System.Int64>. `x:Int64` se trata como un valor con signo. En XAML, la ausencia de un signo más (`+`) en la sintaxis de texto se considera como un valor con signo positivo.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.13 y 5.4.7](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xtimespan"></a>x:TimeSpan

En copias de seguridad de CLR, la primitiva `x:TimeSpan` corresponde a <xref:System.TimeSpan>.

El análisis XAML para el formato de `en-US` fecha y hora se realiza intrínsecamente en la referencia cultural.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.16 y 5.4.10](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xuri"></a>x:Uri

En copias de seguridad de CLR, la primitiva `x:Uri` corresponde a <xref:System.Uri>.

La comprobación de los protocolos no forma parte de la definición de XAML para `x:Uri`.

Para la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.15 y 5.4.9](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xbyte"></a>x:Byte

En copias de seguridad de CLR, la primitiva `x:Byte` corresponde a <xref:System.Byte>. <xref:System.Byte>  /  A `x:Byte` se trata como sin firmar.

Para obtener la definición de especificación del lenguaje XAML, vea [ \[MS-XAML\] Sections 5.2.10 y 5.4.4](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

### <a name="xarray"></a>x:Array

En copias de seguridad de CLR, la primitiva `x:Array` corresponde a <xref:System.Array>.

Puede definir una matriz en XAML 2006 con una sintaxis de extensión de marcado; sin embargo, la sintaxis de XAML 2009 es una primitiva definida por el lenguaje que no necesita acceso a una extensión de marcado. Para más información sobre la compatibilidad con XAML 2006, vea [x:Array Markup Extension](xarray-markup-extension.md).

Para obtener la definición de especificación del lenguaje XAML, vea [ \[Secciones\] 5.2.18 de MS-XAML](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).

## <a name="wpf-support"></a>Compatibilidad de WPF

En WPF, puede usar las características de XAML 2009 pero solo para XAML que no se haya compilado por marcado. XAML compilado por marcado para WPF y el formulario BAML de XAML no admiten de momento las palabras clave y características de XAML 2009.

Un escenario donde puede usar las características de XAML 2009 junto con WPF es si crea XAML dinámico y, a continuación, carga ese XAML en un gráfico de objetos y tiempo de ejecución de WPF con <xref:System.Windows.Markup.XamlReader.Load%2A?displayProperty=nameWithType>. <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> de WPF y su <xref:System.Windows.Markup.XamlReader.Load%2A> pueden procesar las características y palabras clave del lenguaje XAML 2009 en una representación de gráfico de objetos válido.
