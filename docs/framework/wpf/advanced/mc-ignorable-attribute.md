---
title: Atributo mc:Ignorable
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: 03439a2c4a1a4de375e90d0e5121e690541e2f0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219335"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="92fbb-102">Atributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="92fbb-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="92fbb-103">Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacios de nombres que se encuentre en un archivo de marcado pueden ser omitidos por un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador.</span><span class="sxs-lookup"><span data-stu-id="92fbb-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="92fbb-104">El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado tanto para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.</span><span class="sxs-lookup"><span data-stu-id="92fbb-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="92fbb-105">Uso de atributos XAML (un solo prefijo)</span><span class="sxs-lookup"><span data-stu-id="92fbb-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="92fbb-106">Uso de atributos XAML (dos prefijos)</span><span class="sxs-lookup"><span data-stu-id="92fbb-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="92fbb-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="92fbb-107">XAML Values</span></span>  
  
|||  
|-|-|  
|*<span data-ttu-id="92fbb-108">ignorablePrefix, ignorablePrefix1, etc.</span><span class="sxs-lookup"><span data-stu-id="92fbb-108">ignorablePrefix, ignorablePrefix1, etc.</span></span>*|<span data-ttu-id="92fbb-109">Cualquier cadena de prefijo válido, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="92fbb-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|*<span data-ttu-id="92fbb-110">ignorableUri</span><span class="sxs-lookup"><span data-stu-id="92fbb-110">ignorableUri</span></span>*|<span data-ttu-id="92fbb-111">Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="92fbb-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|*<span data-ttu-id="92fbb-112">ThisElementCanBeIgnored</span><span class="sxs-lookup"><span data-stu-id="92fbb-112">ThisElementCanBeIgnored</span></span>*|<span data-ttu-id="92fbb-113">Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones de procesadores, si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="92fbb-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92fbb-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92fbb-114">Remarks</span></span>  
 <span data-ttu-id="92fbb-115">El `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijo de espacio de nombres es la convención de prefijo recomendado para usar al asignar el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] espacio de nombres de compatibilidad [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92fbb-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="92fbb-116">Los elementos o atributos donde se identifican la parte del prefijo del nombre del elemento como `mc:Ignorable` no provocará errores cuando se procesa mediante un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador.</span><span class="sxs-lookup"><span data-stu-id="92fbb-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="92fbb-117">Si no se pudo resolver en un tipo subyacente o la construcción de programación ese atributo, se omite ese elemento.</span><span class="sxs-lookup"><span data-stu-id="92fbb-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="92fbb-118">Sin embargo, tenga en cuenta que los elementos omitidos pueden generar errores de análisis adicionales para los requisitos de elemento adicionales que son los efectos secundarios de ese elemento no se está procesando.</span><span class="sxs-lookup"><span data-stu-id="92fbb-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="92fbb-119">Por ejemplo, un modelo de contenido del elemento en particular podría requerir exactamente un elemento secundario, pero si el elemento secundario especificado estaba en un `mc:Ignorable` prefijo y el elemento secundario especificado no se pueden resolver a un tipo, el [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] podría de procesador se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="92fbb-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 `mc:Ignorable` <span data-ttu-id="92fbb-120">solo se aplica a las asignaciones de espacio de nombres a las cadenas de identificador.</span><span class="sxs-lookup"><span data-stu-id="92fbb-120">only applies to namespace mappings to identifier strings.</span></span> `mc:Ignorable` <span data-ttu-id="92fbb-121">no se aplica a las asignaciones de espacio de nombres en los ensamblados, especifiquen un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] espacio de nombres y un ensamblado (o predeterminada para el ejecutable que el ensamblado actual).</span><span class="sxs-lookup"><span data-stu-id="92fbb-121">does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="92fbb-122">Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación del procesador no debe generar análisis o errores de procesamiento de resolución de tipos para cualquier elemento o atributo que se califica con un prefijo que se identifica como `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="92fbb-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="92fbb-123">Pero la implementación de procesador puede producir excepciones que son el resultado secundario de un elemento no se puede cargar o procesar, como en el ejemplo de un solo elemento secundario proporcionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="92fbb-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="92fbb-124">De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador pasará por alto el contenido dentro de un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="92fbb-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="92fbb-125">Sin embargo, puede especificar un atributo adicional, [atributo ProcessContent](mc-processcontent-attribute.md), para exigir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.</span><span class="sxs-lookup"><span data-stu-id="92fbb-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="92fbb-126">Se pueden especificar varios prefijos en el atributo, con uno o varios caracteres de espacio en blanco como separador, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="92fbb-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="92fbb-127">El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="92fbb-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="92fbb-128">Para obtener más información, consulte [especificación de compatibilidad de marcado XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="92fbb-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92fbb-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="92fbb-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="92fbb-130">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="92fbb-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="92fbb-131">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="92fbb-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="92fbb-132">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="92fbb-132">Documents in WPF</span></span>](documents-in-wpf.md)
