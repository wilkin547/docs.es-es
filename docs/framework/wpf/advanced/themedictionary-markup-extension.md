---
title: Extensión de marcado ThemeDictionary
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: f6ba0fe45aa11063c79d673b26794072968f4200
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646184"
---
# <a name="themedictionary-markup-extension"></a><span data-ttu-id="1ea0a-102">Extensión de marcado ThemeDictionary</span><span class="sxs-lookup"><span data-stu-id="1ea0a-102">ThemeDictionary Markup Extension</span></span>
<span data-ttu-id="1ea0a-103">Proporciona a los autores de controles personalizados o a las aplicaciones que integran controles de otros fabricantes una manera de cargar los diccionarios de recursos específicos del tema para usarlos en la aplicación de estilos al control.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-103">Provides a way for custom control authors or applications that integrate third-party controls to load theme-specific resource dictionaries to use in styling the control.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="1ea0a-104">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="1ea0a-104">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="1ea0a-105">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="1ea0a-105">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="1ea0a-106">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="1ea0a-106">XAML Values</span></span>  
  
|||  
|-|-|  
|`assemblyUri`|<span data-ttu-id="1ea0a-107">Identificador uniforme de recursos (URI) del ensamblado que contiene información del tema.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-107">The uniform resource identifier (URI) of the assembly that contains theme information.</span></span> <span data-ttu-id="1ea0a-108">Normalmente, se trata de un Pack URI que hace referencia a un ensamblado en el paquete mayor.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-108">Typically, this is a pack URI that references an assembly in the larger package.</span></span> <span data-ttu-id="1ea0a-109">Los recursos de ensamblado y los Pack URI simplifican los problemas de implementación.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-109">Assembly resources and pack URIs simplify deployment issues.</span></span> <span data-ttu-id="1ea0a-110">Para más información, vea [Empaquetar URI en WPF](../app-development/pack-uris-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="1ea0a-110">For more information see [Pack URIs in WPF](../app-development/pack-uris-in-wpf.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1ea0a-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1ea0a-111">Remarks</span></span>  
 <span data-ttu-id="1ea0a-112">Esta extensión está diseñada para rellenar solo un <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>valor de propiedad específico: un valor para .</span><span class="sxs-lookup"><span data-stu-id="1ea0a-112">This extension is intended to fill only one specific property value: a value for <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1ea0a-113">Mediante esta extensión, puede especificar un único ensamblado de solo recursos que contenga algunos estilos para usar solo cuando el tema Aero de Windows se aplica al sistema del usuario, otros estilos solo cuando el tema Luna está activo, etc.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-113">By using this extension, you can specify a single resources-only assembly that contains some styles to use only when the Windows Aero theme is applied to the user's system, other styles only when the Luna theme is active, and so on.</span></span> <span data-ttu-id="1ea0a-114">Al usar esta extensión, se puede invalidar automáticamente y volver a cargar el contenido de un diccionario de recursos específico del control de modo que sea específico de otro tema cuando se necesite.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-114">By using this extension, the contents of a control-specific resource dictionary can be automatically invalidated and reloaded to be specific for another theme when required.</span></span>  
  
 <span data-ttu-id="1ea0a-115">La `assemblyUri` cadena<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> (valor de propiedad) forma la base de una convención de nomenclatura que identifica qué diccionario se aplica a un tema determinado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-115">The `assemblyUri` string (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property value) forms the basis of a naming convention that identifies which dictionary applies for a particular theme.</span></span> <span data-ttu-id="1ea0a-116">La <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> lógica `ThemeDictionary` para completar la convención mediante la generación de un identificador uniforme de recursos (URI) que apunta a una variante de diccionario de tema determinado, como se encuentra dentro de un ensamblado de recursos precompilado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-116">The <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> logic for `ThemeDictionary` completes the convention by generating a uniform resource identifier (URI) that points to a particular theme dictionary variant, as contained within a precompiled resource assembly.</span></span> <span data-ttu-id="1ea0a-117">En este artículo no se aborda plenamente la descripción de esta convención, ni el concepto de las interacciones de los temas con la aplicación general de estilos a controles o en el nivel de aplicación o de página.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-117">Describing this convention, or theme interactions with general control styling and page/application level styling as a concept, is not covered fully here.</span></span> <span data-ttu-id="1ea0a-118">El escenario básico `ThemeDictionary` para su <xref:System.Windows.ResourceDictionary.Source%2A> uso `ResourceDictionary` es especificar la propiedad de un declarado en el nivel de aplicación.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-118">The basic scenario for using `ThemeDictionary` is to specify the <xref:System.Windows.ResourceDictionary.Source%2A> property of a `ResourceDictionary` declared at the application level.</span></span> <span data-ttu-id="1ea0a-119">Cuando se proporciona un URI `ThemeDictionary` para el ensamblado a través de una extensión en lugar de como un URI directo, la lógica de extensión proporcionará lógica de invalidación que se aplica siempre que cambie el tema del sistema.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-119">When you provide a URI for the assembly through a `ThemeDictionary` extension rather than as a direct URI, the extension logic will provide invalidation logic that applies whenever the system theme changes.</span></span>  
  
 <span data-ttu-id="1ea0a-120">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-120">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="1ea0a-121">El token de cadena que se proporciona después de la cadena de identificador `ThemeDictionary` se asigna como valor de <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> de la clase de extensión <xref:System.Windows.ThemeDictionaryExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-121">The string token provided after the `ThemeDictionary` identifier string is assigned as the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> value of the underlying <xref:System.Windows.ThemeDictionaryExtension> extension class.</span></span>  
  
 <span data-ttu-id="1ea0a-122">`ThemeDictionary` también se puede usar en la sintaxis de elementos de objeto.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-122">`ThemeDictionary` may also be used in object element syntax.</span></span> <span data-ttu-id="1ea0a-123">En este caso, se requiere <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> especificar el valor de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-123">In this case, specifying the value of the <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> property is required.</span></span>  
  
 <span data-ttu-id="1ea0a-124">`ThemeDictionary` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.Markup.StaticExtension.Member%2A> como un par de propiedad=valor:</span><span class="sxs-lookup"><span data-stu-id="1ea0a-124">`ThemeDictionary` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.Markup.StaticExtension.Member%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 <span data-ttu-id="1ea0a-125">El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-125">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="1ea0a-126">Dado que `ThemeDictionary` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-126">Because `ThemeDictionary` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="1ea0a-127">En [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] la implementación del procesador, la <xref:System.Windows.ThemeDictionaryExtension> clase define el control de esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-127">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.ThemeDictionaryExtension> class.</span></span>  
  
 <span data-ttu-id="1ea0a-128">`ThemeDictionary` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-128">`ThemeDictionary` is a markup extension.</span></span> <span data-ttu-id="1ea0a-129">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-129">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="1ea0a-130">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="1ea0a-130">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="1ea0a-131">Para más información, vea [Extensiones de marcado y XAML de WPF](markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="1ea0a-131">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ea0a-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1ea0a-132">See also</span></span>

- [<span data-ttu-id="1ea0a-133">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="1ea0a-133">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [<span data-ttu-id="1ea0a-134">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="1ea0a-134">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="1ea0a-135">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="1ea0a-135">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="1ea0a-136">Archivos de recursos, contenido y datos de aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="1ea0a-136">WPF Application Resource, Content, and Data Files</span></span>](../app-development/wpf-application-resource-content-and-data-files.md)
