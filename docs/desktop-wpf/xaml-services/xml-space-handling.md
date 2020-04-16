---
title: Control de xml:space en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: 886f906b6d1e3a10920dbf52e36bf76324c5a9f2
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432705"
---
# <a name="xmlspace-handling-in-xaml"></a>Control de xml:space en XAML

El `xml:space` atributo es un atributo definido por XML que declara el comportamiento significativo de procesamiento de espacios en blanco dentro de un elemento de objeto. Este comportamiento es relevante para todo el contenido (texto interno) contenido en el elemento donde `xml:space` se declara y también ámbitos a elementos secundarios.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object xml:space="preserve" />
```

 \- o -

```xaml
<object xml:space="default" />
```

## <a name="remarks"></a>Observaciones

La definición `xml:space` del atributo en XAML, incluidos `xml:space` sus dos valores posibles, se deriva como definido como un "atributo especial" por las especificaciones W3C para XML.

El valor predeterminado `xml:space` del atributo `"default"`es el valor literal . Para el `"default"`valor `xml:space` , o si no se indica en absoluto, el comportamiento del análisis de espacios en blanco significativo es el control predeterminado, tal como se define en el tema Procesamiento de espacio en [blanco en XAML](white-space-processing.md).

Para conservar el espacio en `xml:space="preserve"` blanco dentro del contenido del elemento de objeto, especifique en ese elemento de objeto.

En la mayoría `xml:space` de las interpretaciones, los efectos de atributo y el valor del atributo se limitan a los elementos secundarios.

Para obtener una explicación completa del procesamiento de espacios en blanco en XAML, vea [Procesamiento de espacio en blanco en XAML](white-space-processing.md).

## <a name="see-also"></a>Consulte también

- [Procesamiento de espacios en blanco en XAML](white-space-processing.md)
- [Información general sobre XAML (WPF)](../fundamentals/xaml.md)
