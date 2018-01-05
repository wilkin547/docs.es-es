---
title: Control de xml:lang en XAML
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3dad1600d93f53198d7ca7842148612b7755fc10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="29f98-102">Control de xml:lang en XAML</span><span class="sxs-lookup"><span data-stu-id="29f98-102">xml:lang Handling in XAML</span></span>
<span data-ttu-id="29f98-103">El atributo `xml:lang` es un atributo definido por [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]que declara la información de idioma y referencia cultural para un elemento en XML.</span><span class="sxs-lookup"><span data-stu-id="29f98-103">The `xml:lang` attribute is an [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="29f98-104">Este mismo significado del atributo persiste en XAML; sin embargo, se aplican algunas consideraciones adicionales.</span><span class="sxs-lookup"><span data-stu-id="29f98-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="29f98-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="29f98-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="29f98-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="29f98-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="29f98-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="29f98-107">*rfc3066lang*</span></span>|<span data-ttu-id="29f98-108">Una cadena que se deriva del estándar [RFC 3066](http://go.microsoft.com/fwlink/?LinkId=132454) e identifica un idioma o un idioma-región.</span><span class="sxs-lookup"><span data-stu-id="29f98-108">A string that is derived from the [RFC 3066](http://go.microsoft.com/fwlink/?LinkId=132454) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="29f98-109">En el caso de la segunda opción, el idioma y la región se separan con un solo guión.</span><span class="sxs-lookup"><span data-stu-id="29f98-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="29f98-110">Para más información sobre los valores y el formato, vea <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="29f98-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29f98-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29f98-111">Remarks</span></span>  
 <span data-ttu-id="29f98-112">La definición del atributo `xml:lang` en [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] se deriva de `xml:lang` definido como un "atributo especial" por [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] para [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29f98-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the [!INCLUDE[TLA#tla_w3c](../../../includes/tlasharptla-w3c-md.md)] for [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)].</span></span> <span data-ttu-id="29f98-113">La información del idioma y de la referencia cultural se puede procesar de maneras diferentes, en función de sus implementaciones; sin embargo, no hay ningún procesamiento de [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] predeterminado del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="29f98-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>  
  
 <span data-ttu-id="29f98-114">El valor predeterminado del atributo `xml:lang` es una cadena vacía en el nivel de atributo.</span><span class="sxs-lookup"><span data-stu-id="29f98-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>  
  
 <span data-ttu-id="29f98-115">Los efectos del atributo `xml:lang` y el valor del atributo suelen perpetuarse para los elementos secundarios, cuando se interpretan por los sistemas que actúan en los valores `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="29f98-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>  
  
 <span data-ttu-id="29f98-116">Cuando se interpreta por objetos de escritura XAML de los servicios XAML de .NET Framework, un valor `xml:lang` puede crear objetos <xref:System.Windows.Markup.XmlLanguage> o <xref:System.Globalization.CultureInfo> en la representación de objetos subyacente; sin embargo, ese comportamiento depende de si el valor especificado para `xml:lang` es una construcción válida para esas clases.</span><span class="sxs-lookup"><span data-stu-id="29f98-116">When interpreted by XAML writers of .NET Framework XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>  
  
 <span data-ttu-id="29f98-117">Los marcos de trabajo pueden crear asociaciones entre las propiedades definidas por el marco de trabajo y el significado de `xml:lang` en XML aplicando <xref:System.Windows.Markup.XmlLangPropertyAttribute> a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="29f98-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>  
  
## <a name="wpf-usage-nodes"></a><span data-ttu-id="29f98-118">Nodos de uso de WPF</span><span class="sxs-lookup"><span data-stu-id="29f98-118">WPF Usage Nodes</span></span>  
 <span data-ttu-id="29f98-119">Para los elementos que son las clases derivadas de <xref:System.Windows.FrameworkElement> o <xref:System.Windows.FrameworkContentElement>, puede usar la propiedad de dependencia <xref:System.Windows.FrameworkElement.Language%2A> equivalente en lugar del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="29f98-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="29f98-120">De forma predeterminada, la propiedad <xref:System.Windows.FrameworkElement.Language%2A> usa "en-US" si no se establece de otra manera, a través de la propiedad o mediante el procesamiento del atributo `xml:lang` .</span><span class="sxs-lookup"><span data-stu-id="29f98-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29f98-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="29f98-121">See Also</span></span>  
 [<span data-ttu-id="29f98-122">Globalización de WPF</span><span class="sxs-lookup"><span data-stu-id="29f98-122">Globalization for WPF</span></span>](../../../docs/framework/wpf/advanced/globalization-for-wpf.md)
