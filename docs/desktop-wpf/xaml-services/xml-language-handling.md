---
title: Control de xml:lang en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b5a06adbb7cb874bc09899118f13b91fbec7a85e
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432711"
---
# <a name="xmllang-handling-in-xaml"></a>Control de xml:lang en XAML

El `xml:lang` atributo es un atributo definido por XML que declara la información de idioma y referencia cultural de un elemento en XML. Este mismo significado del atributo persiste en XAML; sin embargo, se aplican algunas consideraciones adicionales.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*rfc3066lang*|Una cadena que se deriva del estándar [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) e identifica un idioma o un idioma-región. En el caso de la segunda opción, el idioma y la región se separan con un solo guión. Para más información sobre los valores y el formato, vea <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Observaciones

La definición `xml:lang` del [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] atributo in `xml:lang` se deriva de la definición definida como un "atributo especial" por el World Wide Web Consortium (W3C) para XML. La información del idioma y de la referencia cultural se puede procesar de maneras diferentes, en función de sus implementaciones; sin embargo, no hay ningún procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predeterminado del atributo `xml:lang` .

El valor predeterminado del atributo `xml:lang` es una cadena vacía en el nivel de atributo.

Los efectos del atributo `xml:lang` y el valor del atributo suelen perpetuarse para los elementos secundarios, cuando se interpretan por los sistemas que actúan en los valores `xml:lang` .

Cuando los escritores XAML de Servicios XAML `xml:lang` de <xref:System.Windows.Markup.XmlLanguage> .NET, un valor puede crear u <xref:System.Globalization.CultureInfo> objetos en la representación de objeto subyacente; sin embargo, ese comportamiento depende `xml:lang` de si el valor especificado para es una construcción válida para esas clases.

Los marcos de trabajo pueden crear asociaciones entre las propiedades definidas por el marco de trabajo y el significado de `xml:lang` en XML aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a la propiedad.

## <a name="wpf-usage-nodes"></a>Nodos de uso de WPF

Para los elementos que son las clases derivadas de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede usar la propiedad de dependencia <xref:System.Windows.FrameworkElement.Language%2A> equivalente en lugar del atributo `xml:lang` . De forma predeterminada, la propiedad <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" si no se establece de otra manera, a través de la propiedad o mediante el procesamiento del atributo `xml:lang` .

## <a name="see-also"></a>Consulte también

- [Globalización de WPF](../../framework/wpf/advanced/globalization-for-wpf.md)
