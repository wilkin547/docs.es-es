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
ms.openlocfilehash: e99ca09d51f3ba6c01b9e400bfba00749faf62b3
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567441"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="d7c45-102">Atributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="d7c45-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="d7c45-103">Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacio de nombres que se encuentran en un archivo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de marcado puede ser omitido por un procesador.</span><span class="sxs-lookup"><span data-stu-id="d7c45-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="d7c45-104">El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] de nombres personalizada y para el control de versiones.</span><span class="sxs-lookup"><span data-stu-id="d7c45-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="d7c45-105">Uso de atributos XAML (prefijo único)</span><span class="sxs-lookup"><span data-stu-id="d7c45-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="d7c45-106">Uso de atributos XAML (dos prefijos)</span><span class="sxs-lookup"><span data-stu-id="d7c45-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="d7c45-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="d7c45-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7c45-108">*ignorablePrefix, ignorablePrefix1, etc.*</span><span class="sxs-lookup"><span data-stu-id="d7c45-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="d7c45-109">Cualquier cadena de prefijo válida, según la especificación de XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="d7c45-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d7c45-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="d7c45-110">*ignorableUri*</span></span>|<span data-ttu-id="d7c45-111">Cualquier URI válido para designar un espacio de nombres, según la especificación de XML 1,0.</span><span class="sxs-lookup"><span data-stu-id="d7c45-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="d7c45-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="d7c45-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="d7c45-113">Un elemento que las implementaciones de [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] procesador pueden omitir, si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="d7c45-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7c45-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d7c45-114">Remarks</span></span>  
 <span data-ttu-id="d7c45-115">El `mc` [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]prefijo de espacio de nombres es la Convención de prefijo recomendada que se va a usar al asignar el espacio de nombres de compatibilidad. [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d7c45-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="d7c45-116">Los elementos o atributos en los que la parte del prefijo del nombre `mc:Ignorable` del elemento se identifican como no producirán errores cuando los procese un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador.</span><span class="sxs-lookup"><span data-stu-id="d7c45-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="d7c45-117">Si ese atributo no se pudo resolver en un tipo o una construcción de programación subyacentes, se omite ese elemento.</span><span class="sxs-lookup"><span data-stu-id="d7c45-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="d7c45-118">Tenga en cuenta, sin embargo, que los elementos omitidos todavía pueden generar errores de análisis adicionales para requisitos de elementos adicionales que son efectos secundarios de ese elemento que no se están procesando.</span><span class="sxs-lookup"><span data-stu-id="d7c45-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="d7c45-119">Por ejemplo, un modelo de contenido de elemento determinado podría requerir exactamente un elemento secundario, pero si el elemento secundario especificado estaba `mc:Ignorable` en un prefijo, y el elemento secundario especificado no se pudo resolver en un tipo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , entonces el procesador podría producir un error.</span><span class="sxs-lookup"><span data-stu-id="d7c45-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="d7c45-120">`mc:Ignorable`solo se aplica a las asignaciones de espacio de nombres a cadenas de identificador.</span><span class="sxs-lookup"><span data-stu-id="d7c45-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="d7c45-121">`mc:Ignorable`no se aplica a las asignaciones de espacio de nombres a los ensamblados, que especifican un espacio de nombres CLR y un ensamblado (o el valor predeterminado para el ejecutable actual como el ensamblado).</span><span class="sxs-lookup"><span data-stu-id="d7c45-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="d7c45-122">Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación del procesador no debe generar errores de análisis o procesamiento en la resolución de tipos para cualquier elemento o atributo calificado con un prefijo identificado `mc:Ignorable`como.</span><span class="sxs-lookup"><span data-stu-id="d7c45-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="d7c45-123">Pero la implementación del procesador todavía puede producir excepciones que son un resultado secundario de un elemento que no se carga o se procesa, como el ejemplo de elemento One-Child proporcionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d7c45-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="d7c45-124">De forma predeterminada, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] un procesador pasará por alto el contenido dentro de un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="d7c45-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="d7c45-125">Sin embargo, puede especificar un atributo adicional, [MC: ProcessContent](mc-processcontent-attribute.md), para requerir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.</span><span class="sxs-lookup"><span data-stu-id="d7c45-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="d7c45-126">Se pueden especificar varios prefijos en el atributo, utilizando uno o más caracteres de espacio en blanco como separador, por `mc:Ignorable="ignore1 ignore2"`ejemplo:.</span><span class="sxs-lookup"><span data-stu-id="d7c45-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="d7c45-127">El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área del SDK.</span><span class="sxs-lookup"><span data-stu-id="d7c45-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="d7c45-128">Para obtener más información, vea [especificación de compatibilidad de marcado XML](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span><span class="sxs-lookup"><span data-stu-id="d7c45-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7c45-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7c45-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="d7c45-130">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="d7c45-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="d7c45-131">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="d7c45-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="d7c45-132">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="d7c45-132">Documents in WPF</span></span>](documents-in-wpf.md)
