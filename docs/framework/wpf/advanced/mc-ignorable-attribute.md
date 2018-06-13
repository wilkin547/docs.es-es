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
ms.openlocfilehash: 7b8a2ef6e27bc6b25776157e59bef04b883fcb1a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546203"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="9c47c-102">Atributo mc:Ignorable</span><span class="sxs-lookup"><span data-stu-id="9c47c-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="9c47c-103">Especifica qué [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijos de espacio de nombres que se encuentran en un archivo de marcado pueden omitir un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador.</span><span class="sxs-lookup"><span data-stu-id="9c47c-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9c47c-104">El `mc:Ignorable` atributo admite la compatibilidad de marcado para la asignación de espacio de nombres personalizado y para [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] control de versiones.</span><span class="sxs-lookup"><span data-stu-id="9c47c-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="9c47c-105">Uso de atributos XAML (un solo prefijo)</span><span class="sxs-lookup"><span data-stu-id="9c47c-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="9c47c-106">Uso de atributos XAML (dos prefijos)</span><span class="sxs-lookup"><span data-stu-id="9c47c-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9c47c-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="9c47c-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9c47c-108">*ignorablePrefix, ignorablePrefix1, etcetera.*</span><span class="sxs-lookup"><span data-stu-id="9c47c-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="9c47c-109">Cualquier cadena de prefijo, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="9c47c-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9c47c-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="9c47c-110">*ignorableUri*</span></span>|<span data-ttu-id="9c47c-111">Cualquier URI válido para designar un espacio de nombres, según la especificación XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="9c47c-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9c47c-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="9c47c-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="9c47c-113">Un elemento que se puede omitir si [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] las implementaciones del procesador, si no se puede resolver el tipo subyacente.</span><span class="sxs-lookup"><span data-stu-id="9c47c-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c47c-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9c47c-114">Remarks</span></span>  
 <span data-ttu-id="9c47c-115">El `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] prefijo de espacio de nombres es la convención de prefijo recomendado que se usará al asignar la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] espacio de nombres de compatibilidad [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c47c-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="9c47c-116">Elementos o atributos en la parte de prefijo del nombre del elemento se identifican como `mc:Ignorable` no genera errores cuando se procesa mediante un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador.</span><span class="sxs-lookup"><span data-stu-id="9c47c-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9c47c-117">Si ese atributo no se puede resolver a un tipo subyacente o la construcción de programación, se omite ese elemento.</span><span class="sxs-lookup"><span data-stu-id="9c47c-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="9c47c-118">Sin embargo, tenga en cuenta que los elementos omitidos pueden generar errores de análisis adicionales para los requisitos de elemento adicionales que son efectos secundarios de ese elemento no se están procesando.</span><span class="sxs-lookup"><span data-stu-id="9c47c-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="9c47c-119">Por ejemplo, un modelo de contenido de elemento en particular podría necesitar exactamente un elemento secundario, pero si el elemento secundario especificado estaba en un `mc:Ignorable` prefijo y el elemento secundario especificado no se pueden resolver a un tipo, la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] posible que el procesador se producirá un error.</span><span class="sxs-lookup"><span data-stu-id="9c47c-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="9c47c-120">`mc:Ignorable` solo se aplica a las asignaciones de espacio de nombres a las cadenas de identificador.</span><span class="sxs-lookup"><span data-stu-id="9c47c-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="9c47c-121">`mc:Ignorable` no se aplica a las asignaciones de espacio de nombres en los ensamblados, especifiquen un [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] espacio de nombres y un ensamblado (o valor predeterminado para el archivo ejecutable actual que el ensamblado).</span><span class="sxs-lookup"><span data-stu-id="9c47c-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="9c47c-122">Si está implementando un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador, la implementación de procesador no debe generar análisis ni el procesamiento de errores en la resolución de tipo para cualquier elemento o atributo que se califica con un prefijo que se identifica como `mc:Ignorable`.</span><span class="sxs-lookup"><span data-stu-id="9c47c-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="9c47c-123">Pero la implementación de procesador puede producir excepciones que sean el efecto secundario de un elemento de un error de carga o se procesarán, tales como el ejemplo de un solo elemento secundario proporcionado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9c47c-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="9c47c-124">De forma predeterminada, un [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] procesador omitirá el contenido incluido en un elemento omitido.</span><span class="sxs-lookup"><span data-stu-id="9c47c-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="9c47c-125">Sin embargo, puede especificar un atributo adicional, [ProcessContent atributo](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), para exigir el procesamiento continuado de contenido dentro de un elemento omitido por el siguiente elemento primario disponible.</span><span class="sxs-lookup"><span data-stu-id="9c47c-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](../../../../docs/framework/wpf/advanced/mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="9c47c-126">Se pueden especificar varios prefijos en el atributo, con uno o más caracteres de espacio en blanco como separador, por ejemplo: `mc:Ignorable="ignore1 ignore2"`.</span><span class="sxs-lookup"><span data-stu-id="9c47c-126">Multiple prefixes can be specified in the attribute, using one or more whitespace characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  
  
 <span data-ttu-id="9c47c-127">El [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] espacio de nombres define otros elementos y atributos que no están documentados en esta área de la [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9c47c-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="9c47c-128">Para obtener más información, consulte [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span><span class="sxs-lookup"><span data-stu-id="9c47c-128">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c47c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c47c-129">See Also</span></span>  
 <xref:System.Windows.Markup.XamlReader>  
 [<span data-ttu-id="9c47c-130">PresentationOptions:Freeze (Atributo)</span><span class="sxs-lookup"><span data-stu-id="9c47c-130">PresentationOptions:Freeze Attribute</span></span>](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)  
 [<span data-ttu-id="9c47c-131">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="9c47c-131">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="9c47c-132">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="9c47c-132">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)
