---
title: "Extensión de marcado StaticResource"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 97b83feb9d19760208d9cc103290c5c6293c30c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="382a8-102">Extensión de marcado StaticResource</span><span class="sxs-lookup"><span data-stu-id="382a8-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="382a8-103">Proporciona un valor para cualquier [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] atributo de propiedad buscando una referencia a un recurso ya definido.</span><span class="sxs-lookup"><span data-stu-id="382a8-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="382a8-104">Comportamiento de búsqueda de ese recurso es análogo a la búsqueda en tiempo de carga, que tendrá un aspecto de los recursos que se cargaron previamente desde el marcado del elemento actual [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] página, así como otros orígenes de la aplicación y generará ese valor de recurso como la valor de propiedad en los objetos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="382a8-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="382a8-105">Uso de atributos XAML</span><span class="sxs-lookup"><span data-stu-id="382a8-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="382a8-106">Uso de elementos de objeto XAML</span><span class="sxs-lookup"><span data-stu-id="382a8-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="382a8-107">Valores XAML</span><span class="sxs-lookup"><span data-stu-id="382a8-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="382a8-108">Clave del recurso solicitado.</span><span class="sxs-lookup"><span data-stu-id="382a8-108">The key for the requested resource.</span></span> <span data-ttu-id="382a8-109">Esta clave se asignó inicialmente por el [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) si un recurso se creó en el marcado, o se proporcionó como el `key` parámetro al llamar a <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> si el recurso se creó en el código.</span><span class="sxs-lookup"><span data-stu-id="382a8-109">This key was initially assigned by the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="382a8-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="382a8-110">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="382a8-111">A `StaticResource` no debe intentar realizar una referencia adelantada a un recurso que se define léxicamente adicional dentro de la [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] archivo.</span><span class="sxs-lookup"><span data-stu-id="382a8-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="382a8-112">No se admite el intento de hacerlo, y aunque no producirá un error en dicha referencia, intentando la referencia adelantada incurrirá en una penalización de rendimiento de tiempo de carga cuando las tablas hash interna que representa un <xref:System.Windows.ResourceDictionary> se buscan.</span><span class="sxs-lookup"><span data-stu-id="382a8-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="382a8-113">Para obtener mejores resultados, ajuste la composición de los diccionarios de recursos, que se pueden evitar las referencias adelantadas.</span><span class="sxs-lookup"><span data-stu-id="382a8-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="382a8-114">Si no se puede evitar una referencia adelantada, utilice [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="382a8-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="382a8-115">Especificado <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> debe corresponder a un recurso existente, identificado con un [x: Key (directiva)](../../../../docs/framework/xaml-services/x-key-directive.md) en algún nivel en la página, aplicación, los temas de control disponibles y recursos externos o recursos del sistema.</span><span class="sxs-lookup"><span data-stu-id="382a8-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="382a8-116">La búsqueda de recursos se produce en ese orden.</span><span class="sxs-lookup"><span data-stu-id="382a8-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="382a8-117">Para obtener más información acerca del comportamiento de búsqueda de recursos para recursos estáticos y dinámicos, consulte [recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span><span class="sxs-lookup"><span data-stu-id="382a8-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](../../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="382a8-118">Una clave de recurso puede ser cualquier cadena definida en el [XamlName (gramática)](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span><span class="sxs-lookup"><span data-stu-id="382a8-118">A resource key can be any string defined in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="382a8-119">Una clave de recurso también puede ser otros tipos de objeto, como un <xref:System.Type>.</span><span class="sxs-lookup"><span data-stu-id="382a8-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="382a8-120">Un <xref:System.Type> clave es fundamental para cómo pueden aplicarse estilos a controles por temas, a través de una clave de estilo implícita.</span><span class="sxs-lookup"><span data-stu-id="382a8-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="382a8-121">Para obtener más información, consulte [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="382a8-121">For more information, see [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="382a8-122">Es la manera declarativa alternativa de hacer referencia a un recurso como una [extensión de marcado DynamicResource](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span><span class="sxs-lookup"><span data-stu-id="382a8-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="382a8-123">La sintaxis de atributo es la que se usa normalmente con esta extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="382a8-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="382a8-124">El token de cadena que se proporciona después de la cadena de identificador `StaticResource` se asigna como valor de <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> de la clase de extensión <xref:System.Windows.StaticResourceExtension> subyacente.</span><span class="sxs-lookup"><span data-stu-id="382a8-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="382a8-125">`StaticResource`puede usarse en la sintaxis de elemento de objeto.</span><span class="sxs-lookup"><span data-stu-id="382a8-125">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="382a8-126">En este caso, especificando el valor de la <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> propiedad es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="382a8-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="382a8-127">`StaticResource` también se puede utilizar en el uso de atributos detallado que especifica la propiedad <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> como un par de propiedad=valor:</span><span class="sxs-lookup"><span data-stu-id="382a8-127">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="382a8-128">El uso detallado suele ser útil para las extensiones que tienen más de una propiedad que se puede configurar, o en aquellos casos en que algunas propiedades son opcionales.</span><span class="sxs-lookup"><span data-stu-id="382a8-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="382a8-129">Dado que `StaticResource` tiene una sola propiedad configurable, que es obligatoria, este uso detallado no es habitual.</span><span class="sxs-lookup"><span data-stu-id="382a8-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="382a8-130">En el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementación del procesador, el control para esta extensión de marcado se define por la <xref:System.Windows.StaticResourceExtension> clase.</span><span class="sxs-lookup"><span data-stu-id="382a8-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="382a8-131">`StaticResource` es una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="382a8-131">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="382a8-132">Las extensiones de marcado se suelen implementar cuando se necesita que los valores de los atributos de escape no sean valores literales o nombres de controladores, y este requisito es de índole más global que limitarse a colocar los convertidores de tipos en determinados tipos o propiedades.</span><span class="sxs-lookup"><span data-stu-id="382a8-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="382a8-133">Todas las extensiones de marcado de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] usan los caracteres { y } en su sintaxis de atributo, que es la convención que permite que un procesador de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reconozca que el atributo se debe procesar mediante una extensión de marcado.</span><span class="sxs-lookup"><span data-stu-id="382a8-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="382a8-134">Para más información, vea [Extensiones de marcado y XAML de WPF](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="382a8-134">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="382a8-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="382a8-135">See Also</span></span>  
 [<span data-ttu-id="382a8-136">Aplicar estilos y plantillas</span><span class="sxs-lookup"><span data-stu-id="382a8-136">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [<span data-ttu-id="382a8-137">Información general sobre XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="382a8-137">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="382a8-138">Extensiones de marcado y XAML de WPF</span><span class="sxs-lookup"><span data-stu-id="382a8-138">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)  
 [<span data-ttu-id="382a8-139">Recursos XAML</span><span class="sxs-lookup"><span data-stu-id="382a8-139">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="382a8-140">Recursos y código</span><span class="sxs-lookup"><span data-stu-id="382a8-140">Resources and Code</span></span>](../../../../docs/framework/wpf/advanced/resources-and-code.md)
