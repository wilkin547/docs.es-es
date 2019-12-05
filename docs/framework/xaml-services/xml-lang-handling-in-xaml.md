---
title: Control de xml:lang en XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: b3f236b2378d6af78f034856e3ba0f7a9e17993c
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837147"
---
# <a name="xmllang-handling-in-xaml"></a>Control de xml:lang en XAML
El atributo `xml:lang` es un atributo definido por XML que declara la información de idioma y de referencia cultural para un elemento en XML. Este mismo significado del atributo persiste en XAML; sin embargo, se aplican algunas consideraciones adicionales.  
  
## <a name="xaml-attribute-usage"></a>Uso de atributos XAML  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|*rfc3066lang*|Una cadena que se deriva del estándar [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) e identifica un idioma o un idioma-región. En el caso de la segunda opción, el idioma y la región se separan con un solo guión. Para más información sobre los valores y el formato, vea <xref:System.Windows.Markup.XmlLanguage> .|  
  
## <a name="remarks"></a>Notas  
 La definición del atributo `xml:lang` en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] deriva de `xml:lang` tal como se define como un "atributo especial" por el World Wide Web Consortium (W3C) for XML. La información del idioma y de la referencia cultural se puede procesar de maneras diferentes, en función de sus implementaciones; sin embargo, no hay ningún procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predeterminado del atributo `xml:lang` .  
  
 El valor predeterminado del atributo `xml:lang` es una cadena vacía en el nivel de atributo.  
  
 Los efectos del atributo `xml:lang` y el valor del atributo suelen perpetuarse para los elementos secundarios, cuando se interpretan por los sistemas que actúan en los valores `xml:lang` .  
  
 Cuando se interpreta por objetos de escritura XAML de los servicios XAML de .NET Framework, un valor `xml:lang` puede crear objetos <xref:System.Windows.Markup.XmlLanguage> o <xref:System.Globalization.CultureInfo> en la representación de objetos subyacente; sin embargo, ese comportamiento depende de si el valor especificado para `xml:lang` es una construcción válida para esas clases.  
  
 Los marcos de trabajo pueden crear asociaciones entre las propiedades definidas por el marco de trabajo y el significado de `xml:lang` en XML aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a la propiedad.  
  
## <a name="wpf-usage-nodes"></a>Nodos de uso de WPF  
 Para los elementos que son las clases derivadas de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede usar la propiedad de dependencia <xref:System.Windows.FrameworkElement.Language%2A> equivalente en lugar del atributo `xml:lang` . De forma predeterminada, la propiedad <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" si no se establece de otra manera, a través de la propiedad o mediante el procesamiento del atributo `xml:lang` .  
  
## <a name="see-also"></a>Vea también

- [Globalización de WPF](../wpf/advanced/globalization-for-wpf.md)
