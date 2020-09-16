---
title: Control de xml:lang en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 92d1eda62ff394df54d9607bab46d9950681e603
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548213"
---
# <a name="xmllang-handling-in-xaml"></a>Control de xml:lang en XAML

El `xml:lang` atributo es un atributo definido por XML que declara la información de idioma y de referencia cultural para un elemento en XML. Este mismo significado del atributo persiste en XAML; sin embargo, se aplican algunas consideraciones adicionales.

## <a name="xaml-attribute-usage"></a>Uso de atributos XAML

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>Valores XAML

|||
|-|-|
|*rfc3066lang*|Una cadena que se deriva del estándar [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) e identifica un idioma o un idioma-región. En el caso de la segunda opción, el idioma y la región se separan con un solo guión. Para más información sobre los valores y el formato, vea <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Comentarios

La definición del `xml:lang` atributo en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] se deriva de `xml:lang` como se define como un "atributo especial" por el World Wide Web Consortium (W3C) para XML. La información del idioma y de la referencia cultural se puede procesar de maneras diferentes, en función de sus implementaciones; sin embargo, no hay ningún procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predeterminado del atributo `xml:lang` .

El valor predeterminado del atributo `xml:lang` es una cadena vacía en el nivel de atributo.

Los efectos del atributo `xml:lang` y el valor del atributo suelen perpetuarse para los elementos secundarios, cuando se interpretan por los sistemas que actúan en los valores `xml:lang` .

Cuando lo interpretan los sistemas de escritura XAML de los servicios XAML de .NET, un `xml:lang` valor puede crear <xref:System.Windows.Markup.XmlLanguage> <xref:System.Globalization.CultureInfo> objetos o en la representación de objeto subyacente; sin embargo, ese comportamiento depende de si el valor especificado para `xml:lang` es una construcción válida para esas clases.

Los marcos de trabajo pueden crear asociaciones entre las propiedades definidas por el marco de trabajo y el significado de `xml:lang` en XML aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a la propiedad.

## <a name="wpf-usage-nodes"></a>Nodos de uso de WPF

Para los elementos que son las clases derivadas de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede usar la propiedad de dependencia <xref:System.Windows.FrameworkElement.Language%2A> equivalente en lugar del atributo `xml:lang` . De forma predeterminada, la propiedad <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" si no se establece de otra manera, a través de la propiedad o mediante el procesamiento del atributo `xml:lang` .

## <a name="see-also"></a>Vea también

- [Globalización de WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
