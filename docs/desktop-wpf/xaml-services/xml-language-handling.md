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
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="12d7d-102">Control de xml:lang en XAML</span><span class="sxs-lookup"><span data-stu-id="12d7d-102">xml:lang Handling in XAML</span></span>

<span data-ttu-id="12d7d-103">El `xml:lang` atributo es un atributo definido por XML que declara la información de idioma y referencia cultural de un elemento en XML.</span><span class="sxs-lookup"><span data-stu-id="12d7d-103">The `xml:lang` attribute is an XML-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="12d7d-104">Este mismo significado del atributo persiste en XAML; sin embargo, se aplican algunas consideraciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="12d7d-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="12d7d-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="12d7d-105">XAML Attribute Usage</span></span>

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a><span data-ttu-id="12d7d-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="12d7d-106">XAML Values</span></span>

|||
|-|-|
|<span data-ttu-id="12d7d-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="12d7d-107">*rfc3066lang*</span></span>|<span data-ttu-id="12d7d-108">Una cadena que se deriva del estándar [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) e identifica un idioma o un idioma-región.</span><span class="sxs-lookup"><span data-stu-id="12d7d-108">A string that is derived from the [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="12d7d-109">En el caso de la segunda opción, el idioma y la región se separan con un solo guión.</span><span class="sxs-lookup"><span data-stu-id="12d7d-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="12d7d-110">Para más información sobre los valores y el formato, vea <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="12d7d-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|

## <a name="remarks"></a><span data-ttu-id="12d7d-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="12d7d-111">Remarks</span></span>

<span data-ttu-id="12d7d-112">La definición `xml:lang` del [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] atributo in `xml:lang` se deriva de la definición definida como un "atributo especial" por el World Wide Web Consortium (W3C) para XML.</span><span class="sxs-lookup"><span data-stu-id="12d7d-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for XML.</span></span> <span data-ttu-id="12d7d-113">La información del idioma y de la referencia cultural se puede procesar de maneras diferentes, en función de sus implementaciones; sin embargo, no hay ningún procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predeterminado del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="12d7d-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>

<span data-ttu-id="12d7d-114">El valor predeterminado del atributo `xml:lang` es una cadena vacía en el nivel de atributo.</span><span class="sxs-lookup"><span data-stu-id="12d7d-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>

<span data-ttu-id="12d7d-115">Los efectos del atributo `xml:lang` y el valor del atributo suelen perpetuarse para los elementos secundarios, cuando se interpretan por los sistemas que actúan en los valores `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="12d7d-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>

<span data-ttu-id="12d7d-116">Cuando los escritores XAML de Servicios XAML `xml:lang` de <xref:System.Windows.Markup.XmlLanguage> .NET, un valor puede crear u <xref:System.Globalization.CultureInfo> objetos en la representación de objeto subyacente; sin embargo, ese comportamiento depende `xml:lang` de si el valor especificado para es una construcción válida para esas clases.</span><span class="sxs-lookup"><span data-stu-id="12d7d-116">When interpreted by XAML writers of .NET XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>

<span data-ttu-id="12d7d-117">Los marcos de trabajo pueden crear asociaciones entre las propiedades definidas por el marco de trabajo y el significado de `xml:lang` en XML aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="12d7d-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>

## <a name="wpf-usage-nodes"></a><span data-ttu-id="12d7d-118">Nodos de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="12d7d-118">WPF Usage Nodes</span></span>

<span data-ttu-id="12d7d-119">Para los elementos que son las clases derivadas de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede usar la propiedad de dependencia <xref:System.Windows.FrameworkElement.Language%2A> equivalente en lugar del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="12d7d-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="12d7d-120">De forma predeterminada, la propiedad <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" si no se establece de otra manera, a través de la propiedad o mediante el procesamiento del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="12d7d-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="12d7d-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="12d7d-121">See also</span></span>

- [<span data-ttu-id="12d7d-122">Globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="12d7d-122">Globalization for WPF</span></span>](../../framework/wpf/advanced/globalization-for-wpf.md)
